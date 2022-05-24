---
title: OData приклади для Dynamics 365 Customer Insights API
description: Зазвичай використовуються приклади протоколу відкритих даних (OData) для запиту API статистики клієнтів для перевірки даних.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740078"
---
# <a name="odata-query-examples"></a>Приклади запитів OData

Протокол відкритих даних (OData) - це протокол доступу до даних, побудований на основних протоколах, таких як HTTP. Він використовує загальноприйняті методології, такі як REST для Інтернету. Існують різні типи бібліотек та інструментів, які можна використовувати для споживання послуг OData.

У цій статті перелічено деякі часто запитані приклади запитів, які допоможуть вам створити власні реалізації на [основі API статистики клієнтів](apis.md).

Ви повинні змінити зразки запит на змінення, щоб змусити їх працювати на цільових середовищах: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` де {instanceId} знаходиться GUID середовища статистики клієнтів, яке потрібно запитати. За [допомогою операції](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) ListAllInstances ви можете знайти доступ до {InstanceId} якого ви маєте доступ.
- {CID}: GUID уніфікованого запису клієнта. Приклад:`ce759201f786d590bf2134bff576c369`
- {AlternateKey}: Ідентифікатор первинного ключа запису клієнта в джерело даних. Приклад: `CNTID_1002`
- {DSname}: Рядок з іменем сутності джерело даних, яка потрапляє до статистики клієнтів. Приклад:`Website_contacts`
- {SegmentName}: Рядок з ім'ям вихідної сутності сегмента в "Інсайті клієнта". Приклад:`Male_under_40`

## <a name="customer"></a>клієнте

Наведена нижче таблиця містить набір зразків запитів для *сутності Клієнта*.


|Тип запиту |Приклад  | Нотатка  |
|---------|---------|---------|
|Єдиний ідентифікатор клієнта     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|альтернативний ключ    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  Альтернативні ключі зберігаються в об'єднаній сутності клієнта       |
|Вибір   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|У    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|альтернативний ключ + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Введіть пошуковий запит  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Повертає 10 найкращих результатів для рядка пошуку      |
|Членство в сегменті  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | Повертає задану кількість рядків із сутності сегментації.      |

## <a name="unified-activity"></a>Уніфікована діяльність

Наведена нижче таблиця містить набір зразків запитів для *сутності UnifiedActivity*.

|Тип запиту |Приклад  | Нотатка  |
|---------|---------|---------|
|Діяльність CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Список дій певного профілю клієнта |
|Часові рамки активності    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Дії профілю клієнта в часові рамки       |
|Тип справи    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Справи за коротким ім'ям     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|Сортування активності    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Сортування дій за зростанням або за спаданням       |
|Діяльність, розширена від членства в сегменті  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Нижче наведено інші приклади

Наведена нижче таблиця містить набір зразків запитів для інших сутностей.

|Тип запиту |Приклад  | Нотатка  |
|---------|---------|---------|
|Заходи CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Збагачені бренди CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Збагачені інтереси CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|У клавці + розгорнути     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |
