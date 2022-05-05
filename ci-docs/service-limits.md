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
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641787"
---
# <a name="service-limits-in-customer-insights"></a>Обмеження на обслуговування в інсайтах клієнтів

У цій статті описуються вбудовані обмеження служби Customer Insights, які призначені для забезпечення надійності та стабільності обслуговування. Будь-які запити щодо внесення змін можна зробити за допомогою [Форуму для ідей](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Область  | Обмеження  | Примітки |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти, міри та прогнози | 300  | Загальна кількість [сегментів](segments.md), [мір](measures.md) і [прогнозів разом узятих](predictions.md) не може перевищувати 300.  |
| Зв'язки | 20 рівнів глибини зв'язків у шляхах сутностей. | Під час створення [сегментів](segments.md) або [вимірювань](measures.md) за допомогою інтерфейсу конструктора шляхи сутності можуть мати до 20 зав'язків між початковою сутністю та кінцевою.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
