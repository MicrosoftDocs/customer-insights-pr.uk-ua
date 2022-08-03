---
title: Підключення до даних в озері з керованим даними Microsoft Dataverse
description: Імпорт даних із керованого озера даних Microsoft Dataverse.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206978"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Підключення до даних в озері з керованим даними Microsoft Dataverse

Microsoft Dataverse користувачі можуть швидко підключатися до аналітичних організацій в керованому Microsoft Dataverse озері. Лише одне джерело даних із середовища може одночасно використовувати кероване озеро Dataverse.

> [!NOTE]
> Ви повинні бути адміністратором організації, Dataverse щоб продовжити та переглянути список організацій, доступних у керованому озері.

## <a name="prerequisites"></a>вимоги

- Дані, що зберігаються в онлайнових службах, наприклад, Azure Data Lake Storage, можуть зберігатися в розташуванні, відмінному від того, в якому дані обробляються або зберігаються в Dynamics 365 Customer Insights.Імпортуючи або підключаючись до даних, що зберігаються в онлайн-сервісах, ви погоджуєтеся з тим, що дані можуть передаватися і зберігатися за допомогою Dynamics 365 Customer Insights. [Дізнайтеся більше в Центрі безпеки та конфіденційності Microsoft](https://www.microsoft.com/trust-center).

- Видно лише Dataverse сутності з [увімкненим відстеженням](/power-platform/admin/enable-change-tracking-control-data-synchronization) змін. Ці об'єкти можна експортувати в Dataverse кероване озеро даних і використовувати в Customer Insights. У нестандартних Dataverse таблицях за замовчуванням увімкнуто відстеження змін. Потрібно ввімкнути відстеження змін для настроюваних таблиць. Щоб перевірити, чи ввімкнуто відстеження змін у Dataverse таблиці, перейдіть до [Power Apps](https://make.powerapps.com) > **розділу Таблиці** > **даних**. Знайдіть цікаву для вас таблицю і виберіть її. Перейдіть до **«Додаткові параметри** > **налаштувань»** і перегляньте **параметр «Відстежувати зміни**».

## <a name="connect-to-a-dataverse-managed-lake"></a>Підключення до керованого озера Dataverse

1. Відкрийте **Дані** > **Джерела даних**.

1. Виберіть **Додати джерело даних**.

1. Виберіть **Microsoft Dataverse**.

1. Введіть Ім'я **джерело** даних та необов'язковий **опис**.

1. Укажіть **Адресу сервера** для організації Dataverse і виберіть **Увійти в систему**.

1. Виберіть таблиці, які ви хочете проковтнути як сутності до Customer Insights із доступного списку.

   > [!NOTE]
   > Якщо деякі таблиці вже вибрано, то їх можуть використовувати інші програми Dynamics 365 (наприклад, Dynamics 365 Sales Insights або Customer Service Insights). Цей вибір змінити не можна. Ці таблиці будуть доступні як сутності після створення джерела даних.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Діалогове вікно, в якому відображається список сутностей у середовищі Dataverse.":::

1. Збережіть вибір, щоб почати синхронізацію вибраних таблиць із Dataverse. На сторінці **Джерела даних** ви побачите нещодавно додане підключення. Його буде поставлено в чергу на оновлення, кількість сутності буде 0 поки не будуть синхронізовані вибрані таблиці.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Завантаження даних може тривати значний час. Після успішного оновлення дані, що надійшли, можна переглянути зі сторінки « [**Сутності**](entities.md) ».

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Редагування джерела даних керованого озера Dataverse

Після створення джерела даних ви можете редагувати тільки вибір сутностей. Наприклад, якщо до Dataverse додано додаткові сутності, і їх також потрібно імпортувати.
Щоб підключитися до іншого озера даних Dataverse, [створіть нове джерело даних](#connect-to-a-dataverse-managed-lake).

1. Відкрийте **Дані** > **Джерела даних**.

1. Поруч із джерело даних потрібно оновити, натисніть кнопку **Редагувати**.

1. Виберіть додаткові сутності з доступного списку суб'єктів.

1. Натисніть кнопку **Зберегти**, щоб застосувати зміни та повернутися на сторінку **Джерела** даних.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
