---
title: Аудит Dynamics 365 Customer Insights за допомогою azure monitor
description: Дізнайтеся, як надсилати журнали Microsoft Azure на монітор.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: d962c359d70a068fcf939b61e340f86de088b419
ms.sourcegitcommit: 0c3c473e0220de9ee3c1f1ee1825de0b3b3663c3
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920879"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Переадресація за Dynamics 365 Customer Insights допомогою azure монітор (попередній перегляд)

Dynamics 365 Customer Insights забезпечує пряму інтеграцію з Azure Monitor. Журнали ресурсів Azure Monitor дають змогу відстежувати та надсилати журнали до [сховища Azure, Azure Log Analytics або передавати їх до центрів подій Azure](https://azure.microsoft.com/services/storage/)[...](/azure/azure-monitor/logs/log-analytics-overview)[...](https://azure.microsoft.com/services/event-hubs/).

Статистика клієнтів надсилає такі журнали подій:

- **Події аудиту**
  - **APIEvent** - дозволяє відстежувати зміни, здійснені за допомогою Dynamics 365 Customer Insights інтерфейсу користувача.
- **Оперативні заходи**
  - **WorkflowEvent** - Робочий процес дозволяє налаштувати джерела [даних](data-sources.md), [об'єднати](data-unification.md) і [збагатити](enrichment-hub.md) і, нарешті, [експортувати дані в інші](export-destinations.md) системи. Всі ці кроки можуть бути зроблені індивідуально (наприклад, викликати один експорт) або організовані (наприклад, оновлення даних з джерел даних, які запускають процес об'єднання, який буде тягнути додаткові збагачення і після того, як це буде зроблено, експортувати дані в іншу систему). Для отримання додаткових відомостей [див](#workflow-event-schema).
  - **APIEvent** - всі виклики API до екземпляра клієнтів до Dynamics 365 Customer Insights. Для отримання додаткових відомостей [див.](#api-event-schema)

## <a name="set-up-the-diagnostic-settings"></a>Настроювання параметрів діагностики

### <a name="prerequisites"></a>вимоги

Щоб настроїти діагностику в Customer Insights, потрібно виконати такі передумови:

- У вас є активна [підписка Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- У вас є [дозволи адміністратора](permissions.md#administrator) в статистики клієнтів.
- У вас є **роль постачальника** та **доступу користувача адміністратора на** цільовому ресурсі на Azure. Ресурс може бути обліковим записом сховища Azure, центром подій Azure або робочою областю Azure Log Analytics. Для отримання додаткових відомостей [див](/azure/role-based-access-control/role-assignments-portal).
- [Вимоги призначення](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) для Azure зберігання, Azure event hub або Azure журнал Analytics виконано.
- У вас є принаймні **роль читача** у групі ресурсів, до якої належить ресурс.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Настроювання діагностики за допомогою azure monitor

1. У службі Customer Insights виберіть **елемент Діагностика системи,** > **щоб переглянути** місця діагностики, настроєні в цьому екземплярі.

1. Виберіть **додати місце призначення**.

   > [!div class="mx-imgBorder"]
   > ![Підключення до діагностики](media/diagnostics-pane.png "Підключення до діагностики")

1. Укажіть ім'я в **полі Ім'я призначення** діагностики.

1. Виберіть **клієнта** передплати Azure з цільовим ресурсом і виберіть **увійти**.

1. Виберіть **тип ресурсу** (обліковий запис сховища, центр подій або аналітика журналу).

1. Виберіть **передплату** для цільового ресурсу.

1. Виберіть **групу ресурсів** для цільового ресурсу.

1. Виберіть **ресурс**.

1. Підтвердіть **декларацію про конфіденційність і відповідність** даних.

1. Виберіть **підключитися до** системи, щоб підключитися до цільового ресурсу. Журнали починають з'являтися в місці призначення через 15 хвилин, якщо API використовується і генерує події.

### <a name="remove-a-destination"></a>Видалення місця призначення

1. Перейдіть до **системної** > **діагностики**.

1. Виберіть місце діагностики у списку.

1. У **стовпці Дії** виберіть **піктограму** Видалити.

1. Підтвердіть видалення, щоб зупинити переадресацію журналу. Ресурс у передплаті Azure не буде видалено. Ви можете вибрати посилання в **стовпці** Дії, щоб відкрити портал Azure для вибраного ресурсу та видалити його там.

## <a name="log-categories-and-event-schemas"></a>Категорії журналу та схеми подій

Наразі [підтримуються події API](apis.md) та події робочого циклу, застосовуються такі категорії та схеми.
Схема журналу слід azure [монітор загальна схема](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Категорії

Статистика клієнтів містить дві категорії:

- **Події** аудиту: [події API для відстеження змін](#api-event-schema) конфігурації в службі. `POST|PUT|DELETE|PATCH` операції відносяться до цієї категорії.
- **Операційні** події: [події API або](#api-event-schema) події [робочого](#workflow-event-schema) циклу, створені під час використання служби.  Наприклад, `GET` запити або події виконання робочого циклу.

## <a name="configuration-on-the-destination-resource"></a>Конфігурація на цільовому ресурсі

Залежно від вашого вибору типу ресурсу автоматично застосовуватимуться наступні кроки:

### <a name="storage-account"></a>Обліковий запис сховища

Принципал служби Customer Insights отримує **дозвіл постачальника облікового запису сховища** на вибраному ресурсі та створює два контейнери у вибраному просторі імен:

- `insight-logs-audit` містить **аудиторські події**
- `insight-logs-operational` містить **оперативні події**

### <a name="event-hub"></a>Концентратор подій

Принципал служби статистики клієнтів отримує **дозвіл власника даних Azure Event Hubs на** ресурсі та створить два центри подій у вибраному просторі імен:

- `insight-logs-audit` містить **аудиторські події**
- `insight-logs-operational` містить **оперативні події**

### <a name="log-analytics"></a>Аналітика журналу

Керівник служби статистики клієнтів отримує **дозвіл постачальника журналу Analytics** на ресурсі. Журнали будуть доступні в **розділі** > **Журнали таблиці** > **керування журналами** в вибраній робочій області Log Analytics. Розгорніть **рішення керування журналами та** знайдіть таблиці та `CIEventsAudit``CIEventsOperational` таблиці.

- `CIEventsAudit` містить **аудиторські події**
- `CIEventsOperational` містить **оперативні події**

У **вікні Запити** розгорніть **рішення Аудиту та** знайдіть приклади запитів, які можна знайти за допомогою пошуку `CIEvents`.

## <a name="event-schemas"></a>Схеми подій

Події API та події робочого циклу мають спільну структуру та деталі, де вони відрізняються, [...](#api-event-schema)[див](#workflow-event-schema).

### <a name="api-event-schema"></a>Схема подій API

| Поле             | Тип даних  | Обов'язково/необов'язково | Опис       | Приклад        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Позначка часу | Обов'язковий          | Часова позначка події (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Обов'язковий          | ResourceId екземпляра, який випустив подію         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Обов'язковий          | Назва операції, представленої цією подією.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Обов'язковий          | Журнал категорії події. Або `Operational``Audit`. Всі ПОСТ / PUT / PATCH / ВИДАЛИТИ HTTP Запити `Audit` позначені, все інше з`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Обов'язковий          | Статус події. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Необов'язково          | Стан результату події. Якщо операція відповідає REST API виклику, це код стану HTTP.        | `200`             |
| `durationMs`      | Довге значення      | Необов'язково          | Тривалість операції в мілісекундах.     | `133`     |
| `callerIpAddress` | String    | Необов'язково          | IP-адреса абонента, якщо операція відповідає виклику API, який надходить з загальнодоступної IP-адреси.                                                 | `144.318.99.233`         |
| `identity`        | String    | Необов'язково          | Об'єкт JSON, що описує особу користувача або програми, яка зробила операцію.       | Дивіться [розділ](#identity-schema) Посвідчення.     |  |
| `properties`      | String    | Необов'язково          | Об'єкт JSON з більшою кількістю властивостей до певної категорії подій.      | [Див.](#api-properties-schema)    |
| `level`           | String    | Обов'язковий          | Рівень тяжкості події.    | `Informational`, `Warning``Error`,, або `Critical`.           |
| `uri`             | String    | Необов'язково          | Абсолютний запит URI.    |               |

#### <a name="identity-schema"></a>Схема посвідчення

`identity` Об'єкт JSON має наступну структуру

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Поле                         | Опис                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Призначена роль для користувача або програми. Для отримання додаткових відомостей [див](permissions.md).                                     |
| `Authorization.RequiredRoles` | Обов'язкові ролі для виконання операції. `Admin` Роль дозволяється виконувати всі операції.                                                    |
| `Claims`                      | Претензії користувача або веб-маркера програми JSON (JWT). Властивості претензії залежать від організації та Azure Active Directory конфігурації. |

#### <a name="api-properties-schema"></a>Схема властивостей API

[Події API](apis.md) мають такі властивості.

| Поле                        | Опис                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Завжди `ApiEvent`, позначаючи подію журналу як подію API.                                                                 |
| `properties.userAgent`       | Агент браузера, який надсилає запит, або `unknown`.                                                                        |
| `properties.method`          | Метод HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Відносний шлях запиту.                                                                                          |
| `properties.origin`          | URI, що вказує, звідки береться отримання або `unknown`.                                                                  |
| `properties.operationStatus` | `Success` код стану HTTP < 400 <br> `ClientError` код стану HTTP < 500 <br> `Error` для > стану HTTP= 500 |
| `properties.tenantId`        | Ідентифікатор організації                                                                                                        |
| `properties.tenantName`      | Назва організації.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId абонента.                                                                         |
| `properties.instanceId`      | Статистика клієнтів`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Схема події робочого циклу

Робочий цикл містить кілька кроків. [Ingest джерел даних](data-sources.md), [об'єднати,](data-unification.md)[збагатити](enrichment-hub.md) та експортувати [дані](export-destinations.md). Всі ці кроки можуть виконуватися індивідуально або організовано за допомогою наступних процесів. 

#### <a name="operation-types"></a>Типи операцій

| OperationType     | Групувати                                     |
| ----------------- | ----------------------------------------- |
| Прийому         | [Джерела даних](data-sources.md)           |
| Підготовка даних   | [Джерела даних](data-sources.md)           |
| Зіставлення               | [Уніфікація даних](data-unification.md)   |
| Збіг             | [Уніфікація даних](data-unification.md)   |
| Злиття             | [Уніфікація даних](data-unification.md)   |
| Магазин профілів      | [Профілі клієнтів](customer-profiles.md) |
| Введіть пошуковий запит            | [Профілі клієнтів](customer-profiles.md) |
| Активність          | [Справи](activities.md)                  |
| АтрибутИЗазначуви | [Сегменти та заходи](segments.md)      |
| EntityMeasures    | [Сегменти та заходи](segments.md)      |
| Вимірювання          | [Сегменти та заходи](segments.md)      |
| Сегментація      | [Сегменти та заходи](segments.md)      |
| Збагачення        | [Збагачення](enrichment-hub.md)                                          |
| Аналітика      | [Прогнози](predictions-overview.md)                                          |
| АйБудівник         | [Прогнози](predictions-overview.md)                                          |
| Аналітика          | [Прогнози](predictions-overview.md)                                          |
| Export            | [Операції експорту](export-destinations.md)                                          |
| Моделькерування   | [Прогнози](custom-models.md)                                           |
| Зв’язки      | [Уніфікація даних](relationships.md)                                           |

#### <a name="field-description"></a>Опис поля

| Поле           | Тип даних  | Обов'язково/необов'язково | Опис                                                                                                                                                   | Приклад                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Позначка часу | Обов'язковий          | Позначка часу події (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Обов'язковий          | ResourceId екземпляра, який випустив подію.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Обов'язковий          | Назва операції, представленої цією подією. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Перегляньте [посилання Типи](#operation-types) операцій. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Обов'язковий          | Журнал категорії події. Завжди `Operational` для подій робочого циклу                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Обов'язковий          | Статус події. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Довге значення      | Необов'язково          | Тривалість операції в мілісекундах.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Необов'язково          | Об'єкт JSON з більшою кількістю властивостей до певної категорії подій.                                                                                        | Переглянути [властивості робочого циклу підсекуми](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Обов'язковий          | Рівень тяжкості події.                                                                                                                                  | `Informational`, `Warning` або `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Схема властивостей робочого циклу

Події робочого циклу мають такі властивості.

| Поле              | Workflow | Завдання | Опис            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Так      | Так  | Завжди `WorkflowEvent`, позначаючи подію як подію робочого циклу.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Так      | Так  | Ідентифікатор запуску робочого циклу. Усі події робочого циклу та завдання в рамках виконання робочого циклу мають однакові `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Так      | Так  | Ідентифікатор операції див. (#operation типи)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Так      | No   | Лише робочий цикл. Кількість завдань, які запускає робочий цикл.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Так      | No   | Необов'язково. Лише події робочого циклу. Ідентифікатор Azure Active Directory [об'єкта](/azure/marketplace/find-tenant-object-id#find-user-object-id) користувача, який ініціював робочий цикл, `properties.workflowSubmissionKind` див.                                   |
| `properties.workflowType`                    | Так      | No   | `full` або `incremental` оновити.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Так      | No   | `OnDemand` або `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Так      | No   | `Running` або `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Так      | Так  | Мітка часу UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Так      | Так  | Мітка часу UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Так      | Так  | Мітка часу UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Так      | Так  | Статистика клієнтів`instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Так  | - Для OperationType = `Export`, ідентифікатор є guid конфігурації експорту. <br> - Для OperationType = `Enrichment`, це керівництво збагачення <br> - Для OperationType `Measures` і, ідентифікатор є `Segmentation` ім'ям сутності. |
| `properties.friendlyName`                    | No       | Так  | Зручне ім'я експорту або оброблюваної сутності.                                                                                                                                                                                           |
| `properties.error`                           | No       | Так  | Необов'язково. Повідомлення про помилку з більш детальною інформацією.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Так  | Необов'язково. Лише для операції `Export` Тип. Визначає тип експорту. Для отримання [додаткових відомостей](export-destinations.md) див.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Так  | Необов'язково. Лише для операції `Export` Тип. Містить список настроєних сутностей під час експорту.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Так  | Необов'язково. Лише для операції `Export` Тип. Детальне повідомлення для експорту.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Так  | Необов'язково. Лише для операції `Segmentation` Тип. Указує загальну кількість членів сегмента.                                                                                                                                                    |
