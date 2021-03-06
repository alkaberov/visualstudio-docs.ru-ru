---
title: JIT-оптимизация и отладка | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], optimized code
- optimized code, debugging
ms.assetid: 19bfabf3-1a2e-49dc-8819-a813982e86fd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ae11860aaa64448cd4d23b5602cf4c2da1575ce3
ms.sourcegitcommit: 939407118f978162a590379997cb33076c57a707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2020
ms.locfileid: "75916228"
---
# <a name="jit-optimization-and-debugging"></a>JIT-отладка и оптимизация
Если вы пытаетесь выполнить отладку кода, проще, если этот код **не** оптимизирован. Когда код оптимизирован, компилятор и среда выполнения вносит изменения в выпущенный код ЦП, чтобы он выполнялся быстрее, но имеет менее прямое сопоставление с исходным исходным кодом. Если сопоставление является менее прямым, то отладчикам часто не удается определить значения локальных переменных, а пошаговое выполнение кода и точки останова могут не работать должным образом.

> [!NOTE]
> Дополнительные сведения об отладке по JIT см. в [этой документации](../debugger/debug-using-the-just-in-time-debugger.md).

## <a name="how-optimizations-work-in-net"></a>Как работает оптимизация в .NET 
Как правило, Конфигурация сборки выпуска создает оптимизированный код, а отладочная конфигурация сборки — нет. `Optimize` свойство MSBuild определяет, нужно ли компилятору оптимизировать код.

В экосистеме .NET код помещается из источника в инструкции ЦП в два этапа: сначала C# компилятор преобразует введенный текст в промежуточную двоичную форму с именем MSIL и записывает код на языке MSIL в DLL-файлы. Позже среда выполнения .NET преобразует этот код MSIL в инструкции ЦП. Оба действия можно оптимизировать до некоторой степени, но второй шаг, выполняемый средой выполнения .NET, выполняет более значительные оптимизации.

## <a name="the-suppress-jit-optimization-on-module-load-managed-only-option"></a>Параметр "подавлять JIT-оптимизацию при загрузке модуля (только управляемый)"
Отладчик предоставляет параметр, который управляет тем, что происходит, когда библиотека DLL, скомпилированная с включенной оптимизацией, загружается внутри целевого процесса. Если этот флажок не установлен (состояние по умолчанию), то когда среда выполнения .NET компилирует код MSIL в код ЦП, она оставляет оптимизацию включенной. Если флажок установлен, отладчик запрашивает отключение оптимизации.

Чтобы найти параметр **Отключить JIT-оптимизацию при загрузке модуля (только управляемый)** , выберите **Сервис** > **Параметры**, а затем выберите страницу **Общие** в узле **Отладка** .

![Отключить JIT-оптимизацию](../debugger/media/suppress-jit-tool-options.png "Отключить JIT-оптимизацию")

## <a name="when-should-you-check-the-suppress-jit-optimization-option"></a>Когда следует проверять параметр "подавлять JIT-оптимизацию"?
Установите этот флажок, если вы загрузили библиотеки DLL из другого источника, например пакета NuGet, и хотите отладить код в этой библиотеке DLL. Чтобы подавить работу, необходимо также найти файл символов (. pdb) для этой библиотеки DLL.

Если вас интересует только отладка кода, который вы создаете локально, лучше оставить этот флажок снятым, как в некоторых случаях включение этого параметра значительно замедляет отладку. Это замедляется по двум причинам.

* Оптимизированный код выполняется быстрее. Если вы отключаете оптимизацию для большого объема кода, это может повлиять на производительность.
* Если Только мой код включен, отладчик даже не будет пытаться загружать символы для оптимизированных DLL. Поиск символов может занять много времени.

## <a name="limitations-of-the-suppress-jit-optimization-option"></a>Ограничения параметра "подавлять JIT-оптимизацию" 
Включение этого параметра **не** будет работать в двух ситуациях:

1. В ситуациях, когда отладчик присоединяется к уже выполняющемуся процессу, этот параметр не влияет на модули, которые уже были загружены во время подключения отладчика.
2. Этот параметр не влияет на библиотеки DLL, которые были предварительно скомпилированы (a. k. нжен'ед) в машинный код. Однако вы можете отключить использование предварительно скомпилированного кода, запустив процесс с переменной среды **"COMPlus_ReadyToRun"** , для которой задано значение **"0"** . Это позволит среде выполнения .NET Core отключить использование предварительно скомпилированных изображений, принудительно вызывая JIT-компиляцию кода платформы в среде выполнения. 

    > [!IMPORTANT]
    > Если вы нацелены на .NET Framework или более старую версию .NET Core (2. x или ниже), добавьте переменную среды "COMPlus_ZapDisable" и задайте для нее значение "1".

    **Чтобы задать переменную среды для проекта .NET Core в Visual Studio, выполните следующие действия.**
    1. В **Обозреватель решений**щелкните **правой кнопкой мыши** файл проекта и выберите пункт **Свойства**.
    2. Перейдите на вкладку " **Отладка** " и в разделе " **переменные среды**" нажмите кнопку " **добавить** ".
    3. Задайте для параметра имя (Key) значение **COMPlus_ReadyToRun** и задайте для значения **0**.

    ![Задать COMPlus_ReadyToRun переменную среды](../debugger/media/environment-variables-debug-menu.png "Задать COMPlus_ReadyToRun переменную среды")

## <a name="see-also"></a>См. также:
- [Отладка исходного кода платформы DotNet](../debugger/how-to-debug-dotnet-framework-source.md)
- [Отладка управляемого кода](../debugger/debugging-managed-code.md)
- [Навигация по коду с помощью отладчика](../debugger/navigating-through-code-with-the-debugger.md)
- [Подключение к выполняющимся процессам](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)
- [Процесс управляемого выполнения](/dotnet/standard/managed-execution-process)
