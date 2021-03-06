---
title: начало работы с отладкой в Visual Studio 2015 | Документация Майкрософт
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: c3a14d28-d811-4ff3-bd09-21dce14025ca
caps.latest.revision: 7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: fe8b158fd870b83b39b9d316e68582f2726d89bb
ms.sourcegitcommit: bad28e99214cf62cfbd1222e8cb5ded1997d7ff0
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74300200"
---
# <a name="getting-started-with-debugging-in-visual-studio-2015"></a>Начало работы с отладкой в Visual Studio 2015
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 2015 включает эффективный интегрированный набор средств сборки и отладки проектов. В этом разделе рассматривается начало работы с основным набором возможностей пользовательского интерфейса отладки.

 Примечание. Ссылки на расширенные функции, а также разделы, посвященные отдельным платформам или функциям, см. в нижней части этой страницы.

## <a name="my-code-doesnt-work-help-me-visual-studio-2015"></a>Код не работает. Как Visual Studio 2015 может помочь?
 Итак, вы разобрались, как работать с редактором, и написали код. Теперь нужно выполнить отладку этого кода. Отладка в Visual Studio 2015, как и в большинстве интегрированных сред разработки (IDE), осуществляется в два этапа: построение кода для обнаружения и устранения ошибок проекта и компилятора и выполнение этого кода в среде для обнаружения и устранения ошибок времени выполнения и динамических ошибок.

### <a name="configuring-a-build"></a>Настройка сборки
 Существует два основных типа конфигурации сборки: **отладка** и **выпуск**. При использовании первой конфигурации создается более крупный и медленный исполняемый файл, обеспечивающий более широкие интерактивные возможности отладки во время выполнения, однако отправлять этот файл не следует. Вторая конфигурация позволяет создать более быстрый оптимизированный исполняемый файл, подходящий для отправки (по крайней мере с точки зрения компилятора).

 По умолчанию используется конфигурация **Отладка**.

 ![Кнопка "Отладочное построение" в Visual Studio](../ide/media/vs-ide-gs-debug-build-type1.PNG "|::ref1::|")

 Можно также указать конкретную целевую платформу сборки, например **x86** (32-разрядные процессоры Intel), **x64** (64-разрядные процессоры Intel) и **ARM** (процессоры ARM, поддерживается только для определенных типов приложений). Значение по умолчанию — **x86** для проектов управляемого и машинного кода. Чтобы изменить его, щелкните раскрывающийся список платформ сборки и выберите другую платформу или выберите **Configuration Manager**.

 ![Окно диспетчера файлов конфигурации в Visual Studio](../ide/media/vs-ide-gs-debug-build-cf-mgr.PNG "|::ref2::|")

 Указать целевую конфигурацию сборки можно с помощью **Configuration Manager**. Чтобы запустить этот компонент, щелкните раскрывающийся список **Конфигурация** или **ЦП** и выберите **Создать...** для создания новой сборки или платформы.

 ![Окно диспетчера конфигурации в Visual Studio](../ide/media/vs-ide-gs-debug-build-cf-mgr-2.PNG "|::ref3::|")

 Если вы только начинаете работу, просто используйте варианты **Отладка** и **x86** в качестве конфигурации сборки и платформы, соответственно. После завершения создания кода и отладки измените конфигурацию на **Выпуск** и выберите определенную целевую платформу. (В предыдущих версиях Visual Studio для проектов кода .NET предоставлялась платформа по умолчанию **AnyCPU**.)

 Примечание. При построении проекта значения конфигурации и платформы также используются для определения создаваемого пути к каталогу проекта для хранения исполняемого файла. Как правило, это **\<путь_к_проекту>\\<имя_проекта>\>\\<конфигурация\>\\<платформа\>** . Например, проект с конфигурацией `Debug` и платформой `x86` будет размещаться по пути `Projects\MyProjectNameHere\MyProjectNameHere\bin\Debug\x86`. Это может быть полезно при наличии собственных средств или сценариев, управляющих исполняемыми файлами сборки.

