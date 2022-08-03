---
title: Експорт сегментів до DotDigital (підготовча версія)
description: Дізнайтеся, як налаштувати підключення та експорт до DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196097"
---
# <a name="export-segments-to-dotdigital-preview"></a>Експорт сегментів до DotDigital (підготовча версія)

Експорт сегментів уніфікованих профілів клієнтів до адресних книг DotDigital і використання їх для кампаній, маркетингових повідомлень і створення сегментів клієнтів за допомогою DotDigital.

## <a name="prerequisites"></a>вимоги

- Обліковий [запис](https://dotdigital.com/) DotDigital і [користувач API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Ідентифікатор DotDigital з нової [або наявної](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) адресної книги в програмі DotDigital. ІДЕНТИФІКАТОР можна знайти в URL-адресі, якщо вибрати та відкрити адресну книгу.
- [Налаштовані сегменти](segments.md) в Customer Insights.
- Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.

## <a name="known-limitations"></a>Відомі обмеження

- До 1 мільйона профілів клієнтів на експорт до DotDigital, заповнення яких може зайняти до трьох годин через обмеження з боку постачальника. Кількість профілів клієнтів, які ви можете експортувати в DotDigital, залежить від вашого контракту з DotDigital.
- Тільки сегменти.

## <a name="set-up-connection-to-dotdigital"></a>Налаштування підключення до DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення** та виберіть **пункт DotDigital**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть ваше **ім’я користувача API DotDigital та пароль**.

1. Введіть ідентифікатор **адресної** книги DotDigital.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Натисніть кнопку **Підключитися**, щоб ініціалізувати підключення.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть Додати **експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу DotDigital. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім'я експорту.

1. У розділі **Зіставлення даних** у полі **Електронна пошта** виберіть поле, яке відповідає адресі електронної пошти клієнта.

1. За потреби експортуйте **ім'я**, **прізвище**, **повне ім'я**, **стать** і **поштовий індекс**.

1. Виберіть сегменти, які потрібно експортувати.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

У dotDigital знайдіть свої сегменти в [адресних книгах](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) DotDigital.

[!INCLUDE [footer-include](includes/footer-banner.md)]
