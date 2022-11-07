---
title: Сегменти експорту до MoEngage
description: Дізнайтеся, як налаштувати підключення та експортувати в MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725291"
---
# <a name="export-segments-to-moengage-preview"></a>Експорт сегментів в MoEngage (попередній перегляд)

Експортуйте сегменти уніфікованих профілів клієнтів в MoEngage і використовуйте їх для email-маркетингу в MoEngage.

## <a name="prerequisites-for-a-connection"></a>Попередні вимоги для підключення

- [Обліковий запис](https://www.moengage.com/) MoEngage і відповідні облікові дані адміністратора.
- Ключ MoEngage API з налаштувань > API в MoEngage.
- [Налаштовані сегменти](segments.md) в Customer Insights.

## <a name="known-limitations"></a>Відомі обмеження

- Приватне посилання в поєднанні з функцією Принесіть власне сховище (BYOS) не підтримується.
- До 100’000 профілів клієнтів на експорт в MoEngage, що може зайняти до 15 хвилин. Кількість профілів клієнтів, які ви можете експортувати в MoEngage, залежить від вашого контракту з MoEngage.
- Лише сегменти.

## <a name="set-up-connection-to-moengage"></a>Налаштування підключення до MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення** та натисніть **MoEngage**, щоб налаштувати з’єднання.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть свій [ідентифікатор API даних MoEngage та ключ API](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Перегляньте [конфіденційність і відповідність даних і виберіть](connections.md#data-privacy-and-compliance) пункт **Я згоден**.

1. Виберіть "Підключитися **·**", щоб ініціалізувати підключення до MoEngage.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати експорт**.

1. **У полі Підключення для експорту** виберіть підключення з розділу MoEngage. Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. У розділі **Зіставлення даних** у полі **Електронна пошта** виберіть поле, яке відповідає адресі електронної пошти клієнта. Повторіть ті самі кроки для інших необов’язкових полів.

1. Виберіть сегменти, які потрібно експортувати. Ми створимо один або кілька сегментів з такою ж назвою, як і вибрані сегменти в MoEngage в розділі **Сегменти** > **користувацьких сегментів**.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