### <a name="building-your-code"></a>Сборка кода
 Настроив среду сборки, можно приступить к фактической сборке проекта. Самый просто способ — нажать клавишу F7, однако вы также можете начать сборку, выбрав в главном меню **Сборка -> Собрать решение**.

 ![Выбор пункта меню "Собрать проект" в Visual Studio](../ide/media/vs-ide-gs-debug-build-menu-item.png "|::ref4::|")

 Процесс сборки можно наблюдать в окне состояния **Вывод** в нижней части пользовательского интерфейса Visual Studio. Здесь отображаются ошибки, предупреждения и операции сборки. При наличии ошибок (или предупреждений выше заданного уровня) сборка завершится ошибкой. Можно щелкнуть ошибку и предупреждение, чтобы перейти к строке, где они возникли. Для перестроения проекта можно нажать клавишу **F7** (чтобы перекомпилировать только файлы с ошибками) или **CTRL+ALT+F7** (для чистого полного перестроения).

 В окне результатов содержатся два окна сборки с вкладками под областью редактора: окно **Вывод**, в котором содержатся необработанные выходные данные компилятора (включая сообщения об ошибках), и окно **Список ошибок**, содержащее список всех ошибок и предупреждений, к которому можно применить сортировку и фильтры.

 В случае успешного выполнения вы увидите примерно следующие результаты в окне **Вывод**.

 ![Выходные данные успешной сборки в Visual Studio](../ide/media/vs-ide-gs-debug-success-build.PNG "|::ref5::|")

### <a name="reviewing-the-error-list"></a>Просмотр списка ошибок
 Если вы внесли какие-либо изменения в код, который был ранее и успешно скомпилирован, возможно, возникнет ошибка. Если вы новичок в написании кода, возможно, их будет много. Ошибки иногда очевидны, например простая синтаксическая ошибка или неправильное имя переменной, а иногда их причину трудно выяснить, имея в распоряжении только зашифрованный код. Чтобы получить более четкое представление о проблеме, перейдите вниз окна **Вывод** сборки и щелкните вкладку **Список ошибок**. При этом вы перейдете к более организованному представлению ошибок и предупреждений для проекта и получите доступ к некоторым дополнительным параметрам.

 ![Список ошибок и вывода в Visual Studio 2015](../ide/media/vs-ide-gs-debug-bad-build-error-list.PNG "|::ref6::|")

 Щелкните строку ошибки в окне **Список ошибок** и перейдите в строку кода, в которой возникла ошибка. (Номера строк также можно включить, щелкнув панель **быстрого запуска** в верхнем правом углу: введите "номера строк" в поле и нажмите клавишу ВВОД.) Это самый быстрый способ перехода в окно **Параметры**, где можно включить номера строк. Узнайте, как использовать панель **быстрого запуска** и избежать лишних действий в пользовательском интерфейсе.

 ![Редактор Visual Studio с номерами строк](../ide/media/vs-ide-gs-debug-line-numbers.png "|::ref7::|")

 ![Параметр "Номера строк" в Visual Studio](../ide/media/vs-ide-gs-debug-options-line-numbers.png "|::ref8::|")

 Нажмите сочетание клавиш CTRL+G для быстрого перехода к номеру строки, в которой возникла ошибка.

 Ошибку можно узнать по подчеркиванию красной волнистой линией. Чтобы получить дополнительные сведения, наведите на нее указатель мыши. Внесите исправления, и подчеркивание исчезнет, хотя в результате исправления может возникнуть новая ошибка (это называется «регрессия»).

 ![Ошибка при наведении курсора мыши в Visual Studio](../ide/media/vs-ide-gs-debug-error-hover1.png "|::ref9::|")

 Пройдите список ошибок и устраните все ошибки в коде.

 ![Окно ошибок отладчика в Visual Studio](../ide/media/vs-ide-gs-debug-error-list.PNG "|::ref10::|")

### <a name="reviewing-errors-in-detail"></a>Просмотр подробных сведений об ошибках
 Многие ошибки трудны для восприятия, будучи представленными в терминах компилятора. В этом случае могут потребоваться дополнительные сведения. В окне **Список ошибок** можно выполнить автоматический поиск Bing, чтобы получить дополнительные сведения об ошибке (или предупреждении): щелкните правой кнопкой мыши в соответствующей строке записи и выберите в меню **Показать справочные сведения об ошибке**.

 ![Поиск в Bing списка ошибок в Visual Studio](../ide/media/vs-ide-gs-debug-error-list-error-help.png "|::ref11::|")

 Внутри Visual Studio 2015 откроется вкладка, на которой будут отображаться результаты поиска Bing для кода ошибки и текста. Представленные результаты — из различных источников в Интернете, и, возможно, не все они будут полезными.

 Кроме того, можно щелкнуть значение кода ошибки с гиперссылкой в столбце **Код** **списка ошибок**. Это приведет к запуску поиска Bing только по коду ошибки.

