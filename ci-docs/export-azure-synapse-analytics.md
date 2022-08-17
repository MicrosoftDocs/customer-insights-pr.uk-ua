---
title: Експорт даних у Azure Synapse Analytics (попередній перегляд)
description: Дізнайтеся, як налаштувати підключення до Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259869"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Експорт даних у Azure Synapse Analytics (попередній перегляд)

Azure Synapse– це служба аналізу, яка прискорює отримання аналітичних висновків у сховищах даних і системах великих даних. Ви можете передати дані Customer Insights й використовувати їх в [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>вимоги

> [!NOTE]
> Переконайтеся, що задано всі **призначення ролей**, як описано.

- У Customer Insights ваш Azure Active Directory обліковий запис користувача (AD) має мати [роль адміністратора](permissions.md#add-users).

В Azure:

- Активна передплата Azure.

- Якщо використовується новий Azure Data Lake Storage обліковий запис Gen2, [принципал служби Customer Insights](connect-service-principal.md) має **дозволи постачальника даних BLOB-сховища**. Для сховища Data Lake Storage Gen2 **необхідно** увімкнути [ієрархічний простір імен](/azure/storage/blobs/data-lake-storage-namespace).

- У групі ресурсів, де розташовано робочу Azure Synapse область, принципалу *служби* та користувачу *Azure AD з дозволами адміністратора в Customer Insights* має бути призначено принаймні **дозволи** Reader [...](/azure/role-based-access-control/role-assignments-portal).

- Користувач *Azure AD із дозволами адміністратора в Customer Insights* має **дозволи постачальника** даних BLOB-сховища в обліковому Azure Data Lake Storage записі Gen2, де дані розташовані та пов’язані з робочою областю Azure Synapse. Дізнайтеся більше про [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволи постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Керований *[Azure Synapse ідентифікатор](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* робочої області має **дозволи постачальника даних сховища BLOB в** обліковому записі Azure Data Lake Storage Gen2, де дані розташовані та пов’язані з робочою областю Azure Synapse. Дізнайтеся більше щодо [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволів постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- У робочій Azure Synapse області директору *служби Customer Insights* призначено **роль** адміністратора [Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Якщо ваше середовище Customer Insights зберігає дані у вашому [власному Azure Data Lake Storage](own-data-lake-storage.md), користувачеві, який налаштовує з’єднання, Azure Synapse Analytics потрібна принаймні вбудована роль Reader **в** обліковому записі Data Lake Storage. Для отримання додаткових відомостей див. [Призначення ролей Azure за допомогою порталу Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="set-up-connection-to-azure-synapse"></a>Настроювання підключення до Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення** та виберіть **Azure Synapse Analytics**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Виберіть або знайдіть передплату, із якою потрібно використати дані Customer Insights. Після вибору передплати можна також вибрати **Робочу область**, **Обліковий запис сховища** та **Контейнер**.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)] Щоб настроїти експорт зі спільним підключенням, потрібні принаймні **дозволи співавтора** в Customer Insights.

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть Додати **експорт**.

1. **У полі Підключення для експорту** виберіть підключення з Azure Synapse Analytics розділу. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Укажіть пізнаване **Коротке ім'я** для експорту та **Ім'я бази даних**. Експорт створить нову [Azure Synapse базу даних](/azure/synapse-analytics/database-designer/concepts-lake-database) озера в робочій області, визначеній у зв’язку.

1. Виберіть об’єкти, до яких потрібно експортувати Azure Synapse Analytics.
   > [!NOTE]
   > Джерела даних на основі папки [Common Data Model](connect-common-data-model.md) не підтримуються.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Щоб запитувати дані, експортовані до Synapse Analytics, потрібен **доступ переглядача даних BLOB-даних** до цільового сховища в робочій області експорту.

## <a name="update-an-export"></a>Оновлення експорту

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть **Редагувати** для експорту, який потрібно змінити.

   - **Додайте** або **Видаліть** зі списку вибрані для експорту сутності. При видаленні сутностей зі списку вони не видаляються з бази даних Synapse Analytics. Проте при подальших оновленнях даних видалені сутності в цій базі даних не оновлюватимуться.

   - **Якщо змінити ім'я бази даних**, створюється нова база даних Synapse Analytics. База даних із налаштованим до цього іменем при майбутніх оновленнях не оновлюватиметься.

[!INCLUDE [footer-include](includes/footer-banner.md)]
