---
title: Невозможно удалить свойство
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 29344a2443708d9ddaed3d90a186ab8424638664
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2019
ms.locfileid: "72640491"
---
# <a name="the-property-property-name-cannot-be-deleted"></a>Не удается удалить свойство \<имя свойства>

Не удается удалить свойство \<имя свойства>, поскольку оно задано в качестве **свойства дискриминатора** для наследования между \<имя класса> и \<имя класса>

Выбранное свойство назначено в качестве **свойства дискриминатора** для наследования между классами, указанными в сообщении об ошибке. Свойства не могут быть удалены, если они участвуют в конфигурации наследования между классами данных.

Установите в качестве **свойства дискриминатора** другое свойство класса данных, чтобы дать возможность успешного удаления нужного свойства.

## <a name="to-correct-this-error"></a>Исправление ошибки

1. В **реляционном конструкторе объектов** выберите линию наследования, которая соединяет классы данных, указанные в сообщении об ошибке.

2. Задайте в качестве свойства **дискриминатора** другое свойство.

3. Попытайтесь снова удалить свойство.

## <a name="see-also"></a>См. также

- [Средства LINQ to SQL в Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)