### <a name="performing-static-code-analysis"></a>Выполнение статического анализа кода
 Под статическим анализом кода мы, как правило, понимаем автоматическую проверку кода на наличие распространенных проблем, которые могут привести к ошибкам во время выполнения или проблемам управления кодом. Запустить этот компонент после устранения всех очевидных ошибок, препятствующих сборке, и потратить некоторое время, чтобы устранить создаваемые им предупреждения, — очень полезная привычка. Вы сможете избавиться от определенных будущих проблем, а также научиться некоторым полезным приемам написания кода.

 Нажмите сочетание клавиш ALT+F11 (или выберите **Анализ -> Выполнить анализ кода в решении** в верхнем меню) для запуска статического анализа кода. При наличии большого объема кода это может занять некоторое время.

 ![Элемент меню "Анализ кода" в Visual Studio 2015](../ide/media/vs-ide-gs-debug-run-code-analysis.png "|::ref12::|")

 Все новые или обновленные предупреждения будут отображаться на вкладке **Список ошибок** в нижней части интегрированной среды разработки. Для перехода к предупреждению щелкните его.

 ![Список ошибок с предупреждениями в Visual Studio 2015](../ide/media/vs-ide-gs-debug-code-analysis-warning-error-list.PNG "|::ref13::|")

 Предупреждения выделяются яркой желто-зеленой волнистой линией вместо красной. Наведите указатель мыши на предупреждение, чтобы получить дополнительные сведения. При щелчке правой мыши выводится контекстное меню, в котором можно выбрать пункты для исправления или рефакторинга.

 ![Предупреждение анализа в Visual Studio Code при наведении указателя мыши](../ide/media/vs-ide-gs-debug-code-analysis-warning-hover.png "|::ref14::|")

### <a name="using-light-bulbs-to-fix-or-refactor-code"></a>Использование значка лампочки для исправления или рефакторинга кода
 Лампочки — это новая возможность Visual Studio 2015, позволяющая выполнить рефакторинг кода в окне решения. Это простой способ быстрого и эффективного устранения распространенных предупреждений. Для доступа к ним щелкните правой кнопкой мыши волнистую линию предупреждения или нажмите сочетание клавиш CTRL+. (указатель мыши должен быть наведен на волнистую линию), а затем выберите пункт меню **Быстрые действия**.

 ![Быстрые параметры лампочки в Visual Studio 2015](../ide/media/vs-ide-gs-debug-light-bulb1.png "|::ref15::|")

 Вы увидите список возможных исправлений или операций рефакторинга, которые можно применить к соответствующей строке кода.

 ![Предварительный просмотр лампочки в Visual Studio 2015](../ide/media/vs-ide-gs-debug-light-bulb-preview-changes.PNG "|::ref16::|")

 Лампочки можно использовать в любом случае, когда средство анализа кода определяет возможность исправления, рефакторинга или улучшения кода. Щелкните любую строку кода, вызовите контекстное меню и выберите **Быстрые параметры** (или, если вы предпочитаете эффективность, нажмите сочетание клавиш CTRL+.). Если для этой области есть доступные параметры рефакторинга или улучшения, они будут выведены на экран; в противном случае на панели в левом нижнем углу окна IDE будет выведено сообщение `No quick options available here`.

 ![Текст "Нет параметра" для лампочки в Visual Studio 2015](../ide/media/vs-ide-gs-debug-light-bulb-no-options.PNG "|::ref17::|")

 Если вы привыкли работать с клавиатурой, вы можете использовать клавиши со стрелками и сочетание клавиш CTRL+. для проверки возможностей оптимизации с помощью быстрых параметров и очистки кода.

 Дополнительные сведения о лампочках см. в статье [Perform quick actions with light bulbs](../ide/perform-quick-actions-with-light-bulbs.md) (Выполнение быстрых действий с лампочками).

