---
title: Експорт сегментів до Microsoft Advertising (підготовча версія)
description: Дізнайтеся, як налаштувати підключення та експорт до Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196557"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Експорт сегментів до Microsoft Advertising (підготовча версія)

Експортуйте сегменти Customer Insights до Microsoft Advertising та створіть аудиторії Customer Match. Використовуйте ці аудиторії для своїх рекламних кампаній.

## <a name="prerequisites"></a>вимоги

- Обліковий [запис](https://ads.microsoft.com/) Microsoft Advertising і відповідні облікові дані адміністратора.
- Microsoft Advertising ID клієнта та ідентифікатор облікового запису. Знайдіть ідентифікатор клієнта (`cid`) та ідентифікатор облікового запису (`aid`) у параметрах URL-адреси під час входу в службу Microsoft Advertising.
- Умови використання Матчу Клієнтів приймаються.
- [Налаштовані сегменти](segments.md) в Customer Insights.
- Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.

## <a name="known-limitations"></a>Відомі обмеження

- До 500 000 профілів клієнтів на експорт до Microsoft Advertising, що може зайняти до 10 хвилин.
- Тільки сегменти.

## <a name="set-up-connection-to-microsoft-advertising"></a>Настроювання підключення до служби Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть елемент **Додати підключення**, а потім – елемент **Microsoft Advertising**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За замовчуванням це будуть адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Введіть код** клієнта з реклами Microsoft.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Натисніть кнопку **Підключитися**, щоб ініціалізувати підключення.

1. Виберіть **Автентифікація в Microsoft Advertising** і введіть облікові дані адміністратора Microsoft Advertising.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть Додати **експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу «Microsoft Advertising». Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім'я експорту.

1. Виберіть сегменти для експорту. Аудиторії Customer Match у Microsoft Advertising створюються автоматично і отримують назви, що відповідають назвам вибраних для експорту сегментів. В результаті для кожного сегмента буде створено окрему аудиторію Customer Match.

1. Уведіть **ідентифікатор клієнта та ідентифікатор облікового запису Microsoft Advertising**.

1. У розділі **Зіставлення даних** у полі **Електронна пошта** виберіть поле, що містить адресу електронної пошти клієнта.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
