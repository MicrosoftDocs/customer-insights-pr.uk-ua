---
title: Експорт сегментів в MoEngage
description: Дізнайтеся, як налаштувати підключення та експорт в MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199239"
---
# <a name="export-segments-to-moengage-preview"></a>Експорт сегментів в MoEngage (попередній перегляд)

Експортуйте сегменти уніфікованих профілів клієнтів в MoEngage і використовуйте їх для маркетингу електронною поштою в MoEngage.

## <a name="prerequisites-for-a-connection"></a>Попередні вимоги для підключення

- [Обліковий запис](https://www.moengage.com/) MoEngage та відповідні облікові дані адміністратора.
- Ключ API MoEngage від Налаштування > API в MoEngage.
- [Налаштовані сегменти](segments.md) в Customer Insights.

## <a name="known-limitations"></a>Відомі обмеження

- До 100'000 профілів клієнтів за експорт до MoEngage, що може зайняти до 15 хвилин. Кількість профілів клієнтів, які ви можете експортувати в MoEngage, залежить від вашого контракту з MoEngage.
- Тільки сегменти.

## <a name="set-up-connection-to-moengage"></a>Налаштування підключення до MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення** та виберіть **MoEngage**, щоб налаштувати з'єднання.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть свій [ідентифікатор API даних MoEngage та ключ API](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Виберіть **Підключитися**, щоб ініціалізувати з'єднання з MoEngage.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати експорт**.

1. **У полі Підключення для експорту** виберіть підключення з розділу MoEngage. Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. У розділі **Зіставлення даних** у полі **Електронна пошта** виберіть поле, яке відповідає адресі електронної пошти клієнта. Повторіть ті самі дії для інших необов'язкових полів.

1. Виберіть сегменти, які потрібно експортувати. Ми створимо один або кілька сегментів з такою ж назвою, як і вибрані сегменти в MoEngage в розділі **Сегменти** > **Користувацькі сегменти**.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
