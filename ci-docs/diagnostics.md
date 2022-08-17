---
title: Експорт діагностичних журналів (попередній перегляд)
description: Дізнайтеся, як надсилати журнали на Microsoft Azure монітор.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245950"
---
# <a name="export-diagnostic-logs-preview"></a>Експорт діагностичних журналів (попередній перегляд)

Пересилання журналів із Customer Insights за допомогою Azure Monitor. Журнали ресурсів Azure Monitor дають змогу відстежувати та надсилати журнали до [Сховища Azure,](https://azure.microsoft.com/services/storage/) Azure Log Analytics [або передавати їх до](/azure/azure-monitor/logs/log-analytics-overview) Центрів подій Azure.[...](https://azure.microsoft.com/services/event-hubs/)

Customer Insights надсилає такі журнали подій:

- **Заходи аудиту**
  - **APIEvent** - дозволяє відстежувати зміни через Dynamics 365 Customer Insights інтерфейс користувача.
- **Оперативні заходи**
  - **WorkflowEvent** - дозволяє налаштовувати [джерела](data-sources.md) даних, [уніфікувати](data-unification.md), [збагачувати](enrichment-hub.md) та [експортувати](export-destinations.md) дані в інші системи. Ці кроки можна виконати індивідуально (наприклад, ініціювати один експорт). Вони також можуть запускатися організовано (наприклад, оновлення даних з джерел даних, які запускають процес уніфікації, що призведе до збагачення та експорту даних в іншу систему). Для отримання додаткових відомостей перегляньте [схему workflowEvent.](#workflow-event-schema)
  - **APIEvent** - відправляє всі виклики API екземпляра клієнтів на Dynamics 365 Customer Insights адресу. Для отримання додаткової інформації дивіться [схему](#api-event-schema) APIEvent.

## <a name="set-up-the-diagnostic-settings"></a>Настроювання параметрів діагностики

### <a name="prerequisites"></a>вимоги

- Активна [підписка Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Дозволи адміністратора](permissions.md#admin) в Розділі "Статистика клієнтів".
- [Роль](/azure/role-based-access-control/role-assignments-portal) постачальника та адміністратора доступу користувачів на цільовому ресурсі в Azure. Ресурс може бути обліковим записом Azure Data Lake Storage, центром подій Azure або робочою областю Azure Log Analytics. Цей дозвіл необхідний під час настроювання параметрів діагностики в Customer Insights, але його можна змінити після успішного настроювання.
- [Цільові вимоги для](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) Сховища Azure, Центру подій Azure або Azure Log Analytics виконуються.
- Принаймні роль Читача **в** групі ресурсів, до якої належить ресурс.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Настроювання діагностики за допомогою монітора Azure

1. У розділі Customer Insights перейдіть до **адміністративної** > **системи** та виберіть вкладку **Діагностика**.

1. Виберіть Додати **ціль**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Діагностика підключення.":::

1. Вкажіть ім’я в полі Ім’я **для призначення** діагностики.

1. **Виберіть тип** ресурсу (Обліковий запис сховища, Центр подій або Log Analytics).

1. Виберіть елемент Передплата, група **Ресурсів і** Ресурс **для цільового** ресурсу.**·** Перегляньте розділ [Конфігурація на цільовому ресурсі](#configuration-on-the-destination-resource), щоб отримати дозвіл і відомості журналу.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Виберіть Підключитися **до системи**, щоб підключитися до цільового ресурсу. Журнали починають з’являтися в пункті призначення через 15 хвилин, якщо API використовується і генерує події.

## <a name="configuration-on-the-destination-resource"></a>Конфігурація на цільовому ресурсі

Виходячи з вашого вибору типу ресурсу, автоматично відбуваються наступні зміни:

### <a name="storage-account"></a>Обліковий запис сховища

Директор служби Customer Insights отримує **дозвіл постачальника** облікового запису сховища на вибраному ресурсі та створює два контейнери під вибраним простором імен:

- `insight-logs-audit` що містять аудиторські **заходи**
- `insight-logs-operational` що містять оперативні **події,**

### <a name="event-hub"></a>Концентратор подій

Директор служби Customer Insights отримує **дозвіл власника** даних Azure Event Hubs на ресурсі та створює два Центри подій під вибраним простором імен:

- `insight-logs-audit` що містять аудиторські **заходи**
- `insight-logs-operational` що містять оперативні **події,**

### <a name="log-analytics"></a>Аналітика журналів

Директор служби Customer Insights отримує **дозвіл постачальника** Log Analytics на ресурсі. Журнали доступні в розділі **Керування** > **журналами таблиць** > **журналів** у вибраній робочій області Log Analytics. **Розгорніть рішення "Керування журналами**" та знайдіть таблиці `CIEventsAudit` та `CIEventsOperational` таблиці.

- `CIEventsAudit` що містять аудиторські **заходи**
- `CIEventsOperational` що містять оперативні **події,**

**У вікні Запити** розгорніть **рішення Аудит** і знайдіть приклад запитів, наданих під час пошуку .`CIEvents`

## <a name="remove-a-diagnostics-destination"></a>Видалення призначення діагностики

1. Перейдіть до **адміністративної** > **системи** та виберіть вкладку **Діагностика**.

1. Виберіть місце призначення діагностики в списку.

   > [!TIP]
   > Видалення пункту призначення зупиняє переадресацію журналу, але не видаляє ресурс за передплатою Azure. Щоб видалити ресурс в Azure, виберіть посилання в **стовпці Дії**, щоб відкрити портал Azure для обраного ресурсу і видаліть його там. Потім видаліть призначення діагностики.

1. У стовпці **Дії** виберіть піктограму **Видалити**.

1. Підтвердіть видалення, щоб видалити пункт призначення, і припиніть пересилання журналу.

## <a name="log-categories-and-event-schemas"></a>Категорії журналів і схеми подій

Наразі [підтримуються події](apis.md) API та події робочого циклу, застосовуються такі категорії та схеми.
Схема журналу відповідає загальній схемі [Azure](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema) Monitor.

### <a name="categories"></a>Категорії

Customer Insights містить дві категорії:

- **Події** аудиту: [події](#api-event-schema) API для відстеження змін конфігурації на сервісі. `POST|PUT|DELETE|PATCH` операції переходять в цю категорію.
- **Операційні події**: [події API або](#api-event-schema) події [робочого процесу,](#workflow-event-schema) що генеруються під час використання сервісу.  Наприклад, `GET` запити або події виконання робочого циклу.

## <a name="event-schemas"></a>Схеми подій

Події API та події робочого процесу мають загальну структуру, але з кількома відмінностями. Для отримання додаткової інформації перегляньте [схему подій API або](#api-event-schema) схему [подій робочого циклу](#workflow-event-schema).

### <a name="api-event-schema"></a>Схема подій API

| Поле             | Тип даних  | Обов’язково/Необов’язково | Опис       | Приклад        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Позначка часу | Обов'язковий          | Позначка часу події (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Обов'язковий          | ResourceId екземпляра, який випустив подію         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Обов'язковий          | Назва операції, представленої даним заходом.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Обов'язковий          | Категорія журналу події. Або `Operational` або `Audit`. Усі запити HTTP POST/PUT/PATCH/DELETE позначені тегами `Audit`, все інше з`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Обов'язковий          | Статус заходу. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Необов'язково          | Підсумковий статус заходу. Якщо операція відповідає виклику REST API, це код стану HTTP.        | `200`             |
| `durationMs`      | Довге значення      | Необов'язково          | Тривалість операції в мілісекундах.     | `133`     |
| `callerIpAddress` | String    | Необов'язково          | IP-адреса абонента, якщо операція відповідає виклику API, який надходить із загальнодоступної IP-адреси.                                                 | `144.318.99.233`         |
| `identity`        | String    | Необов'язково          | Об’єкт JSON, що описує особу користувача або програми, яка виконувала операцію.       | Дивіться [розділ "Ідентичність"](#identity-schema).     |  
| `properties`      | String    | Необов'язково          | Об’єкт JSON з більшою кількістю властивостей до певної категорії подій.      | Дивіться [розділ Властивості](#api-properties-schema).    |
| `level`           | String    | Обов'язковий          | Рівень тяжкості заходу.    | `Informational`, `Warning`, `Error`, або `Critical`.           |
| `uri`             | String    | Необов'язково          | Абсолютний запит URI.    |               |

#### <a name="identity-schema"></a>Схема ідентичності

Об’єкт `identity` JSON має наступну структуру

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
| `Authorization.UserRole`      | Призначена роль для користувача або програми. Щоб отримати додаткові відомості, перегляньте [розділ Дозволи](permissions.md) користувачів.                                     |
| `Authorization.RequiredRoles` | Необхідні ролі для виконання операції. `Admin` роль дозволяється виконувати всі операції.                                                    |
| `Claims`                      | Претензії користувача або веб-токена JSON (JWT). Властивості претензій залежать від організації та конфігурації Azure Active Directory. |

#### <a name="api-properties-schema"></a>Схема властивостей API

[Події](apis.md) API мають такі властивості.

| Поле                        | Опис                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Завжди `ApiEvent`, позначаючи подію журналу як подію API.                                                                 |
| `properties.userAgent`       | Браузерний агент, що відправляє запит або `unknown`.                                                                        |
| `properties.method`          | Метод HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Відносний шлях запиту.                                                                                          |
| `properties.origin`          | URI, що вказує, звідки береться отримання або `unknown`.                                                                  |
| `properties.operationStatus` | `Success` для коду стану HTTP < 400 <br> `ClientError` для коду стану HTTP < 500 <br> `Error` для > стану HTTP= 500 |
| `properties.tenantId`        | Ідентифікатор організації                                                                                                        |
| `properties.tenantName`      | Назва організації.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Об’єкт Ід того, хто телефонує.                                                                         |
| `properties.instanceId`      | Інсайти клієнтів`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Схема події робочого циклу

Робочий цикл містить кілька кроків. [Отримувати джерела](data-sources.md) даних, [уніфікувати](data-unification.md), [збагачувати](enrichment-hub.md) та [експортувати](export-destinations.md) дані. Усі ці кроки можуть виконуватися окремо або організовано за допомогою наступних процесів.

#### <a name="operation-types"></a>типи операцій

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
| Атрибутиздатності | [Сегменти та міри](segments.md)      |
| Сутністьзрозуміє    | [Сегменти та міри](segments.md)      |
| Вимірювання          | [Сегменти та міри](segments.md)      |
| Сегментація      | [Сегменти та міри](segments.md)      |
| Збагачення        | [Збагачення](enrichment-hub.md)                                          |
| Аналітика      | [Прогнози](predictions-overview.md)                                          |
| AiBuilder         | [Прогнози](predictions-overview.md)                                          |
| Аналітика          | [Прогнози](predictions-overview.md)                                          |
| Export            | [Операції експорту](export-destinations.md)                                          |
| Модельменеджмент   | [Прогнози](custom-models.md)                                           |
| Зв’язки      | [Уніфікація даних](relationships.md)                                           |

#### <a name="field-description"></a>Опис поля

| Поле           | Тип даних  | Обов’язково/Необов’язково | Опис                                                                                                                                                   | Приклад                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Позначка часу | Обов'язковий          | Позначка часу події (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Обов'язковий          | ResourceId екземпляра, який випустив подію.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Обов'язковий          | Назва операції, представленої даним заходом. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Дивіться [Типи](#operation-types) операцій для довідки. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Обов'язковий          | Категорія журналу події. Завжди `Operational` для подій робочого циклу                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Обов'язковий          | Статус заходу. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Довге значення      | Необов'язково          | Тривалість операції в мілісекундах.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Необов'язково          | Об’єкт JSON з більшою кількістю властивостей до певної категорії подій.                                                                                        | Перегляньте підрозділ Властивості [робочого циклу](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Обов'язковий          | Рівень тяжкості заходу.                                                                                                                                  | `Informational`, `Warning` або `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Схема властивостей робочого циклу

Події робочого циклу мають такі властивості.

| Поле              | Workflow | Завдання | Опис            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Так      | Так  | Завжди `WorkflowEvent`, позначаючи подію як подію робочого циклу.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Так      | Так  | Ідентифікатор виконуваного робочого циклу. Усі події робочого циклу та завдань у процесі виконання робочого циклу мають однаковий вигляд `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Так      | Так  | Ідентифікатор операції дивіться [Типи](#operation-types) операцій.                                                                                                                                                                               |
| `properties.tasksCount`                      | Так      | No   | Лише робочий цикл. Кількість завдань, які запускає робочий процес.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Так      | No   | Необов'язково. Лише події робочого циклу. Об’єктІде Azure Active Directory [користувача](/azure/marketplace/find-tenant-object-id#find-user-object-id), який запустив робочий процес, див.`properties.workflowSubmissionKind`                                   |
| `properties.workflowType`                    | Так      | No   | `full` або `incremental` оновити.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Так      | No   | `OnDemand` або `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Так      | No   | `Running` або `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Так      | Так  | Часова позначка UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Так      | Так  | Часова позначка UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Так      | Так  | Часова позначка UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Так      | Так  | Інсайти клієнтів`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Так  | - Для OperationType = `Export`, ідентифікатор є дороговказом експортної конфігурації. <br> - Для OperationType = `Enrichment`, це дороговказ збагачення <br> - Для OperationType `Measures` і `Segmentation`, ідентифікатором є ім’я сутності. |
| `properties.friendlyName`                    | No       | Так  | Зручна назва експорту або організації, яка обробляється.                                                                                                                                                                                           |
| `properties.error`                           | No       | Так  | Необов'язково. Повідомлення про помилку з докладними відомостями.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Так  | Необов'язково. Лише для operationType `Export`. Визначає тип експорту. Щоб отримати додаткові відомості, перегляньте [огляд напрямків](export-destinations.md) експорту.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Так  | Необов'язково. Лише для operationType `Export`. Містить список налаштованих сутностей в експорті.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Так  | Необов'язково. Лише для operationType `Export`. Докладне повідомлення для експорту.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Так  | Необов'язково. Лише для operationType `Segmentation`. Указує загальну кількість учасників сегмента.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
