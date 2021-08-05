---
title: Обмеження послуг
description: Дізнайтеся про граничні значення й обмеження.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604394"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Обмеження послуг для функціоналу аналізу аудиторій у Dynamics 365 Customer Insights

У цій статті описуються вбудовані обмеження служби Customer Insights, які призначені для забезпечення надійності та стабільності обслуговування. Будь-які запити щодо внесення змін можна зробити за допомогою [Форуму для ідей](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Область  | Обмеження  | Примітки |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти та показники | 100 сегментів або показників. | Загальна кількість активних [сегментів](segments.md) і [показників](measures.md) сумарно не може перевищувати 100.  |
| Зв'язки | 20 рівнів глибини зв'язків у шляхах сутностей. | Під час створення [сегментів](segments.md) або [вимірювань](measures.md) за допомогою інтерфейсу конструктора шляхи сутності можуть мати до 20 зав'язків між початковою сутністю та кінцевою.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]