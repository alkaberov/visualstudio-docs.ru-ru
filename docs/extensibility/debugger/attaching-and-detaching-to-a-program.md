---
title: Присоединение и отсоединение программы | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, attaching to programs
- debug engines, detaching from programs
ms.assetid: 79dcbb9b-c7f8-40fc-8a00-f37fe1934f51
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9edbabb078bc46c55431276e9c1fe8d1f807d76f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350913"
---
# <a name="attaching-and-detaching-to-a-program"></a>Присоединение и отсоединение к программе
Подключение отладчика требуется отправить правильную последовательность методов и событий с верными атрибутами.

## <a name="sequence-of-methods-and-events"></a>Последовательность методов и событий

1. Диспетчер отладки сеансов (SDM) вызывает [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) метод.

    На основе модели процесса отладки ядра (DE), `IDebugProgramNodeAttach2::OnAttach` метод возвращает одно из следующих методов, которые определяет, что будет дальше.

    Если `S_FALSE` возвращается, модуль отладки успешного присоединения к программе. В противном случае [Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) метод вызывается для завершения процесса присоединения.

    Если `S_OK` возвращается, DE является должен быть загружен в тот же процесс, что SDM. SDM выполняет следующие задачи:

   1. Вызовы [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) получить сведения из DE.

   2. Совместно создает DE.

   3. Вызовы [присоединить](../../extensibility/debugger/reference/idebugengine2-attach.md).

2. Отправляет DE [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) для SDM с `EVENT_SYNC` атрибута.

3. Отправляет DE [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) для SDM с `EVENT_SYNC` атрибута.

4. Отправляет DE [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) для SDM с `EVENT_SYNC_STOP` атрибута.

   Отсоединение от программы является простое, двухэтапный процесс, следующим образом:

5. Вызовы SDM [отсоединения](../../extensibility/debugger/reference/idebugprogram2-detach.md).

6. Отправляет DE [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md).

## <a name="see-also"></a>См. также
- [Вызов событий отладчика](../../extensibility/debugger/calling-debugger-events.md)