---
title: Підключення до даних в озері з керованим даними Microsoft Dataverse
description: Імпорт даних із керованого озера даних Microsoft Dataverse.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609876"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Підключення до даних в озері з керованим даними Microsoft Dataverse

Microsoft Dataverse користувачі можуть швидко підключатися до аналітичних організацій в керованому Microsoft Dataverse озері. Лише одне джерело даних із середовища може одночасно використовувати кероване озеро Dataverse.

> [!NOTE]
> Ви повинні бути адміністратором організації, Dataverse щоб продовжити та переглянути список організацій, доступних у керованому озері.

## <a name="prerequisites"></a>вимоги

- Дані, що зберігаються в онлайнових службах, наприклад, Azure Data Lake Storage, можуть зберігатися в розташуванні, відмінному від того, в якому дані обробляються або зберігаються в Dynamics 365 Customer Insights.Імпортуючи або підключаючись до даних, що зберігаються в онлайн-сервісах, ви погоджуєтеся з тим, що дані можуть передаватися і зберігатися за допомогою Dynamics 365 Customer Insights. [Дізнайтеся більше в Центрі](https://www.microsoft.com/trust-center) безпеки та конфіденційності Microsoft.

- Видно лише Dataverse сутності з [увімкненим відстеженням](/power-platform/admin/enable-change-tracking-control-data-synchronization) змін. Ці об’єкти можна експортувати в Dataverse кероване озеро даних і використовувати в Customer Insights. У нестандартних Dataverse таблицях за замовчуванням увімкнуто відстеження змін. Потрібно ввімкнути відстеження змін для настроюваних таблиць. Щоб перевірити, чи ввімкнуто відстеження змін у Dataverse таблиці, перейдіть до [Power Apps](https://make.powerapps.com) > **розділу Таблиці** > **даних**. Знайдіть цікаву для вас таблицю і виберіть її. Перейдіть до **«Додаткові параметри** > **налаштувань»** і перегляньте **параметр «Відстежувати зміни**».

## <a name="connect-to-a-dataverse-managed-lake"></a>Підключення до керованого озера Dataverse

1. Відкрийте **Дані** > **Джерела даних**.

1. Виберіть **Додати джерело даних**.

1. Виберіть **Microsoft Dataverse**.

1. Введіть Ім’я **джерело** даних та необов’язковий **опис**.

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

1. Виберіть додаткові сутності з доступного списку суб’єктів.

1. Натисніть кнопку **Зберегти**, щоб застосувати зміни та повернутися на сторінку **Джерела** даних.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Поширені причини помилок при попаданні або пошкоджених даних

Для показу пошкоджених записів виконуються наведені нижче перевірки.

- Значення поля не збігається з типом даних у стовпці.
- Поля містять символи, які призводь до того, що стовпці не збігаються з очікуваною схемою. Наприклад, неправильно відформатовані цінові пропозиції, нерозголошені цінові пропозиції або символи нового рядку.
- Якщо є стовпці datetime/date/datetimeoffset, їх формат потрібно вказати в моделі, якщо він не відповідає стандартному формату ISO.

### <a name="schema-or-data-type-mismatch"></a>Невідповідність схеми або типу даних

Якщо дані не відповідають схемі, записи класифікуються як пошкоджені. Виправте вихідні дані або схему та повторно проковтніть дані.

### <a name="datetime-fields-in-the-wrong-format"></a>Поля datetime у неправильному форматі

Поля datetime в сутності не мають форматів ISO або en-US. Формат дати за замовчуванням у Customer Insights – це формат en-US. Усі поля datetime в сутності мають бути в однаковому форматі. Customer Insights підтримує інші формати за умови, що анотації або риси зроблені на рівні джерела або сутності в моделі або manifest.json. Наприклад:

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  У manifest.json формат datetime може бути вказаний на рівні сутності або на рівні атрибута. На рівні сутності використовуйте "exhibitsTraits" в сутності в *.manifest.cdm.json для визначення формату datatime. На рівні атрибута використовуйте "appliedTraits" в атрибуті в назві сутності.cdm.json.

**Manifest.json на рівні сутності**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json на рівні атрибутів**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
