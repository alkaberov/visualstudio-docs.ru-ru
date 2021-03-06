---
title: Структура файла Content_types]. XML | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- content_types
- content types
- opc
- vsix
ms.assetid: 9c399598-b9fa-4da7-84b5-defbf82e9335
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 3185b70f74478a9a55c4fb918c1535c86d154c76
ms.sourcegitcommit: c150d0be93b6f7ccbe9625b41a437541502560f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75846372"
---
# <a name="the-structure-of-the-content_typesxml-file"></a>Структура файла [типы_содержимого].xml
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Содержит сведения о типах содержимого в пакете VSIX. Visual Studio использует файл [Content_Types]. XML для установки пакета, но не устанавливает сам файл.  
  
> [!NOTE]
> Хотя этот раздел применим только к файлам [Content_Type]. XML, которые используются в пакетах VSIX, тип файла [Content_Types]. XML является частью стандарта *Open Packaging Conventions (OPC)* . Дополнительные сведения см. в статье [OPC: новый стандарт для упаковки данных](https://msdn.microsoft.com/magazine/cc163372.aspx) на веб-сайте MSDN.  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описывается корневой элемент, его атрибуты и дочерние элементы.  
  
### <a name="root-element"></a>Элемент Root  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`Types`|Содержит дочерние элементы, которые перечисляют типы файлов в пакете VSIX.|  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`Xmlns`|(Обязательно.) Расположение схемы, используемой для этого файла [Content_Types]. XML.|  
  
### <a name="attribute-name-attribute"></a>{Имя атрибута} Версию  
  
|                           {2&gt;Value&lt;2}                           |                Описание                |
|-----------------------------------------------------------|-------------------------------------------|
| http://schemas.openformats.org/package/2006/content-types | Расположение схемы типов содержимого. |
  
### <a name="child-elements"></a>Дочерние элементы  
 Элемент `Types` может содержать любое число элементов `Default`.  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`Default`|Описывает тип содержимого в пакете VSIX. Каждый тип файлов в пакете должен иметь собственный элемент `Default`.|  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`Extension`|Расширение имени файла в пакете VSIX.|  
|`ContentType`|Описывает тип содержимого, связанного с расширением имени файла.|  
  
### <a name="attribute-name-attribute"></a>{Имя атрибута} Версию  
 Visual Studio распознает следующие `ContentType` значения для связанных типов `Extension`.  
  
|Расширение|ContentType|  
|---------------|-----------------|  
|txt|текст/обычный|  
|pkgdef|текст/обычный|  
|xml|text/xml|  
|vsixmanifest|text/xml|  
|htm или HTML|text/html|  
|RTF|приложение/RTF|  
|pdf|приложение/PDF|  
|gif|image/gif|  
|JPG или JPEG|Image/JPG|  
|tiff|image/tiff|  
|vsix|приложение/ZIP-файл|  
|zip|приложение/ZIP-файл|  
|dll|application/octet-stream|  
|Все прочие типы файлов|application/octet-stream|  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 Следующий файл [Content_Types]. XML описывает типичный пакет VSIX.  
  
### <a name="code"></a>Код  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<Types xmlns="http://schemas.openxmlformats.org/package/2006/content-types">  
    <Default Extension="vsixmanifest" ContentType="text/xml" />   
    <Default Extension="dll" ContentType="application/octet-stream" />   
    <Default Extension="png" ContentType="application/octet-stream" />   
    <Default Extension="txt" ContentType="text/plain" />   
    <Default Extension="pkgdef" ContentType="text/plain" />   
</Types>  
```  
  
## <a name="see-also"></a>См. также раздел  
 [Анатомия пакета VSIX](../extensibility/anatomy-of-a-vsix-package.md)   
 [Справочник по схеме расширения VSIX 1,0](https://msdn.microsoft.com/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [OPC: новый стандарт для упаковки данных](https://msdn.microsoft.com/magazine/cc163372.aspx)
