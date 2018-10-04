---
title: Схемы вариантов использования свойства элементов на UML | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.teamarch.usecasediagram.artifact.properties
- vs.teamarch.usecasediagram.shapes.properties
helpviewer_keywords:
- use case diagrams, properties
ms.assetid: 2728fb26-a275-4fce-8a2c-5a78af6bee04
caps.latest.revision: 13
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: dd23baadfca51bf669336ab96bf00ee5d4594a08
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47568303"
---
# <a name="properties-of-elements-on-uml-use-case-diagrams"></a>Свойства элементов на схемах вариантов использования UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [схемы вариантов использования свойства элементов на UML](https://docs.microsoft.com/visualstudio/modeling/properties-of-elements-on-uml-use-case-diagrams).  
  
На схеме вариантов использования UML каждый элемент имеет свойства. Чтобы просмотреть свойства элемента, щелкните правой кнопкой мыши элемент на схеме или в **Обозреватель моделей UML** и нажмите кнопку **свойства**. Свойства отображаются в **свойства** окна.  
  
> [!NOTE]
>  В этом разделе описываются свойства элементов на схемах вариантов использования UML. Дополнительные сведения о чтении UML-схемы деятельности, см. в разделе [схемах вариантов использования UML: Справочник по](../modeling/uml-use-case-diagrams-reference.md). Дополнительные сведения о рисовании схем деятельности UML см. в разделе [UML-схемы деятельности: рекомендации по](../modeling/uml-use-case-diagrams-guidelines.md).  
  
## <a name="properties-of-elements"></a>Свойства элементов  
  
|Свойство|По умолчанию|Элемент|Описание|  
|--------------|-------------|-------------|-----------------|  
|**Name**|Имя по умолчанию|Все|Идентифицирует элемент.|  
|**Полное имя**|Пакет :: Имя|Все|Уникально идентифицирует элемент. Перед именем элемента указывается полное имя пакета, содержащего его.|  
|**Рабочие элементы**|0 связанных|Все|Число рабочих элементов, связанных с этим элементом. Чтобы связать рабочие элементы, см. в разделе [связывание элементов модели и рабочими элементами](../modeling/link-model-elements-and-work-items.md).|  
|**Описание**|(нет)|Все|Здесь можно вести общие заметки об элементе.|  
|**Цвет**|(по умолчанию)|Все|Цвет фигуры. В отличие от других свойств это свойство элемента не отображается в фигуре.|  
|**Путь к изображению**|(нет)|Actor|Путь к файлу изображения, которое следует использовать вместо значка субъекта по умолчанию. Значок должен быть файлом ресурсов в проекте Visual Studio.|  
|**Субъекты**|(нет)|Вариант использования|Подсистема или другой тип, которому принадлежит вариант использования.<br /><br /> Его можно задать, разместив вариант использования в подсистеме на схеме.|  
|**Видимость**|Public|Вариант использования, субъект, подсистема|**Открытый** — видимый глобально.<br /><br /> **Пакет** — видимый в пределах пакета.|  
|**Является абстрактным**|False|Вариант использования, субъект, подсистема|Если значение true, не удается создать экземпляр типа, который в этом случае предназначен для использования в качестве основы для специализации другими определениями.|  
|**Является неявно создаваемым экземпляром**|Да|Подсистема|Подсистема существует только как артефакт конструкции. Во время выполнения существуют только ее части.|  
|**Гиперссылка**|(нет)|Артефакт|URL-адрес или путь к файлу схемы или документа, на который артефакт предоставляет ссылку.|  
  
 Список свойств ассоциаций, см. в разделе [свойства ассоциаций на UML схемах классов](../modeling/properties-of-associations-on-uml-class-diagrams.md).  
  
## <a name="see-also"></a>См. также  
 [Схемы вариантов использования UML: Справочник по](../modeling/uml-use-case-diagrams-reference.md)   
 [UML-схемы вариантов использования: правила работы](../modeling/uml-use-case-diagrams-guidelines.md)


