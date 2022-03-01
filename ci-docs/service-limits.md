---
title: Ліміти послуг у Dynamics 365 Customer Insights
description: Дізнайтеся про граничні значення й обмеження.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483719"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Обмеження послуг в можливостях Customer Insights

У цій статті описуються вбудовані обмеження служби Customer Insights, які призначені для забезпечення надійності та стабільності обслуговування. Будь-які запити щодо внесення змін можна зробити за допомогою [Форуму для ідей](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Аналіз аудиторії

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Обмеження послуг для функціоналу аналізу аудиторій у Dynamics 365 Customer Insights

| Область  | Обмеження  | Примітки |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти та показники | 100 сегментів або показників. | Загальна кількість активних [сегментів](audience-insights/segments.md) і [показників](audience-insights/measures.md) сумарно не може перевищувати 100.  |
| Зв'язки | 20 рівнів глибини зв'язків у шляхах сутностей. | Під час створення [сегментів](audience-insights/segments.md) або [вимірювань](audience-insights/measures.md) за допомогою інтерфейсу конструктора шляхи сутності можуть мати до 20 зав'язків між початковою сутністю та кінцевою.  |


## <a name="engagement-insights"></a>Аналітика взаємодії

### <a name="workspace-and-event-quotas"></a>Квоти робочої області та подій

Аналітичні висновки щодо взаємодії — це високомасштабована програма, яка може підтримувати мільйони подій за секунду. Під час використання загальнодоступної підготовчої версії події мають обмеження на об’єм. Існує також обмеження на кількість робочих областей в організації.

### <a name="engagement-insights-limits"></a>Обмеження аналітичних висновків щодо взаємодії

- Максимальний об’єм подій на робочу область = 100 подій за секунду

- Максимальна кількість робочих областей на організацію = 100

Перевищення максимальної кількості подій може призвести до втрати даних у звітах, створених на основі цих подій. Ви можете [звернутися до служби підтримки](https://go.microsoft.com/fwlink/?linkid=2145734) із запитом на збільшення об’єма до того, як ви перевищите обмеження. Ми допоможемо вам визначити потребу в збільшенні об’єму та надамо підтримку вашому запиту.


[!INCLUDE[footer-include](includes/footer-banner.md)]