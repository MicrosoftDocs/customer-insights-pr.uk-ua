---
title: Експорт даних Customer Insights до HubSpot
description: Дізнайтеся, як налаштувати підключення та експорт у HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588940"
---
# <a name="export-segments-to-hubspot-preview"></a>Експорт сегментів у HubSpot (попередній перегляд)

Експортуйте сегменти уніфікованих профілів клієнтів у HubSpot і використовуйте їх для маркетингу електронною поштою.

## <a name="prerequisites-for-a-connection"></a>Попередні вимоги для підключення

- Обліковий [запис](https://www.hubspot.com/) HubSpot і відповідні облікові дані адміністратора.
- [Ключ](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) API від HubSpot.
- [Налаштовані сегменти](segments.md) в Customer Insights.

## <a name="known-limitations"></a>Відомі обмеження

- До 100’000 профілів клієнтів за експорт до HubSpot, що може зайняти до 15 хвилин. Кількість профілів клієнтів, які ви можете експортувати в HubSpot, залежить і обмежена від вашого контракту з HubSpot.
- Тільки сегменти.

## <a name="set-up-connection-to-hubspot"></a>Налаштування підключення до HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення** та виберіть **HubSpot**, щоб налаштувати з’єднання.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть свої облікові дані HubSpot, коли з’явиться запит.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Виберіть **Підключитися**, щоб ініціалізувати з’єднання з HubSpot.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати експорт**.

1. **У полі Підключення для експорту** виберіть підключення з розділу HubSpot. Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. У розділі **Зіставлення даних** у полі **Електронна пошта** виберіть поле, яке відповідає адресі електронної пошти клієнта. Повторіть ті самі дії для інших необов’язкових полів.

1. Виберіть сегменти, які потрібно експортувати.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
