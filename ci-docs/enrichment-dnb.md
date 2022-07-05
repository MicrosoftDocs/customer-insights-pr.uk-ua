---
title: Збагачуйте профілі компаній за допомогою Dun &brudstreet (попередній перегляд)
description: Загальні відомості про збагачення третьої сторони Dun &ddstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 51f2e4e46aa25d10502d0feb5ea42eb7d2d637b9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082565"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Збагачуйте профілі компаній за допомогою Dun &brudstreet (попередній перегляд)

Dun &brudstreet надає комерційні дані, аналітику та ідеї для бізнесу. Вона дає змогу клієнтам з уніфікованими профілями клієнтів для компаній збагачувати свої дані. Збагачення включає такі атрибути, як номер DUNS, розмір компанії, місце розташування, галузь тощо.

## <a name="prerequisites"></a>вимоги

- Активна [ліцензія Dun &bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Уніфіковані профілі](customer-profiles.md) клієнтів для компаній.
- Створено проект [Dun &Bradstreet](#set-up-your-dun--bradstreet-project).
- Підключення Dun &bradstreet [налаштовується](connections.md) [адміністратором](#configure-a-connection-for-dun--bradstreet).

## <a name="set-up-your-dun--bradstreet-project"></a>Налаштуйте свій проект «Дан і Бредстріт»

Як ліцензований користувач Dun &bradstreet, ви можете налаштувати проект в [Dun &bdstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. увійдіть [в Dun &ddstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Щоб отримати облікові дані, [відновіть пароль](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Завантажте [наш файл](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) шаблону CSV, який буде використовуватися для зіставлення полів Customer Insights з відповідними полями Dun &bradstreet.

1. Завантажте файл на **кроці завантаження даних** досвіду створення проекту Dun &amp Bradstreet.

1. Виберіть горизонтальні точки під відповідним **джерелом** у новоствореному проекті Dun &amp Bradstreet, щоб побачити доступні варіанти.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Знімок екрана: крапки в проекті Dun &ddstreet.":::

1. Виберіть елемент **Отримати відомості про** S3. Зберігайте цю інформацію в безпечному місці. Він знадобиться вам, щоб [налаштувати з'єднання для збагачення](#configure-a-connection-for-dun--bradstreet) в Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Знімок екрана: вибір інформації s3 у проекті Dun &bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Налаштування з'єднання для Dun &ddstreet

Ви повинні бути адміністратором [Customer](permissions.md#admin) Insights і мати облікові дані від Dun &ddstreet Connect.

1. Виберіть елемент Додати підключення **під час налаштування збагачення або перейдіть до** розділу Підключення **адміністратора** > **та виберіть настроїти** **на плитці Dun &ddstreet.**

1. Введіть ім'я підключення.

1. Надайте дійсні облікові дані Dun &bradstreet та деталі *проекту Dun &bradstreet Регіон, шлях до папки Drop та ім'я* папки Drop. Ви [отримуєте цю інформацію](#set-up-your-dun--bradstreet-project) з проекту Dun &ddstreet.

1. Перегляньте документ [Конфіденційність і відповідність даних](#data-privacy-and-compliance) і надайте згоду з його вмістом способом вибору пункту **Погоджуюся**.

1. Натисніть кнопку **Перевірити**, щоб перевірити конфігурацію, а потім натисніть кнопку **Зберегти**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Сторінка конфігурації з'єднання Dun &bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

Коли ви дозволяєте Dynamics 365 Customer Insights передавати дані в Dun &Bradstreet, ви дозволяєте передавати дані за межі відповідності для Dynamics 365 Customer Insights, включаючи потенційно конфіденційні дані, такі як Персональні дані. Корпорація Майкрософт передаватиме такі дані за вашою інструкцією, але ви несете відповідальність за те, щоб Dun &ddstreet виконували будь-які зобов'язання щодо конфіденційності або безпеки, які ви можете мати. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити використання цієї функції.

## <a name="supported-countries-or-regions"></a>Підтримувані країни або регіони

В даний час ми підтримуємо наступні варіанти країни або регіону: Канада (англійська) або Сполучені Штати (англійська).

## <a name="configure-the-enrichment"></a>Налаштуйте збагачення

1. Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.

1. Виберіть Збагачувати **мої дані** про **дані** компанії для плитки Dun &bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Знімок екрана: плитка Dun &bdstreet.":::

1. Перегляньте огляд і натисніть кнопку **Далі**.

1. Виберіть з'єднання і підтвердіть. Зверніться до адміністратора, якщо він недоступний.

1. Виберіть **Далі**.

1. **Виберіть набір** даних Клієнта та виберіть профіль або сегмент, який ви хочете збагатити даними компанії з Dun &bradstreet. Компанія *Клієнта* збагачує всі ваші профілі клієнтів, тоді як сегмент збагачує лише профілі клієнтів, що містяться в цьому сегменті.

1. Визначте, який тип полів з ваших уніфікованих профілів використовувати для зіставлення даних компанії з Dun &bradstreet. Обов’язковим є принаймні одне з наведених далі полів: **Ім'я та адреса**, **Телефон** або **Ел. пошта**.

1. Виберіть **Далі**

1. Зіставте свої поля з даними компанії з Dun &bradstreet. Потрібно або **номер** DUNS, або **назва поля компанії** та **країна/регіон**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Область відображення полів Dun &bdstreet.":::

1. Виберіть **Далі**, щоб завершити зіставлення полів.

1. **Надайте назву** для збагачення та назву **організації виводу**.

1. Виберіть пункт **Зберегти збагачення** після того, як переглянете доступні вам варіанти вибору.

1. Натисніть кнопку **Виконати**, щоб розпочати процес збагачення, або закрити, щоб повернутися на сторінку **Збагачення**.

## <a name="view-enrichment-results"></a>Переглянути результати збагачення

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Наступні кроки

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
