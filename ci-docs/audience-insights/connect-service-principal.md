---
title: Підключення до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби
description: Скористайтеся принципалом служби Azure для аналізу аудиторій, щоб підключитися до власного озера даних під час підключення його до аналізу аудиторії.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267747"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="c53a0-103">Для аналізу аудиторії підключіться до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure</span><span class="sxs-lookup"><span data-stu-id="c53a0-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="c53a0-104">Для автоматичних інструментів, які використовують служби Azure, завжди мають обмежені дозволи.</span><span class="sxs-lookup"><span data-stu-id="c53a0-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="c53a0-105">Замість того, щоб входити в програму як привілейований користувач, Azure пропонує принципали служби.</span><span class="sxs-lookup"><span data-stu-id="c53a0-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="c53a0-106">Ознайомтеся, щоб дізнатися, як підключити аналізи аудиторі з обліковим записом Azure Data Lake Storage Gen2 за допомогою принципала служби Azure, а не ключів облікового запису сховища.</span><span class="sxs-lookup"><span data-stu-id="c53a0-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="c53a0-107">Принципал служби можна використовувати для того, щоб безпечно [додавати або редагувати папку Common Data Model як джерело даних](connect-common-data-model.md) або [створювати нове або оновлювати наявне середовище](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="c53a0-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="c53a0-108">Для облікового запису сховища Azure Data Lake Gen2, який має намір використовувати принципал служби, необхідно увімкнути [Ієрархічний простір імен (HNS)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="c53a0-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="c53a0-109">Для створення принципала служби потрібно мати дозвіл адміністратора для вашої підписки Azure.</span><span class="sxs-lookup"><span data-stu-id="c53a0-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="c53a0-110">Створення принципала служби Azure для аналізу аудиторії.</span><span class="sxs-lookup"><span data-stu-id="c53a0-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="c53a0-111">Перш ніж створити новий принципал служби для аналізу аудиторій, перевірте, чи він вже існує в організації.</span><span class="sxs-lookup"><span data-stu-id="c53a0-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="c53a0-112">Знайдіть наявний принципал служби</span><span class="sxs-lookup"><span data-stu-id="c53a0-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="c53a0-113">Відкрийте [портал адміністратора Azure](https://portal.azure.com) та ввійдіть в організацію.</span><span class="sxs-lookup"><span data-stu-id="c53a0-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="c53a0-114">Виберіть **Azure Active Directory** у службах Azure.</span><span class="sxs-lookup"><span data-stu-id="c53a0-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="c53a0-115">У розділі **Керування** виберіть **Програма підприємства**.</span><span class="sxs-lookup"><span data-stu-id="c53a0-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="c53a0-116">Знайдіть ідентифікатор першої програми аналізу аудиторії `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` або ім’я `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="c53a0-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="c53a0-117">Якщо ви знайдете відповідний запис, це означає, що існує принципал служби для аналізу аудиторії.</span><span class="sxs-lookup"><span data-stu-id="c53a0-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="c53a0-118">Не потрібно створювати його повторно.</span><span class="sxs-lookup"><span data-stu-id="c53a0-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Скріншот показує наявний принципал служби.":::
   
6. <span data-ttu-id="c53a0-120">Якщо результатів не буде знайдено, створіть новий принципал служби.</span><span class="sxs-lookup"><span data-stu-id="c53a0-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="c53a0-121">Створення нового принципалу служби</span><span class="sxs-lookup"><span data-stu-id="c53a0-121">Create a new service principal</span></span>

1. <span data-ttu-id="c53a0-122">Інсталюйте найновішу версію **Azure Active Directory PowerShell для графа**.</span><span class="sxs-lookup"><span data-stu-id="c53a0-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="c53a0-123">Для отримання додаткових відомостей див. розділ [Інсталяція Azure Active Directory PowerShell для графа](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="c53a0-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="c53a0-124">Натисніть клавішу Windows на клавіатурі комп’ютера і знайдіть **Windows PowerShell** і **Запустити як адміністратор**.</span><span class="sxs-lookup"><span data-stu-id="c53a0-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="c53a0-125">У вікні PowerShell, що відкриється, введіть `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="c53a0-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="c53a0-126">Створення принципалу служби для аналізу аудиторії за допомогою модуля Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c53a0-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="c53a0-127">У вікні PowerShell введіть `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="c53a0-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="c53a0-128">Замініть «ваш ідентифікатор клієнта» на фактичний ІДЕНТИФІКАТОР клієнта, в якому потрібно створити принципал служби.</span><span class="sxs-lookup"><span data-stu-id="c53a0-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="c53a0-129">Параметр назви середовища `AzureEnvironmentName` є необов’язковим.</span><span class="sxs-lookup"><span data-stu-id="c53a0-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="c53a0-130">Введіть `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="c53a0-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="c53a0-131">Ця команда створює принципал служби для аналізу аудиторії у вибраному клієнті.</span><span class="sxs-lookup"><span data-stu-id="c53a0-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="c53a0-132">Надання дозволів для принципала служби для доступу до облікового запису сховища</span><span class="sxs-lookup"><span data-stu-id="c53a0-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="c53a0-133">Відкрийте портал Azure, щоб надати дозволи принципалам служби для облікового запису сховища, який ви хочете використати в аналізі аудиторії.</span><span class="sxs-lookup"><span data-stu-id="c53a0-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="c53a0-134">Відкрийте [портал адміністратора Azure](https://portal.azure.com) та ввійдіть в організацію.</span><span class="sxs-lookup"><span data-stu-id="c53a0-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="c53a0-135">Відкрийте обліковий запис сховища, для якого має мати дозвіл принципал служби для аналізу аудиторії.</span><span class="sxs-lookup"><span data-stu-id="c53a0-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="c53a0-136">Виберіть **Керування доступом (IAM)** на панелі переходів і натисніть **Додати** > **Додати призначення ролі**.</span><span class="sxs-lookup"><span data-stu-id="c53a0-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Скріншот, на якому зображено портал Azure під час додавання призначення ролі.":::
   
1. <span data-ttu-id="c53a0-138">В області **Додавання призначення ролі** встановіть такі властивості:</span><span class="sxs-lookup"><span data-stu-id="c53a0-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="c53a0-139">Роль: *Постачальник даних BLOB-об’єктів сховища*</span><span class="sxs-lookup"><span data-stu-id="c53a0-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="c53a0-140">Призначення доступу для: *Користувач, група або принципал служби*</span><span class="sxs-lookup"><span data-stu-id="c53a0-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="c53a0-141">Виберіть: *Dynamics 365 AI для Customer Insights* ([створений принципал служби](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="c53a0-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="c53a0-142">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="c53a0-142">Select **Save**.</span></span>

<span data-ttu-id="c53a0-143">Для впровадження змін може знадобитися до 15 хвилин.</span><span class="sxs-lookup"><span data-stu-id="c53a0-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="c53a0-144">Введіть ідентифікатор ресурсу Azure або деталі підписки Azure у вкладенні облікового запису сховища до аналізу аудиторії.</span><span class="sxs-lookup"><span data-stu-id="c53a0-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="c53a0-145">Прикріпіть обліковий запис сховища Azure Data Lake у аналізі аудиторії до [store output data](manage-environments.md) або [використовуйте його як джерело даних](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="c53a0-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="c53a0-146">Вибір параметра Azure Data Lake дає змогу вибирати між підходом на основі ресурсу та підходом на основі передплати.</span><span class="sxs-lookup"><span data-stu-id="c53a0-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="c53a0-147">Виконайте наведені нижче кроки, щоб надати необхідну інформацію щодо вибраного підходу.</span><span class="sxs-lookup"><span data-stu-id="c53a0-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="c53a0-148">Підключення облікового запису сховища на основі ресурсу</span><span class="sxs-lookup"><span data-stu-id="c53a0-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="c53a0-149">Відкрийте [портал адміністратора Azure](https://portal.azure.com), увійдіть у підписку та відкрийте обліковий запис сховища.</span><span class="sxs-lookup"><span data-stu-id="c53a0-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="c53a0-150">В області переходів натисніть **Налаштування** > **Властивості**.</span><span class="sxs-lookup"><span data-stu-id="c53a0-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="c53a0-151">Скопіюйте значення ідентифікатора ресурсів облікового запису сховища.</span><span class="sxs-lookup"><span data-stu-id="c53a0-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Скопіюйте значення ідентифікатора ресурсів облікового запису сховища.":::

1. <span data-ttu-id="c53a0-153">У аналізі аудиторії вставте ідентифікатор ресурсу у поле ресурсу, відображене на екрані підключення облікового запису сховища.</span><span class="sxs-lookup"><span data-stu-id="c53a0-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Введіть інформацію про ідентифікатор ресурсу облікового запису сховища.":::   
   
1. <span data-ttu-id="c53a0-155">Продовжуйте дії, які залишилися в аналізі аудиторії, щоб прикріпити обліковий запис сховища.</span><span class="sxs-lookup"><span data-stu-id="c53a0-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="c53a0-156">Підключення облікового запису сховища на основі передплати</span><span class="sxs-lookup"><span data-stu-id="c53a0-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="c53a0-157">Відкрийте [портал адміністратора Azure](https://portal.azure.com), увійдіть у підписку та відкрийте обліковий запис сховища.</span><span class="sxs-lookup"><span data-stu-id="c53a0-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="c53a0-158">В області переходів натисніть **Налаштування** > **Властивості**.</span><span class="sxs-lookup"><span data-stu-id="c53a0-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="c53a0-159">Перевірте **Передплату**, **Групу ресурсів** і **Ім’я** облікового запису сховища, щоб перевірити, що ви вибрали правильні значення у аналізі аудиторії.</span><span class="sxs-lookup"><span data-stu-id="c53a0-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="c53a0-160">У аналізі аудиторії виберіть значення або відповідні поля під час прикріплення облікового запису сховища.</span><span class="sxs-lookup"><span data-stu-id="c53a0-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="c53a0-161">Продовжуйте дії, які залишилися в аналізі аудиторії, щоб прикріпити обліковий запис сховища.</span><span class="sxs-lookup"><span data-stu-id="c53a0-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]