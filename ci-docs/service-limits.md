---
title: Ліміти послуг у Dynamics 365 Customer Insights
description: Дізнайтеся про граничні значення й обмеження.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350432"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Обмеження послуг в можливостях Customer Insights

У цій статті описуються вбудовані обмеження служби Customer Insights, які призначені для забезпечення надійності та стабільності обслуговування. Будь-які запити щодо внесення змін можна зробити за допомогою [Форуму для ідей](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Audience insights

| Область  | Обмеження  | Примітки |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти, заходи та прогнози | 300  | Загальна кількість [сегментів](audience-insights/segments.md), [заходів](audience-insights/measures.md) і [прогнозів разом узятих](audience-insights/predictions.md) не може перевищувати 300.  |
| Зв'язки | 20 рівнів глибини зв'язків у шляхах сутностей. | Під час створення [сегментів](audience-insights/segments.md) або [вимірювань](audience-insights/measures.md) за допомогою інтерфейсу конструктора шляхи сутності можуть мати до 20 зав'язків між початковою сутністю та кінцевою.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
