---
title: Підключення до облікового запису Azure Data Lake Storage за допомогою принципала служби
description: Використайте принципала служби Azure, щоб підключатися до власного data lake.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1af01e5579f85d7c8bc8976a003f53ef2dd280d1
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088172"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Підключення до облікового запису Azure Data Lake Storage за допомогою принципала служби Azure

У цій статті описано, як підключитися Dynamics 365 Customer Insights до облікового Azure Data Lake Storage запису за допомогою служби Azure принципал замість ключів облікового запису сховища. 

Для автоматичних інструментів, які використовують служби Azure, завжди мають обмежені дозволи. Замість того, щоб входити в програму як привілейований користувач, Azure пропонує принципали служби. За допомогою принципалів служб можна безпечно [додавати або редагувати спільну модель даних як джерело даних](connect-common-data-model.md) або [створювати або оновлювати середовище](create-environment.md).

> [!IMPORTANT]
> - Обліковий запис А комп'ютера сховища data lake, який використовуватиме принципал служби, має бути Gen2 і [мати ієрархічний простір імен](/azure/storage/blobs/data-lake-storage-namespace). Облікові записи сховища озера Даних Azure Gen1 не підтримуються.
> - Для створення принципала служби потрібні дозволи адміністратора для передплати Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Створення принципала служби Azure для Customer Insights

Перш ніж створювати новий принципал обслуговування для статистики клієнтів, перевірте, чи вона вже існує у вашій організації.

### <a name="look-for-an-existing-service-principal"></a>Знайдіть наявний принципал служби

1. Відкрийте [портал адміністратора Azure](https://portal.azure.com) та ввійдіть в організацію.

2. У розділі **Служби Azure**, виберіть **Azure Active Directory**.

3. У розділі **Керування** виберіть **Програма підприємства**.

4. Знайдіть ідентифікатор програми Microsoft:
   - Аналітичні огляди аудиторії: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` з назвою `Dynamics 365 AI for Customer Insights`
   - Аналітичні огляди взаємодії: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` з назвою `Dynamics 365 AI for Customer Insights engagement insights`

5. Якщо знайдете відповідний запис, це означає, що принципал служби вже існує. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Знімок екрана: наявний принципал служби.":::
   
6. Якщо результатів не буде знайдено, створіть новий принципал служби.

>[!NOTE]
>Щоб повною мірою скористатися можливостями Dynamics 365 Customer Insights, радимо додати до принципалу служби обидві програми.

### <a name="create-a-new-service-principal"></a>Створення нового принципалу служби

1. Встановіть найновішу версію Azure Active Directory PowerShell for Graph. Для отримання додаткових відомостей, перейдіть до розділу [Встановлення Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. На комп'ютері натисніть клавішу Windows на клавіатурі, знайдіть **Windows PowerShell** і виберіть **Запуск від імені адміністратора**.
   
   1. У вікні PowerShell, що відкриється, введіть `Install-Module AzureAD`.

2. Створіть принципала служби для Customer Insights з модулем Azure AD PowerShell.

   1. У вікні PowerShell введіть `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Замініть *[your tenant ID]* на фактичний ідентифікатор клієнта, в якому потрібно створити принципал служби. Параметр назви середовища `AzureEnvironmentName` не обов'язковий.
  
   1. Введіть `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ця команда створює принципал служби для аналізу аудиторії у вибраному клієнті. 

   1. Введіть `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. За допомогою цієї команди у вибраному клієнті створюється принципал служби для аналітики взаємодії.

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

Ви можете прикріпити обліковий запис Data Lake Storage в аналізі аудиторії, щоб [зберегти вихідні дані](manage-environments.md) або [використати його як джерело даних](connect-common-data-service-lake.md). Цей параметр дає змогу вибрати підхід на основі ресурсів чи підписки. Залежно від вибраного підходу, дотримуйтеся процедури в одному з наведених нижче розділів.

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
