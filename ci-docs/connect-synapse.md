---
title: Проковтнути дані з Azure Synapse Analytics
description: Використання бази даних як Azure Synapse джерело даних у програмі Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644051"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse Підключення джерело даних (попередній перегляд)

Azure Synapse Analytics— це служба корпоративної аналітики, яка прискорює час до статистики на складах даних та системах великих даних. Azure Synapse Analytics об'єднує найкращі технології SQL, що використовуються в корпоративному сховищі даних, технології Spark, що використовуються для великих даних, Data Explorer для аналітики журналів та часових рядів, конвеєри для інтеграції даних та ETL/ELT, а також глибоку інтеграцію з іншими службами Azure, такими як Power BI, Cosmos DB та AzureML.

Для отримання додаткових відомостей див [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>вимоги

Для настроювання підключення від Dynamics 365 Customer Insights до Azure Synapse.

> [!IMPORTANT]
> Переконайтеся, що задано всі **призначення ролей**, як описано.  

## <a name="prerequisites-in-customer-insights"></a>Попередні вимоги в Customer Insights

* У вас є **роль адміністратора** в інсайтах клієнтів. Докладніше про [дозволи користувачів можна дізнатися в розділі "Статистика клієнтів"](permissions.md#assign-roles-and-permissions).

В Azure: 

- Активна передплата Azure.

- Якщо використовується новий Azure Data Lake Storage обліковий запис Gen2, *принципал служби для статистики клієнтів потребує* дозволів **постачальника даних blob-об'єкта** сховища. Докладніше про [підключення до принципала Azure Data Lake Storage служби для статистики](connect-service-principal.md) клієнтів. Для сховища Data Lake Storage Gen2 **необхідно** увімкнути [ієрархічний простір імен](/azure/storage/blobs/data-lake-storage-namespace).

- У групі ресурсів, розташованій Azure Synapse робоча область, *принципал* служби та *користувач для статистики* клієнтів повинні бути призначені принаймні **дозволи читача**. Для отримання додаткових відомостей див. [Призначення ролей Azure за допомогою порталу Azure](/azure/role-based-access-control/role-assignments-portal).

- *Користувачу* потрібні дозволи **постачальника даних BLOB-об’єктів сховища** для облікового запису Azure Data Lake Storage Gen2, в якому дані розташовані та зв'язані з робочою областю Azure Synapse. Дізнайтеся більше про [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволи постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Кероване посвідчення робочої області Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* повинне мати дозволи **постачальника даних BLOB-об’єктів сховища** для облікового запису Azure Data Lake Storage Gen2, в якому дані розташовані та зв'язані з робочою областю Azure Synapse. Дізнайтеся більше щодо [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволів постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- У робочій Azure Synapse області принципалу *служби для customer insights* потрібна **призначена роль адміністратора** Synapse. Для отримання додаткових відомостей див. [процедуру настроювання керування доступом для робочої області Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Підключення до баз даних озера даних у Azure Synapse Analytics

1. Відкрийте **Дані** > **Джерела даних**.

1. Виберіть **Додати джерело даних**.

1. **Azure Synapse Analytics Виберіть метод (Попередній перегляд).**

1. Укажіть **Ім'я** для джерела даних, а тоді виберіть **Далі**, щоб створити джерело даних. 

1. Виберіть доступне [підключення](connections.md) до Azure Synapse Analytics нового або створіть його.

1. **Виберіть базу даних** озера з робочої області, підключеної до вибраного Azure Synapse Analytics підключення, і натисніть кнопку **Далі**.

1. Виберіть сутності, які потрібно проковтнути з підключеної бази даних. 

1. За бажанням виберіть сутності даних, щоб дозволити профілювання даних. 

1. Натисніть кнопку **Зберегти**, щоб застосувати виділений фрагмент і почати потрапляння даних із новостворених джерело даних зв'язаних із таблицями бази даних Lake у Azure Synapse Analytics програмі.
