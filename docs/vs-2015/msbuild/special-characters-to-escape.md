---
title: Знаки, требующие отключения их специального значения | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- special characters to escape
- msbuild, special characters to escape
ms.assetid: 5b5172c3-41e4-4f38-a16f-2aeac831a5fc
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd69e5ad896db0949a380ac64d57dbc925b3878f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47572861"
---
# <a name="special-characters-to-escape"></a>Знаки, требующие отключения их специального значения
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [специальные знаки, требующие](https://docs.microsoft.com/visualstudio/msbuild/special-characters-to-escape).  
  
  
Специальные знаки необходимо экранировать только в том случае, если они имеют особое значение в контексте, в котором используются. Например, звездочка (*) является специальным символом только в атрибутах "Включить" и "Исключить" определения элемента или при вызове <xref:Microsoft.Build.Tasks.CreateItem>. Во всех остальных случаях звездочка считается символом звездочки. Если не требуется экранировать звездочки в файлах проекта, использование их в таком виде не приносит никакого вреда.  
  
 Вместо специального знака используйте нотацию %*xx*, где *xx* представляет собой шестнадцатеричное значение символа ASCII. Например, чтобы использовать символ звездочки (*) как буквенный символ, используйте значение `%2A`.  
  
 Полный список специальных символов для экранирования см. далее.  
  
|Знак|Описание|  
|---------------|-----------------|  
|%|Знак процента, используемый для ссылки на метаданные.|  
|$|Знак доллара, используемый для ссылки на свойства.|  
|@|Знак at, используемый для ссылки на списки элементов.|  
|(|Открывающая скобка, используемая в списках.|  
|)|Закрывающая скобка, используемая в списках.|  
|`|Апостроф (или деление), используемый в условиях и других выражениях.|  
|;|Точка с запятой — разделитель элементов списка.|  
|?|Вопросительный знак — подстановочный знак, используемый при описании файловой спецификации в разделе включение/исключение элемента.|  
|*|Звездочка — подстановочный знак, используемый при описании файловой спецификации в разделе включение/исключение элемента.|  
  
## <a name="see-also"></a>См. также  
 [How to: Escape Special Characters in MSBuild](../msbuild/how-to-escape-special-characters-in-msbuild.md)  (Как обеспечить пропуск специальных знаков в MSBuild)  
 [Справочные сведения о MSBuild](../msbuild/msbuild-reference.md)


