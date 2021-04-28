---
title: Експорт даних Customer Insights до сховища BLOB-об'єктів Azure
description: Дізнайтеся, як налаштувати підключення та експорт до сховища BLOB-об'єктів Azure.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760260"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="08d91-103">Експортуйте список сегментів та інші дані до сховища BLOB-об'єктів Azure (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="08d91-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="08d91-104">Зберігайте дані Customer Insights у сховищі BLOB-об’єктів Azure або використовуйте його для передавання даних до інших програм.</span><span class="sxs-lookup"><span data-stu-id="08d91-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="08d91-105">Налаштуйте підключення до сховища BLOB-об'єктів Azure</span><span class="sxs-lookup"><span data-stu-id="08d91-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="08d91-106">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="08d91-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="08d91-107">Виберіть **Додати підключення**, потім виберіть **Сховище BLOB-об'єктів Azure**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="08d91-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="08d91-108">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="08d91-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="08d91-109">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="08d91-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="08d91-110">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="08d91-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="08d91-111">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="08d91-111">Choose who can use this connection.</span></span> <span data-ttu-id="08d91-112">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="08d91-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="08d91-113">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="08d91-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="08d91-114">Введіть **Ім’я бізнес-партнера**, **Ключ бізнес-партнера** та **Контейнер** для облікового запису сховища BLOB-об'єктів Azure.</span><span class="sxs-lookup"><span data-stu-id="08d91-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="08d91-115">Щоб отримати докладніші відомості про те, як знайти ім’я облікового запису сховища BLOB-об’єктів, див. розділ [Керуйте налаштуваннями облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="08d91-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="08d91-116">Щоб дізнатися, як створити контейнер, див. розділ [Створення контейнера ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="08d91-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="08d91-117">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="08d91-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="08d91-118">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="08d91-118">Configure an export</span></span>

<span data-ttu-id="08d91-119">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="08d91-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="08d91-120">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="08d91-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="08d91-121">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="08d91-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="08d91-122">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="08d91-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="08d91-123">У полі **Підключення для експорту** виберіть підключення з розділу «Сховище BLOB-об’єктів Azure».</span><span class="sxs-lookup"><span data-stu-id="08d91-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="08d91-124">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="08d91-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="08d91-125">Установіть прапорець поруч із кожною із сутностей, які ви хочете експортувати до цього призначення.</span><span class="sxs-lookup"><span data-stu-id="08d91-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="08d91-126">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="08d91-126">Select **Save**.</span></span>

<span data-ttu-id="08d91-127">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="08d91-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="08d91-128">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="08d91-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="08d91-129">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="08d91-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="08d91-130">Експортовані дані зберігаються в контейнері сховища BLOB-об'єктів, який ви налаштували.</span><span class="sxs-lookup"><span data-stu-id="08d91-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="08d91-131">У контейнері автоматично створюються наведені далі шляхи папок.</span><span class="sxs-lookup"><span data-stu-id="08d91-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="08d91-132">Для сутностей джерел і сутностей, згенерованих у системі: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="08d91-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="08d91-133">Приклад: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="08d91-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="08d91-134">Файл model.json для експортованих сутностей буде на рівні %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="08d91-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="08d91-135">Приклад: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="08d91-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
