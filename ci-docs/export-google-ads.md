---
title: Експорт сегментів до Google Ads (підготовча версія)
description: Дізнайтеся, як налаштувати підключення та експорт до Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196603"
---
# <a name="export-segments-to-google-ads-preview"></a>Експорт сегментів до Google Ads (підготовча версія)

Експортуйте сегменти єдиних профілів клієнтів до списку аудиторій Google Ads і використовуйте їх для реклами в Пошуку Google, Gmail, YouTube і медійній мережі Google.

## <a name="prerequisites"></a>вимоги

- Обліковий [запис](https://ads.google.com/) Google Ads і відповідні облікові дані адміністратора.
- Ідентифікатор [клієнта Google Ads](https://support.google.com/google-ads/answer/1704344).
- Виконуються вимоги [Політики](https://support.google.com/adspolicy/answer/6299717) відповідності клієнтів.
- Виконуються вимоги [розмірів списків](https://support.google.com/google-ads/answer/7558048) ремаркетингу.
- [Налаштовані сегменти](segments.md).
- Уніфіковані профілі клієнтів в експортованих сегментах містять поля, що представляють адресу електронної пошти, телефон, ідентифікатор мобільного рекламодавця, ідентифікатор стороннього користувача або адресу.

## <a name="known-limitations"></a>Відомі обмеження

- Експортуйте до Google Ads понад 1 мільйон профілів клієнтів для експорту, виконання яких може зайняти до 30 хвилин через обмеження з боку постачальника.
- Тільки сегменти.
- Матч у Google Ads може тривати до 48 годин.

## <a name="set-up-connection-to-google-ads"></a>Налаштування підключення до Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть елемент **Додати з'єднання**, а потім – **Google Ads**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть свій ідентифікатор клієнта Google Ads.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Виберіть **Автентифікацію за допомогою Google Ads** і надайте облікові дані Google Ads.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть Додати **експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу Google Ads. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім'я експорту.

1. Виберіть, чи використовувати наявну аудиторію, чи створити нову.
   - Щоб оновити наявну аудиторію Google Ads, введіть свій [ідентифікатор](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns) аудиторії Google Ads.
   - Щоб створити нову аудиторію, залиште поле Ідентифікатор аудиторії Google порожнім. Customer Insights автоматично створить нову аудиторію у вашому обліковому записі Google Ads і використовуватиме назву експортованого сегмента.

1. **У розділі Зіставлення** даних виберіть одне або кілька полів даних для експорту та виберіть поле, яке представляє відповідні поля даних, у Customer Insights.

1. Виберіть сегменти, які потрібно експортувати.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
