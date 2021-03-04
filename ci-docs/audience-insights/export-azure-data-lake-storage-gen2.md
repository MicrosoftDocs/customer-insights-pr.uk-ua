---
title: Експорт даних Customer Insights до Azure Data Lake Storage Gen2
description: Дізнайтесь, як налаштувати підключення до Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477204"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="f0831-103">З'єднувач для Azure Data Lake Storage Gen2 (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="f0831-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="f0831-104">Зберігайте дані Customer Insights у Azure Data Lake Storage Gen2 або використовуйте його для передавання даних в інші програми.</span><span class="sxs-lookup"><span data-stu-id="f0831-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="f0831-105">Налаштування з’єднувача Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="f0831-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="f0831-106">У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.</span><span class="sxs-lookup"><span data-stu-id="f0831-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f0831-107">У розділі **Azure Data Lake Storage Gen2** виберіть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="f0831-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="f0831-108">Дайте своєму призначенню ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="f0831-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f0831-109">Введіть **Ім’я облікового запису**, **Ключ облікового запису** і **Контейнер** для Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="f0831-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="f0831-110">Щоб дізнатися, як створити обліковий запис сховища для використання з Azure Data Lake Storage Gen2, див. [Створення облікового запису сховища](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="f0831-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="f0831-111">Докладніше про те, як знайти ім'я облікового запису й ключ облікового запису сховища Azure Data Lake Gen2, див. тут: [Керування параметрами облікового запису сховища на порталі Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="f0831-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="f0831-112">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="f0831-112">Select **Next**.</span></span>

1. <span data-ttu-id="f0831-113">Установіть прапорець поруч із кожною із сутностей, які ви хочете експортувати до цього призначення.</span><span class="sxs-lookup"><span data-stu-id="f0831-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="f0831-114">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="f0831-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f0831-115">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="f0831-115">Export the data</span></span>

<span data-ttu-id="f0831-116">Ви можете [експортувати дані вручну](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f0831-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="f0831-117">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f0831-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
