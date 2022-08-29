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
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304728"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Експорт сегментів до LinkedIn Ads (підготовча версія)

Експортуйте сегменти уніфікованих профілів клієнтів до LinkedIn Ads, щоб створити зіставлені аудиторії. Використовуйте зіставлені аудиторії для націлювання на компанії та націлювання на контактних осіб.

## <a name="prerequisites"></a>вимоги

- Обліковий [LinkedIn Campaign Manager запис](https://business.linkedin.com/marketing-solutions/ads) і відповідні облікові дані адміністратора.
- [LinkedIn Campaign Manager Ідентифікатор облікового запису](https://www.linkedin.com/help/lms/answer/a424270).
- [Налаштовані сегменти](segments.md) в Customer Insights.
- Експортовані сегменти потребують принаймні одного конкретного поля залежно від того, чи вибрано [націлювання](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) контактів або [націлювання](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) на компанію в LinkedIn. Можливі поля відображаються на кроці **зіставлення** даних під [час настроювання експорту](#configure-an-export).

## <a name="known-limitations"></a>Відомі обмеження

- До 100 000 профілів клієнтів за експорт до Оголошень LinkedIn, заповнення яких може зайняти до 10 хвилин.
- Тільки сегменти. Сегмент повинен містити не менше 300 унікальних профілів.

## <a name="set-up-connection-to-linkedin-ads"></a>Налаштуйте з’єднання з оголошеннями LinkedIn

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати з’єднання** та виберіть **Оголошення** LinkedIn.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Вкажіть ідентифікатор облікового LinkedIn Campaign Manager запису.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Натисніть кнопку **Підключитися**, щоб ініціалізувати підключення.

1. Виберіть **Автентифікація в LinkedIn** і введіть облікові дані адміністратора для LinkedIn Campaign Manager.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть Додати **експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу LinkedIn Ads. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім’я експорту.

1. Виберіть, чи хочете ви експортувати дані для здійснення [націлювання на контактну особу](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) або для [націлювання на компанію](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) на LinkedIn.

1. У розділі **Зіставлення даних**, при націлюванні на контактних осіб виберіть принаймні одне поле, яке відповідає адресі електронної пошти клієнта, ідентифікатору Apple Ad ID чи Google Ad ID, ідентифікатору користувача Google або імені й прізвищу. Якщо вибрати націлювання на компанії, виберіть принаймні одне поле, яке відповідає імені компанії, домену електронної пошти, URL-адресі сторінки LinkedIn, символу біржі або веб-сайту.

1. За бажанням можна додати поля для подальшого визначення експорту. Виберіть **Додати атрибут**, щоб зіставити ці поля.

1. Виберіть сегменти, які потрібно експортувати. Зіставлені аудиторії у LinkedIn Campaign Manager будуть створені автоматично і отримають назви, що відповідають назвам сегментів, вибраних для експорту. В результаті для кожного сегмента буде створено окрему зіставлену аудиторію.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
