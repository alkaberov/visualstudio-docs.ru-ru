---
title: Использование моделей в процессе разработки | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-techdebt
ms.tgt_pltfrm: ''
ms.topic: get-started-article
helpviewer_keywords:
- UML, using models
ms.assetid: a33ac8fc-4ba0-4850-b71b-014dc8674e54
caps.latest.revision: 31
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: 5ff2526d6ff7bb19448674aed043848e760b85e3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47563651"
---
# <a name="use-models-in-your-development-process"></a>Использование моделей в процессе разработки
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [использование моделей в процессе разработки](https://docs.microsoft.com/visualstudio/modeling/use-models-in-your-development-process).  
  
В Visual Studio можно использовать модель для изучения и изменения системы, приложения или компонента. Модель может помочь визуализировать среду, в которой работает система, уточнить требования пользователей, определить архитектуру системы, проанализировать код и убедиться, что код удовлетворяет этим требованиям. См. в разделе [видео Channel 9: Совершенствование архитектуры путем моделирования](http://go.microsoft.com/fwlink/?LinkID=252078).  
  
 Чтобы узнать, какие версии Visual Studio поддерживают каждый тип модели, см. раздел [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="how-to-use-models"></a>Использование моделей  
 Модели можно использовать несколькими способами:  
  
-   Рисование схем моделирования помогает уточнять концепции, связанные с требованиями, архитектурой и высокоуровневой структурой. Дополнительные сведения см. в разделе [моделирование требований пользователей](../modeling/model-user-requirements.md).  
  
-   Работа с моделями помогает выявить несогласованность требований.  
  
-   Взаимодействие с моделями помогает четко пояснять важные концепции на естественном языке. Дополнительные сведения см. в разделе [Моделирование архитектуры приложения](../modeling/model-your-app-s-architecture.md).  
  
-   Иногда можно использовать модели для создания кода или других артефактов, таких как документы или схемы баз данных. Например, компоненты моделирования [!INCLUDE[vsUltShort](../includes/vsultshort-md.md)] создаются из модели.  Дополнительные сведения см. в разделе [Создание и настройка приложения на основе моделей](../modeling/generate-and-configure-your-app-from-models.md).  
  
 Модели можно использовать в самых разнообразных процессах — от максимально гибких до предельно формальных.  
  
### <a name="use-models-to-reduce-ambiguity"></a>Использование моделей для сокращения неоднозначности  
 Язык моделирования менее неоднозначен, чем естественный язык, и предназначен для выражения идей, характерных для разработки программного обеспечения.  
  
 Если в проекте участвует небольшая команда, использующая гибкий подход к работе, можно использовать модели для уточнения пользовательских историй. При обсуждении с клиентом его потребностей создание модели помогает получать полезные вопросы намного быстрее и по более обширному ассортименту продуктов по сравнению с созданием копилки или кода прототипа.  
  
 Если проект большой и включает в себя команды в разных странах, можно использовать модели для более эффективного обмена сведениями о требованиях и архитектуре и по сравнению с обычным текстом.  
  
 В обоих случаях создание модели почти всегда позволяет значительно уменьшить число несоответствий и неоднозначностей. Разные заинтересованные лица часто имеют разное представление о производственной среде, в которой работает система, а разные разработчики часто по-разному понимают принципы работы системы. Использование модели в качестве основы для обсуждения обычно позволяет выявить эти различия. Дополнительные сведения о том, как использовать модель для уменьшения числа несоответствий, см. в разделе [моделирование требований пользователей](../modeling/model-user-requirements.md).  
  
### <a name="use-models-with-other-artifacts"></a>Использование моделей с другими артефактами  
 Сама по себе модель не является спецификацией требований или архитектурой. Это средство для более четкого выражения некоторых аспектов этих понятий, однако выразить можно далеко не все понятия, необходимые во время разработки программного обеспечения. Поэтому модели следует использовать вместе с другими средствами взаимодействия, такими как абзацы или страницы OneNote, документы Microsoft Office, рабочие элементы в [!INCLUDE[esprfound](../includes/esprfound-md.md)] или стикеры на стене кабинета. Кроме последнего, все эти типы объектов могут быть связаны с частями элементов модели.  
  
 Ниже перечислены другие аспекты спецификации, которые обычно используются вместе с моделями. В зависимости от масштаба и стиля проекта можно использовать лишь часть этих аспектов или не использовать их совсем:  
  
-   Пользовательские истории. Пользовательская история — это согласованное с пользователями и другими заинтересованными лицами краткое описание какого-либо аспекта поведения системы, который будет реализован на одной из итераций проекта. Типичное описание начинается  с фразы "Клиент сможет...". Пользовательская история может представлять группу вариантов использования или определять расширения вариантов использования, которые были разработаны ранее. Определение или расширение вариантов использования помогает сделать пользовательскую историю яснее.  
  
-   Запросы на изменение. Запрос на изменение в более формальном проекте очень похож на пользовательскую историю в проекте с гибким подходом к работе. При гибком подходе все требования рассматриваются как изменения для того, что было разработано в предыдущих итерациях.  
  
-   Описание варианта использования. Вариант использования представляет один способ взаимодействия пользователя с системой для достижения определенной цели. Полное описание включает в себя цель, основную и альтернативную последовательность событий, а также исключительные результаты. Схема вариантов использования помогает подвести итог по вариантам использования.  
  
-   Сценарии. Сценарий — это довольно подробное описание последовательности событий, показывающее совместную работу системы, пользователей и других систем в пользу заинтересованных лиц. Может принимать форму слайд-шоу  пользовательского интерфейса или прототипа пользовательского интерфейса в форме. Сценарий может описывать один вариант использования или последовательность вариантов использования.  
  
-   Глоссарий. Глоссарий требований проекта описывает слова, с помощью которых клиенты описывают свою рабочую среду. Эти термины также следует использовать в пользовательском интерфейсе и требованиях к модели. Схема классов может помочь прояснить отношения между большинством этих терминов. Создание схем и глоссария не только снижает число недопониманий между пользователями и разработчиками, но и почти всегда выявляет недопонимания между различными заинтересованными лицами.  
  
-   Бизнес-правила. Многие бизнес-правила могут быть выражены как инвариантные ограничения ассоциаций и атрибутов в модели классов требований и как ограничения на схемах последовательностей.  
  
-   Высокоуровневая структура. Описывает основные части и их совместную работу. Схемы компонентов, последовательностей и интерфейса являются основной частью высокоуровневой структуры.  
  
-   Конструктивные шаблоны. Описывают правила проектирования, которые являются общими для различных частей системы.  
  
-   Спецификации тестирования. В сценариях теста и структуре для кода теста можно активно применять схемы деятельности и последовательностей для описания последовательности шагов теста. Системные тесты должны выражаться в терминах модели требований, чтобы их можно было легко изменить при изменении требований.  
  
-   План проекта. План проекта или невыполненная работа определяет, когда будет доставлена каждая из функций. Каждую функцию можно определить, указав, какие варианты использования и бизнес-правила она реализует или расширяет. Можно ссылаться на варианты использования и бизнес-правила непосредственно в плане или определить набор функций в отдельном документе, а в плане использовать названия функций.  
  
### <a name="use-models-in-iteration-planning"></a>Использование моделей при планировании итераций  
 Хотя все проекты отличаются по масштабу и организации, типичный проект планируется как серия итераций длительностью от двух до шести недель. Важно запланировать достаточно итераций, чтобы отзывы по ранним итерациям можно было использовать для корректировки области действия и планов на более поздних итерациях.  
  
 Следующие предложения могут помочь вам понять преимущества моделирования в итеративном проекте.  
  
#### <a name="sharpen-focus-as-each-iteration-approaches"></a>Корректировка фокуса при приближении очередной итерации  
 По мере приближения очередной итерации используйте модели, чтобы определить, что именно предоставляется в конце итерации.  
  
-   Не применяйте детальное моделирование на ранних итерациях. В первой итерации создайте схему классов для основных элементов в глоссарии пользователя, нарисуйте схему для основных вариантов использования и схему для основных компонентов. Не описывайте эти элементы подробно, потому что отдельные детали изменятся позднее в ходе проекта. Используйте термины, определенные в этой модели, для создания списка функций или основных пользовательских историй. Назначьте функции итерациям, чтобы приблизительно сбалансировать предполагаемую рабочую нагрузку в рамках всего проекта. Эти назначения изменятся позднее в ходе проекта.  
  
-   В ранних итерациях попытайтесь реализовать упрощенные версии всех наиболее важных вариантов использования. Расширьте эти варианты использования в последующих итерациях. Такой подход позволяет снизить риск запоздалого обнаружения недостатков в требованиях или архитектуре проекта, когда уже ничего нельзя сделать.  
  
-   В конце каждой итерации проводите обсуждение требований, чтобы подробно определить требования или пользовательские истории, которые будут реализованы в следующей итерации. Пригласите пользователей и заинтересованных лиц из бизнес-среды, которые могут определить приоритеты, а также разработчиков и системных тест-инженеров. Отведите три часа на определение требований для 2-недельной итерации.  
  
-   Задача обсуждения заключается в том, чтобы все участники договорились о том, что должно быть сделано к концу следующей итерации. Используйте модели как одно из средств для уточнения этих требований. Результатом такого обсуждения является невыполненная работа по итерации: то есть список задач разработки в [!INCLUDE[esprfound](../includes/esprfound-md.md)] и наборов тестов в [!INCLUDE[TCMext](../includes/tcmext-md.md)].  
  
-   В обсуждение требований рассматривайте структуру только до такой степени, которая позволяет определить оценки для задач разработки. В противном случае обсуждайте поведение системы, с которым пользователи могут столкнуться непосредственно. Отделите модель требований от модели архитектуры.  
  
-   У заинтересованных лиц, не имеющих технических навыков, обычно не возникает проблем с восприятием схем UML, сопровождаемых вашими пояснениями.  
  
#### <a name="link-model-to-work-items"></a>Связывание модели с рабочими элементами  
 После обсуждения требований уточните сведения о модели требований и свяжите ее с задачами разработки. Это можно сделать путем связывания рабочих элементов в [!INCLUDE[esprfound](../includes/esprfound-md.md)] с элементами в модели. Чтобы узнать, как это сделать, см. в разделе [связывание элементов модели и рабочими элементами](../modeling/link-model-elements-and-work-items.md).  
  
 С рабочими элементами можно связать любой элемент, но наиболее полезными являются следующие элементы:  
  
-   Варианты использования. Вариант использования можно связать с задачами разработки, которые будут его реализовывать.  
  
-   Расширения вариантов использования. Если в ходе итерации будет реализован только один аспект варианта использования, можно разделить его на основной вариант использования и одно или несколько расширений. Расширения — это варианты использования, связанные с основным вариантом отношением "расширение". Дополнительные сведения о расширении варианта использования, см. в разделе [схем вариантов использования UML: Справочник по](../modeling/uml-use-case-diagrams-reference.md).  
  
-   Комментарии, описывающие бизнес-правила или требования к качеству обслуживания. Дополнительные сведения см. в разделе [моделирование требований пользователей](../modeling/model-user-requirements.md).  
  
#### <a name="link-model-to-tests"></a>Связывание модели с тестами  
 Используйте модель требований для управления разработкой тестов приемки. Создавайте эти тесты одновременно с разработкой.  
  
 Дополнительные сведения об этом методе см. в разделе [Разработка тестов из модели](../modeling/develop-tests-from-a-model.md).  
  
#### <a name="estimate-remaining-work"></a>Оценка оставшихся трудозатрат  
 Модель требований может помочь оценить общий размер проекта по сравнению с размером каждой итерации. Оценка числа и сложности вариантов использования и классов может помочь определить необходимый объем работ по разработке. После завершения нескольких первых итераций можно провести сравнение выполненных требований и требований, которые еще предстоит выполнить, чтобы приблизительно оценить стоимость и масштаб оставшейся части проекта.  
  
 В конце каждой итерации рассмотрите назначение требований для будущих итераций. Может оказаться полезным представлять состояние программного обеспечения в конце каждой итерации в виде подсистемы на схеме вариантов использования. Во время обсуждения можно перемещать варианты использования и расширения вариантов использования из одной такой подсистемы в другую.  
  
## <a name="levels-of-abstraction"></a>Уровни абстракции  
 Модели имеют диапазон абстракции в отношении программного обеспечения. Наиболее конкретные модели непосредственно представляют код программы, а наиболее абстрактные модели представляют бизнес-концепции, которые могут быть как представлены, так и не представлены в коде.  
  
 Модель можно просмотреть с помощью нескольких типов схем. Сведения о моделях и схемах см. в разделе [Создание моделей для приложения](../modeling/create-models-for-your-app.md).  
  
 Различные виды схем полезны для описания разработки на различных уровнях абстракции. Многие типы схем можно с пользой применять сразу на нескольких уровнях. В этой таблице показано, как можно использовать каждый тип схем.  
  
|Уровень разработки|Типы схем|  
|------------------|-------------------|  
|Бизнес-процесс<br /><br /> Общее представление о контексте, в котором будет использоваться система, помогает понять потребности пользователей.|-Схемы деятельности описывают поток работ между людьми и системами для достижения бизнес-целей.<br />-Принципиальные схемы классов описывают бизнес-концепции, используемые в бизнес-процесса.|  
|Требования пользователей<br /><br /> Определение того, что нужно пользователям от вашей системы.|— Схемы вариантов использования обобщают взаимодействия пользователей и других внешних систем, имеют в системе, которую вы разрабатываете. К каждому варианту использования можно присоединить другие документы, чтобы подробно его описать.<br />-UML схемы классов описывают типов данных, пользователями и системой обмен данными о.<br />-Бизнес-правила и требования к качеству обслуживания могут быть описаны в отдельных документах.|  
|Высокоуровневая структура<br /><br /> Общая структура системы: основные компоненты и их взаимосвязи.|-Схемы слоев описывают структуру системы на независимые части. Можно проверить код программы по схеме слоев, чтобы убедиться в его соответствии архитектуре.<br />-Схемы компонентов показывают интерфейсы частей, указывая сообщения и службы, которые являются предоставленными и требуемыми каждым компонентом.<br />-Схемы последовательностей показывают, как компоненты взаимодействуют для реализации каждого варианта использования.<br />-UML схемы классов описывают интерфейсы компонентов и типы данных, передаваемых между компонентами.|  
|Конструктивные шаблоны<br /><br /> Соглашения и методы решения проблем проектирования, которые используются во всех частях процесса разработки|-UML схемы классов описывают структуры шаблона.<br />-Последовательностей или деятельности показывают взаимодействия и алгоритмы|  
|Анализ кода<br /><br /> Из кода можно создать несколько типов схем.|-Последовательностей показывают взаимодействие между объектами в коде.<br />-Схемы слоев показывают зависимости между классами. Обновленный код можно проверить на соответствие схеме слоев.<br />-Схемы классов показывают классы в коде.|  
  
## <a name="external-resources"></a>Внешние ресурсы  
  
|**Категория**|**Ссылки**|  
|------------------|---------------|  
|**Видеоролики**|![ссылка на видео](../data-tools/media/playvideo.gif "PlayVideo") [MSDN видеоматериалов: как создание и использование моделей и схем UML (Visual Studio 2010 Ultimate)](http://go.microsoft.com/fwlink/?LinkId=214460)<br /><br /> ![ссылка на видео](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: Использование UML в Visual Studio 2010](http://go.microsoft.com/fwlink/?LinkID=201106)<br /><br /> ![ссылка на видео](../data-tools/media/playvideo.gif "PlayVideo") [MSDN практические руководства: средства UML и расширяемость (Visual Studio 2010 Ultimate)](http://go.microsoft.com/fwlink/?LinkID=214467)|  
|**Форумы**|-   [Средства моделирования и визуализации Visual Studio](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Пакет SDK для моделирования и визуализации в Visual Studio (инструменты DSL)](http://go.microsoft.com/fwlink/?LinkId=184721)|  
|**Блоги**|[Блог по Visual Studio ALM + Team Foundation Server](http://go.microsoft.com/fwlink/?LinkID=201340)|  
|**Технические статьи и журналы**|[Центр архитекторов на MSDN](http://go.microsoft.com/fwlink/?LinkId=201343)<br /><br /> [Руководство по средствам проектирования архитектуры Visual Studio](../modeling/visual-studio-architecture-tooling-guidance.md)|  
  
## <a name="see-also"></a>См. также  
 [Использование моделей в гибкой разработке](http://msdn.microsoft.com/en-us/592ac27c-3d3e-454a-9c38-b76658ed137f)   
 [Создание моделей для приложения](../modeling/create-models-for-your-app.md)   
 [Моделирование требований пользователей](../modeling/model-user-requirements.md)   
 [Моделирование архитектуры приложения](../modeling/model-your-app-s-architecture.md)   
 [Разработка тестов из модели](../modeling/develop-tests-from-a-model.md)   
 [Разработка структуры решения моделирования](../modeling/structure-your-modeling-solution.md)


