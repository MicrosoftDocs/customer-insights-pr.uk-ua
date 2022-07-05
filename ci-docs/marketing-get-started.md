---
title: Використання уніфікованих профілів у dynamics 365 Marketing
description: Дізнайтеся, як інтегрувати уніфіковані профілі та сегменти з Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054457"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>Використання уніфікованих профілів клієнтів у Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) підвищує клієнтський досвід, дозволяючи організувати персоналізовані подорожі по всіх точках дотику, щоб зміцнити відносини та заслужити лояльність. Додаток Dynamics 365 Marketing безперебійно працює з Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams та іншими продуктами і дозволяє приймати швидші та кращі рішення, використовуючи потужність даних та штучного інтелекту.

Підключивши дані Customer Insights до маркетингу, ви можете:

- Цільові уніфіковані профілі клієнтів і сегменти. Це дозволяє залучити кожного клієнта, незалежно від місця розташування даних клієнта.
- Базовий динамічний вміст (наприклад, персоналізовані токени) в електронних листах, SMS та push-сповіщеннях про такі заходи, як статус лояльності, дата поновлення підписки, первинний партнер або будь-який інший захід, який ви зафіксували в єдиному профілі Customer Insights.
- Завантажуйте дані з маркетингу в Customer Insights і об'єднуйте їх з даними клієнтів з інших джерел.
- Застосовуйте інструменти для очищення, збагачення та нечіткого підбору даних Customer Insights.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Використовуйте багаті профілі клієнтів у маркетингу в режимі реального часу

Маркетинг у режимі реального часу дозволяє створювати [власні тригери](/dynamics365/marketing/real-time-marketing-custom-triggers), які запускають шляхи клієнтів на основі будь-яких дій клієнтів. Чим більш персоналізованими будуть ваші дані, тим більш актуальними та персоналізованими будуть ваші подорожі. Це те, що робить поєднання маркетингу та розуміння клієнтів таким потужним. Ви можете [уніфікувати дані](data-unification.md) з будь-якого джерела, а потім використовувати їх для підживлення гіперперсоналізованих подорожей клієнтів.

Дізнайтеся більше: [Використовуйте профілі та сегменти Customer Insights у маркетингу в режимі реального часу](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Використовуйте уніфіковані сегменти з вихідними шляхами клієнтів

Customer Insights дозволяє уточнювати дані з багатьох джерел і об'єднувати їх в агреговані сегменти клієнтів. Підключивши [Customer Insights до вихідного маркетингу](export-dynamics365-marketing.md), ці сегменти автоматично з'являться *та* автоматично оновляться в шлях клієнта дизайнера.

Дізнайтеся більше: [Використовуйте сегменти з Dynamics 365 Customer Insights маркетингу Dynamics 365](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Отримуйте дані з власних Azure Data Lake Storage

Ви не обмежуєтеся хмарним сховищем, якщо хочете використовувати дані Customer Insights з маркетингом. Якщо у вас уже є власне Azure Data Lake Storage налаштування, ви можете зв'язатися з Customer Insights, а потім поділитися даними з програмою Marketing так само, як і з хмарним налаштуванням.

Дізнайтеся більше: [Увімкніть обмін даними за допомогою Dataverse власних Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
