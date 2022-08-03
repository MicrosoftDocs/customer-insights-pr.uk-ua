---
title: Збагачуйте профілі компаній за допомогою Dun & Bradstreet (попередній перегляд)
description: Загальна інформація про стороннє збагачення Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 71b35e4295e19c13edadc6548ac79715555e8183
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196051"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Збагачуйте профілі компаній за допомогою Dun & Bradstreet (попередній перегляд)

Dun & Bradstreet надає комерційні дані, аналітику та статистику для бізнесу. Вона дає змогу клієнтам з уніфікованими профілями клієнтів для компаній збагачувати свої дані. Збагачення включають такі атрибути, як номер DUNS, розмір компанії, місцезнаходження, галузь тощо.

## <a name="prerequisites"></a>вимоги

- Активна [ліцензія Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Уніфіковані профілі](customer-profiles.md) клієнтів для компаній.
- Створено проект [Dun & Bradstreet](#set-up-your-dun--bradstreet-project).
- З'єднання [Dun & Bradstreet](connections.md) налаштовується [адміністратором](#configure-a-connection-for-dun--bradstreet).

## <a name="set-up-your-dun--bradstreet-project"></a>Налаштуйте свій проект Dun & Bradstreet

Як ліцензований користувач Dun & Bradstreet, ви можете налаштувати проект в [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. увійдіть [в Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Щоб отримати облікові дані, [відновіть пароль](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Завантажте [наш файл](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) шаблону CSV, який буде використовуватися для зіставлення полів Customer Insights з відповідними полями Dun & Bradstreet.

1. Завантажте файл на кроці **Завантаження даних** досвіду створення проекту Dun & Bradstreet.

1. Виберіть горизонтальні точки під відповідним **джерелом** у новоствореному проекті Dun & Bradstreet, щоб побачити доступні варіанти.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Знімок екрана: крапки в проекті Dun & Bradstreet.":::

1. Виберіть елемент **Отримати відомості про** S3. Зберігайте цю інформацію в надійному місці. Він знадобиться вам, щоб [налаштувати з'єднання для збагачення](#configure-a-connection-for-dun--bradstreet) в Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Знімок екрана: вибір інформації s3 у проекті Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Налаштування з'єднання для Dun & Bradstreet

Ви повинні бути адміністратором [Customer](permissions.md#admin) Insights і мати облікові дані від Dun & Bradstreet Connect.

1. Виберіть Додати з'єднання **під час налаштування збагачення або перейдіть до** Підключення **адміністратора** > **та виберіть** Налаштувати **на плитці Dun & Bradstreet.**

1. Введіть ім'я підключення.

1. Надайте дійсні облікові дані Dun & Bradstreet та деталі *проекту Dun & Bradstreet регіон, шлях до папки та ім'я* папки Drop. Цю [інформацію](#set-up-your-dun--bradstreet-project) ви отримуєте від проекту Dun & Bradstreet.

1. Перегляньте документ [Конфіденційність і відповідність даних](#data-privacy-and-compliance) і надайте згоду з його вмістом способом вибору пункту **Погоджуюся**.

1. Натисніть кнопку **Перевірити**, щоб перевірити конфігурацію, а потім натисніть кнопку **Зберегти**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Сторінка конфігурації з'єднання Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

Коли ви дозволяєте Dynamics 365 Customer Insights передавати дані в Dun & Bradstreet, ви дозволяєте передавати дані за межі відповідності для Dynamics 365 Customer Insights, включаючи потенційно конфіденційні дані, такі як Персональні дані. Корпорація Майкрософт передаватиме такі дані за вашою вказівкою, але ви несете відповідальність за те, щоб Dun & Bradstreet виконували будь-які зобов'язання щодо конфіденційності та безпеки, які ви можете мати. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити використання цієї функції.

## <a name="supported-countries-or-regions"></a>Підтримувані країни або регіони

В даний час ми підтримуємо наступні варіанти країни або регіону: Канада (англійська) або Сполучені Штати (англійська).

## <a name="configure-the-enrichment"></a>Налаштуйте збагачення

1. Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.

1. Виберіть елемент **Збагатити мої дані** на **даних** компанії для плитки Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Знімок екрана: плитка Dun & Bradstreet.":::

1. Перегляньте огляд і натисніть кнопку **Далі**.

1. Виберіть підключення і підтвердіть. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Виберіть **Далі**.

1. **Виберіть набір** даних для клієнтів і виберіть профіль або сегмент, який ви хочете збагатити даними компанії з Dun & Bradstreet. Організація *клієнта* збагачує всі ваші профілі клієнтів, тоді як сегмент збагачує лише профілі клієнтів, що містяться в цьому сегменті.

1. Визначте, який тип полів з ваших уніфікованих профілів використовувати для зіставлення даних компанії з Dun & Bradstreet. Обов’язковим є принаймні одне з наведених далі полів: **Ім'я та адреса**, **Телефон** або **Ел. пошта**.

1. Виберіть **Далі**

1. Зіставте свої поля з даними компанії з Dun & Bradstreet. Потрібно або **номер** DUNS, або **назва поля компанії** та **країна/регіон**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Область відображення полів Dun & Bradstreet.":::

1. Виберіть **Далі**, щоб завершити зіставлення полів.

1. Вкажіть ім'я **для** збагачення та ім'я **сутності виводу**.

1. Виберіть пункт **Зберегти збагачення** після того, як переглянете доступні вам варіанти вибору.

1. Натисніть кнопку **Виконати**, щоб розпочати процес збагачення, або близько, щоб повернутися на сторінку **Збагачення**.

## <a name="view-enrichment-results"></a>Переглянути результати збагачення

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Наступні кроки

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
