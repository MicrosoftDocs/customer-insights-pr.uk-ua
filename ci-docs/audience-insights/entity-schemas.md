---
title: Схеми сутностей Customer Insights у Common Data Model
description: Робота з сутностями в Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269309"
---
# <a name="entity-schemas-in-common-data-model"></a>Схеми сутностей у Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) — це декларативна специфікація, а також визначення стандартних сутностей, які представляють загальновживані концепції та справи в додатках для ведення бізнесу й підвищення продуктивності. Ця модель також поширюється на експериментальні та аналітичні дані. Common Data Model пропонує чітко визначені, модульні та розширювані бізнес-сутності, такі як Бізнес-партнер, Підрозділ, Інцидент, Контактна особа, Потенційний клієнт, Потенційна угода та Продукт, а також засоби взаємодії з постачальниками, працівниками та клієнтами, такі як справи та угоди про рівень послуг. Будь-які особи можуть використовувати визначення Common Data Model для їхнього розширення та як основу власних проектів, щоб збирати ідеї для конкретного бізнесу.

Це спільна модель даних, яка дає змогу програмам та інтеграторами даних ефективніше співпрацювати, надаючи уніфіковане визначення даних. Common Data Model має багату систему метаданих зі стандартними сутностями, зв'язками, ієрархіями, рисами тощо. Вона походить з програм Dynamics 365 і має відкритий код на GitHub, а також включає понад 260 стандартних сутностей. Велика система внутрішніх і зовнішніх партнерів вносить специфічних для кожної галузі поняття в Common Data Model.

Багато систем і платформ реалізують модель Common Data Model, зокрема потоки даних Power BI та служби даних Azure. Вона вже підтримується в Common Data Service, Dynamics 365, Power Apps, Power BI і службах даних Azure, що невдовзі вийдуть, безпосередньо забезпечуючи додану вартість у рамках [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Схеми сутностей Customer Insights

Щоб задати комплексні стандарти щодо відомостей про клієнта та зробити моделі Customer Insights доступними у Common Data Model для розширюваності, ми опублікували перелічені нижче схеми сутностей.

| Сутність | Опис |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Дія, виконана користувачем, яка має експериментальну вартість для бізнесу. |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Особа або організація, яка виконала справи або має потенціальну можливість взяти участь у справах. |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Визначення ключових показників ефективності, поділене на нуль або більше вимірів (наприклад, Щомісячні активні користувачі, Загальна сума витрат за клієнтом, Середня вартість придбання клієнта) |
|[Сегмент](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Визначає групу учасників зі спільними рисами. |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Учасники, які беруть участь у тому або іншому сегменті. |

Для отримання додаткових відомостей див. документацію про [схеми сутностей Customer Insights у Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Перегляд сутностей за допомогою засобу переходу між сутностями Common Data Model

Сутності можна переглянути в [Навігаторі сутності Common Data Model](https://microsoft.github.io/CDM/). Виберіть кнопку **Завантажити з GitHub!** і перейдіть до розділу **foundationCommon** > **crmCommon** > **рішення** > **customerInsights**, де можна знайти список сутностей Customer Insights та їхні визначення.
> [!div class="mx-imgBorder"]
> ![Засіб переходу між сутностями CDM, у якому відображається сутність CustomerActivity](media/CDM-entity-navigator.png "Засіб переходу між сутностями CDM, у якому відображається сутність CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]