---
title: Підключення Azure Synapse джерело даних (попереднього перегляду)
description: Використання бази даних у Azure Synapse джерело даних в Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738181"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Підключення Azure Synapse Analytics джерело даних (попереднього перегляду)

Azure Synapse Analytics це служба корпоративної аналітики, яка прискорює час для отримання інформації про сховища даних та системи великих даних. Azure Synapse Analytics об'єднує найкращі з технологій SQL, що використовуються в корпоративному сховищі даних, технології Spark, що використовуються для великих даних, Data Explorer для аналізу журналів і часових рядів, конвеєри для інтеграції даних і ETL/ELT, а також глибоку інтеграцію з іншими службами Azure, такими як Power BI, Cosmos DB, і AzureML.

Для отримання додаткової інформації дивіться [Azure Synapse огляд](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>вимоги

> [!NOTE]
> Робочі області Synapse, у яких [увімкнуто](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) брандмауер, наразі не підтримуються.
> [!IMPORTANT]
> Переконайтеся, що задано всі **призначення ролей**, як описано.  

**В Інсайтах** клієнтів:

* У вас є **роль адміністратора** в Customer Insights. Дізнайтеся більше про [дозволи користувачів у Customer Insights](permissions.md#add-users).

**In Azure**:

- Активна передплата Azure.

- Якщо використовується новий Azure Data Lake Storage обліковий запис Gen2, принципал *служби Customer Insights – «Dynamics 365 AI for Customer Insights* » потребує **дозволів постачальника** даних Storage Blob. Дізнайтеся більше про [підключення до принципала Azure Data Lake Storage служби для Customer Insights](connect-service-principal.md). Для сховища Data Lake Storage Gen2 **необхідно** увімкнути [ієрархічний простір імен](/azure/storage/blobs/data-lake-storage-namespace).

- У групі Azure Synapse ресурсів розташована робоча область, принципом *служби* якої є "Dynamics 365 AI for Customer Insights", а *користувачеві для Customer Insights* потрібно призначити принаймні **дозволи Reader**. Для отримання додаткових відомостей див. [Призначення ролей Azure за допомогою порталу Azure](/azure/role-based-access-control/role-assignments-portal).

- *Користувачу* потрібні дозволи **постачальника даних BLOB-об’єктів сховища** для облікового запису Azure Data Lake Storage Gen2, в якому дані розташовані та зв'язані з робочою областю Azure Synapse. Дізнайтеся більше про [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволи постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Кероване посвідчення робочої області Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* повинне мати дозволи **постачальника даних BLOB-об’єктів сховища** для облікового запису Azure Data Lake Storage Gen2, в якому дані розташовані та зв'язані з робочою областю Azure Synapse. Дізнайтеся більше щодо [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволів постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- У Azure Synapse робочій області директору *служби Customer Insights – «Dynamics 365 AI for Customer Insights* » призначено **роль адміністратора** синапсу. Користувачеві **потрібна** принаймні роль співавтора **синапсу**, призначена для робочої області. Для отримання додаткових відомостей див. [процедуру настроювання керування доступом для робочої області Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Якщо ваше середовище Customer Insights зберігає дані у вашому [власному Azure Data Lake Storage](own-data-lake-storage.md) середовищі, користувачеві, який налаштовує з'єднання Azure Synapse Analytics , потрібна принаймні вбудована **роль Reader** в обліковому записі Data Lake Storage. Для отримання додаткових відомостей див. [Призначення ролей Azure за допомогою порталу Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Підключення до бази даних озера даних у Azure Synapse Analytics

1. Відкрийте **Дані** > **Джерела даних**.

1. Виберіть **Додати джерело даних**.

1. Виберіть **Azure Synapse Analytics метод (попередній перегляд).**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Діалогове вікно для підключення до даних Synapse Analytics":::
  
1. Введіть **ім'я** джерело даних та необов'язковий **опис**.

1. Виберіть доступне [підключення](connections.md) або Azure Synapse Analytics [створіть нове](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. Виберіть **базу даних** із робочої області, підключеної до вибраного Azure Synapse Analytics підключення, і натисніть кнопку Далі.**·** Наразі ми підтримуємо лише базу даних типу *Озеро*.

1. Виберіть сутності для прийому з підключеної бази даних і натисніть кнопку **Далі**.

1. За бажанням виберіть сутності даних, на яких можна дозволити профілювання даних.

1. Натисніть кнопку **Зберегти**, щоб застосувати вибраний вибір і почати отримувати дані з новоствореного джерело даних, зв'язаного з таблицями бази даних Озера в Azure Synapse Analytics. Відкриється сторінка "Джерела **даних**", на якій відображається нова джерело даних у **стані оновлення**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Завантаження даних може тривати значний час. Після успішного оновлення отримані дані можна переглянути на [**сторінці сутностей**](entities.md) .

[!INCLUDE [footer-include](includes/footer-banner.md)]
