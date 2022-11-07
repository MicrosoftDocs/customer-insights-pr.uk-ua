---
title: Експорт сегментів в ActiveCampaign
description: Дізнайтеся про те, як налаштувати підключення та експортувати дані до ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725425"
---
# <a name="export-segments-to-activecampaign-preview"></a>Експортуйте сегменти до ActiveCampaign (підготовча версія)

Експортуйте сегменти єдиних профілів клієнтів до ActiveCampaign і використовуйте їх для маркетингової діяльності.

## <a name="prerequisites"></a>вимоги

- Обліковий [запис](https://www.activecampaign.com/) ActiveCampaign і відповідні облікові дані адміністратора.
- Ідентифікатор [списку ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- Ключ [API](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) ActiveCampaign та ім’я хоста кінцевої точки REST.
- [Налаштовані сегменти](segments.md) в Customer Insights.
- Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.

## <a name="known-limitations"></a>Відомі обмеження

- Приватне посилання в поєднанні з функцією Принесіть власне сховище (BYOS) не підтримується.
- До 1 мільйона профілів клієнтів на експорт в ActiveCampaign, що може зайняти до 90 хвилин. Кількість профілів клієнтів, які можна експортувати в ActiveCampaign, визначається умовами сервісного договору з ActiveCampaign.
- Лише сегменти.

## <a name="set-up-connection-to-activecampaign"></a>Налаштуйте підключення до ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення** та виберіть **ActiveCampaign**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть ключ API ActiveCampaign API та ім’я хоста кінцевої точки REST. Ім'я хоста кінцевої точки REST — це лише ім’я хоста, без https://.

1. Перегляньте [конфіденційність і відповідність даних і виберіть](connections.md#data-privacy-and-compliance) пункт **Я згоден**.

1. Натисніть кнопку **Підключитися**, щоб ініціалізувати підключення.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть **Додати експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу ActiveCampaign. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім’я експорту.

1. Введіть ідентифікатор списку **ActiveCampaign**.

1. У розділі **Зіставлення даних** у полі **Електронна пошта** виберіть поле, яке відповідає адресі електронної пошти клієнта.

1. За бажанням експортуйте **ім’я**, **прізвище** та **телефон**, щоб створити більш персоналізовані електронні листи. Виберіть **Додати атрибут**, щоб зіставити ці поля.

1. Виберіть сегменти, які потрібно експортувати.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
