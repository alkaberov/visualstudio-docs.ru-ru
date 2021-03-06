---
title: Область тестирования 7. Общий доступ | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], sharing items
- source control plug-ins, sharing items
ms.assetid: 6ec4780a-bda4-4327-bb3e-c6c9e7eabf35
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c7b698f3802425a16476931513b6e4fe314d9954
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72722382"
---
# <a name="test-area-7-share"></a>Область тестирования 7. Предоставление общего доступа
Эта область тестирования охватывает общий доступ к элементам между расположениями с помощью команды **Share** .

 Операция ххаре является очевидным дублированием файлов и элементов папок между двумя или более местами в иерархии файлов системы управления версиями. Дублирование на сервере на самом деле не происходит, но пользователь увидит тот же файл в двух или более указанных расположениях. При каждом внесении изменений в общие элементы эти изменения отображаются во всех других общих расположениях.

 Общий доступ к папкам работает при выборе папки, в которой в системе управления версиями находится хотя бы один файл. Команда Share отключена при следующих условиях.

- Если выбранная папка является пустой папкой.

- Если имеется папка Real, но она не содержит файлов системы управления версиями.

- Если имеется виртуальная папка, в ней находятся файлы в системе управления версиями.

- Если имеется веб-проект удаленного сайта.

## <a name="command-menu-access"></a>Доступ к меню команд
 В тестовых случаях используются следующие [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] пути меню интегрированной среды разработки.

 Общий доступ: **файловый** ->**система управления версиями** ->**общий ресурс**.

## <a name="expected-behavior"></a>Ожидаемое поведение

- Общий файл отображается в общем расположении.

- Просмотр журнала хранилища версий системы управления версиями показывает, что эти файлы являются общими.

- Изменение общего файла изменяет оба расположения файла.

## <a name="test-cases"></a>Тестовые случаи
 Ниже приведены конкретные тестовые случаи для области тестирования общего ресурса.

|Действие|Шаги теста|Ожидаемые результаты для проверки|
|------------|----------------|--------------------------------|
|Совместное использование файла из одного загруженного проекта в системе управления версиями с другим загруженным проектом|1. Создайте новый проект.<br />2. Добавьте в решение второй проект.<br />3. Создайте файл во втором проекте с именем, которое не находится в первом проекте.<br />4. Добавьте решение в систему управления версиями.<br />5. Выберите первый проект.<br />6. Откройте диалоговое окно **общий доступ** (**файл**  -> **система управления версиями**  -> **общий ресурс**).<br />7. Предоставьте общий доступ к файлу из второго проекта в первый проект.<br />8. при появлении запроса **примите извлечение.**|Типичное ожидаемое поведение.|
|Совместное использование файла из одного проекта в другой|1. Создайте новый проект.<br />2. Добавьте его в систему управления версиями.<br />3. Закройте решение.<br />4. Создайте второй проект (новое решение).<br />5. Добавьте решение в систему управления версиями.<br />6. Выберите проект.<br />7. Откройте диалоговое окно " **общий доступ** " (**файл**  -> **система управления версиями**  -> **общий доступ**).<br />8. предоставление общего доступа к файлу из ранее добавленного проекта в открытый проект.<br />9. при появлении запроса примите условия **поиска** .|Типичное ожидаемое поведение.|
|Совместное использование файла не входит в проект из системы управления версиями в текущий загруженный проект|1. Создайте новый проект.<br />2. Добавьте решение в систему управления версиями.<br />3. Добавьте файл в систему управления версиями, который не является частью проекта или решения.<br />4. Выберите проект и откройте диалоговое окно " **общий доступ** " (**файл**  -> **система управления версиями**  -> **общий доступ**).<br />5. Выберите файл в диалоговом окне " **общий доступ** ", который не существует в текущем проекте или решении, и предоставьте к нему общий доступ.<br />6. Если будет предложено, примите **проверку** .|Хранилище системы управления версиями выполнило Get, поэтому файл теперь находится в локальном расположении проекта.|
|Совместное использование файлов в одном проекте с другой папкой|1. Выберите пункт **извлечь автоматически** в **меню сервис**  -> **Параметры**  -> **система управления версиями**.<br />2. Создайте новый проект и добавьте его в систему управления версиями.<br />3. Добавьте папку в проект.<br />4. Добавьте файл в папку и верните его в папку.<br />5. Выберите папку.<br />6. Откройте диалоговое окно **общий доступ** (**файл**  -> **система управления версиями**  -> **общий ресурс**).<br />7. Общий доступ к файлу для выбранной папки.|Типичное ожидаемое поведение.<br /><br /> Папка должна быть возвращена с файлом, прежде чем ее можно будет использовать для общего доступа.|
|Предоставление общего доступа к папке в загруженном проекте — рекурсивно|1. Создайте новый проект.<br />2. Добавьте решение в систему управления версиями.<br />3. Выберите проект.<br />4. Откройте диалоговое окно " **общий доступ** " (**файл**  -> **система управления версиями**  -> **общий доступ**).<br />5. Выберите папку.<br />6. Предоставьте доступ к папке рекурсивно в проекте.|Типичное ожидаемое поведение.|
|Совместное использование нескольких файлов из одного проекта в другой|1. Создайте новый проект с несколькими файлами в нем.<br />2. Добавьте решение в систему управления версиями.<br />3. Закройте решение.<br />4. Создайте новый проект в новом решении.<br />5. Добавьте решение в систему управления версиями.<br />6. Выберите проект.<br />7. Откройте диалоговое окно " **общий доступ** " (**файл**  -> **система управления версиями**  -> **общий доступ**).<br />8. Общий доступ к нескольким файлам из ранее созданного проекта к текущему открытому проекту.|Типичное ожидаемое поведение.|

## <a name="see-also"></a>См. также
- [Руководство по тестированию подключаемых модулей системы управления версиями](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)