### <a name="debugging-your-running-code"></a>Отладка выполняемого кода
 Успешно завершив построение кода и его очистку, запустите код, нажав клавишу F5 или выбрав **Отладка > Начать отладку**. Приложение будет запущено в среде отладки, и вы сможете пронаблюдать его поведение. Среда IDE Visual Studio 2015 изменяется во время выполнения приложения: окно **Вывод** заменяется двумя новыми окнами (в конфигурации окна по умолчанию), окном с вкладками **Авто/Локальные/Модули/Контрольные значения** и окном с вкладками **Стеки вызовов/Точки останова/Параметры исключений/Вывод**. Эти окна имеют несколько вкладок, которые позволяют просмотреть и проверить переменные, потоки, стеки вызовов приложения и другие характеристики поведения во время выполнения приложения.

 ![Окна "Видимые" и "Стек вызовов" в VS2015](../ide/media/vs-ide-gs-debug-autos-and-call-stack.PNG "|::ref18::|")

 Выполните разные действия с приложением и понаблюдайте за изменениями. Если приложение ведет себя ненормально, приостановите его с помощью сочетания клавиш CTRL+ALT+ BREAK (или нажмите кнопку **Приостановить**).

 ![Кнопка "Прервать все" в Visual Studio](../ide/media/vs-ide-gs-debug-break-all-button.png "|::ref19::|")

 Нажмите клавишу F5 для продолжения выполнения приложения (или нажмите кнопку **Продолжить**).

 ![Кнопка "Продолжить отладку" в Visual Studio](../ide/media/vs-ide-gs-debug-continue-button.png "|::ref20::|")

 Остановить приложение можно, нажав клавиши SHIFT+F5 или кнопку **Остановить**. Кроме того, можно просто закрыть главное окно приложения (или диалоговое окно командной строки).

 Если код выполняется полностью и точно так, как ожидалось, вас можно поздравить. Измените конфигурацию сборки на **Выпуск** и перестройте его для развертывания. (Профессионалы, возможно, предпочтут сначала выполнить модульное тестирование). Однако в случае зависания, сбоя или непредвиденных результатов может потребоваться найти источник проблем и исправить ошибки.

### <a name="setting-simple-breakpoints"></a>Задание простых точек останова
 Точки останова — это один из самых простых и важных компонентов надежной отладки. Точка останова указывает, где Visual Studio следует приостановить выполнение кода, чтобы вы могли проверить значения переменных или поведение памяти либо выполнение ветви кода. После установки или удаления точек останова перестраивать проект НЕ НУЖНО.

 Установите точку останова, щелкнув дальнее поле строки, где требуется приостановить выполнение, или выберите строку кода и нажмите клавишу F9. При выполнении кода оно останавливается перед выполнением инструкций для этой строки кода.

 ![Точка останова в Visual Studio](../ide/media/vs-ide-gs-debug-breakpoint1.png "|::ref21::|")

 В момент прерывания кода отмеченная строка кода еще не выполнена. На этом этапе вы можете выполнить инструкции для строки кода, отмеченной точкой останова, и проверить измененные значения. Это называется «пошаговым выполнением» кода. Если отмеченный код является вызовом метода, вы можете выполнить его, нажав клавишу F11. Кроме того, можно "перешагнуть" через строку кода, нажав клавишу F10. Дополнительные сведения о действиях шагов точек останова см. в статье [Навигация по коду с помощью отладчика](../debugger/navigating-through-code-with-the-debugger.md).

 Чаще всего точки останова используются для решения следующих задач.

1. Для сужения области поиска источника сбоя или зависания, когда точки останова устанавливаются в разных местах участка кода вызова метода, который, возможно, является источником проблемы, и за его пределами. При пошаговом выполнении кода удаляйте, а затем снова устанавливайте точки останова ближе друг к другу, пока не найдете строку кода, вызывающую ошибку.

2. При вводе нового кода установите точку останова в начале кода и пройдите по коду, чтобы убедиться, что он работает правильно.

3. При реализации сложного поведения задайте точки останова для алгоритмического кода, чтобы можно было проверить значения переменных и данные при прерывании программы.

