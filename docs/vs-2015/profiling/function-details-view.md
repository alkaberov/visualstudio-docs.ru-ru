---
title: Представление сведений о функции | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.view.functiondetails
helpviewer_keywords:
- Function Details view
- Profiling Tools, Function Details view
ms.assetid: 8806954f-cf28-48d5-81b2-d722ceaf7d27
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3b243e6fee02e0d093cac17352803bfd66016bdf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47559379"
---
# <a name="function-details-view"></a>Представление сведений о функции
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [представление сведений о функции](https://docs.microsoft.com/visualstudio/profiling/function-details-view).  
  
В окне **Function Details View** (Представление сведений о функции) отображаются следующие сведения:  
  
-   В линейчатой диаграмме **Распределение стоимости** отображаются связи между выбираемой функцией и вызывающими функциями, выполнившими выбранную, а также между выбранной функцией и вызванными ею функциями.  
  
-   В таблице **Сведения о производительности функции** отображаются сводные данные профилирования для указанной функции.  
  
-   В окне **Представление кода функции** отображается код функции, если он доступен.  
  
 Окно **Представление кода функции** является отдельной областью. Две области разделены по горизонтали по умолчанию, а окно **Представление кода функции** располагается в нижней части окна области.  
  
-   Чтобы разделить две области по вертикали, на панели инструментов щелкните **Разделить экран по вертикали**.  
  
-   Чтобы изменить относительный размер областей, щелкните затененную границу между кадрами и перетащите границу в другое место.  
  
## <a name="cost-distribution-bar-chart"></a>Линейчатая диаграмма "Распределение стоимости"  
  
### <a name="performance-metrics"></a>Метрики производительности  
 В раскрывающемся списке **Метрика производительности** вы можете указать значения, отображаемые в представлении. Доступные значения зависят от способа профилирования, который использовался в файлах данных профилирования. Имена в круглых скобках являются именами строк в таблице **Сведения о производительности функции**.  
  
### <a name="bar-chart"></a>Линейчатая диаграмма  
 **Вызывающие функции**  
  
 В области **Вызывающие функции** отображаются функции, вызвавшие выбранную функцию. Размер блока, содержащего вызывающую функцию, пропорционален вкладу вызывающей функции в общее значение метрики производительности для выбранной функции.  
  
 Вы можете щелкнуть имя вызывающей функции, чтобы сделать ее выбранной функцией в представлении.  
  
-   Если вызывающих функций, которые нужно вывести, слишком много, вы можете использовать блок **Other** (Другие), в котором размещены функции с наименьшими вкладами. Щелкните блок **Other** (Другие) для отображения всех вызывающих и вызванных функций выбранной функции в окне **Caller/Callee View** (Представление вызывающего и вызываемого объектов). Дополнительные сведения см. в разделе [Представление "Вызывающий/вызываемый"](../profiling/caller-callee-view.md).  
  
-   Если вызывающие функции отсутствуют или если функция является функцией ввода потока или процесса, появится блок **Вершина стека**.  
  
 **Выбранная функция**  
  
 На панели выбранной функции отображаются вклады вызываемых функций и кода выбранной функции в общую метрику производительности выбранной функции. Размер блока, содержащего вызванную функцию или текст функции, пропорционален ее вкладу в общее значение метрики производительности для выбранной функции.  
  
 Вы можете щелкнуть имя вызванной функции, чтобы сделать ее выбранной функцией в представлении.  
  
-   Значение **Всего** является метрикой производительности для выбранной функции.  
  
-   Блок **Тело функции** представляет общее значение метрики производительности в ходе выполнения кода в теле функции.  
  
-   Функции, вызванные выбранной функцией, перечисляются в блоках. Размер блока выбранных функций представляет значение общей метрики производительности для выбранной функции в вызванной функции.  
  
-   Если вызывающих функций, которые нужно вывести, слишком много, вы можете использовать блок **Other** (Другие), в котором размещены функции с наименьшими вкладами. Щелкните блок **Other** (Другие) для отображения всех вызывающих и вызванных функций выбранной функции в окне **Caller/Callee View** (Представление вызывающего и вызываемого объектов). Дополнительные сведения см. в разделе [Представление "Вызывающий/вызываемый"](../profiling/caller-callee-view.md).  
  
-   Если вызванные функции отсутствуют, появляется блок **Дно стека**.  
  
## <a name="function-performance-details"></a>Сведения о производительности функции  
 В таблице сведений о производительности функций представлены сводные данные для метрик производительности выбранной функции. Отображаются значение и процент. Вам необходимо указать данные профилирования диаграммы и таблицу данных в списке **Метрика производительности**.  
  
|Столбец|Описание|  
|------------|-----------------|  
|**Монопольный доступ**|— Значение метрики производительности при выполнении текста функции.|  
|**В вызовах**|— Значение метрики производительности в функциях, вызванных выбранной функцией.|  
|**Включающий итог**|— Общее значение столбцов **Монопольный доступ** и **В вызовах**.|  
  
## <a name="function-code-view"></a>Представление кода функции  
 В окне **Представление кода функции** отображается список исходного кода, если он доступен. Рядом со строками исходного кода, вызывающего другие функции, затененный столбец содержит значения метрики производительности для вызванных функций. Чтобы изменить исходный код, щелкните ссылку на файл исходного кода.  
  
## <a name="cost-distribution-bar-chart-values"></a>Значения линейчатой диаграммы "Распределение стоимости"  
  
### <a name="sampling"></a>Дискретизация  
 В таблице ниже описаны значения в списке метрик производительности для данных профилирования, собранных с использованием метода выборки.  
  
|||  
|-|-|  
|**Включающие выборки (собранные)**|— Для вызывающей функции — количество выборок, собранных при вызове выбранной функции вызывающей функцией.<br />— Для текста функции — количество выборок, собранных при выполнении кода выбранной функцией.<br />— Для вызванной функции — количество выборок, собранных при выполнении вызванной функции за счет вызова выбранной функции.|  
  
### <a name="instrumentation"></a>Инструментирование  
 В таблице ниже описаны значения в списке метрик производительности для данных профилирования, собранных с использованием метода инструментирования.  
  
|||  
|-|-|  
|**Затраченное инклюзивное время (затраченное время)**|Затраченное время включает время, затраченное на выполнение системных вызовов, например переключение контекста и операции ввода-вывода.<br /><br /> — Для **вызывающей функции** — количество затраченного времени на выполнение экземпляров выбранной функции, вызванных функцией. Время, затраченное на выполнение функций, вызванных выбранной функцией, включено.<br />— Для **текста функции** — общее значение затраченного времени на выполнение кода выбранной функции. Время, затраченное в вызванных функциях, не включено.<br />— Для вызванной функции — время, затраченное на выполнение экземпляров функции, вызванных выбранной функцией. Общее значение включает время, затраченное в функциях, вызванных функцией. Время, затраченное на выполнение функций, вызванных выбранной функцией, включено.|  
|**Инклюзивное время приложения (время приложения)**|Время приложения не включает время, которое было затрачено на выполнение системных вызовов, например переключение контекста и операции ввода-вывода.<br /><br /> — Для **вызывающей функции** — количество времени приложения, затраченного на выполнение экземпляров выбранной функции, вызванных функцией. Время, затраченное на выполнение функций, вызванных выбранной функцией, включено.<br />— Для **текста функции** — общее значение времени приложения, затраченного на выполнение кода выбранной функции. Время, затраченное в вызванных функциях, не включено.<br />— Для вызванной функции — время приложения, затраченное на выполнение экземпляров функции, вызванных выбранной функцией. Общее значение включает время, затраченное в функциях, вызванных функцией.|  
  
### <a name="net-memory"></a>Память .NET  
 В таблице ниже описаны значения в списке метрик производительности для данных профилирования, собранных с использованием способа профилирования памяти .NET.  
  
|||  
|-|-|  
|**Включающие выделения (выделения)**|— Для **вызывающей функции** — количество объектов, выделенных экземплярами выбранной функции, вызванной функцией. Это значение включает объекты, выделенные функциями, которые были вызваны выбранной функцией.<br />— Для **текста функции** — количество объектов, выделенных выбранной функцией при выполнении кода. Объекты, выделенные в функциях, вызванных выбранной функцией, не включаются.<br />— Для вызванной функции — количество объектов, выделенных экземплярами функции, вызванных выбранной функцией. Это число включает объекты, выделенные функциями, которые вызвала функция.|  
|**Включающие байты (байты)**|— Для **вызывающей функции** — количество байтов, выделенных экземплярами выбранной функции, вызванной функцией. Это значение включает байты, выделенные функциями, которые были вызваны выбранной функцией.<br />— Для **текста функции** — общее количество байтов, выделенных выбранной функцией при выполнении кода. Байты, выделенные в функциях, вызванных выбранной функцией, не включаются.<br />— Для вызванной функции — количество байтов, выделенных экземплярами функции, вызванных выбранной функцией. Это число включает байты, выделенные функциями, которые вызвала функция.|  
  
### <a name="concurrency"></a>Параллельность  
 В таблице ниже описаны значения в списке метрики производительности для данных профилирования, собранных с использованием метода обеспечения параллельности.  
  
|||  
|-|-|  
|**Включая конфликты (конфликты)**|— Для **вызывающей функции** — количество событий конфликтов ресурсов в экземплярах выбранной функции, вызванной функцией. Это значение включает события конфликтов в функциях, вызванных выбранной функцией.<br />— Для **тела функции** — общее количество событий конфликтов при выполнении кода функцией. Конфликты, произошедшие в функциях, вызванных выбранной функцией, не включены.<br />— Для вызванной функции — количество событий конфликтов в экземплярах функции, вызванных выбранной функцией. Это значение включает события конфликтов в функциях, вызванных функцией.|  
|**Включая время блокирования (время блокировки)**|— Для вызывающей функции — время, затраченное в событиях конфликтов ресурсов для экземпляров выбранной функции, вызванной функцией. Время включает время блокировки в функциях, вызванных выбранной функцией.<br />— Для **тела функции** — общее время, затраченное в событиях конфликтов при выполнении кода функцией. Конфликты, происходящие в функциях, вызванных выбранной функцией, не включены.<br />— Для вызванной функции — время, затраченное в событиях конфликтов ресурсов для экземпляров функции, вызванной выбранной функцией. Время включает время блокировки в функциях, вызванных функцией.|


