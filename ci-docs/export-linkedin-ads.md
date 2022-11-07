---
title: Експорт сегментів до LinkedIn Ads (підготовча версія)
description: Дізнайтеся, як налаштувати підключення та експорт до LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 06eb915e352ad545f95e96e6108be0f81f43a451
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725333"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Експорт сегментів до LinkedIn Ads (підготовча версія)

Експортуйте сегменти уніфікованих профілів клієнтів до LinkedIn Ads, щоб створити зіставлені аудиторії. Використовуйте зіставлені аудиторії для націлювання на компанії та націлювання на контактних осіб.

## <a name="prerequisites"></a>вимоги

- Обліковий [LinkedIn Campaign Manager запис](https://business.linkedin.com/marketing-solutions/ads) і відповідні облікові дані адміністратора.
- [LinkedIn Campaign Manager Ідентифікатор облікового запису](https://www.linkedin.com/help/lms/answer/a424270).
- [Налаштовані сегменти](segments.md) в Customer Insights.
- Експортованим сегментам потрібно принаймні одне певне поле, залежно від того, чи вибрано [націлювання на контакти, чи націлювання](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting)[компанії](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) на LinkedIn. Можливі поля відображаються на **етапі зіставлення** даних під час [налаштування експорту](#configure-an-export).

## <a name="known-limitations"></a>Відомі обмеження

- Приватне посилання в поєднанні з функцією Принесіть власне сховище (BYOS) не підтримується.
- До 100 000 профілів клієнтів на експорт в LinkedIn Ads, що може зайняти до 10 хвилин.
- Лише сегменти. Сегмент повинен містити не менше 300 унікальних профілів.

## <a name="set-up-connection-to-linkedin-ads"></a>Налаштуйте підключення до оголошень LinkedIn

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення** та виберіть Оголошення **LinkedIn**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Вкажіть свій LinkedIn Campaign Manager ідентифікатор облікового запису.

1. Перегляньте [конфіденційність і відповідність даних і виберіть](connections.md#data-privacy-and-compliance) пункт **Я згоден**.

1. Натисніть кнопку **Підключитися**, щоб ініціалізувати підключення.

1. Виберіть **Автентифікація в LinkedIn** і введіть облікові дані адміністратора для LinkedIn Campaign Manager.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть **Додати експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу LinkedIn Ads. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім’я експорту.

1. Виберіть, чи хочете ви експортувати дані для здійснення [націлювання на контактну особу](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) або для [націлювання на компанію](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) на LinkedIn.

1. У розділі **Зіставлення даних**, при націлюванні на контактних осіб виберіть принаймні одне поле, яке відповідає адресі електронної пошти клієнта, ідентифікатору Apple Ad ID чи Google Ad ID, ідентифікатору користувача Google або імені й прізвищу. Якщо вибрати націлювання на компанії, виберіть принаймні одне поле, яке відповідає імені компанії, домену електронної пошти, URL-адресі сторінки LinkedIn, символу біржі або веб-сайту.

1. За бажанням додайте поля, щоб додатково визначити експорт. Виберіть **Додати атрибут**, щоб зіставити ці поля.

1. Виберіть сегменти, які потрібно експортувати. Зіставлені аудиторії у LinkedIn Campaign Manager будуть створені автоматично і отримають назви, що відповідають назвам сегментів, вибраних для експорту. В результаті для кожного сегмента буде створено окрему зіставлену аудиторію.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
