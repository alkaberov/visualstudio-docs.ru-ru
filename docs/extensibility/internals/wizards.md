---
title: Мастеры | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], providing wizard support
ms.assetid: 59d9a77f-ee80-474b-a14f-90f477ab717b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e3b17d7ef3137c48ddda97e1b2b5bbf0e58cf5bb
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66312840"
---
# <a name="wizards"></a>Мастера
Обычно после создания мастера, вы хотите добавить его в [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] интегрированной среды разработки (IDE), чтобы его смогут использовать другие. Затем откроется мастер добавлена в **Добавление нового проекта** или **Добавление нового элемента** диалоговым окнам. Чтобы увидеть **Добавление нового проекта** или **Добавление нового элемента** диалоговое окно поля, щелкните правой кнопкой мыши в открытом решении **обозревателе решений**, пункты **добавить**, и Нажмите кнопку **новый проект** или **новый элемент**.

 Мастера могут быть реализованы в [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] пользователям выберите из представления дерева доступных значений, при открытии **Добавление нового проекта** диалоговое окно или **Добавление нового элемента** диалоговом окне или при их правой кнопкой мыши элемент в **обозревателе решений**.

 В мастере можно предоставить возможность локализации имя нового проекта или ites и выяснить, значок, который пользователи будут видеть при выборе мастера. Также можно управлять порядком, в котором появляются новые элементы относительно других доступных элементов; элементы не нужно быть упорядочены по алфавиту.

 Можно также указать мастер, начинающий по-разному, на основе пользовательских параметров, которые передаются при открытии мастера.

 В этом разделе рассматриваются файлы, которые реализуют заставить [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **Добавление нового проекта** и **Добавление нового элемента** диалоговым окнам, чтобы получить список мастера среди доступных мастерах и шаблоны и требования, которые должны соответствовать мастера для правильной работы в интегрированной среде разработки.

## <a name="in-this-section"></a>В этом разделе
- [Файлы описания каталога шаблона (VSDIR-файлы)](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)

 Общие сведения о какой шаблон файлы описания каталога и объясняется их работы в интегрированной среде разработки для отображения папок, мастера VSZ-файлы и файлы шаблонов, связанных с проектом в диалоговых окнах.

- [Файл мастера (VSZ-файл)](../../extensibility/internals/wizard-dot-vsz-file.md)

 Описание запуска мастеров в интегрированной среде разработки и перечислены три части VSZ-файле.

- [Интерфейс мастера (IDTWizard)](../../extensibility/internals/wizard-interface-idtwizard.md)

 Описывает `IDTWizard` интерфейс, который должен быть реализован мастеров для работы в интегрированной среде разработки.

- [Контекстные параметры](../../extensibility/internals/context-parameters.md)

 Описание реализации мастеров и что происходит по истечении интегрированной среды разработки контекстных параметров к реализации.

- [Настраиваемые параметры](../../extensibility/internals/custom-parameters.md)

 Объясняется, как использовать настраиваемые параметры для управления ее работой мастера, после запуска мастера.

## <a name="related-sections"></a>Связанные разделы
- [Типы проектов](../../extensibility/internals/project-types.md)

 Ссылки на дополнительные разделы, которые содержат сведения о создании новых типов проектов.

- [Расширение проектов](../../extensibility/extending-projects.md)

 Описывается использование проектов и решений [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] для организации файлов кода и файлов ресурсов, а также реализация системы управления версиями.