---
title: Підключення до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби
description: Скористайтеся принципалом служби для аналізу аудиторій Azure, щоб підключитися до власного озера даних під час вкладення в аналіз аудиторії.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644113"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="6b584-103">Для аналізу аудиторії підключіться до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure</span><span class="sxs-lookup"><span data-stu-id="6b584-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="6b584-104">Для автоматичних інструментів, які використовують служби Azure, завжди мають обмежені дозволи.</span><span class="sxs-lookup"><span data-stu-id="6b584-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="6b584-105">Замість того, щоб входити в програму як привілейований користувач, Azure пропонує принципали служби.</span><span class="sxs-lookup"><span data-stu-id="6b584-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="6b584-106">Ознайомтеся, щоб дізнатися, як підключити аналізи аудиторі з обліковим записом Azure Data Lake Storage Gen2 за допомогою принципала служби Azure, а не ключів облікового запису сховища.</span><span class="sxs-lookup"><span data-stu-id="6b584-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="6b584-107">Принципал служби можна використовувати для того, щоб безпечно [додавати або редагувати папку Common Data Model як джерело даних](connect-common-data-model.md) або [створювати нове або оновлювати наявне середовище](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="6b584-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="6b584-108">Для створення принципала служби потрібно мати дозвіл адміністратора для вашої підписки Azure.</span><span class="sxs-lookup"><span data-stu-id="6b584-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="6b584-109">Створення принципала служби Azure для аналізу аудиторії.</span><span class="sxs-lookup"><span data-stu-id="6b584-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="6b584-110">Перш ніж створити новий принципал служби для аналізу аудиторій, перевірте, чи він вже існує в організації.</span><span class="sxs-lookup"><span data-stu-id="6b584-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="6b584-111">Знайдіть наявний принципал служби</span><span class="sxs-lookup"><span data-stu-id="6b584-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="6b584-112">Відкрийте [портал адміністратора Azure](https://portal.azure.com) та ввійдіть в організацію.</span><span class="sxs-lookup"><span data-stu-id="6b584-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="6b584-113">Виберіть **Azure Active Directory** у службах Azure.</span><span class="sxs-lookup"><span data-stu-id="6b584-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="6b584-114">У розділі **Керування** виберіть **Програма підприємства**.</span><span class="sxs-lookup"><span data-stu-id="6b584-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="6b584-115">Знайдіть ідентифікатор першої програми аналізу аудиторії `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` або ім’я `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="6b584-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="6b584-116">Якщо ви знайдете відповідний запис, це означає, що існує принципал служби для аналізу аудиторії.</span><span class="sxs-lookup"><span data-stu-id="6b584-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="6b584-117">Не потрібно створювати його повторно.</span><span class="sxs-lookup"><span data-stu-id="6b584-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Скріншот показує наявний принципал служби.":::
   
6. <span data-ttu-id="6b584-119">Якщо результатів не буде знайдено, створіть новий принципал служби.</span><span class="sxs-lookup"><span data-stu-id="6b584-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="6b584-120">Створення нового принципалу служби</span><span class="sxs-lookup"><span data-stu-id="6b584-120">Create a new service principal</span></span>

1. <span data-ttu-id="6b584-121">Інсталюйте найновішу версію **Azure Active Directory PowerShell для графа**.</span><span class="sxs-lookup"><span data-stu-id="6b584-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="6b584-122">Для отримання додаткових відомостей див. розділ [Інсталяція Azure Active Directory PowerShell для графа](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="6b584-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="6b584-123">Натисніть клавішу Windows на клавіатурі комп’ютера і знайдіть **Windows PowerShell** і **Запустити як адміністратор**.</span><span class="sxs-lookup"><span data-stu-id="6b584-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="6b584-124">У вікні PowerShell, що відкриється, введіть `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="6b584-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="6b584-125">Створення принципалу служби для аналізу аудиторії за допомогою модуля Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b584-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="6b584-126">У вікні PowerShell введіть `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="6b584-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="6b584-127">Замініть «ваш ідентифікатор клієнта» на фактичний ІДЕНТИФІКАТОР клієнта, в якому потрібно створити принципал служби.</span><span class="sxs-lookup"><span data-stu-id="6b584-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="6b584-128">Параметр назви середовища `AzureEnvironmentName` є необов’язковим.</span><span class="sxs-lookup"><span data-stu-id="6b584-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="6b584-129">Введіть `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="6b584-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="6b584-130">Ця команда створює принципал служби для аналізу аудиторії у вибраному клієнті.</span><span class="sxs-lookup"><span data-stu-id="6b584-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="6b584-131">Надання дозволів для принципала служби для доступу до облікового запису сховища</span><span class="sxs-lookup"><span data-stu-id="6b584-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="6b584-132">Відкрийте портал Azure, щоб надати дозволи принципалам служби для облікового запису сховища, який ви хочете використати в аналізі аудиторії.</span><span class="sxs-lookup"><span data-stu-id="6b584-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="6b584-133">Відкрийте [портал адміністратора Azure](https://portal.azure.com) та ввійдіть в організацію.</span><span class="sxs-lookup"><span data-stu-id="6b584-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="6b584-134">Відкрийте обліковий запис сховища, для якого має мати дозвіл принципал служби для аналізу аудиторії.</span><span class="sxs-lookup"><span data-stu-id="6b584-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="6b584-135">Виберіть **Керування доступом (IAM)** на панелі переходів і натисніть **Додати** > **Додати призначення ролі**.</span><span class="sxs-lookup"><span data-stu-id="6b584-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Скріншот, на якому зображено портал Azure під час додавання призначення ролі.":::
   
1. <span data-ttu-id="6b584-137">В області **Додавання призначення ролі** встановіть такі властивості:</span><span class="sxs-lookup"><span data-stu-id="6b584-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="6b584-138">Роль: *Постачальник даних BLOB-об’єктів сховища*</span><span class="sxs-lookup"><span data-stu-id="6b584-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="6b584-139">Призначення доступу для: *Користувач, група або принципал служби*</span><span class="sxs-lookup"><span data-stu-id="6b584-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="6b584-140">Виберіть: *Dynamics 365 AI для Customer Insights* ([створений принципал служби](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="6b584-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="6b584-141">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="6b584-141">Select **Save**.</span></span>

<span data-ttu-id="6b584-142">Для впровадження змін може знадобитися до 15 хвилин.</span><span class="sxs-lookup"><span data-stu-id="6b584-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="6b584-143">Введіть ідентифікатор ресурсу Azure або деталі підписки Azure у вкладенні облікового запису сховища до аналізу аудиторії.</span><span class="sxs-lookup"><span data-stu-id="6b584-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="6b584-144">Прикріпіть обліковий запис сховища Azure Data Lake у аналізі аудиторії до [store output data](manage-environments.md) або [використовуйте його як джерело даних](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="6b584-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="6b584-145">Вибір параметра Azure Data Lake дає змогу вибирати між підходом на основі ресурсу та підходом на основі передплати.</span><span class="sxs-lookup"><span data-stu-id="6b584-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="6b584-146">Виконайте наведені нижче кроки, щоб надати необхідну інформацію щодо вибраного підходу.</span><span class="sxs-lookup"><span data-stu-id="6b584-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="6b584-147">Підключення облікового запису сховища на основі ресурсу</span><span class="sxs-lookup"><span data-stu-id="6b584-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="6b584-148">Відкрийте [портал адміністратора Azure](https://portal.azure.com), увійдіть у підписку та відкрийте обліковий запис сховища.</span><span class="sxs-lookup"><span data-stu-id="6b584-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="6b584-149">В області переходів натисніть **Налаштування** > **Властивості**.</span><span class="sxs-lookup"><span data-stu-id="6b584-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="6b584-150">Скопіюйте значення ідентифікатора ресурсів облікового запису сховища.</span><span class="sxs-lookup"><span data-stu-id="6b584-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Скопіюйте значення ідентифікатора ресурсів облікового запису сховища.":::

1. <span data-ttu-id="6b584-152">У аналізі аудиторії вставте ідентифікатор ресурсу у поле ресурсу, відображене на екрані підключення облікового запису сховища.</span><span class="sxs-lookup"><span data-stu-id="6b584-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Введіть інформацію про ідентифікатор ресурсу облікового запису сховища.":::   
   
1. <span data-ttu-id="6b584-154">Продовжуйте дії, які залишилися в аналізі аудиторії, щоб прикріпити обліковий запис сховища.</span><span class="sxs-lookup"><span data-stu-id="6b584-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="6b584-155">Підключення облікового запису сховища на основі передплати</span><span class="sxs-lookup"><span data-stu-id="6b584-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="6b584-156">Відкрийте [портал адміністратора Azure](https://portal.azure.com), увійдіть у підписку та відкрийте обліковий запис сховища.</span><span class="sxs-lookup"><span data-stu-id="6b584-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="6b584-157">В області переходів натисніть **Налаштування** > **Властивості**.</span><span class="sxs-lookup"><span data-stu-id="6b584-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="6b584-158">Перевірте **Передплату**, **Групу ресурсів** і **Ім’я** облікового запису сховища, щоб перевірити, що ви вибрали правильні значення у аналізі аудиторії.</span><span class="sxs-lookup"><span data-stu-id="6b584-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="6b584-159">У аналізі аудиторії виберіть значення або відповідні поля під час прикріплення облікового запису сховища.</span><span class="sxs-lookup"><span data-stu-id="6b584-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Введіть інформацію про ідентифікатор ресурсу облікового запису сховища.":::
   
1. <span data-ttu-id="6b584-161">Продовжуйте дії, які залишилися в аналізі аудиторії, щоб прикріпити обліковий запис сховища.</span><span class="sxs-lookup"><span data-stu-id="6b584-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
