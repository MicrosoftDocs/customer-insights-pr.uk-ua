---
title: Збагачення профілів компанії за допомогою Dun & Bradstreet
description: Загальна інформація про збагачення третьої сторони Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953916"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Збагачення профілів компаній за допомогою Dun & Bradstreet (Preview)

Dun & Bradstreet надає комерційні дані, аналітику та статистику для бізнесу. Вона дає змогу клієнтам з уніфікованими профілями клієнтів для компаній збагачувати свої дані. Збагачення включає такі атрибути, як номер DUNS, розмір компанії, місце розташування, промисловість тощо.

## <a name="prerequisites"></a>вимоги

- Активна [ліцензія Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Уніфіковані профілі](customer-profiles.md) клієнтів для компаній.
- Створюється проект [Dun & Bradstreet](#set-up-your-dun--bradstreet-project).
- З'єднання [Dun & Bradstreet](connections.md) налаштовано [адміністратором](#configure-a-connection-for-dun--bradstreet).

## <a name="set-up-your-dun--bradstreet-project"></a>Налаштуйте свій проект Dun & Bradstreet

Як ліцензований користувач Dun & Bradstreet, ви можете створити проект в [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. увійдіть в [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Щоб отримати облікові дані, [відновіть пароль](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Завантажте [наш файл](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) шаблону CSV, який буде використано для зіставлення полів «Статистика клієнтів» з відповідними полями Dun & Bradstreet.

1. Завантажте файл на **кроці завантаження даних** досвіду створення проекту Dun & Bradstreet.

1. Виберіть горизонтальні точки під відповідним **джерелом** у новоствореному проекті Dun & Bradstreet, щоб переглянути доступні параметри.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Скріншот точок у проекті Dun & Bradstreet.":::

1. Виберіть " **Отримати відомості S3"**. Зберігайте цю інформацію в безпечному місці. Вам знадобиться це, щоб [налаштувати з'єднання для збагачення](#configure-a-connection-for-dun--bradstreet) в Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Знімок екрана: вибір інформації про s3 у проекті Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Настроювання з'єднання для Dun & Bradstreet

Ви повинні бути адміністратором [у](permissions.md#admin) службі статистики клієнтів і мати облікові дані від Dun & Bradstreet Connect.

1. Виберіть пункт **Додати підключення** під час налаштування збагачення або перейдіть до розділу **Підключення** > **адміністратора** та виберіть **налаштувати** на плитці Dun & Bradstreet.

1. Введіть ім'я підключення.

1. Надайте дійсні облікові дані Dun & Bradstreet та відомості *про проект Dun & Bradstreet Регіон, Шлях до папки Drop та назву* папки Drop. Ви [отримуєте цю інформацію](#set-up-your-dun--bradstreet-project) з проекту Dun & Bradstreet.

1. Перегляньте документ [Конфіденційність і відповідність даних](#data-privacy-and-compliance) і надайте згоду з його вмістом способом вибору пункту **Погоджуюся**.

1. Натисніть кнопку **Перевірити**, щоб перевірити конфігурацію, а потім натисніть кнопку **Зберегти**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Сторінка конфігурації з'єднання Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

Коли ви дозволяєте Dynamics 365 Customer Insights передавати дані в Dun & Bradstreet, ви дозволяєте передавати дані за межі відповідності, Dynamics 365 Customer Insights включаючи потенційно конфіденційні дані, такі як Персональні дані. Корпорація Майкрософт передаватиме такі дані за вашими вказівками, але ви несете відповідальність за те, щоб Dun & Bradstreet відповідав будь-яким зобов'язанням щодо конфіденційності або безпеки, які ви можете мати. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити використання цієї функції.

## <a name="supported-countries-or-regions"></a>Підтримувані країни або регіони

В даний час ми підтримуємо наступні варіанти країни або регіону: Канада (англійська) або Сполучені Штати (англійська).

## <a name="configure-the-enrichment"></a>Налаштуйте збагачення

1. Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.

1. Виберіть Збагатити **мої дані** про **дані** компанії для плитки Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Знімок екрана: плитка Dun & Bradstreet.":::

1. Перегляньте огляд і натисніть кнопку **Далі**.

1. Виберіть з'єднання та підтвердьте. Зверніться до адміністратора, якщо він недоступний.

1. Виберіть **Далі**.

1. **Виберіть набір** даних Клієнта та виберіть профіль або сегмент, який ви хочете збагатити даними компанії з Dun & Bradstreet. Організація *Клієнта* збагачує всі ваші профілі клієнтів, тоді як сегмент збагачує лише профілі клієнтів, що містяться в цьому сегменті.

1. Визначте тип полів з ваших уніфікованих профілів, які слід використовувати для зіставлення даних компанії з Dun & Bradstreet. Обов’язковим є принаймні одне з наведених далі полів: **Ім'я та адреса**, **Телефон** або **Ел. пошта**.

1. Виберіть **Далі**

1. Зіставте свої поля з даними компанії з Dun & Bradstreet. Потрібно або **номер** DUNS, або **назва поля компанії** та **країна/регіон**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Область відображення полів Dun & Bradstreet.":::

1. Виберіть **Далі**, щоб завершити зіставлення полів.

1. Укажіть ім'я **для** збагачення та ім'я **вихідної** сутності.

1. Виберіть пункт **Зберегти збагачення** після того, як переглянете доступні вам варіанти вибору.

1. Натисніть кнопку **Виконати,** щоб розпочати процес збагачення, або близько, щоб повернутися до **сторінки "Збагачення** ".

## <a name="enrichment-results"></a>Результати збагачення

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Наступні кроки

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
