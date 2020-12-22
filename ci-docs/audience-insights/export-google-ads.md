---
title: Експорт даних Customer Insights до Google Ads
description: Дізнайтесь, як настроїти підключення до Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568517"
---
# <a name="connector-for-google-ads-preview"></a>З'єднувач для Google Ads (попередній перегляд)

Експорт сегментів уніфікованих профілів клієнтів до списків аудиторій Google Ads та використовуйте їх для рекламування у Google Search, Gmail, YouTube і Google Display Network. 

## <a name="prerequisites"></a>Вимоги

-   Ви маєте [обліковий запис Google Ads](https://ads.google.com/) і відповідні облікові дані адміністратора.
-   У Google Ads наявні аудиторії й відповідні ідентифікатори. Для отримання додаткових відомостей див. [Аудиторії Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Ви маєте [налаштовані сегменти](segments.md)
-   Уніфіковані профілі клієнтів у експортованих сегментах містять поля, що представляють адресу електронної пошти, ім'я та прізвище

## <a name="connect-to-google-ads"></a>Підключення до Google Ads

1. Відкрийте **Адміністрування** > **Призначення експорту**.

1. У розділі **Google Ads** виберіть **Налаштувати**.

1. Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.

1. Введіть свій **[ідентифікатор клієнта Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Введіть свій **[маркер, схвалений розробником Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.

1. Введіть **[ідентифікатор аудиторії Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** і виберіть **З'єднати**, щоб ініціалізувати підключення до Google Ads.

1. Виберіть **Автентифікацію за допомогою Google Ads** і надайте облікові дані Google Ads.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Експорт скріншоту для підключення до Google Ads":::

1. Натисніть **Далі**, щоб налаштувати експорт.

## <a name="configure-the-connector"></a>Настроювання з’єднувача

1. У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта. повторіть ці самі кроки для полів **Ім’я** і **Прізвище**.

1. Виберіть сегменти, які потрібно експортувати. Загалом до Google Ads можна експортувати до 1 000 000 профілів клієнтів.

1. Виберіть **Зберегти**.

## <a name="export-the-data"></a>Експорт даних

Ви можете [експортувати дані вручну](export-destinations.md). Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab). Тепер в Google Ads можна знайти сегменти в розділі [Аудиторія Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Відомі обмеження

- До 1 000 000 профілів на експорт до Google Ads.
- Експорт до Google Ads обмежується сегментами.
- Експортування сегментів загальною кількістю 1 000 000 профілів може тривати до 5 хвилин через обмеження з боку постачальника. 
- Зіставлення в Google Ads може тривати до 48 годин.

## <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Google Ads можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними. Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб Google Ads відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.
