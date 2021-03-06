---
title: 'Идиаенумсектионконтрибс:: Item | Документация Майкрософт'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::Item method
ms.assetid: 63a28f23-0ca0-44a7-b11b-ca0206d642a0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d021b5016bd0e0039f2bf175102dc44f04dabaab
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72744299"
---
# <a name="idiaenumsectioncontribsitem"></a>IDiaEnumSectionContribs::Item
Извлекает вклады раздела с помощью индекса.

## <a name="syntax"></a>Синтаксис

```C++
HRESULT Item ( 
   DWORD                index,
   IDiaSectionContrib** section
);
```

#### <a name="parameters"></a>Параметры
 индекс

окне Индекс объекта [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md) для извлечения. Индекс находится в диапазоне от 0 до `count`-1, где `count` возвращается методом [идиаенумсектионконтрибс:: get_Count](../../debugger/debug-interface-access/idiaenumsectioncontribs-get-count.md) .

 section

заполняет Возвращает объект [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md) , представляющий нужную публикацию раздела.

## <a name="return-value"></a>Возвращаемое значение
 В случае успеха возвращает `S_OK`; в противном случае возвращает код ошибки.

## <a name="see-also"></a>См. также
- [IDiaEnumSectionContribs::get_Count](../../debugger/debug-interface-access/idiaenumsectioncontribs-get-count.md)
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)