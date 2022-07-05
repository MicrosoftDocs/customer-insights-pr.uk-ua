---
title: Журнал пересилання за Dynamics 365 Customer Insights допомогою монітора Azure (попередній перегляд)
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
ms.openlocfilehash: 8c72df7054a682244215bbee54968d6aef4bbf59
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052678"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Журнал пересилання за Dynamics 365 Customer Insights допомогою монітора Azure (попередній перегляд)

Dynamics 365 Customer Insights забезпечує пряму інтеграцію з Azure Monitor. Журнали ресурсів Azure Monitor дозволяють відстежувати та надсилати журнали до [сховища Azure,](https://azure.microsoft.com/services/storage/) Azure Log Analytics [або передавати їх потоком до](/azure/azure-monitor/logs/log-analytics-overview)[Центрів подій Azure](https://azure.microsoft.com/services/event-hubs/).

Customer Insights надсилає такі журнали подій:

- **Аудиторські заходи**
  - **APIEvent** - дозволяє відстежувати зміни, здійснені Dynamics 365 Customer Insights через інтерфейс користувача.
- **Операційні заходи**
  - **WorkflowEvent** - Робочий процес дозволяє налаштувати [джерела](data-sources.md) даних, уніфікувати [,](data-unification.md)[збагатити](enrichment-hub.md) та, нарешті [, експортувати](export-destinations.md) дані в інші системи. Всі ці кроки можна зробити індивідуально (наприклад, запустити один експорт). Також можна запустити організовано (наприклад, оновлення даних з джерел даних, що запускає процес уніфікації, який потягне за собою збагачення і після завершення експорту даних в іншу систему). Щоб отримати додаткові відомості, перегляньте [схему](#workflow-event-schema) WorkflowEvent.
  - **APIEvent** - всі ВИКЛИКИ API на екземпляр клієнтів до Dynamics 365 Customer Insights. Для отримання додаткової інформації перегляньте [схему](#api-event-schema) APIEvent.

## <a name="set-up-the-diagnostic-settings"></a>Настроювання параметрів діагностики

### <a name="prerequisites"></a>вимоги

Для налаштування діагностики в Customer Insights повинні бути дотримані наступні передумови:

- У вас є активна [підписка Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- У вас є [дозволи адміністратора](permissions.md#admin) в Customer Insights.
- Ви виконуєте **роль постачальника** та **адміністратора** доступу користувачів у цільовому ресурсі в Azure. Ресурсом може бути обліковий Azure Data Lake Storage запис, Центр подій Azure або робоча область Azure Log Analytics. Для отримання додаткових відомостей перегляньте статтю [Додавання або видалення рольових призначень Azure за допомогою порталу](/azure/role-based-access-control/role-assignments-portal) Azure. Цей дозвіл необхідний під час налаштування діагностичних налаштувань в Customer Insights, його можна змінити після успішного налаштування.
- [Цільові вимоги для](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) сховища Azure, Центру подій Azure або Azure Log Analytics виконані.
- У вас є принаймні роль Читача **в** групі ресурсів, до якої належить ресурс.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Настроювання діагностики за допомогою монітора Azure

1. У розділі Customer Insights виберіть елемент **Діагностика** > **системи**, щоб переглянути місця діагностики, настроєні в цьому екземплярі.

1. Виберіть елемент **Додати ціль**.

   > [!div class="mx-imgBorder"]
   > ![підключення діагностики](media/diagnostics-pane.png "підключення діагностики")

1. Вкажіть ім'я в **полі Призначення для діагностики Ім'я для діагностики**.

1. **Виберіть клієнт** передплати Azure з цільовим ресурсом і виберіть команду **Увійти**.

1. **Виберіть тип** ресурсу (обліковий запис сховища, центр подій або аналітика журналу).

1. Виберіть елемент Передплата **для** цільового ресурсу.

1. **Виберіть групу «Ресурси»** для цільового ресурсу.

1. **Виберіть ресурс**.

1. Підтвердьте декларацію про **конфіденційність і відповідність даних**.

1. Виберіть елемент **Підключитися до системи**, щоб підключитися до цільового ресурсу. Журнали починають з'являтися в місці призначення через 15 хвилин, якщо API використовується і генерує події.

### <a name="remove-a-destination"></a>Видалення цілі

1. Перейдіть до **розділу Діагностика** > **системи**.

1. Виберіть місце діагностики у списку.

1. У стовпці **Дії** виберіть піктограму **Видалити**.

1. Підтвердіть видалення, щоб зупинити пересилання журналу. Ресурс у підписці Azure не буде видалено. Ви можете вибрати посилання в стовпці **Дії**, щоб відкрити портал Azure для вибраного ресурсу і видалити його там.

## <a name="log-categories-and-event-schemas"></a>Категорії журналів і схеми подій

Наразі [підтримуються події](apis.md) API та події робочого процесу, а також застосовуються такі категорії та схеми.
Схема журналу відповідає загальній схемі [Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Категорії

Customer Insights надає дві категорії:

- **Події** аудиту: [події](#api-event-schema) API для відстеження змін конфігурації на сервісі. `POST|PUT|DELETE|PATCH` операції переходять в цю категорію.
- **Операційні події**: [події](#api-event-schema) API або [події](#workflow-event-schema) робочого процесу, згенеровані під час використання сервісу.  Наприклад, `GET` запити або події виконання робочого циклу.

## <a name="configuration-on-the-destination-resource"></a>Конфігурація на цільовому ресурсі

Виходячи з вашого вибору за типом ресурсу, автоматично застосовуватимуться наступні кроки:

### <a name="storage-account"></a>Обліковий запис сховища

Директор служби Customer Insights отримує **дозвіл постачальника** облікового запису сховища на вибраний ресурс і створює два контейнери у вибраному просторі імен:

- `insight-logs-audit` що містять аудиторські **заходи**
- `insight-logs-operational` що містять оперативні **заходи**

### <a name="event-hub"></a>Концентратор подій

Директор служби Customer Insights отримує **дозвіл власника** даних Центрів подій Azure на ресурсі та створить два центри подій у вибраному просторі імен:

- `insight-logs-audit` що містять аудиторські **заходи**
- `insight-logs-operational` що містять оперативні **заходи**

### <a name="log-analytics"></a>Аналітика журналів

Директор служби Customer Insights отримує **дозвіл постачальника** log analytics на ресурсі. Журнали будуть доступні в розділі **Керування** > **журналами таблиць** > **журналів** у вибраній робочій області Log Analytics. Розгорніть рішення для **керування журналами** та знайдіть таблиці `CIEventsAudit` та `CIEventsOperational` таблиці.

- `CIEventsAudit` що містять аудиторські **заходи**
- `CIEventsOperational` що містять оперативні **заходи**

**У вікні Запити** розгорніть **рішення аудиту** та знайдіть приклади запитів, що надаються під `CIEvents` час пошуку.

## <a name="event-schemas"></a>Схеми подій

Події API та події робочого процесу мають загальну структуру та деталі, де вони відрізняються, перегляньте [схему](#api-event-schema) подій API або [схему](#workflow-event-schema) подій робочого процесу.

### <a name="api-event-schema"></a>Схема подій API

| Поле             | Тип даних  | Обов'язково/необов'язково | Опис       | Приклад        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Позначка часу | Обов'язковий          | Позначка часу події (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Обов'язковий          | ResourceId випадку, який випустив подію         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Обов'язковий          | Назва операції, представленої цією подією.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Обов'язковий          | Журнал категорії заходу. Або `Operational` або `Audit`. Усі ЗАПИТИ POST/PUT/PATCH/DELETE HTTP позначені тегами `Audit`, все інше за допомогою`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Обов'язковий          | Статус заходу. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Необов'язково          | Статус результату заходу. Якщо операція відповідає виклику REST API, це код стану HTTP.        | `200`             |
| `durationMs`      | Довге значення      | Необов'язково          | Тривалість операції в мілісекундах.     | `133`     |
| `callerIpAddress` | String    | Необов'язково          | IP-адреса абонента, якщо операція відповідає виклику API, який надходить із загальнодоступної IP-адреси.                                                 | `144.318.99.233`         |
| `identity`        | String    | Необов'язково          | Об'єкт JSON, що описує особу користувача або програми, яка виконувала операцію.       | Дивіться [розділ "Посвідчення"](#identity-schema).     |  
| `properties`      | String    | Необов'язково          | Об'єкт JSON з більшими властивостями до конкретної категорії подій.      | Дивіться [Розділ Властивості](#api-properties-schema).    |
| `level`           | String    | Обов'язковий          | Рівень тяжкості події.    | `Informational`, `Warning`,, `Error` або `Critical`.           |
| `uri`             | String    | Необов'язково          | Абсолютний запит URI.    |               |

#### <a name="identity-schema"></a>Схема ідентифікації

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
| `Authorization.UserRole`      | Призначена роль для користувача або програми. Щоб отримати додаткові відомості, перегляньте [дозволи](permissions.md) користувачів.                                     |
| `Authorization.RequiredRoles` | Необхідні ролі для проведення операції. `Admin` роль дозволяється виконувати всі операції.                                                    |
| `Claims`                      | Претензії користувача або додатка веб-токена JSON (JWT). Властивості претензії залежать від організації та конфігурації Azure Active Directory. |

#### <a name="api-properties-schema"></a>Схема властивостей API

[Події](apis.md) API мають такі властивості.

| Поле                        | Опис                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Завжди `ApiEvent`, позначаючи подію журналу як подію API.                                                                 |
| `properties.userAgent`       | Агент браузера, що відправляє запит або `unknown`.                                                                        |
| `properties.method`          | Метод HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Відносний шлях запиту.                                                                                          |
| `properties.origin`          | URI, що вказує, звідки береться прибуток або `unknown`.                                                                  |
| `properties.operationStatus` | `Success` код статусу HTTP < 400 <br> `ClientError` для HTTP Код статусу < 500 <br> `Error` для > статусу HTTP= 500 |
| `properties.tenantId`        | Ідентифікатор організації                                                                                                        |
| `properties.tenantName`      | Назва організації.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Об'єктІд з того, хто телефонує.                                                                         |
| `properties.instanceId`      | Статистика клієнтів`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Схема події робочого циклу

Робочий цикл містить кілька кроків. [Поглинайте джерела](data-sources.md) даних, [уніфікуйте](data-unification.md), [збагачуйте](enrichment-hub.md) та [експортуйте](export-destinations.md) дані. Усі ці кроки можуть працювати індивідуально або оркеструватися з наступними процесами.

#### <a name="operation-types"></a>види операцій

| OperationType     | Групувати                                     |
| ----------------- | ----------------------------------------- |
| Прийому         | [Джерела даних](data-sources.md)           |
| Підготовка даних   | [Джерела даних](data-sources.md)           |
| Зіставлення               | [Уніфікація даних](data-unification.md)   |
| Збіг             | [Уніфікація даних](data-unification.md)   |
| Злиття             | [Уніфікація даних](data-unification.md)   |
| ПрофайлШодер      | [Профілі клієнтів](customer-profiles.md) |
| Введіть пошуковий запит            | [Профілі клієнтів](customer-profiles.md) |
| Активність          | [Справи](activities.md)                  |
| АтрибутЗаходи | [Сегменти та заходи](segments.md)      |
| СутністьЗаходи    | [Сегменти та заходи](segments.md)      |
| Вимірювання          | [Сегменти та заходи](segments.md)      |
| Сегментація      | [Сегменти та заходи](segments.md)      |
| Збагачення        | [Збагачення](enrichment-hub.md)                                          |
| Аналітика      | [Прогнози](predictions-overview.md)                                          |
| AiBuilder         | [Прогнози](predictions-overview.md)                                          |
| Аналітика          | [Прогнози](predictions-overview.md)                                          |
| Export            | [Операції експорту](export-destinations.md)                                          |
| Модельне управління   | [Прогнози](custom-models.md)                                           |
| Зв’язки      | [Уніфікація даних](relationships.md)                                           |

#### <a name="field-description"></a>Опис поля

| Поле           | Тип даних  | Обов'язково/необов'язково | Опис                                                                                                                                                   | Приклад                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Позначка часу | Обов'язковий          | Позначка часу події (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Обов'язковий          | ResourceId екземпляра, який випромінював подію.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Обов'язковий          | Назва операції, представленої цією подією. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Дивіться [Типи](#operation-types) операцій для довідки. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Обов'язковий          | Журнал категорії заходу. Завжди `Operational` для подій робочого циклу                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Обов'язковий          | Статус заходу. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Довге значення      | Необов'язково          | Тривалість операції в мілісекундах.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Необов'язково          | Об'єкт JSON з більшими властивостями до конкретної категорії подій.                                                                                        | Переглянути підрубрику [Властивості робочого циклу](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Обов'язковий          | Рівень тяжкості події.                                                                                                                                  | `Informational`, `Warning` або `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Схема властивостей робочого циклу

Події робочого циклу мають такі властивості.

| Поле              | Workflow | Завдання | Опис            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Так      | Так  | Завжди `WorkflowEvent`, позначаючи подію як подію робочого процесу.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Так      | Так  | Ідентифікатор запущеного робочого циклу. Усі події робочого циклу та завдання у виконанні робочого циклу мають однаковий `workflowJobId` характер.                                                                                                                                   |
| `properties.operationType`                   | Так      | Так  | Ідентифікатор операції [див](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Так      | No   | Тільки робочий процес. Кількість завдань, які ініціює робочий цикл.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Так      | No   | Необов'язково. Лише події робочого циклу. Об'єктІд Azure Active Directory [користувача](/azure/marketplace/find-tenant-object-id#find-user-object-id), який ініціював робочий цикл, див `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Так      | No   | `full` або `incremental` оновити.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Так      | No   | `OnDemand` або `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Так      | No   | `Running` або `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Так      | Так  | Часова позначка UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Так      | Так  | Часова позначка UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Так      | Так  | Часова позначка UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Так      | Так  | Статистика клієнтів`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Так  | - Для OperationType = `Export`, ідентифікатор є керівництвом конфігурації експорту. <br> - Для операціїType = `Enrichment`, це керівництво збагаченням <br> - Для OperationType `Measures` і `Segmentation`, ідентифікатором є назва сутності. |
| `properties.friendlyName`                    | No       | Так  | Зручна назва експорту або суб'єкта господарювання, що обробляється.                                                                                                                                                                                           |
| `properties.error`                           | No       | Так  | Необов'язково. Повідомлення про помилку з докладнішими відомостями.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Так  | Необов'язково. Тільки для операціїType `Export`. Визначає тип експорту. Для отримання додаткової інформації дивіться [огляд напрямків](export-destinations.md) експорту.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Так  | Необов'язково. Тільки для операціїType `Export`. Містить список налаштованих сутностей в експорті.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Так  | Необов'язково. Тільки для операціїType `Export`. Детальне повідомлення для експорту.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Так  | Необов'язково. Тільки для операціїType `Segmentation`. Вказується загальна кількість членів, які має сегмент.                                                                                                                                                    |
