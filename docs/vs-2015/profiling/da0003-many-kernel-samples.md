---
title: DA0003. Много выборок в режиме ядра | Документы Майкрософт
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
- vs.performance.rules.DA0003
- vs.performance.DA0003
- vs.performance.3
- vs.performance.rules.DAManyKernelSamples
ms.assetid: c1f46f77-eb95-42e5-b340-d86bc9de41b4
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd4412fc120eb0a0fa039ac91bec4da4ba4a6f44
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47571024"
---
# <a name="da0003-many-kernel-samples"></a>DA0003. Много выборок в режиме ядра
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [DA0003: много выборок в режиме ядра](https://docs.microsoft.com/visualstudio/profiling/da0003-many-kernel-samples).  
  
ИД правила | DA0003 |  
| Категория | Использование средств профилирования |  
| Методы профилирования | Выборка |  
| Сообщение | У вас есть большая доля выборок в режиме ядра. Это может указывать на слишком большое количество операций ввода-вывода или высокую частоту переключения контекста. Рекомендуется воспользоваться для профилирования приложения снова, используя режим инструментария. |  
| Тип правила | Сведения |  
  
## <a name="cause"></a>Причина  
 Значительная часть выборок стека вызовов, собранных для приложения, выполнялась в режиме ядра. Рекомендуется воспользоваться для профилирования приложения другим методом профилирования.  
  
## <a name="rule-description"></a>Описание правила  
 В Windows код может выполняться в режиме ядра или в пользовательском режиме. (Режим ядра также называется привилегированным.) В режиме ядра выполняется только низкоуровневый системный код, например драйверы устройств. Приложение, работающее в пользовательском режиме, может переходить в режим ядра для выполнения операций ввода-вывода, ожидания примитивов синхронизации потоков или процессов либо выполнения системных вызовов.  
  
 Метод выборки дает наилучший результат при профилировании приложений, которые основную часть времени работают в пользовательском режиме. Количество выборок, собранных при выполнении приложения в режиме ядра, может указывать на частые операции ввода-вывода или переключения контекста. Ни одну из этих операций невозможно изучить с помощью метода выборки. Если получено слишком много выборок в режиме ядра, выборка может не содержать достаточное количество выборок в пользовательском режиме для обеспечения статистической достоверности.  
  
## <a name="how-to-fix-violations"></a>Устранение нарушений  
 Рекомендуется повторить профилирование одним из следующих способов:  
  
-   Профилирование с помощью метода инструментирования  
  
-   Увеличение частоты выборки, чтобы и попытаться собрать больше данных в пользовательском режиме.


