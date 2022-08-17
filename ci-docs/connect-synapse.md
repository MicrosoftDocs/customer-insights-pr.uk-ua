---
title: Azure Synapse Підключення джерело даних (попередній перегляд)
description: Використовуйте базу даних в Azure Synapse якості джерело даних в Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7bc0c3614e6dd39fbd65ae098ed679d95d09de9d
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259823"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Azure Synapse Analytics Підключення джерело даних (попередній перегляд)

Azure Synapse Analytics це служба корпоративної аналітики, яка прискорює час для отримання інформації між сховищами даних та системами великих даних. Azure Synapse Analytics об’єднує найкращі технології SQL, що використовуються в корпоративному сховищі даних, технології Spark, що використовуються для великих даних, Data Explorer для аналітики журналів та часових рядів, конвеєри для інтеграції даних та ETL/ELT, а також глибоку інтеграцію з іншими службами Azure, такими як Power BI, Cosmos DB та AzureML.

Для отримання додаткової інформації дивіться [Azure Synapse огляд](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>вимоги

> [!NOTE]
> Робочі області Synapse, у [яких увімкнено](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) брандмауер, наразі не підтримуються.
> [!IMPORTANT]
> Переконайтеся, що задано всі **призначення ролей**, як описано.  

**У розділі "Інсайти клієнтів"**:

* У вас є **роль адміністратора** в Customer Insights. Дізнайтеся більше про [дозволи користувачів у розділі Customer Insights](permissions.md#add-users).

**In Azure**:

- Активна передплата Azure.

- Якщо використовується новий Azure Data Lake Storage обліковий запис Gen2, принципалу служби Customer Insights *,* яким є "Dynamics 365 AI for Customer Insights", потрібні **дозволи постачальника даних BLOB-сервера**. Дізнайтеся більше про [підключення до Azure Data Lake Storage служби за допомогою принципала обслуговування для Customer Insights](connect-service-principal.md). Для сховища Data Lake Storage Gen2 **необхідно** увімкнути [ієрархічний простір імен](/azure/storage/blobs/data-lake-storage-namespace).

- У групі Azure Synapse ресурсів розташована робоча область, *директором* служби якої є "Dynamics 365 AI for Customer Insights", а *користувачеві Customer Insights* потрібно призначити принаймні **дозволи Reader**. Для отримання додаткових відомостей див. [Призначення ролей Azure за допомогою порталу Azure](/azure/role-based-access-control/role-assignments-portal).

- *Користувачу* потрібні дозволи **постачальника даних BLOB-об’єктів сховища** для облікового запису Azure Data Lake Storage Gen2, в якому дані розташовані та зв'язані з робочою областю Azure Synapse. Дізнайтеся більше про [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволи постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Кероване посвідчення робочої області Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* повинне мати дозволи **постачальника даних BLOB-об’єктів сховища** для облікового запису Azure Data Lake Storage Gen2, в якому дані розташовані та зв'язані з робочою областю Azure Synapse. Дізнайтеся більше щодо [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволів постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- У робочій Azure Synapse області принципу служби Customer Insights *, яким є "Dynamics 365 AI for Customer Insights",* потрібна **роль адміністратора** Synapse. Для отримання додаткових відомостей див. [процедуру настроювання керування доступом для робочої області Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Якщо ваше середовище Customer Insights зберігає дані у вашому [власному Azure Data Lake Storage](own-data-lake-storage.md), користувачеві, який налаштовує з’єднання, Azure Synapse Analytics потрібна принаймні вбудована роль Reader **в** обліковому записі Data Lake Storage. Для отримання додаткових відомостей див. [Призначення ролей Azure за допомогою порталу Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Підключення до бази даних озера даних у Azure Synapse Analytics

1. Відкрийте **Дані** > **Джерела даних**.

1. Виберіть **Додати джерело даних**.

1. **Azure Synapse Analytics Виберіть метод (Попередній перегляд).**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Діалогове вікно для підключення до даних Synapse Analytics":::
  
1. Введіть Ім’я **джерело** даних та необов’язковий **опис**.

1. Виберіть доступне [підключення](connections.md) або Azure Synapse Analytics [створіть нове](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. **Виберіть базу даних** із робочої області, підключеної до вибраного Azure Synapse Analytics підключення, і натисніть кнопку **Далі**. Наразі ми підтримуємо лише базу *даних типу* Lake.

1. Виберіть сутності, які потрібно проковтнути з підключеної бази даних, і натисніть кнопку **Далі**.

1. За бажанням виберіть сутності даних, на яких можна дозволити профілювання даних.

1. Натисніть кнопку **Зберегти**, щоб застосувати виділений фрагмент і почати прийом даних із новоствореного джерело даних, зв’язаних із таблицями бази даних Lake у Azure Synapse Analytics. Відкриється сторінка Джерела **даних** із новим джерело даних у **стані Оновлення**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Завантаження даних може тривати значний час. Після успішного оновлення дані, що надійшли, можна переглянути зі сторінки « [**Сутності**](entities.md) ».

[!INCLUDE [footer-include](includes/footer-banner.md)]
