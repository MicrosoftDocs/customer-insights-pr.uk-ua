---
title: Дані Customer Insights у Microsoft Dataverse
description: Використовуйте сутності Customer Insights як таблиці у Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741390"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Робота із даними Customer Insights у Microsoft Dataverse

Customer Insights дозволяє зробити вихідні сутності доступними в [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ця інтеграція дозволяє легко обмінюватися даними та індивідуальну розробку за допомогою низького підходу коду / без коду. Вихідні [сутності](#output-entities) доступні як таблиці в Dataverse середовищі. Дані можна використовувати для будь-якої іншої програми на Dataverse основі таблиць. У цих таблицях містяться такі сценарії, як автоматичні робочі цикли або Power Automate створення програм за допомогою програми за допомогою програми Power Apps. Поточна реалізація в основному підтримує пошуки, де дані з доступних об'єктів статистики клієнтів можуть бути отримані для певного ідентифікатора клієнта.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>прикріплення середовища Dataverse до Customer Insights

**Існуюча організація**

Адміністратори можуть налаштувати статистику клієнтів на [використання наявного Dataverse середовища](create-environment.md) під час створення середовища статистики клієнтів. Надаючи URL-адресу навколишньому середовищу Dataverse, вона прикріплюється до їх нового середовища статистики клієнтів. Статистика клієнтів і Dataverse середовища повинні розміщуватися в одному регіоні. 

Якщо ви не хочете використовувати існуюче Dataverse середовище, система створює нове середовище для даних Статистики клієнта у вашому клієнті. 

> [!NOTE]
> Якщо ваші організації вже використовують Dataverse у своєму клієнті, важливо пам'ятати, що [Dataverse створення середовища контролюється адміністратором](/power-platform/admin/control-environment-creation). Наприклад, якщо ви налаштовуєте нове середовище статистики клієнтів за допомогою організаційного облікового запису, а адміністратор вимкнув створення ознайомлювальних Dataverse середовищ для всіх, крім адміністраторів, ви не можете створити нове пробне середовище.
> 
> Ознайомлювальні середовища Dataverse, створені в Customer Insights, мають 3 ГБ сховища, які не враховуються в загальній виробничій спроможності, гарантованій клієнту. Платні версії отримують для Dataverse право на використання обсягу 15 ГБ для бази даних і 20 ГБ для сховища файлів.

**Нова організація**

Якщо ви створюєте нову організацію під час налаштування статистики клієнтів, система автоматично створює нове Dataverse середовище у вашій організації для вас.

## <a name="output-entities"></a>Вихідні сутності

Деякі вихідні сутності зі статистики клієнтів доступні як таблиці в Dataverse програмі. У розділах нижче описано очікувану схему таких таблиць.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Збагачення](#enrichment)
- [Прогноз](#prediction)
- [Членство в сегменті](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Ця таблиця містить уніфікований профіль клієнта з Customer Insights. Схема для уніфікованого профілю клієнта залежить від сутностей і атрибутів, які використовуються в процесі об'єднання даних. Схема профілю клієнта зазвичай містить підмножину атрибутів із [визначення CustomerProfile в Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

У таблиці AlternateKey містяться ключі сутностей, які брали участь в процесі уніфікації.

|Column  |Ввести  |Опис  |
|---------|---------|---------|
|DataSourceName    |String         | Ім'я джерела даних. Наприклад: `datasource5`        |
|EntityName        | String        | Ім'я сутності в Службі статистики клієнтів. Наприклад: `contact1`        |
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

### <a name="segment-membership"></a>Членство в сегменті

Ця таблиця містить відомості про членство в сегменті профілів клієнтів.

| Column        | Ввести | Опис                        |
|--------------------|--------------|-----------------------------|
| Ідентифікатор клієнта        | String       | Ідентифікатор профілю клієнта        |
| SegmentProvider      | String       | Додаток, який публікує сегменти.      |
| Тип перетину сегмента | String       | Тип клієнта цього запису членства в сегменті. Підтримує кілька типів, таких як клієнт, контакт або бізнес-партнер. Типове значення: Клієнт  |
| Сегменти       | Рядок JSON  | Список унікальних сегментів профілю клієнта є членом      |
| msdynci_identifier  | String   | Унікальний ідентифікатор запису членства в сегменті. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детермінований GUID, створений з`msdynci_identifier`          |
