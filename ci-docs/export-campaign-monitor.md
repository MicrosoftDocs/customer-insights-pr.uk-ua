---
title: Експорт сегментів до Campaign Monitor (підготовча версія)
description: Дізнайтеся, як налаштувати підключення та експорт до Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 82303c7bcb269ee68419c9639ee743e13451f273
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724709"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Експорт сегментів до Campaign Monitor (підготовча версія)

Експортуйте сегменти, що складаються з уніфікованих профілів клієнтів, до Campaign Monitor і використовуйте їх для маркетингової діяльності.

## <a name="prerequisites"></a>вимоги

- Обліковий [запис](https://www.campaignmonitor.com/) моніторингу кампанії та відповідні облікові дані адміністратора.
- ідентифікатор списку моніторів [кампанії](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Згенерований [ключ](https://www.campaignmonitor.com/api/getting-started/) API з **налаштувань** облікового запису в Campaign Monitor для отримання ідентифікатора списку API.
- [Налаштовані сегменти](segments.md) в Customer Insights.
- Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.

## <a name="known-limitations"></a>Відомі обмеження

- Приватне посилання в поєднанні з функцією Принесіть власне сховище (BYOS) не підтримується.
- До 1 мільйона профілів клієнтів на експорт до Campaign Monitor, що може зайняти до 20 хвилин. Кількість профілів клієнтів, які можна експортувати в Campaign Monitor, залежить від вашого контракту з Campaign Monitor.
- Лише сегменти.

## <a name="set-up-connection-to-campaign-monitor"></a>Налаштуйте підключення до Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення** та виберіть **Монітор** кампанії.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Перегляньте [конфіденційність і відповідність даних і виберіть](connections.md#data-privacy-and-compliance) пункт **Я згоден**.

1. Виберіть **Підключити**, щоб ініціалізувати підключення до Campaign Monitor.

1. Виберіть **Автентифікація за допомогою Campaign Monitor** і введіть облікові дані адміністратора Campaign Monitor.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу «Campaign Monitor». Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім’я експорту.

1. Введіть ідентифікатор **списку** моніторингу кампанії.

1. У розділі **Зіставлення даних** у полі **Електронна пошта** виберіть поле, яке відповідає адресі електронної пошти клієнта. Це необхідно для експорту сегментів до Campaign Monitor.

1. Виберіть сегменти, які потрібно експортувати.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
