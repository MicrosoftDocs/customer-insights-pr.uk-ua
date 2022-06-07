---
title: Audit Dynamics 365 Customer Insights with Azure Monitor
description: Дізнайтеся, як надсилати журнали на Microsoft Azure монітор.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 15ae772617efa4c64cf79d0bac10a0c3cb28ca30
ms.sourcegitcommit: a92bf5985263240fd07bad98d8e119b88cf2c9d9
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/26/2022
ms.locfileid: "8807606"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Переадресація входу за Dynamics 365 Customer Insights допомогою azure monitor (попередній перегляд)

Dynamics 365 Customer Insights забезпечує пряму інтеграцію з Azure Monitor. Журнали ресурсів Azure Monitor дають змогу відстежувати та надсилати журнали до [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) або передавати їх потоком до [Центрів](https://azure.microsoft.com/services/event-hubs/) подій Azure.

Статистика клієнта надсилає такі журнали подій:

- **Аудиторські події**
  - **APIEvent** - дозволяє відстежувати зміни, зроблені через Dynamics 365 Customer Insights інтерфейс користувача.
- **Оперативні події**
  - **WorkflowEvent** - Робочий процес дозволяє налаштувати [джерела](data-sources.md) даних, уніфікувати [...](data-unification.md), [збагатити](enrichment-hub.md) і, нарешті [, експортувати](export-destinations.md) дані в інші системи. Всі ці кроки можна зробити індивідуально (наприклад, запустити єдиний експорт). Вони також можуть працювати організовано (наприклад, оновлення даних з джерел даних, що запускає процес об'єднання, що призведе до збагачення і після завершення експорту даних в іншу систему). Для отримання додаткових [відомостей](#workflow-event-schema) див.
  - **APIEvent** - всі дзвінки API до екземпляра клієнтів до Dynamics 365 Customer Insights. Для отримання додаткових [відомостей](#api-event-schema) див.

## <a name="set-up-the-diagnostic-settings"></a>Настроювання параметрів діагностики

### <a name="prerequisites"></a>вимоги

Щоб настроїти діагностику в Customer Insights, необхідно виконати такі передумови:

- У вас є активна [підписка](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) Azure.
- У вас є [дозволи адміністратора](permissions.md#admin) в Службі статистики клієнтів.
- У вас є **роль постачальника** та **адміністратора доступу користувача** на цільовий ресурс на Azure. Ресурс може бути обліковим записом Azure Data Lake Storage, центром подій Azure або робочою областю Azure Log Analytics. Для отримання додаткових [відомостей див](/azure/role-based-access-control/role-assignments-portal). Цей дозвіл необхідний під час налаштування параметрів діагностики в Customer Insights, його можна змінити після успішного налаштування.
- [Вимоги до](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) призначення для Azure Storage, Azure Event Hub або Azure Log Analytics зустрілися.
- У вас є принаймні **роль читача** в групі ресурсів ресурс належить до ресурсу.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Настроювання діагностики за допомогою монітора Azure

1. У службі статистики клієнтів виберіть елемент **Системна** > **діагностика**, щоб переглянути діагностичні призначення, настроєні в цьому екземплярі.

1. Виберіть додати **місце призначення**.

   > [!div class="mx-imgBorder"]
   > ![Діагностичне підключення](media/diagnostics-pane.png "Діагностичне підключення")

1. Укажіть ім'я в **полі Ім'я призначення** діагностики.

1. **Виберіть клієнта** передплати Azure з цільовим ресурсом і виберіть **увійти**.

1. **Виберіть тип** ресурсу (обліковий запис сховища, центр подій або аналітика журналу).

1. Виберіть передплату **для** цільового ресурсу.

1. **Виберіть групу** Ресурс для кінцевого ресурсу.

1. **Виберіть ресурс**.

1. Підтвердьте декларацію про **конфіденційність і відповідність** даних.

1. Виберіть підключитися **до системи**, щоб підключитися до цільового ресурсу. Журнали починають з'являтися в місці призначення через 15 хвилин, якщо API використовується і генерує події.

### <a name="remove-a-destination"></a>Видалення місця призначення

1. Перейдіть до **системної** > **діагностики**.

1. Виберіть місце діагностики у списку.

1. **У стовпці Дії** виберіть піктограму **Видалити**.

1. Підтвердьте видалення, щоб зупинити пересилання журналу. Ресурс на azure підписки не буде видалено. Ви можете вибрати посилання у **стовпці Дії,** щоб відкрити портал Azure для вибраного ресурсу та видалити його там.

## <a name="log-categories-and-event-schemas"></a>Журнал категорій і схем подій

Наразі підтримуються [події](apis.md) API та події робочого процесу, застосовуються такі категорії та схеми.
Схема журналу слідує за загальною схемою [Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Категорії

Статистика клієнтів надає дві категорії:

- **Події** аудиту: [події](#api-event-schema) API для відстеження змін конфігурації служби. `POST|PUT|DELETE|PATCH` операції переходять в цю категорію.
- **Операційні події**: [події](#api-event-schema) API або [події робочого процесу,](#workflow-event-schema) створені під час використання служби.  Наприклад, `GET` запити або події виконання робочого циклу.

## <a name="configuration-on-the-destination-resource"></a>Конфігурація на цільовому ресурсі

На основі вашого вибору типу ресурсу автоматично застосовуватимуться такі кроки:

### <a name="storage-account"></a>Обліковий запис сховища

Принципал служби Customer Insights отримує **дозвіл постачальника** облікового запису сховища на вибраний ресурс і створює два контейнери під вибраним простором імен:

- `insight-logs-audit` містить аудиторські **події**
- `insight-logs-operational` що містять оперативні **події**

### <a name="event-hub"></a>Концентратор подій

Клієнт статистики служби принципал отримує **azure event hubs власник** даних власника на ресурсі і створить два центри подій у вибраному просторі імен:

- `insight-logs-audit` містить аудиторські **події**
- `insight-logs-operational` що містять оперативні **події**

### <a name="log-analytics"></a>Аналітика журналу

Принципал служби статистики клієнтів отримує **дозвіл постачальника** журналу Analytics на ресурсі. Журнали будуть доступні в розділі **Журнали таблиць** > **управління журналами** > **на** вибраній робочій області Log Analytics. Розгорніть **рішення керування журналом** і знайдіть `CIEventsAudit``CIEventsOperational` і таблиці.

- `CIEventsAudit` містить аудиторські **події**
- `CIEventsOperational` що містять оперативні **події**

У вікні Запити розгорніть **рішення для аудиту** та знайдіть приклад запитів, наданих пошуком **.**`CIEvents`

## <a name="event-schemas"></a>Схеми подій

Події API та події робочого процесу мають загальну структуру та деталі, де вони відрізняються, див [...](#api-event-schema)[...](#workflow-event-schema).

### <a name="api-event-schema"></a>Схема подій API

| Поле             | Тип даних  | Обов'язковий/необов'язковий | Опис       | Приклад        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Позначка часу | Обов'язковий          | Позначка часу події (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Обов'язковий          | Ідентифікатор ресурсу екземпляра, який випустив подію         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Обов'язковий          | Назва операції, представленої цією подією.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Обов'язковий          | Категорія журналу події. Або `Operational` .`Audit` Усі ЗАПИТИ HTTP POST/PUT/PATCH/PATCH/DELETE позначені тегами `Audit`, все інше з`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Обов'язковий          | Статус події. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Необов'язково          | Стан результату події. Якщо операція відповідає REST API виклику, це код стану HTTP.        | `200`             |
| `durationMs`      | Довге значення      | Необов'язково          | Тривалість операції в мілісекундах.     | `133`     |
| `callerIpAddress` | String    | Необов'язково          | IP-адреса абонента, якщо операція відповідає виклику API, який надходить з загальнодоступної IP-адреси.                                                 | `144.318.99.233`         |
| `identity`        | String    | Необов'язково          | Об'єкт JSON, що описує ідентичність користувача або застосунку, який виконав операцію.       | Дивіться [розділ Посвідчення](#identity-schema).     |  
| `properties`      | String    | Необов'язково          | Об'єкт JSON з більшою кількістю властивостей для конкретної категорії подій.      | Дивіться [розділ Властивості](#api-properties-schema).    |
| `level`           | String    | Обов'язковий          | Рівень тяжкості події.    | `Informational`, `Warning`, `Error`, або `Critical`.           |
| `uri`             | String    | Необов'язково          | Абсолютний запит URI.    |               |

#### <a name="identity-schema"></a>Схема посвідчення

Об'єкт `identity` JSON має наступну структуру

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
| `Authorization.RequiredRoles` | Необхідні ролі для виконання операції. `Admin` Роль дозволяється робити всі операції.                                                    |
| `Claims`                      | Претензії користувача або програми JSON веб-токен (JWT). Властивості претензії залежать від організації та конфігурації Azure Active Directory. |

#### <a name="api-properties-schema"></a>Схема властивостей API

[Події](apis.md) API мають наступні властивості.

| Поле                        | Опис                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Завжди `ApiEvent`, позначаючи подію журналу як подію API.                                                                 |
| `properties.userAgent`       | Агент браузера надсилає запит або `unknown`.                                                                        |
| `properties.method`          | Метод HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Відносний шлях запиту.                                                                                          |
| `properties.origin`          | URI, що вказує, звідки походить витяг або `unknown`.                                                                  |
| `properties.operationStatus` | `Success` код стану HTTP < 400 <br> `ClientError` код стану HTTP < 500 <br> `Error` для стану HTTP > = 500 |
| `properties.tenantId`        | Ідентифікатор організації                                                                                                        |
| `properties.tenantName`      | Назва організації.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId абонента.                                                                         |
| `properties.instanceId`      | Статистика клієнтів`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Схема події робочого циклу

Робочий цикл містить кілька кроків. [Проковтнути джерела](data-sources.md) даних, [об'єднати](data-unification.md), [збагатити](enrichment-hub.md) та [експортувати](export-destinations.md) дані. Всі ці кроки можуть виконуватися індивідуально або організовано з наступними процесами.

#### <a name="operation-types"></a>Типи операцій

| OperationType     | Групувати                                     |
| ----------------- | ----------------------------------------- |
| Прийому         | [Джерела даних](data-sources.md)           |
| Підготовка даних   | [Джерела даних](data-sources.md)           |
| Зіставлення               | [Уніфікація даних](data-unification.md)   |
| Збіг             | [Уніфікація даних](data-unification.md)   |
| Злиття             | [Уніфікація даних](data-unification.md)   |
| Таблиця профілів      | [Профілі клієнтів](customer-profiles.md) |
| Введіть пошуковий запит            | [Профілі клієнтів](customer-profiles.md) |
| Активність          | [Справи](activities.md)                  |
| AttributeMeasures | [Сегменти та заходи](segments.md)      |
| СутностіЗаспокоєння    | [Сегменти та заходи](segments.md)      |
| Вимірювання          | [Сегменти та заходи](segments.md)      |
| Сегментація      | [Сегменти та заходи](segments.md)      |
| Збагачення        | [Збагачення](enrichment-hub.md)                                          |
| Аналітика      | [Прогнози](predictions-overview.md)                                          |
| AiBuilder         | [Прогнози](predictions-overview.md)                                          |
| Аналітика          | [Прогнози](predictions-overview.md)                                          |
| Export            | [Операції експорту](export-destinations.md)                                          |
| Керування моделлю   | [Прогнози](custom-models.md)                                           |
| Зв’язки      | [Уніфікація даних](relationships.md)                                           |

#### <a name="field-description"></a>Опис поля

| Поле           | Тип даних  | Обов'язковий/необов'язковий | Опис                                                                                                                                                   | Приклад                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Позначка часу | Обов'язковий          | Позначка часу події (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Обов'язковий          | Ідентифікатор ресурсу екземпляра, який випустив подію.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Обов'язковий          | Назва операції, представленої цією подією. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Докладніше про типи [операцій див](#operation-types). | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Обов'язковий          | Категорія журналу події. Завжди `Operational` для подій робочого циклу                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Обов'язковий          | Статус події. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Довге значення      | Необов'язково          | Тривалість операції в мілісекундах.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Необов'язково          | Об'єкт JSON з більшою кількістю властивостей для конкретної категорії подій.                                                                                        | Переглянути властивості робочого циклу під [розділу](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Обов'язковий          | Рівень тяжкості події.                                                                                                                                  | `Informational`, `Warning` або `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Схема властивостей робочого циклу

Події робочого циклу мають такі властивості.

| Поле              | Workflow | Завдання | Опис            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Так      | Так  | Завжди `WorkflowEvent` позначати подію як подію робочого циклу.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Так      | Так  | Ідентифікатор запуску робочого циклу. Усі події робочого циклу та завдань у виконанні робочого циклу мають однакові `workflowJobId` значення.                                                                                                                                   |
| `properties.operationType`                   | Так      | Так  | Ідентифікатор операції [див](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Так      | No   | Лише робочий цикл. Кількість завдань, які запускає робочий цикл.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Так      | No   | Необов'язково. Лише події робочого циклу. Ідентифікатор Azure Active Directory [об'єкта користувача](/azure/marketplace/find-tenant-object-id#find-user-object-id), який ініціював робочий цикл, див `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Так      | No   | `full` або `incremental` оновити.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Так      | No   | `OnDemand` або `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Так      | No   | `Running` або `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Так      | Так  | Позначка часу UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Так      | Так  | Позначка часу UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Так      | Так  | Позначка часу UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Так      | Так  | Статистика клієнтів`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Так  | - Для OperationType = `Export`, ідентифікатор є guid конфігурації експорту. <br> - Для OperationType = `Enrichment`, це напрямок збагачення <br> - Для OperationType `Measures` і `Segmentation`, ідентифікатор є ім'ям сутності. |
| `properties.friendlyName`                    | No       | Так  | Зручне ім'я експорту або сутності, яка обробляється.                                                                                                                                                                                           |
| `properties.error`                           | No       | Так  | Необов'язково. Повідомлення про помилку з додатковими відомостями.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Так  | Необов'язково. Лише для типу `Export` операції. Визначає тип експорту. Для отримання додаткових [відомостей див](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Так  | Необов'язково. Лише для типу `Export` операції. Містить список налаштованих сутностей в експорті.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Так  | Необов'язково. Лише для типу `Export` операції. Докладне повідомлення для експорту.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Так  | Необов'язково. Лише для типу `Segmentation` операції. Указує загальну кількість учасників сегмента.                                                                                                                                                    |
