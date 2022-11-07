---
title: Експортуйте дані Customer Insights до HubSpot
description: Дізнайтеся, як налаштувати підключення та експортувати в HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725379"
---
# <a name="export-segments-to-hubspot-preview"></a>Експорт сегментів до HubSpot (попередній перегляд)

Експортуйте сегменти уніфікованих профілів клієнтів у HubSpot і використовуйте їх для маркетингу електронною поштою.

## <a name="prerequisites-for-a-connection"></a>Попередні вимоги для підключення

- Обліковий [запис](https://www.hubspot.com/) HubSpot і відповідні облікові дані адміністратора.
- [Ключ](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) API від HubSpot.
- [Налаштовані сегменти](segments.md) в Customer Insights.

## <a name="known-limitations"></a>Відомі обмеження

- Приватне посилання в поєднанні з функцією Принесіть власне сховище (BYOS) не підтримується.
- До 100’000 профілів клієнтів на експорт до HubSpot, що може зайняти до 15 хвилин. Кількість профілів клієнтів, які ви можете експортувати в HubSpot, залежить і обмежується вашим контрактом з HubSpot.
- Лише сегменти.

## <a name="set-up-connection-to-hubspot"></a>Настроювання підключення до HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення та виберіть** HubSpot **, щоб налаштувати підключення**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть облікові дані HubSpot, коли з’явиться відповідний запит.

1. Перегляньте [конфіденційність і відповідність даних і виберіть](connections.md#data-privacy-and-compliance) пункт **Я згоден**.

1. Виберіть **«Підключитися** », щоб ініціалізувати підключення до HubSpot.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати експорт**.

1. **У полі Підключення для експорту** виберіть підключення з розділу HubSpot. Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. У розділі **Зіставлення даних** у полі **Електронна пошта** виберіть поле, яке відповідає адресі електронної пошти клієнта. Повторіть ті самі кроки для інших необов’язкових полів.

1. Виберіть сегменти, які потрібно експортувати.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
