---
title: Задача AssignTargetPath | Документы Майкрософт
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 0e830e31-3bcf-4259-b2a8-a5df49b92d51
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 41a32b914cab8626df513994a3d68c2aac3d7cb7
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/01/2020
ms.locfileid: "75593438"
---
# <a name="assigntargetpath-task"></a>Задача AssignTargetPath
Эта задача принимает список файлов и добавляет атрибуты `<TargetPath>`, если они еще не указаны.

## <a name="task-parameters"></a>Параметры задачи
В следующей таблице приводятся параметры задачи `AssignTargetPath` .

|Параметр|Описание|
|---------------|-----------------|
|`RootFolder`|Необязательный входной параметр `string`.<br /><br /> Содержит путь к папке с целевыми ссылками.|
|`Files`|Необязательный входной параметр <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Содержит исходный список файлов.|
|`AssignedFiles`|Необязательный<br /><br /> Выходной параметр <xref:Microsoft.Build.Framework.ITaskItem> `[]`.<br /><br /> Содержит итоговый список файлов.|

## <a name="remarks"></a>Примечания
Помимо перечисленных выше параметров, эта задача наследует параметры от класса <xref:Microsoft.Build.Tasks.TaskExtension>, который, в свою очередь, наследует от класса <xref:Microsoft.Build.Utilities.Task>. Список этих дополнительных параметров и их описания см. в статье [Базовый класс TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Пример
Следующий пример выполняет задачу `AssignTargetPath`, чтобы настроить проект.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <Target Name="MyProject">
        <AssignTargetPath
RootFolder="Resources"
            Files="@(ResourceFiles)"
            <Output TaskParameter="AssignedFiles"
                ItemName="OutAssignedFiles"/>
        </AssignTargetPath>
    </Target>
</Project>
```

## <a name="see-also"></a>См. также
- [Задачи](../msbuild/msbuild-tasks.md)
- [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)
