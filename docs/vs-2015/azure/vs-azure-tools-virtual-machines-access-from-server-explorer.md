---
title: Доступ к виртуальным машинам Azure из обозревателя сервера | Документация Майкрософт
description: Общие сведения о просмотре и создании виртуальных машин Azure, а также об управлении ими в обозревателе сервера в Visual Studio.
author: ghogen
manager: jillfra
assetId: eb3afde6-ba90-4308-9ac1-3cc29da4ede0
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 8/31/2017
ms.author: ghogen
ms.openlocfilehash: f4c1ff547d9d550cbbc2e77435b159543fc16bf6
ms.sourcegitcommit: 939407118f978162a590379997cb33076c57a707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2020
ms.locfileid: "75917098"
---
# <a name="accessing-azure-virtual-machines-from-server-explorer"></a>Доступ к виртуальным машинам Azure из обозревателя сервера

Если виртуальные машины размещены в Azure, то они будут доступны через обозреватель серверов. Чтобы просмотреть мобильные службы, войдите в свою подписку Azure. Для этого откройте контекстное меню узла Azure в обозревателе сервера и выберите пункт **Подключиться к Microsoft Azure**.

1. В обозревателе сервера выберите виртуальную машину и откройте окно с ее свойствами, нажав клавишу F4.

    В следующей таблице показаны доступные свойства. Обратите внимание, что все они доступны только для чтения. Чтобы изменить эти свойства, используйте [портал Azure](https://portal.azure.com/).

   | Идентификаторы | Описание |
   | --- | --- |
   | DNS-имя |URL-адрес виртуальной машины в Интернете. |
   | Среда |У виртуальной машины значение этого свойства всегда равно "Производство". |
   | Name |Имя виртуальной машины. |
   | Размер |Размер виртуальной машины, который отражает объем памяти и доступного дискового пространства. См. дополнительные сведения о [размерах виртуальных машин](/azure/cloud-services/cloud-services-sizes-specs). |
   | Status |Возможные значения: "Запуск", "Запущено", "Остановка", "Остановлено" и "Получение состояния". Если отображается значение "Получение состояния", текущее состояние неизвестно. Значения этого свойства отличаются от значений, используемых на [портале Azure](https://portal.azure.com/). |
   | SubscriptionID |Идентификатор подписки вашей учетной записи Azure. Эти сведения можно узнать на [портале Azure](https://portal.azure.com/), просмотрев свойства подписки. |
2. Выберите узел конечной точки, а затем просмотрите окно **Свойства** .
3. В следующей таблице описаны доступные свойства конечных точек, но они доступны только для чтения. Чтобы добавить или изменить конечные точки для виртуальной машины, используйте [портал Azure](https://portal.azure.com/). 

   | Идентификаторы | Описание |
   | --- | --- |
   | Name |Идентификатор конечной точки. |
   | Закрытый порт |Порт для доступа к сети, являющийся внутренним для приложения. |
   | Протокол |Протокол, используемый на транспортном уровне для этой конечной точки (TCP или UDP). |
   | Общий порт |Порт, используемый для общего доступа к приложению. |
