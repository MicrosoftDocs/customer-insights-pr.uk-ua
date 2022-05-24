---
title: Підключення до облікового запису Azure Data Lake Storage за допомогою принципала служби
description: Використайте принципала служби Azure, щоб підключатися до власного data lake.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 776eee79c25edbd40ed119510a314f5126933c3e
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/11/2022
ms.locfileid: "8739187"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Підключення до облікового запису Azure Data Lake Storage за допомогою принципала служби Azure

У цій статті розглядається підключення до Dynamics 365 Customer Insights облікового запису Azure Data Lake Storage за допомогою принципала служби Azure замість ключів облікового запису сховища. 

Для автоматичних інструментів, які використовують служби Azure, завжди мають обмежені дозволи. Замість того, щоб входити в програму як привілейований користувач, Azure пропонує принципали служби. Принципали служб можна використовувати для безпечного [додавання або редагування папки Common Data Model як джерело даних](connect-common-data-model.md) або створення або [оновлення середовища](create-environment.md).

> [!IMPORTANT]
> - Обліковий запис А комп'ютера сховища даних, який буде використовувати принципал служби має бути Gen2 і ієрархічний [простір імен увімкнуто](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1 онлайнове пул носіїв облікових записів не підтримуються.
> - Щоб створити принципал служби, потрібні дозволи адміністратора для передплати Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Створення принципала служби Azure для Customer Insights

Перш ніж створювати нову принципал служби для Customer Insights, перевірте, чи вона вже існує у вашій організації.

### <a name="look-for-an-existing-service-principal"></a>Знайдіть наявний принципал служби

1. Відкрийте [портал адміністратора Azure](https://portal.azure.com) та ввійдіть в організацію.

2. У розділі **Служби Azure**, виберіть **Azure Active Directory**.

3. У розділі **Керування** виберіть **Програма підприємства**.

4. Додайте фільтр для **ідентифікатора застосунку або**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` знайдіть ім'я `Dynamics 365 AI for Customer Insights`.

5. Якщо знайдете відповідний запис, це означає, що принципал служби вже існує. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Знімок екрана: наявний принципал служби.":::
   
6. Якщо результатів не буде знайдено, створіть новий принципал служби.

### <a name="create-a-new-service-principal"></a>Створення нового принципалу служби

1. Встановіть найновішу версію Azure Active Directory PowerShell for Graph. Для отримання додаткових відомостей, перейдіть до розділу [Встановлення Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. На комп'ютері натисніть клавішу Windows на клавіатурі, знайдіть **Windows PowerShell** і виберіть **Запуск від імені адміністратора**.
   
   1. У вікні PowerShell, що відкриється, введіть `Install-Module AzureAD`.

2. Створіть принципала служби для Customer Insights з модулем Azure AD PowerShell.

   1. У вікні PowerShell введіть `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Замініть *[ідентифікатор каталогу]* фактичним ідентифікатором каталогу вашої передплати Azure, де потрібно створити принципала служби. Параметр назви середовища `AzureEnvironmentName` не обов'язковий.
  
   1. Введіть `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ця команда створює принципал служби для статистики клієнтів на вибрану передплату Azure. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Надання дозволів для принципала служби для доступу до облікового запису сховища

Перейдіть на портал Azure, щоб надати дозволи принципалу служби для облікового запису сховища, який потрібно використовувати в Customer Insights.

1. Відкрийте [портал адміністратора Azure](https://portal.azure.com) та ввійдіть в організацію.

1. Відкрийте обліковий запис сховища, до якого потрібно отримати доступ принципалу служби для статистики клієнтів.

1. В області ліворуч натисніть **Керування доступом (IAM)**, а потім **Додати** > **Додати призначення ролі**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Знімок екрана: портал Azure під час додавання призначення ролі.":::

1. В області **Додавання призначення ролі** задайте такі властивості:
   - Роль: **Постачальник даних BLOB-об’єктів сховища**
   - Призначення доступу для: **Користувач, група або принципал служби**
   - Виберіть учасників: **Dynamics 365 AI для статистики** клієнтів (принципал послуги, [який](#create-a-new-service-principal) ви створили раніше в цій процедурі)

1.  Виберіть **Переглянути + призначити**.

Для впровадження змін може знадобитися до 15 хвилин.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Введіть ідентифікатор ресурсу Azure або відомості про передплату Azure у вкладенні облікового запису сховища до статистики клієнтів

Ви можете вкласти обліковий запис сховища data lake у службі підтримки клієнтів, щоб [зберігати вихідні дані](manage-environments.md) або [використовувати їх як джерело даних](connect-dataverse-managed-lake.md). Цей параметр дає змогу вибрати підхід на основі ресурсів чи підписки. Залежно від вибраного підходу, дотримуйтеся процедури в одному з наведених нижче розділів.

### <a name="resource-based-storage-account-connection"></a>Підключення облікового запису сховища на основі ресурсу

1. Відкрийте [портал адміністратора Azure](https://portal.azure.com), увійдіть у підписку та відкрийте обліковий запис сховища.

1. В області ліворуч перейдіть до меню **Параметри** > **Властивості**.

1. Скопіюйте значення ідентифікатора ресурсів облікового запису сховища.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Скопіюйте значення ідентифікатора ресурсів облікового запису сховища.":::

1. У вікні Customer Insights вставте ідентифікатор ресурсу в поле ресурсу, яке відображається на екрані підключення облікового запису сховища.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Введіть інформацію про ідентифікатор ресурсу облікового запису сховища.":::   

1. Перейдіть до решти кроків у Службі статистики клієнтів, щоб вкласти обліковий запис сховища.

### <a name="subscription-based-storage-account-connection"></a>Підключення облікового запису сховища на основі передплати

1. Відкрийте [портал адміністратора Azure](https://portal.azure.com), увійдіть у підписку та відкрийте обліковий запис сховища.

1. В області ліворуч перейдіть до меню **Параметри** > **Властивості**.

1. Перегляньте **передплату**, **групу** ресурсів і **ім'я** облікового запису сховища, щоб переконатися, що вибрано правильні значення в службі "Статистика клієнтів".

1. У розділі Статистика клієнтів виберіть значення для відповідних полів під час вкладення облікового запису сховища.

1. Перейдіть до решти кроків у Службі статистики клієнтів, щоб вкласти обліковий запис сховища.


[!INCLUDE [footer-include](includes/footer-banner.md)]