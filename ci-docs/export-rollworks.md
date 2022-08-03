---
title: Експорт сегментів до RollWorks (підготовча версія)
description: Дізнайтеся, як налаштувати підключення та експорт до RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e13aeca4ee5309f85e7de2986cd1a2ba5d2992fb
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195637"
---
# <a name="export-segments-to-rollworks-preview"></a>Експорт сегментів до RollWorks (підготовча версія)

Експортуйте сегменти, що складаються з уніфікованих профілів клієнтів, до RollWorks і використовуйте їх для реклами.

## <a name="prerequisites"></a>вимоги

- Обліковий [запис](https://www.rollworks.com/) RollWorks і відповідні облікові дані адміністратора.
- [Код рекламодавця RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Налаштовані сегменти](segments.md) в Customer Insights.
- Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.

## <a name="known-limitations"></a>Відомі обмеження

- До 250 000 профілів клієнтів за експорт до RollWorks, що може зайняти до 10 хвилин. Кількість профілів клієнтів, які можна експортувати в RollWorks, залежить від вашого контракту з RollWorks.
- Тільки сегменти.

## <a name="set-up-connection-to-rollworks"></a>Налаштування підключення до RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть додати **підключення** та виберіть **RollWorks**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення.  За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Натисніть кнопку **Підключитися**, щоб ініціалізувати підключення.

1. Виберіть **Автентифікація за допомогою RollWorks** і введіть облікові дані адміністратора для RollWorks.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть Додати **експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу RollWorks. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім'я експорту.

1. Введіть свій **ідентифікатор** рекламодавця RollWorks.

1. У розділі **Зіставлення даних** у полі **Електронна пошта** виберіть поле, яке відповідає адресі електронної пошти клієнта.

1. Виберіть сегменти, які потрібно експортувати.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
