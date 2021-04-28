---
title: Експорт даних Customer Insights до Azure Data Lake Storage Gen2
description: Дізнайтесь, як налаштувати підключення до Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760076"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="492b3-103">Налаштуйте підключення до Azure Data Lake Storage Gen2 (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="492b3-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="492b3-104">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="492b3-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="492b3-105">Виберіть **Додати підключення**, потім виберіть **Azure Data Lake Gen 2**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="492b3-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="492b3-106">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="492b3-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="492b3-107">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="492b3-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="492b3-108">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="492b3-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="492b3-109">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="492b3-109">Choose who can use this connection.</span></span> <span data-ttu-id="492b3-110">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="492b3-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="492b3-111">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="492b3-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="492b3-112">Введіть **Ім’я облікового запису**, **Ключ облікового запису** і **Контейнер** для Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="492b3-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="492b3-113">Щоб дізнатися, як створити обліковий запис сховища для використання з Azure Data Lake Storage Gen2, див. [Створення облікового запису сховища](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="492b3-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="492b3-114">Щоб отримати докладніші відомості про те, як знайти ім’я облікового запису сховища Azure Data Lake Gen2, див. розділ [Керуйте налаштуваннями облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="492b3-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="492b3-115">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="492b3-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="492b3-116">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="492b3-116">Configure an export</span></span>

<span data-ttu-id="492b3-117">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="492b3-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="492b3-118">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="492b3-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="492b3-119">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="492b3-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="492b3-120">Щоб створити новий експорт, виберіть **Додати експорт**.</span><span class="sxs-lookup"><span data-stu-id="492b3-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="492b3-121">У полі **Підключення для експорту** виберіть підключення з розділу **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="492b3-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="492b3-122">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="492b3-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="492b3-123">Установіть прапорець поруч із кожною із сутностей, які ви хочете експортувати до цього призначення.</span><span class="sxs-lookup"><span data-stu-id="492b3-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="492b3-124">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="492b3-124">Select **Save**.</span></span>

<span data-ttu-id="492b3-125">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="492b3-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="492b3-126">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="492b3-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="492b3-127">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="492b3-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="492b3-128">Експортовані дані зберігаються в контейнері сховища Azure Data Lake Gen 2, який ви налаштували.</span><span class="sxs-lookup"><span data-stu-id="492b3-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
