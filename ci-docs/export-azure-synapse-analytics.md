---
title: Експорт даних до Azure Synapse Analytics (попередній перегляд)
description: Дізнайтеся, як налаштувати підключення на Azure Synapse Analytics.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 60bacb313e0426564310f3c1339bf3b732e17489
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082880"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Експорт даних до Azure Synapse Analytics (попередній перегляд)

Azure Synapse– це служба аналізу, яка прискорює отримання аналітичних висновків у сховищах даних і системах великих даних. Ви можете передати дані Customer Insights й використовувати їх в [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Вимоги

Щоб налаштувати підключення Customer Insights до Azure Synapse, потрібно виконати наведені нижче попередні вимоги.

> [!NOTE]
> Переконайтеся, що задано всі **призначення ролей**, як описано.  

## <a name="prerequisites-in-customer-insights"></a>Попередні вимоги в Customer Insights

* Ваш Azure Active Directory обліковий запис користувача (AD) відіграє **роль адміністратора** в Customer Insights. Дізнайтеся більше про [настроювання дозволів користувачів](permissions.md#assign-roles-and-permissions).

В Azure: 

- Активна передплата Azure.

- Якщо використовується новий Azure Data Lake Storage обліковий запис Gen2, директору *служби Customer Insights* потрібні **дозволи Постачальника** даних Зберігання BLOB. Дізнайтеся більше про [підключення до облікового Azure Data Lake Storage запису Gen2 за допомогою принципу обслуговування Azure для Customer Insights](connect-service-principal.md). Для сховища Data Lake Storage Gen2 **необхідно** увімкнути [ієрархічний простір імен](/azure/storage/blobs/data-lake-storage-namespace).

- У групі ресурсів, де розташовано робочу Azure Synapse область, головному керівнику *служби* та користувачу *Azure AD з дозволами адміністратора в Customer Insights* потрібно призначити принаймні **дозволи Reader**. Для отримання додаткових відомостей див. [Призначення ролей Azure за допомогою порталу Azure](/azure/role-based-access-control/role-assignments-portal).

- Користувачеві *Azure AD з дозволами адміністратора в Customer Insights* потрібні **дозволи Постачальника** даних зберігання BLOB в обліковому Azure Data Lake Storage записі Gen2, де дані розташовані та пов'язані з робочою Azure Synapse областю. Дізнайтеся більше про [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволи постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Кероване посвідчення робочої області Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* повинне мати дозволи **постачальника даних BLOB-об’єктів сховища** для облікового запису Azure Data Lake Storage Gen2, в якому дані розташовані та зв'язані з робочою областю Azure Synapse. Дізнайтеся більше щодо [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволів постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- У робочій Azure Synapse області принципу *обслуговування Customer Insights* призначена **роль адміністратора** Synapse. Для отримання додаткових відомостей див. [процедуру настроювання керування доступом для робочої області Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Налаштуйте підключення та експорт до Azure Synapse

### <a name="configure-a-connection"></a>Налаштуйте підключення

Щоб створити підключення, принципалу служби та обліковому запису користувача в Customer Insights потрібні **дозволи Reader** для *групи* ресурсів, де розташована робоча область Synapse Analytics. Крім того, директор служби та користувач робочої області Synapse Analytics потребують **дозволів адміністратора** Synapse. 

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть елемент **Додати підключення** та виберіть **Azure Synapse Analytics** або виберіть **настроїти** на плитці **Azure Synapse Analytics**, щоб настроїти підключення.

1. Надайте у полі Коротке ім’я для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Виберіть або знайдіть передплату, із якою потрібно використати дані Customer Insights. Після вибору передплати можна також вибрати **Робочу область**, **Обліковий запис сховища** та **Контейнер**.

1. Виберіть **Зберегти**, щоб зберегти підключення.

### <a name="configure-an-export"></a>Налаштування експорту

Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу. Щоб настроїти експорт за допомогою спільного підключення, потрібні принаймні **дозволи постачальника** в Customer Insights. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати експорт**.

1. **У полі Підключення для експорту** виберіть підключення з **Azure Synapse Analytics** розділу. Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного [підключення](connections.md) цього типу.

1. Укажіть пізнаване **Коротке ім'я** для експорту та **Ім'я бази даних**. Експорт створить нову [Azure Synapse базу даних](/azure/synapse-analytics/database-designer/concepts-lake-database) озер у робочій області, визначеній у зв'язку.

1. Виберіть, до яких сутностей ви хочете експортувати Azure Synapse Analytics.
   > [!NOTE]
   > Джерела даних на основі папки [Common Data Model](connect-common-data-model.md) не підтримуються.

1. Виберіть **Зберегти**.

При збереженні експорт не запуститься негайно.

Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab). Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).

Щоб запитувати дані, експортовані в Synapse Analytics, вам потрібен **доступ зчитувача** даних Storage BLOB до цільового сховища в робочій області експорту. 

### <a name="update-an-export"></a>Оновлення експорту

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть **Редагувати** для експорту, який потрібно змінити.

   - **Додайте** або **Видаліть** зі списку вибрані для експорту сутності. При видаленні сутностей зі списку вони не видаляються з бази даних Synapse Analytics. Проте при подальших оновленнях даних видалені сутності в цій базі даних не оновлюватимуться.

   - **Якщо змінити ім'я бази даних**, створюється нова база даних Synapse Analytics. База даних із налаштованим до цього іменем при майбутніх оновленнях не оновлюватиметься.