4. При написании кода C или C++ используйте точки останова для остановки кода, чтобы можно было проверить значения адреса (ищите значение NULL) и просмотреть значения счетчиков при отладке ошибок, связанных с памятью.

   Дополнительные сведения о точках останова см. в статье [Использование точек останова](../debugger/using-breakpoints.md).

### <a name="setting-conditional-breakpoints"></a>Задание условных точек останова
 При наличии точки останова в цикле или рекурсии или большого числа точек останова, которые вы часто будете просматривать пошагово, используйте условную точку останова, которая позволяет приостанавливать код ТОЛЬКО при выполнении определенных условий. В противном случае вы устанете нажимать клавишу F11.

 Чтобы задать условную точку останова и приостанавливать код при установке определенного значения переменной (или достижения определенного порогового значения), щелкните поле для задания точки остановка и выберите в меню, появившемся при наведении указателя мыши, значок шестеренки.

 ![Параметры точки останова в Visual Studio 2015](../ide/media/vs-ide-gs-debug-breakpoint-settings.png "|::ref22::|")

 Появится диалоговое окно, где можно задать определенные условия для останова, которое выглядит следующим образом.

 ![Условная точка останова в Visual Studio 2015](../ide/media/vs-ide-gs-debug-breakpoint-conditional.PNG "|::ref23::|")

 Дополнительные сведения об объявлении выражений, используемых для оценки условных точек останова, см. в видеозаписи канала Channel9 [Настройка точек останова в Visual Studio 2015](https://channel9.msdn.com/Events/Visual-Studio/Connect-event-2014/711).

### <a name="inspecting-your-code-at-run-time"></a>Проверка кода во время выполнения
 Когда выполняемый код достигает точки останова и останавливается, можно проверить переменные и стеки вызовов, чтобы разобраться в происходящем. Находятся ли значения в тех диапазонах, которые вы ожидали увидеть? Выполняются ли вызовы в правильном порядке?

 ![Проверка значения времени выполнения&#45;Visual Studio 2015](../ide/media/vs-ide-gs-debug-inspect-value.PNG "|::ref24::|")

 Наведите указатель мыши на переменную, чтобы просмотреть значения и ссылки, которые она содержит в данный момент. Если отображается значение, которое вы не ожидали увидеть, возможно, в предыдущей или вызывающей строке кода имеется ошибка. Переместите точки остановки выше или добавьте условия в существующие точки останова, чтобы сузить область поиска.

 Кроме того, Visual Studio 2015 выводит на экран окно средств диагностики, где можно наблюдать за загрузкой ЦП и использованием памяти приложением в динамике по времени. Их рекомендуется использовать в случае непредвиденно больших показателей загрузки ЦП или выделения памяти. Это окно можно использовать в сочетании с окном **Контрольные значения** и точками останова, чтобы определить причину непредвиденно интенсивного использования или неосвобожденных ресурсов.

 ![Окно "Средства диагностики" в Visual Studio 2015](../ide/media/vs-ide-gs-debug-diagnostic-tools.PNG "|::ref25::|")

### <a name="running-unit-tests"></a>Выполнение модульных тестов
 Модульные тесты — это программы, выполняющие ветви кода в приложении или службе. Visual Studio 2015 устанавливает платформу модульного тестирования Майкрософт для управляемого и машинного кода. Платформа модульного тестирования используется для создания модульных тестов, их запуска и передачи результатов таких тестов. Завершив внесение изменений, запустите модульные тесты повторно, чтобы убедиться, что код по-прежнему работает правильно. При использовании выпуска Visual Studio 2015 Enterprise можно настроить автоматический запуск тестов после каждой сборки.

 Чтобы приступить к работе с модульными тестами, ознакомьтесь со статьей [Создание модульных тестов для кода с помощью IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md).

 Дополнительные сведения о модульных тестах в Visual Studio 2015, а также о том, как они могут помочь в создании более качественного кода, см. в разделе [Основные сведения о модульных тестах](../test/unit-test-basics.md).

## <a name="see-also"></a>См. также
 [Отладка в](../debugger/debugging-in-visual-studio.md) [параметрах отладчика](../debugger/debugger-settings-and-preparation.md) Visual Studio и [Основные понятия отладчика](../debugger/debugger-basics.md) для [отладки 64-bit Applications](../debugger/debug-64-bit-applications.md)
