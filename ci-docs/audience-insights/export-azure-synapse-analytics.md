---
title: Експортування даних Customer Insights до Azure Synapse Analytics
description: Дізнайтеся, як налаштувати підключення до Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977402"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="b091f-103">Експортування даних до Azure Synapse Analytics (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="b091f-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="b091f-104">Azure Synapse– це служба аналізу, яка прискорює отримання аналітичних висновків у сховищах даних і системах великих даних.</span><span class="sxs-lookup"><span data-stu-id="b091f-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="b091f-105">Ви можете передати дані Customer Insights й використовувати їх в [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="b091f-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b091f-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="b091f-106">Prerequisites</span></span>

<span data-ttu-id="b091f-107">Щоб налаштувати підключення Customer Insights до Azure Synapse, потрібно виконати наведені нижче попередні вимоги.</span><span class="sxs-lookup"><span data-stu-id="b091f-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="b091f-108">Переконайтеся, що задано всі **призначення ролей**, як описано.</span><span class="sxs-lookup"><span data-stu-id="b091f-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="b091f-109">Попередні вимоги в Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b091f-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="b091f-110">Ви маєте роль **Адміністратор** для аналізу аудиторії.</span><span class="sxs-lookup"><span data-stu-id="b091f-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="b091f-111">Докладніше про [настроювання дозволів користувачів в аналізі аудиторії](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="b091f-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="b091f-112">В Azure:</span><span class="sxs-lookup"><span data-stu-id="b091f-112">In Azure:</span></span> 

- <span data-ttu-id="b091f-113">Активна передплата Azure.</span><span class="sxs-lookup"><span data-stu-id="b091f-113">An active Azure subscription.</span></span>

- <span data-ttu-id="b091f-114">Якщо використовується новий обліковий запис Azure Data Lake Storage Gen2, для *принципала служби для аналізу аудиторії* необхідні дозволи **Постачальника даних BLOB-об’єктів сховища**.</span><span class="sxs-lookup"><span data-stu-id="b091f-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="b091f-115">Докладніше про [підключення до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure для аналізу аудиторії](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="b091f-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="b091f-116">Для сховища Data Lake Storage Gen2 **необхідно** увімкнути [ієрархічний простір імен](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="b091f-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="b091f-117">У групі ресурсів, де розташована робоча область Azure Synapse, *принципал служби* та *користувач для аналізу аудиторії* повинні мати щонайменше дозволи **Читача**.</span><span class="sxs-lookup"><span data-stu-id="b091f-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="b091f-118">Для отримання додаткових відомостей див. [Призначення ролей Azure за допомогою порталу Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="b091f-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="b091f-119">*Користувачу* потрібні дозволи **постачальника даних BLOB-об’єктів сховища** для облікового запису Azure Data Lake Storage Gen2, в якому дані розташовані та зв'язані з робочою областю Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="b091f-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="b091f-120">Дізнайтеся більше про [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволи постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="b091f-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="b091f-121">*[Кероване посвідчення робочої області Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* повинне мати дозволи **постачальника даних BLOB-об’єктів сховища** для облікового запису Azure Data Lake Storage Gen2, в якому дані розташовані та зв'язані з робочою областю Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="b091f-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="b091f-122">Дізнайтеся більше щодо [використання порталу Azure для призначення ролей для доступу BLOB-об'єктів та постановки даних у чергу](/azure/storage/common/storage-auth-aad-rbac-portal) та [дозволів постачальника даних BLOB-об’єктів сховища](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="b091f-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="b091f-123">У робочій області Azure Synapse *принципалу служби для аналізу аудиторії* необхідно призначити роль **Адміністратор Synapse**.</span><span class="sxs-lookup"><span data-stu-id="b091f-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="b091f-124">Для отримання додаткових відомостей див. [процедуру настроювання керування доступом для робочої області Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="b091f-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="b091f-125">Налаштуйте підключення та експорт до Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="b091f-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="b091f-126">Налаштуйте підключення</span><span class="sxs-lookup"><span data-stu-id="b091f-126">Configure a connection</span></span>

1. <span data-ttu-id="b091f-127">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="b091f-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b091f-128">Виберіть **Додати підключення**, потім виберіть **Azure Synapse Analytics**, або виберіть **Налаштувати** на плитці **Azure Synapse Analytics** для налаштування підключення.</span><span class="sxs-lookup"><span data-stu-id="b091f-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="b091f-129">Надайте у полі Коротке ім’я для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="b091f-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="b091f-130">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="b091f-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="b091f-131">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="b091f-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b091f-132">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="b091f-132">Choose who can use this connection.</span></span> <span data-ttu-id="b091f-133">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="b091f-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b091f-134">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b091f-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b091f-135">Виберіть або знайдіть передплату, із якою потрібно використати дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b091f-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="b091f-136">Після вибору передплати можна також вибрати **Робочу область**, **Обліковий запис сховища** та **Контейнер**.</span><span class="sxs-lookup"><span data-stu-id="b091f-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="b091f-137">Виберіть **Зберегти**, щоб зберегти підключення.</span><span class="sxs-lookup"><span data-stu-id="b091f-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="b091f-138">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="b091f-138">Configure an export</span></span>

<span data-ttu-id="b091f-139">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="b091f-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b091f-140">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b091f-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b091f-141">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="b091f-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b091f-142">Щоб створити новий експорт, виберіть **Додати експорт**.</span><span class="sxs-lookup"><span data-stu-id="b091f-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="b091f-143">У полі **Підключення для експорту** виберіть підключення з розділу **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="b091f-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="b091f-144">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного [підключення](connections.md) цього типу.</span><span class="sxs-lookup"><span data-stu-id="b091f-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="b091f-145">Укажіть пізнаване **Коротке ім'я** для експорту та **Ім'я бази даних**.</span><span class="sxs-lookup"><span data-stu-id="b091f-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="b091f-146">Виберіть сутності, які потрібно експортувати до Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="b091f-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="b091f-147">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="b091f-147">Select **Save**.</span></span>

<span data-ttu-id="b091f-148">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="b091f-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b091f-149">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b091f-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b091f-150">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b091f-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="b091f-151">Оновлення експорту</span><span class="sxs-lookup"><span data-stu-id="b091f-151">Update an export</span></span>

1. <span data-ttu-id="b091f-152">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="b091f-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b091f-153">Виберіть **Редагувати** для експорту, який потрібно змінити.</span><span class="sxs-lookup"><span data-stu-id="b091f-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="b091f-154">**Додайте** або **Видаліть** зі списку вибрані для експорту сутності.</span><span class="sxs-lookup"><span data-stu-id="b091f-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="b091f-155">При видаленні сутностей зі списку вони не видаляються з бази даних Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="b091f-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="b091f-156">Проте при подальших оновленнях даних видалені сутності в цій базі даних не оновлюватимуться.</span><span class="sxs-lookup"><span data-stu-id="b091f-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="b091f-157">**Якщо змінити ім'я бази даних**, створюється нова база даних Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="b091f-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="b091f-158">База даних із налаштованим до цього іменем при майбутніх оновленнях не оновлюватиметься.</span><span class="sxs-lookup"><span data-stu-id="b091f-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
