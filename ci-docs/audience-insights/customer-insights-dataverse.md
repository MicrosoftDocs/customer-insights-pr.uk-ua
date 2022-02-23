---
title: Дані статистики клієнтів у Microsoft Dataverse
description: Використовуйте сутності Статистики клієнтів як таблиці в Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866959"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Робота з даними статистики клієнтів у Microsoft Dataverse

Статистика клієнтів надає можливість зробити сутності виводу доступними в [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Ця інтеграція дає змогу легко використовувати дані спільно і розробляти користувацькі рішення, майже не застосовуючи кодування даних або й зовсім без написання коду. Сутності виводу будуть доступні як таблиці в Dataverse. Ці таблиці дозволяють сценарії, такі як [автоматизовані робочі цикли, за допомогою](/power-automate/getting-started) Power Automate, [програм на основі моделі та програм на](/powerapps/maker/model-driven-apps/)[полотні через](/powerapps/maker/canvas-apps/) Power Apps. Дані можна використовувати для будь-якої іншої програми, заснованої на Dataverse таблицях. Поточна реалізація підтримує здебільшого підстановки, в яких можна отримувати дані для певного ідентифікатора клієнта з наявних сутностей аналізу аудиторії.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Вкласти Dataverse середовище до статистики клієнтів

**Організації з наявними Dataverse середовищами**

Організації, які вже використовують Dataverse, можуть [використовувати одне з наявних Dataverse середовищ,](create-environment.md) коли адміністратор налаштовує статистику аудиторії. Надаючи URL-адресу Dataverse середовищі, вона додається до нового середовища статистики аудиторії. Щоб забезпечити найкращу продуктивність, у тому самому регіоні має бути розміщено статистику клієнтів і Dataverse середовища.

**Нова організація**

Якщо під час настроювання статистики клієнтів створюється нова організація, ви автоматично отримаєте нове Dataverse середовище.

> [!NOTE]
> Якщо організації вже використовують Dataverse у своєму клієнті, важливо пам'ятати, що [створення Dataverse середовища контролюється адміністратором.](/power-platform/admin/control-environment-creation.md) Наприклад, якщо ви налаштовуєте нове середовище статистики аудиторії за допомогою облікового запису організації, а адміністратор вимкнув створення Dataverse ознайомлювального середовища для всіх, крім адміністраторів, створити нове ознайомлювальну середовище не можна.
> 
> Ознайомлювальну Dataverse середовища, створену в Customer Insights, має 3 ГБ пам'яті, що не враховуватимуть загальну ємність, що має право на клієнта. Платні підписки отримують Dataverse права 15 ГБ для бази даних і 20 ГБ для зберігання файлів.

## <a name="output-entities"></a>Вихідні сутності

Деякі сутності виводу зі статистики аудиторії доступні як таблиці в Dataverse. У розділах нижче описано очікувану схему таких таблиць.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Збагачення](#enrichment)
- [Прогноз](#prediction)
- [Членство в сегменті](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Ця таблиця містить уніфікований профіль клієнта з Customer Insights. Схема уніфікованого профілю клієнта залежатиме від сутностей і атрибутів, застосованих в процесі злиття. Схема профілю клієнта зазвичай містить підмножину атрибутів із [визначення CustomerProfile в Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

У таблиці AlternateKey містяться ключі сутностей, які брали участь в процесі уніфікації.

|Column  |Ввести  |Опис  |
|---------|---------|---------|
|DataSourceName    |String         | Ім'я джерела даних. Наприклад: `datasource5`        |
|EntityName        | String        | Ім'я сутності в аналізі аудиторії. Наприклад: `contact1`        |
|AlternateValue    |String         |Альтернативний ідентифікатор, зіставлений з ідентифікатором клієнта. Приклад: `cntid_1078`         |
|KeyRing           | Багаторядковий текст        | Значення JSON  </br> Зразок: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"ключі":[" cntid_1078"]}]       |
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

### <a name="segment-membership"></a>Членство в сегменті

Ця таблиця містить відомості про членство в сегменті профілів клієнтів.

| Column        | Ввести | Опис                        |
|--------------------|--------------|-----------------------------|
| Ідентифікатор клієнта        | String       | Ідентифікатор профілю клієнта        |
| SegmentProvider      | String       | Додаток, який публікує сегменти. За замовчуванням: статистика аудиторії         |
| Тип сегмента | String       | Тип клієнта цей запис членства в сегменті. Підтримує кілька типів, наприклад Клієнт, Контактна особа або Бізнес-партнер. За замовчуванням: клієнт  |
| Сегменти       | Рядок JSON  | Список унікальних сегментів, членом яких є профіль клієнта      |
| msdynci_identifier  | String   | Унікальний ідентифікатор запису членства в сегменті. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детермінований GUID, створений з`msdynci_identifier`          |
