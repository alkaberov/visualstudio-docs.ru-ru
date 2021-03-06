---
title: '&gt; &lt;returns (JavaScript) | Документация Майкрософт'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- returns JavaScript XML tag
- <returns> JavaScript XML tag
ms.assetid: 10d97829-c0ae-40a5-b04c-d8b538cdefbc
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: f8fd8cdc8acdbf42b97e00f3c85647dd863721d5
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2019
ms.locfileid: "72669955"
---
# <a name="ltreturnsgt-javascript"></a>&gt; &lt;returns (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Указывает сведения о документации для результата вызова функции или метода.

## <a name="syntax"></a>Синтаксис

```
<returns type="ValueType" integer="true|false"
    domElement="true|false" mayBeNull="true|false"
    elementType="ArrayElementType" elementInteger="true|false"
    elementDomElement="true|false" elementMayBeNull="true|false"
    locid="descriptionID" value="code">description
</returns>
```

#### <a name="parameters"></a>Параметры
 `type` Необязательный. Тип данных возвращаемого значения. Тип может быть одним из следующих:

- Тип языка ECMAScript в спецификации ECMAScript 5, например `Number` и `Object`.

- Объект DOM, например `HTMLElement`, `Window` и `Document`.

- Функция конструктора JavaScript.

  `integer` Необязательный. Если `type` `Number`, указывает, является ли возвращаемое значение целым числом. Задайте для значение `true`, чтобы указать, что возвращаемым значением является целое число. в противном случае задайте значение `false`. Этот атрибут не используется средой Visual Studio для предоставления сведений IntelliSense.

  `domElement` Необязательный. Этот атрибут является устаревшим; атрибут `type` имеет приоритет над этим атрибутом. Этот атрибут указывает, является ли задокументированное возвращаемое значение элементом DOM. Установите в значение `true`, чтобы указать, что возвращаемое значение является элементом DOM; в противном случае задайте значение `false`. Если атрибут `type` не задан и `domElement` имеет значение `true`, IntelliSense считает задокументированное возвращаемое значение как `HTMLElement` при выполнении инструкции.

  `mayBeNull` Необязательный. Указывает, может ли задокументированное возвращаемое значение быть установлено в NULL. Установите в значение `true`, чтобы указать, что возвращаемое значение может быть равно null. в противном случае задайте значение `false`. Значение по умолчанию — `false`. Этот атрибут не используется средой Visual Studio для предоставления сведений IntelliSense.

  `elementType` Необязательный. Если `type` является `Array`, этот атрибут указывает тип элементов в массиве.

  `elementInteger` Необязательный. Если `type` — `Array`, а `elementType` — `Number`, этот атрибут указывает, являются ли элементы в массиве целыми числами. Значение `true` указывает, что элементы в массиве являются целыми числами; в противном случае — значение `false`. Этот атрибут не используется средой Visual Studio для предоставления сведений IntelliSense.

  `elementDomElement` Необязательный. Этот атрибут является устаревшим; атрибут `elementType` имеет приоритет над этим атрибутом. Если `type` — `Array`, этот атрибут указывает, являются ли элементы в массиве элементами DOM. Значение `true` указывает, что элементы являются элементами DOM; в противном случае используется значение `false`. Если атрибут `elementType` не задан, а для `elementDomElement` установлено `true`, IntelliSense считает каждый элемент в массиве как `HTMLElement` при выполнении завершения операторов.

  `elementMayBeNull` Необязательный. Если `type` является `Array`, указывает, могут ли элементы в массиве принимать значение NULL. Значение `true` указывает, что элементы в массиве могут принимать значение NULL; в противном случае — значение `false`. Значение по умолчанию — `false`. Этот атрибут не используется средой Visual Studio для предоставления сведений IntelliSense.

  `locid` Необязательный. Идентификатор для сведений о локализации возвращаемого значения. Идентификатор является идентификатором члена или соответствует значению атрибута `name` в наборе сообщений, определенном метаданными OpenAjax. Тип идентификатора зависит от формата, указанного в теге [\<loc>](../ide/loc-javascript.md).

  `value` Необязательный. Указывает код, который должен быть вычислен для использования IntelliSense вместо самого кода функции. Например, этот атрибут можно использовать для предоставления IntelliSense для асинхронных обратных вызовов, таких как `Promise`. Использование атрибута `value` с элементом `<returns>` может повысить производительность IntelliSense за счет обхода длинного выполнения кода.

  `description` Необязательный. Описание возвращаемого значения.

## <a name="remarks"></a>Примечания
 Элемент `<returns>` должен быть помещен в тело функции перед любыми инструкциями.

## <a name="example"></a>Пример
 В следующем примере кода показано использование элемента `<returns>`.

```javascript
function areaFunction(radiusParam)
{
    /// <summary>Determines the area of a circle when provided a radius parameter.</summary>
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>
    /// <returns type="Number">The area.</returns>
    var areaVal;
    areaVal = Math.PI * radiusParam * radiusParam;
    return areaVal;
}

// The following examples use the <remarks> element with a value attribute.

function getJson(complete) {
    /// <returns value='complete("")' ></returns>
    var r = new XMLHttpRequest();
    // . . .
}

getJson(function (json) {
    json.  // IntelliSense for a String object is
           // available here.
});

function calculate(x) {
    /// <returns value='1'/>
}
calculate().  // Completion list for a Number.

```

## <a name="see-also"></a>См. также
 [Комментарии XML-документации](../ide/xml-documentation-comments-javascript.md)
