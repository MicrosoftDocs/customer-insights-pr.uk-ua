---
title: Найбільший доступ до даних з Azure Synapse Analytics
description: Використання бази даних як Azure Synapse джерело даних у програми Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356057"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse Підключення джерело даних (попередній перегляд)

Azure Synapse Analytics це служба аналітики підприємства, яка прискорює час для розуміння на складах даних та системах великих даних. Azure Synapse Analytics Об'єднує найкращі технології SQL, що використовуються в складуванні корпоративних даних, технології Spark, що використовуються для великих даних, Data Explorer для аналізу журналів та часових рядів, трубопроводи для інтеграції даних та ETL /ELT, а також глибоку інтеграцію з іншими службами Azure, такими як Power BI, Cosmos DB та AzureML.

Для отримання додаткових відомостей див [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>вимоги

Щоб налаштувати підключення Customer Insights до Azure Synapse, потрібно виконати наведені нижче попередні вимоги.

> [!IMPORTANT]
> Переконайтеся, що задано всі **призначення ролей**, як описано.  

## <a name="prerequisites-in-customer-insights"></a>Попередні вимоги в Customer Insights

* У вас є **роль адміністратора** в інсайтах клієнтів. Докладніше про [дозволи для користувачів в аналізі аудиторії](permissions.md#assign-roles-and-permissions)

В Azure: 

- Активна передплата Azure.

- Якщо використовується новий обліковий запис Azure Data Lake Storage Gen2, для *принципала служби для аналізу аудиторії* необхідні дозволи **Постачальника даних BLOB-об’єктів сховища**. Докладніше про [підключення до принципала Azure Data Lake Storage служби для отримання статистики аудиторії](connect-service-principal.md). Для сховища Data Lake Storage Gen2 **необхідно** увімкнути [ієрархічний простір імен](/azure/storage/blobs/data-lake-storage-namespace).

- У групі ресурсів, де розташована робоча область Azure Synapse, *принципал служби* та *користувач для аналізу аудиторії* повинні мати щонайменше дозволи **Читача**. Для отримання додаткових відомостей див. [Призначення ролей Azure за допомогою порталу Azure](/azure/role-based-access-control/role-assignments-portal).

- *Користувачу* потрібні дозволи **постачальника даних BLOB-об’єктів сховища** для облікового запису Azure Data Lake Storage Gen2, в якому дані розташовані та зв'язані з робочою областю Azure Synapse. Дізнайтеся більше про [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволи постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Кероване посвідчення робочої області Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* повинне мати дозволи **постачальника даних BLOB-об’єктів сховища** для облікового запису Azure Data Lake Storage Gen2, в якому дані розташовані та зв'язані з робочою областю Azure Synapse. Дізнайтеся більше щодо [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволів постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- У робочій області Azure Synapse *принципалу служби для аналізу аудиторії* необхідно призначити роль **Адміністратор Synapse**. Для отримання додаткових відомостей див. [процедуру настроювання керування доступом для робочої області Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Підключення до баз даних озера даних у Azure Synapse Analytics

1. Відкрийте **Дані** > **Джерела даних**.

1. Виберіть **Додати джерело даних**.

1. **Azure Synapse Analytics Виберіть метод (Попередній перегляд).**

1. Укажіть **Ім'я** для джерела даних, а тоді виберіть **Далі**, щоб створити джерело даних. 

1. [Виберіть доступне підключення](connections.md)Azure Synapse Analytics або створіть нове.

1. **Виберіть базу даних** Lake з робочої області, підключеної до вибраного Azure Synapse Analytics підключення, і натисніть кнопку **Далі**.

1. Виберіть сутності для отримання з підключеної бази даних. 

1. За потреби виберіть сутності даних, щоб дозволити профілювання даних. 

1. Натисніть кнопку **Зберегти**, щоб застосувати вибране та розпочати поїднення даних із новоствореної джерело даних, зв'язаної з таблицями бази даних Lake у Azure Synapse Analytics.
