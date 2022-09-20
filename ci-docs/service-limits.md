---
title: Обмеження на обслуговування в Customer Insights
description: Зрозумійте обмеження та обмеження в сервісі Customer Insights SaaS.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c3863b1a72fd92ddc87755699feda11371ec9214
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463244"
---
# <a name="service-limits-in-customer-insights"></a>Обмеження на обслуговування в Customer Insights

 Customer Insights має вбудовані ліміти, призначені для забезпечення надійності та стабільності сервісу. Будь-які запити щодо внесення змін можна зробити за допомогою [Форуму для ідей](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Область  | Обмеження  | Примітки |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Сегменти, міри та прогнози | 300  | Загальна кількість [сегментів](segments.md), [мір](measures.md) і [прогнозів разом узятих](predictions-overview.md) не може перевищувати 300.  |
| Зв'язки | 20 рівнів глибини зв'язків у шляхах сутностей. | Під час створення [сегментів](segments.md) або [вимірювань](measures.md) за допомогою інтерфейсу конструктора шляхи сутності можуть мати до 20 зав'язків між початковою сутністю та кінцевою.  |
|Приймання даних| Одночасні оцінки джерел Power Query даних обмежені. | Customer Insights має такі ж [обмеження оновлення, як і Потоки даних у PowerBI.com](/power-query/power-query-online-limits#refresh-limits). |

## <a name="fair-scheduling-of-jobs"></a>Чесне планування робочих місць

Customer Insights – це служба SaaS, яка використовує спільні ресурси Azure. Клієнти, як правило, мають навантаження різної інтенсивності та за різними графіками. Щоб забезпечити справедливий доступ до базових ресурсів, ми гарантуємо, що системні процеси виконуються в справедливому порядку. Прикладами системних процесів є завдання, пов’язані з уніфікацією даних, оновленням сегментів або обчисленням міри. Чесне планування захищає вас від черги за ресурсами, якщо є сплеск запитаних вакансій. У той же час Customer Insights не гарантує, що всі вакансії, на які ви стоїте в черзі, обробляються паралельно.

[!INCLUDE [footer-include](includes/footer-banner.md)]
