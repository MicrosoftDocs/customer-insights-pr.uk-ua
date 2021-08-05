---
title: Дані Customer Insights у Microsoft Dataverse
description: Використовуйте сутності Customer Insights як таблиці у Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 220e01a06711a5d35b8df09e265017a6d8fd0490
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650067"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Робота із даними Customer Insights у Microsoft Dataverse

Customer Insights дозволяє зробити вихідні сутності доступними в [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Ця інтеграція дає змогу легко використовувати дані спільно і розробляти користувацькі рішення, майже не застосовуючи кодування даних або й зовсім без написання коду. Вихідні сутності будуть доступні як таблиці в Dataverse. Ці таблиці дозволяють використовувати такі сценарії, як [автоматизація робочих циклів за допомогою Power Automate](/power-automate/getting-started), а також [модельні програми](/powerapps/maker/model-driven-apps/) та [компоновані програми](/powerapps/maker/canvas-apps/) із використанням Power Apps. Дані можна використовувати для будь-якої іншої програми, основаній на таблицях Dataverse. Поточна реалізація підтримує здебільшого підстановки, в яких можна отримувати дані для певного ідентифікатора клієнта з наявних сутностей аналізу аудиторії.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>прикріплення середовища Dataverse до Customer Insights

**Організації з наявними середовищами Dataverse**

Організації, які вже використовують Dataverse, можуть [використовувати одне зі своїх наявних середовищ Dataverse](get-started-paid.md), якщо адміністратор настроїть аналіз аудиторій. Якщо вказати URL-адресу у середовищі Dataverse, його можна прикріпити до нового середовища аналізу аудиторії. Для того, щоб продуктивність була якомога вищою, потрібно розміщувати Customer Insights та Dataverse в одному регіоні.

Щоб прикріпити середовище Dataverse, розгорніть **Додаткові параметри** під час створення середовища аналізу аудиторії. Укажіть **URL-адресу середовища Microsoft Dataverse** та встановіть прапорець, щоб **Увімкнути спільний доступ до даних**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt.":::

**Нова організація**

Якщо під час настройки Customer Insights створюється нова організація, ви автоматично отримуєте нове середовище Dataverse.

> [!NOTE]
> Якщо організації вже використовують Dataverse у клієнті, важливо пам'ятати, що [створенням середовищ Dataverse керує адміністратор](/power-platform/admin/control-environment-creation.md). Наприклад, якщо ви налаштовуєте нове середовище статистики аудиторії, використовуючи обліковий запис вашої організації, а адміністратор вимкнув створення ознайомлювальних середовищ Dataverse для всіх, крім адміністраторів, ви не зможете створити нове ознайомлювальне середовище.
> 
> Ознайомлювальні середовища Dataverse, створені в Customer Insights, мають 3 ГБ сховища, які не враховуються в загальній виробничій спроможності, гарантованій клієнту. Платні версії отримують для Dataverse право на використання обсягу 15 ГБ для бази даних і 20 ГБ для сховища файлів.

## <a name="output-entities"></a>Вихідні сутності

Деякі вихідні сутності статистики аудиторії доступні в Dataverse як таблиці. У розділах нижче описано очікувану схему таких таблиць.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Збагачення](#enrichment)
- [Прогноз](#prediction)


### <a name="customerprofile"></a>CustomerProfile

Ця таблиця містить уніфікований профіль клієнта з Customer Insights. Схема уніфікованого профілю клієнта залежатиме від сутностей і атрибутів, застосованих в процесі злиття. Схема профілю клієнта зазвичай містить підмножину атрибутів із [визначення CustomerProfile в Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

У таблиці AlternateKey містяться ключі сутностей, які брали участь в процесі уніфікації.

|Column  |Ввести  |Опис  |
|---------|---------|---------|
|DataSourceName    |String         | Ім'я джерела даних. Наприклад: `datasource5`        |
|EntityName        | String        | Ім'я сутності в аналізі аудиторії. Наприклад: `contact1`        |
|AlternateValue    |String         |Альтернативний ідентифікатор, зіставлений з ідентифікатором клієнта. Приклад: `cntid_1078`         |
|KeyRing           | Багаторядковий текст        | Значення JSON  </br> Зразок: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|Ідентифікатор клієнта         | String        | Ідентифікатор уніфікованого профілю клієнта.         |
|AlternateKeyId     | GUID         |  Визначальний ідентифікатор GUID AlternateKey на основі msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Зразок: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Ця таблиця містить справи різних користувачів, доступних в Customer Insights.

| Column            | Ввести        | Опис                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| Ідентифікатор клієнта        | String      | Ідентифікатор профілю клієнта                                                                      |
| ActivityId        | String      | Внутрішній ідентифікатор справи клієнта (первинний ключ)                                       |
| SourceEntityName  | String      | Ім'я сутності-джерела                                                                |
| SourceActivityId  | String      | Первинний ключ із сутності-джерела                                                       |
| ActivityType      | String      | Семантичний тип справи або ім'я користувацької справи                                        |
| ActivityTimeStamp | DATETIME    | Позначка часу справи                                                                      |
| Посада             | String      | Назва або ім’я справи                                                               |
| Опис       | String      | Опис справи                                                                     |
| URL-адреса               | String      | Посилання на зовнішню URL-адресу, унікальну для цієї справи                                         |
| SemanticData      | Рядок JSON | Містить список пар ключ-значення для семантичного зіставлення полів, характерних для типу справи |
| RangeIndex        | String      | Позначка часу Unix, яка використовується для сортування часової шкали справ та запитів ефективного діапазону |
| mydynci_unifiedactivityid   | GUID | Внутрішній ідентифікатор справи клієнта (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

У цій таблиці містяться вихідні дані про показники, що залежать від атрибутів клієнта.

| Column             | Ввести             | Опис                 |
|--------------------|------------------|-----------------------------|
| Ідентифікатор клієнта         | String           | Ідентифікатор профілю клієнта        |
| Показники           | Рядок JSON      | Містить список пар ключ-значення із іменами показників та значеннями для певного клієнта | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Ідентифікатор профілю клієнта |


### <a name="enrichment"></a>Збагачення

У цій таблиці містяться результати процесу збагачення.

| Column               | Ввести             |  Опис                                          |
|----------------------|------------------|------------------------------------------------------|
| Ідентифікатор клієнта           | String           | Ідентифікатор профілю клієнта                                 |
| EnrichmentProvider   | String           | Ім’я постачальника збагачення                                  |
| EnrichmentType       | String           | Тип збагачення                                      |
| Значення               | Рядок JSON      | Список атрибутів, створених під час процесу збагачення |
| msdynci_enrichmentid | GUID             | Визначальний ідентифікатор GUID, створений на основі msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Прогноз

У цій таблиці містяться результати прогнозів моделі.

| Column               | Ввести        | Опис                                          |
|----------------------|-------------|------------------------------------------------------|
| Ідентифікатор клієнта           | String      | Ідентифікатор профілю клієнта                                  |
| ModelProvider        | String      | Ім’я постачальника моделі                                      |
| Модель                | String      | Ім’я моделі                                                |
| Значення               | Рядок JSON | Список атрибутів, створених моделлю |
| msdynci_predictionid | GUID        | Визначальний ідентифікатор GUID, створений на основі msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |
