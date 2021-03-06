---
title: Служебные методы для текстовых шаблонов
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- text templates, utility methods
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c55da4d58b717bc4d42b6fafdd084067b7e21a31
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/01/2020
ms.locfileid: "75591766"
---
# <a name="text-template-utility-methods"></a>Служебные методы для текстовых шаблонов

Существует несколько методов, которые всегда доступны при написании кода в текстовом шаблоне Visual Studio. Эти методы определяются в <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>.

> [!TIP]
> Кроме того, можно использовать другие методы и службы, предоставляемые средой размещения, в обычном (не предварительно обработанном) текстовом шаблоне. Например, можно разрешить пути к файлам, вести журнал ошибок и получить службы, предоставляемые Visual Studio, и все загруженные пакеты. Дополнительные сведения см. в разделе [доступ к Visual Studio из текстового шаблона](/previous-versions/visualstudio/visual-studio-2010/gg604090\(v\=vs.100\)).

## <a name="write-methods"></a>Методы записи

Можно использовать методы `Write()` и `WriteLine()` для добавления текста в стандартный блок кода вместо использования блока кода выражения. Следующие два блока кода функционально эквивалентны.

### <a name="code-block-with-an-expression-block"></a>Блок кода с блоком выражения

```
<#
int i = 10;
while (i-- > 0)
    { #>
        <#= i #>
    <# }
#>
```

### <a name="code-block-using-writeline"></a>Блок кода с помощью метода WriteLine ()

```
<#
    int i = 10;
    while (i-- > 0)
    {
        WriteLine((i.ToString()));
    }
#>
```

Может оказаться полезным использовать один из этих служебных методов вместо блока выражения внутри длинного блока кода с вложенными структурами элементов управления.

Методы `Write()` и `WriteLine()` имеют две перегрузки, один из которых принимает один строковый параметр и один, принимающий строку составного формата плюс массив объектов для включения в строку (например, метод `Console.WriteLine()`). Следующие два применения `WriteLine()` функционально эквивалентны:

```
<#
    string msg = "Say: {0}, {1}, {2}";
    string s1 = "hello";
    string s2 = "goodbye";
    string s3 = "farewell";

    WriteLine(msg, s1, s2, s3);
    WriteLine("Say: hello, goodbye, farewell");
#>
```

## <a name="indentation-methods"></a>Методы отступов

Для форматирования выходных данных текстового шаблона можно использовать методы отступов. Класс <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation> имеет `CurrentIndent` строкового свойства, показывающего текущий отступ в текстовом шаблоне, и поле `indentLengths`, которое представляет собой список добавленных отступов. Можно добавить отступ с помощью метода `PushIndent()` и вычесть отступ с помощью метода `PopIndent()`. Если необходимо удалить все отступы, используйте метод `ClearIndent()`. В следующем блоке кода показано использование следующих методов:

```
<#
    WriteLine(CurrentIndent + "Hello");
    PushIndent("    ");
    WriteLine(CurrentIndent + "Hello");
    PushIndent("    ");
    WriteLine(CurrentIndent + "Hello");
    ClearIndent();
    WriteLine(CurrentIndent + "Hello");
    PushIndent("    ");
    WriteLine(CurrentIndent + "Hello");
#>
```

Этот блок кода создает следующие выходные данные:

```
Hello
        Hello
                Hello
Hello
        Hello
```

## <a name="error-and-warning-methods"></a>Методы error и Warning

Для добавления сообщений в Список ошибок Visual Studio можно использовать служебные методы ошибок и предупреждений. Например, следующий код добавит сообщение об ошибке в Список ошибок.

```
<#
  try
  {
    string str = null;
    Write(str.Length.ToString());
  }
  catch (Exception e)
  {
    Error(e.Message);
  }
#>
```

## <a name="access-to-host-and-service-provider"></a>Доступ к узлу и поставщику услуг

Свойство `this.Host` может предоставлять доступ к свойствам, предоставляемым узлом, выполняющим шаблон. Чтобы использовать `this.Host`, необходимо задать атрибут `hostspecific` в директиве `<@template#>`:

`<#@template ... hostspecific="true" #>`

Тип `this.Host` зависит от типа узла, в котором выполняется шаблон. В шаблоне, который выполняется в Visual Studio, можно привести `this.Host` к `IServiceProvider`, чтобы получить доступ к службам, таким как интегрированная среда разработки. Например:

```
EnvDTE.DTE dte = (EnvDTE.DTE) ((IServiceProvider) this.Host)
                       .GetService(typeof(EnvDTE.DTE));
```

## <a name="using-a-different-set-of-utility-methods"></a>Использование другого набора служебных методов

В рамках процесса формирования текста файл шаблона преобразуется в класс, который всегда называется `GeneratedTextTransformation`и наследуется от <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>. Если вместо этого вы хотите использовать другой набор методов, можно написать собственный класс и указать его в директиве template. Класс должен наследовать от <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>.

```
<#@ template inherits="MyUtilityClass" #>
```

Используйте директиву `assembly` для ссылки на сборку, в которой можно найти скомпилированный класс.
