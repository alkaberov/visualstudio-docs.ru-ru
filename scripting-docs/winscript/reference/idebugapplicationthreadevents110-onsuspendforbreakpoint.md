---
title: 'IDebugApplicationThreadEvents110:: Онсуспендфорбреакпоинт | Документация Майкрософт'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThreadEvents110::OnSuspendForBreakPoint
ms.assetid: 224245ac-2aa2-43ae-97ed-493afc3d0122
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b5d73d7769dd48889a75da63da64be1d2977a088
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72573338"
---
# <a name="idebugapplicationthreadevents110onsuspendforbreakpoint"></a>IDebugApplicationThreadEvents110::OnSuspendForBreakPoint
Определяет, полностью ли приостановлен поток для точки останова и еще не возобновил нормальное выполнение.  
  
> [!IMPORTANT]
> [Интерфейс IDebugApplicationThreadEvents110](../../winscript/reference/idebugapplicationthreadevents110-interface.md) реализуется с помощью PDM v 11.0 и более поздних версий. Обнаружено в activdbg100.h.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OnSuspendForBreakPoint( void );  
```  
  
#### <a name="parameters"></a>Параметры  
 Этот метод не имеет параметров.  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IDebugApplicationThreadEvents110](../../winscript/reference/idebugapplicationthreadevents110-interface.md)