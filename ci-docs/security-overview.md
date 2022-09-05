---
title: Налаштування параметрів захисту
description: Дізнайтеся про параметри безпеки в Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387283"
---
# <a name="configure-security-settings"></a>Налаштування параметрів захисту

Керуйте ключами API, отримуйте доступ до даних клієнтів і налаштовуйте приватне посилання Azure.

## <a name="manage-api-keys"></a>Керування ключами API

Переглядайте ключі та керуйте ними, щоб використовувати [API](apis.md) Customer Insights з даними у вашому середовищі.

1. Перейдіть до **Безпека** > **адміністратора** та виберіть вкладку **API**.

1. Якщо доступ API до середовища не був налаштований, виберіть **Увімкнути**. Або, щоб заблокувати доступ API до середовища, виберіть **Вимкнути** та підтвердити.

1. Керуйте первинними та вторинними ключами API:

   1. Щоб показати основний або додатковий ключ API, виберіть **символ Показати** .

   1. Щоб скопіювати основний або додатковий ключ API, виберіть **символ Копіювати** .

   1. Щоб створити нові первинні або вторинні ключі API, виберіть **"Відновити первинний** " або **"Відновити вторинний"**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Безпечний доступ до даних клієнтів за допомогою клієнтського замка (Попередній перегляд)

Customer Insights використовує функцію захищеного Power Platform доступу клієнта. Клієнтський сейф надає інтерфейс для розгляду та затвердження (або відхилення) запитів на доступ до даних. Ці запити виникають, коли доступ даних до даних клієнтів необхідний для вирішення справи підтримки. Щоб використовувати цю функцію, Customer Insights має мати наявний зв'язок із середовищем Microsoft Dataverse у вашому клієнті.

Щоб дізнатися більше про клієнтську скриньку [, перегляньте зведення](/power-platform/admin/about-lockbox#summary) Power Platform програми "Клієнтська скринька". У статті також описано [робочий цикл](/power-platform/admin/about-lockbox#workflow) і необхідні [настройки](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) для ввімкнення функції блокування клієнта.

> [!IMPORTANT]
> Глобальні адміністратори Power Platform або Power Platform адміністратори можуть схвалювати запити на повний контроль доступу для клієнтів, видані для Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Настроювання приватного посилання Azure

[Azure Private Link](/azure/private-link/private-link-overview) дозволяє Customer Insights підключатися до вашого Azure Data Lake Storage облікового запису через приватну кінцеву точку у вашій віртуальній мережі. Для даних в обліковому записі сховища, який не має доступу до загальнодоступного Інтернету, Private Link дозволяє підключатися до цієї обмеженої мережі.

> [!IMPORTANT]
> Мінімальні вимоги до ролі для настроювання з'єднання private link:
>
> - Статистика клієнтів: адміністратор
> - Вбудована роль Azure: [постачальник облікового запису сховища](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Дозволи для настроюваної ролі Azure: [Microsoft.Storage/storageAccounts/read і Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. У розділі Customer Insights перейдіть до **Безпека** > **адміністратора** та виберіть вкладку **Приватні посилання**.

1. Виберіть Додати **приватне посилання**.

   В області Додавання **приватного посилання** перелічено облікові записи сховища клієнта, на перегляд яких ви маєте дозволи.

1. Виберіть передплату, групу ресурсів і обліковий запис сховища.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Виберіть **Зберегти**.

1. Перейдіть до свого облікового запису Data Lake Storage і відкрийте посилання, представлену на екрані.

1. Затвердити приватне посилання.


[!INCLUDE [footer-include](includes/footer-banner.md)]
