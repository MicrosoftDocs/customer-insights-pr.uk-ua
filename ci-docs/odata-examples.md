---
title: Приклади запитів OData для API Customer Insights
description: Зазвичай використовуються приклади протоколу відкритих даних (OData) для запиту API Customer Insights для перегляду даних.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8843fc04e4e6eaba0019d932c54f62561ffbdb92
ms.sourcegitcommit: f3c12ad445d5f91a88f91a7bbc40790ebcfaa826
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/06/2022
ms.locfileid: "9121587"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Приклади запитів OData для API Customer Insights

Протокол відкритих даних (OData) - це протокол доступу до даних, побудований на основних протоколах, таких як HTTP. Він використовує загальноприйняті методології, такі як REST для Інтернету. Існують різного роду бібліотеки та інструменти, які можна використовувати для споживання служб OData.

У цій статті наведено кілька часто запитаних прикладів, які допоможуть вам створити власні реалізації на [основі API Customer Insights](apis.md).

Потрібно змінити зразки запитів, щоб вони працювали в цільових середовищах: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` де {instanceId} – ідентифікатор середовища Customer Insights, до якого потрібно надіслати запит. Операція [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) дозволяє знайти доступ {InstanceId} до нього.
- {CID}: GUID єдиного запису клієнта. Приклад:`ce759201f786d590bf2134bff576c369`
- {AlternateKey}: Ідентифікатор первинного ключа запису клієнта в джерело даних. Приклад: `CNTID_1002`
- {DSname}: Рядок із назвою сутності джерело даних, який потрапляє до Customer Insights. Приклад:`Website_contacts`
- {SegmentName}: Рядок з іменем вихідної сутності сегмента в Customer Insights. Приклад:`Male_under_40`

## <a name="customer"></a>клієнте

У таблиці нижче наведено набір зразків запитів для юридичної *особи клієнта*.

|Тип запиту |Приклад  | Нотатка  |
|---------|---------|---------|
|Єдиний ідентифікатор клієнта     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|альтернативний ключ    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Альтернативні ключі зберігаються в єдиній сутності клієнта       |
|Вибір   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|У    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|альтернативний ключ + В   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Введіть пошуковий запит  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Повертає 10 найкращих результатів для рядка пошуку.      |
|Членство в сегменті  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Повертає задану кількість рядків від сутності сегментації.      |
|Сегментне членство для клієнта | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Повертає профіль клієнта, якщо він є учасником указаного сегмента.     |

## <a name="unified-activity"></a>Єдина діяльність

У таблиці нижче наведено набір зразків запитів для *сутності UnifiedActivity*.

|Тип запиту |Приклад  | Нотатка  |
|---------|---------|---------|
|Діяльність CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Список дій певного профілю клієнта |
|Часові рамки діяльності    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Діяльність профілю клієнта в часових рамках       |
|Тип справи    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Дія за коротким іменем     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Сортування діяльності    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Сортування дій за зростанням або спаданням       |
|Діяльність розширена за рахунок членства в сегменті  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Нижче наведено інші приклади

У таблиці нижче наведено набір зразків запитів для інших сутностей.

|Тип запиту |Приклад  | Нотатка  |
|---------|---------|---------|
|Показники CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Збагачені марки CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Збагачені інтереси CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-clause + Розгорнути     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Не підтримуються запити OData

Наведені нижче запити не підтримуються в Customer Insights.

- `$filter` на проковтнуті вихідні сутності. Ви можете виконувати лише $filter запити щодо системних сутностей, які створює Customer Insights.
- `$expand``$search` із запиту. Приклад: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` з `$select`, якщо виділено лише підмножину атрибутів. Приклад: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` збагачений бренд або спорідненість інтересів для даного клієнта. Приклад: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Запит прогноз моделі вихідних сутностей через альтернативний ключ. Приклад: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
