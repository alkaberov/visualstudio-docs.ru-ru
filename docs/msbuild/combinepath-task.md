---
title: Задача CombinePath | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CombinePath task
- CombinePath task [MSBuild]
ms.assetid: c20edbf4-3d4f-4f66-b1d5-753a0d858ed8
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a52e0d770a535b0fa7d29a379a7f6aba63e62d78
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/01/2020
ms.locfileid: "75593347"
---
# <a name="combinepath-task"></a>CombinePath - задача
Объединяет указанные пути в единый путь.

## <a name="task-parameters"></a>Параметры задачи
 В следующей таблице приводятся параметры [задачи CombinePath](../msbuild/combinepath-task.md).

|Параметр|Описание|
|---------------|-----------------|
|`BasePath`|Обязательный параметр `String` .<br /><br /> Базовый путь для объединения с другими путями. Может представлять собой относительный, абсолютный путь или быть пустым.|
|`Paths`|Обязательный параметр <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Список отдельных путей, объединяемых с BasePath для получения объединенного пути. Пути могут быть как относительными, так и абсолютными.|
|`CombinedPaths`|Необязательный выходной параметр <xref:Microsoft.Build.Framework.ITaskItem>`[]` .<br /><br /> Объединенный путь, созданный этой задачей.|

## <a name="remarks"></a>Примечания
 Помимо перечисленных выше параметров, эта задача наследует параметры от класса <xref:Microsoft.Build.Tasks.TaskExtension>, который, в свою очередь, наследует от класса <xref:Microsoft.Build.Utilities.Task>. Список этих дополнительных параметров и их описания см. в статье [Базовый класс TaskExtension](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>См. также
- [Задачи](../msbuild/msbuild-tasks.md)
- [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)
