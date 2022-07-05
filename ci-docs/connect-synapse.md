---
title: Azure Synapse Підключення джерело даних (попередній перегляд)
description: Використовуйте базу даних як Azure Synapse джерело даних в Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c4ae65613a02df38a30f907dae72d413bf1a702f
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052724"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Azure Synapse Analytics Підключення джерело даних (попередній перегляд)

Azure Synapse Analytics це служба корпоративної аналітики, яка прискорює час для отримання інформації про сховища даних та системи великих даних. Azure Synapse Analytics об'єднує найкращі з SQL-технологій, що використовуються у складуванні корпоративних даних, технології Spark, що використовуються для великих даних, Data Explorer для аналізу журналів та часових рядів, Конвеєри для інтеграції даних та ETL/ELT, а також глибоку інтеграцію з іншими службами Azure, такими як Power BI, Cosmos DB, та AzureML.

Для отримання додаткової інформації дивіться [Azure Synapse огляд](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>вимоги

> [!IMPORTANT]
> Переконайтеся, що задано всі **призначення ролей**, як описано.  

**В інсайтах** клієнтів:

* Ви виконуєте **роль адміністратора** в Customer Insights. Дізнайтеся більше про [дозволи користувачів у розділі "Статистика клієнтів"](permissions.md#assign-roles-and-permissions).

**In Azure**:

- Активна передплата Azure.

- Якщо використовується новий Azure Data Lake Storage обліковий запис Gen2, директору *служби Customer Insights* потрібні **дозволи Постачальника** даних Зберігання BLOB. Дізнайтеся більше про [зв'язок Azure Data Lake Storage із директором служби Customer Insights](connect-service-principal.md). Для сховища Data Lake Storage Gen2 **необхідно** увімкнути [ієрархічний простір імен](/azure/storage/blobs/data-lake-storage-namespace).

- У групі ресурсів розташовано робочу Azure Synapse область, *принципу* служби та користувачу *Customer Insights* потрібно присвоїти принаймні **дозволи Reader**. Для отримання додаткових відомостей див. [Призначення ролей Azure за допомогою порталу Azure](/azure/role-based-access-control/role-assignments-portal).

- *Користувачу* потрібні дозволи **постачальника даних BLOB-об’єктів сховища** для облікового запису Azure Data Lake Storage Gen2, в якому дані розташовані та зв'язані з робочою областю Azure Synapse. Дізнайтеся більше про [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволи постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Кероване посвідчення робочої області Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* повинне мати дозволи **постачальника даних BLOB-об’єктів сховища** для облікового запису Azure Data Lake Storage Gen2, в якому дані розташовані та зв'язані з робочою областю Azure Synapse. Дізнайтеся більше щодо [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволів постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- У робочій Azure Synapse області принципу *обслуговування Customer Insights* призначена **роль адміністратора** Synapse. Для отримання додаткових відомостей див. [процедуру настроювання керування доступом для робочої області Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Підключення до бази даних озера даних у Azure Synapse Analytics

1. Відкрийте **Дані** > **Джерела даних**.

1. Виберіть **Додати джерело даних**.

1. **Azure Synapse Analytics Виберіть метод (Попередній перегляд).**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Діалогове вікно для підключення до даних Synapse Analytics":::
  
1. Введіть ім'я **для** джерело даних та необов'язковий **опис**.

1. Виберіть доступне [підключення](connections.md) або Azure Synapse Analytics створіть нове.

1. **Виберіть базу даних** у робочій області, підключеній до вибраного Azure Synapse Analytics підключення, і натисніть кнопку **Далі**. Наразі ми підтримуємо лише базу *даних типу* Lake.

1. Виберіть об'єкти, які потрібно проковтнути з підключеної бази даних, і натисніть кнопку **Далі**.

1. За потреби виберіть об'єкти даних, на яких можна дозволити профілювання даних.

1. Натисніть кнопку **Зберегти**, щоб застосувати вибране параметр і почати прийом даних із щойно створених джерело даних, зв'язаних із таблицями бази даних Lake у Azure Synapse Analytics. Відкриється **сторінка Джерела** даних із новим джерело даних у **стані оновлення**.
