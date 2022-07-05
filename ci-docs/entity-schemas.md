---
title: Схеми сутностей у Common Data Model
description: Робота з сутностями в Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 92d37fc0950fefcb5c2a5d26214a469d3693980d
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054779"
---
# <a name="entity-schemas-in-common-data-model"></a>Схеми сутностей у Common Data Model

[Common Data Model](/common-data-model/) — це декларативна специфікація, а також визначення стандартних сутностей, які представляють загальновживані концепції та справи в додатках для ведення бізнесу й підвищення продуктивності. Ця модель також поширюється на експериментальні та аналітичні дані. Common Data Model пропонує чітко визначені, модульні та розширювані бізнес-сутності, такі як Бізнес-партнер, Підрозділ, Інцидент, Контактна особа, Потенційний клієнт, Потенційна угода та Продукт, а також засоби взаємодії з постачальниками, працівниками та клієнтами, такі як справи та угоди про рівень послуг. Будь-які особи можуть використовувати визначення Common Data Model для їхнього розширення та як основу власних проектів, щоб збирати ідеї для конкретного бізнесу.

Це спільна модель даних, яка дає змогу програмам та інтеграторами даних ефективніше співпрацювати, надаючи уніфіковане визначення даних. Common Data Model має багату систему метаданих зі стандартними сутностями, зв'язками, ієрархіями, рисами тощо. Вона походить з програм Dynamics 365 і має відкритий код на GitHub, а також включає понад 260 стандартних сутностей. Велика система внутрішніх і зовнішніх партнерів вносить специфічних для кожної галузі поняття в Common Data Model.

Сьогодні Common Data Model запроваджено в багатьох системах і платформах, включно з потоками даних Power BI і службами даних Azure. Вона уже підтримується в Microsoft Dataverse, Dynamics 365, Power Apps, Power BI і майбутніх службах даних Azure, безпосередньо накопичуючи значення для [Open Data Initiative](https://dynamics.microsoft.com/en-us/open-data-initiative/).

## <a name="customer-insights-entity-schemas"></a>Схеми сутностей Customer Insights

Щоб задати комплексні стандарти щодо відомостей про клієнта та зробити моделі Customer Insights доступними у Common Data Model для розширюваності, ми опублікували перелічені нижче схеми сутностей.

| Сутність | Опис |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Дія, виконана користувачем, яка має експериментальну вартість для бізнесу. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Особа або організація, яка виконала справи або має потенціальну можливість взяти участь у справах. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Визначення ключових показників ефективності, поділене на нуль або більше вимірів (наприклад, Щомісячні активні користувачі, Загальна сума витрат за клієнтом, Середня вартість придбання клієнта) |
|[Сегмент](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Визначає групу учасників зі спільними рисами. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Учасники, які беруть участь у тому або іншому сегменті. |

Для отримання додаткових відомостей див. документацію про [схеми сутностей Customer Insights у Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Перегляд сутностей за допомогою засобу переходу між сутностями Common Data Model

Сутності можна переглянути в [Навігаторі сутності Common Data Model](https://microsoft.github.io/CDM/). Виберіть сутність у розділі Insights "Програма", щоб отримати список сутностей Customer Insights та їх визначення.
> [!div class="mx-imgBorder"]
> ![Засіб переходу між сутностями CDM, у якому відображається сутність CustomerActivity.](media/CDM-entity-navigator.png "Засіб переходу між сутностями CDM, у якому відображається сутність CustomerActivity")


[!INCLUDE [footer-include](includes/footer-banner.md)]
