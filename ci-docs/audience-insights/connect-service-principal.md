---
title: Підключення до облікового запису Azure Data Lake Storage за допомогою принципала служби
description: Використайте принципала служби Azure, щоб підключатися до власного data lake.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461173"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Підключення до облікового запису Azure Data Lake Storage за допомогою принципала служби Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Для автоматичних інструментів, які використовують служби Azure, завжди мають обмежені дозволи. Замість того, щоб входити в програму як привілейований користувач, Azure пропонує принципали служби. Дізнайтеся, як підключитися до Dynamics 365 Customer Insights з обліковим записом Azure Data Lake Storage за допомогою принципала служби Azure, а не ключів облікового запису сховища. 

За допомогою принципала служби можна безпечно [додавати або редагувати папку Common Data Model в якості джерела даних](connect-common-data-model.md), або [створювати чи оновлювати середовище](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - В обліковому записі Data Lake Storage, який використовуватиме<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> принципал служби має бути увімкнутий [ієрархічний простір імен](/azure/storage/blobs/data-lake-storage-namespace).
> - Для створення принципала служби потрібно мати дозвіл адміністратора для вашої підписки Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Створення принципала служби Azure для Customer Insights

Перш ніж створити нового принципала служби для аналітичних оглядів аудиторії чи взаємодії, перевірте, чи не існує він уже в організації.

### <a name="look-for-an-existing-service-principal"></a>Знайдіть наявний принципал служби

1. Відкрийте [портал адміністратора Azure](https://portal.azure.com) та ввійдіть в організацію.

2. У розділі **Служби Azure**, виберіть **Azure Active Directory**.

3. У розділі **Керування** виберіть **Програма підприємства**.

4. Знайдіть ідентифікатор<!--note from editor: Via Microsoft Writing Style Guide.--> програми Microsoft:
   - Аналітичні огляди аудиторії: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` з назвою `Dynamics 365 AI for Customer Insights`
   - Аналітичні огляди взаємодії: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` з назвою `Dynamics 365 AI for Customer Insights engagement insights`

5. Якщо знайдете відповідний запис, це означає, що принципал служби вже існує. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Знімок екрана: наявний принципал служби.":::
   
6. Якщо результатів не буде знайдено, створіть новий принципал служби.

>[!NOTE]
>Щоб повною мірою скористатися можливостями Dynamics 365 Customer Insights, радимо додати до принципалу служби обидві програми.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Створення нового принципалу служби
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Встановіть найновішу версію Azure Active Directory PowerShell for Graph. Для отримання додаткових відомостей, перейдіть до розділу [Встановлення Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. На комп'ютері натисніть клавішу Windows на клавіатурі, знайдіть **Windows PowerShell** і виберіть **Запуск від імені адміністратора**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. У вікні PowerShell, що відкриється, введіть `Install-Module AzureAD`.

2. Створіть принципала служби для Customer Insights з модулем Azure AD PowerShell.

   1. У вікні PowerShell введіть `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Замініть позначку *"[ідентифікатор вашого клієнта]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> фактичним ідентифікатором клієнта, в якому потрібно створити принципала служби. Параметр назви середовища `AzureEnvironmentName` не обов'язковий.
  
   1. Введіть `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ця команда створює принципал служби для аналізу аудиторії у вибраному клієнті. 

   1. Введіть `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. За допомогою цієї команди на вибраному клієнті створюється принципал служби<!--note from editor: Edit okay?-->  для аналітичних оглядів взаємодії.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Надання дозволів для принципала служби для доступу до облікового запису сховища

Відкрийте портал Azure, щоб надати дозволи принципалам служби для облікового запису сховища, який ви хочете використати в аналізі аудиторії.

1. Відкрийте [портал адміністратора Azure](https://portal.azure.com) та ввійдіть в організацію.

1. Відкрийте обліковий запис сховища, для якого має мати дозвіл принципал служби для аналізу аудиторії.

1. В області ліворуч натисніть **Керування доступом (IAM)**, а потім **Додати** > **Додати призначення ролі**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Знімок екрана: портал Azure під час додавання призначення ролі.":::

1. В області **Додавання призначення ролі** задайте такі властивості:
   - Роль: **Постачальник даних BLOB-об’єктів сховища**
   - Призначення доступу для: **Користувач, група або принципал служби**
   - Виберіть: **Dynamics 365 AI for Customer Insights** та **Dynamics 365 AI for Customer Insights** (два [принципала служби](#create-a-new-service-principal), створені на попередньому етапі процедури)

1.  Виберіть **Зберегти**.

Для впровадження змін може знадобитися до 15 хвилин.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Введіть ідентифікатор ресурсу Azure або деталі підписки Azure у вкладенні облікового запису сховища до аналітичних оглядів аудиторії.

Можна <!--note from editor: Edit suggested only if this section is optional.--> прикріпити обліковий запис Data Lake Storage в аналітичних оглядах аудиторії, щоб [зберегти вихідні дані](manage-environments.md) або [використати його як джерело даних](connect-common-data-service-lake.md). Цей параметр дає змогу вибрати підхід на основі ресурсів чи підписки. Залежно від вибраного підходу, дотримуйтеся процедури в одному з наведених нижче розділів.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Підключення облікового запису сховища на основі ресурсу

1. Відкрийте [портал адміністратора Azure](https://portal.azure.com), увійдіть у підписку та відкрийте обліковий запис сховища.

1. В області ліворуч перейдіть до меню **Параметри** > **Властивості**.

1. Скопіюйте значення ідентифікатора ресурсів облікового запису сховища.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Скопіюйте значення ідентифікатора ресурсів облікового запису сховища.":::

1. В аналітичних оглядах аудиторії вставте ідентифікатор ресурсу в поле ресурсу, що відображається на екрані підключення до облікового запису сховища.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Введіть інформацію про ідентифікатор ресурсу облікового запису сховища.":::   

1. Продовжуйте дії, які залишилися в аналізі аудиторії, щоб прикріпити обліковий запис сховища.

### <a name="subscription-based-storage-account-connection"></a>Підключення облікового запису сховища на основі передплати

1. Відкрийте [портал адміністратора Azure](https://portal.azure.com), увійдіть у підписку та відкрийте обліковий запис сховища.

1. В області ліворуч перейдіть до меню **Параметри** > **Властивості**.

1. Перевірте **Передплату**, **Групу ресурсів** і **Ім’я** облікового запису сховища, щоб перевірити, що ви вибрали правильні значення у аналізі аудиторії.

1. В аналітичних оглядах аудиторії, виберіть значення відповідних полів, прикріпляючи обліковий запису сховища.

1. Продовжуйте дії, які залишилися в аналізі аудиторії, щоб прикріпити обліковий запис сховища.


[!INCLUDE[footer-include](../includes/footer-banner.md)]