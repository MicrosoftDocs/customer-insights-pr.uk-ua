---
title: Експорт даних Customer Insights до Azure Data Lake Storage Gen2
description: Дізнайтесь, як налаштувати підключення до Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596668"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="88237-103">З'єднувач для Azure Data Lake Storage Gen2 (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="88237-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="88237-104">Зберігайте дані Customer Insights у Azure Data Lake Storage Gen2 або використовуйте його для передавання даних в інші програми.</span><span class="sxs-lookup"><span data-stu-id="88237-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="88237-105">Налаштування з’єднувача Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="88237-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="88237-106">У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.</span><span class="sxs-lookup"><span data-stu-id="88237-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="88237-107">У розділі **Azure Data Lake Storage Gen2** виберіть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="88237-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="88237-108">Дайте своєму призначенню ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="88237-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="88237-109">Введіть **Ім’я облікового запису**, **Ключ облікового запису** і **Контейнер** для Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="88237-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="88237-110">Щоб дізнатися, як створити обліковий запис сховища для використання з Azure Data Lake Storage Gen2, див. [Створення облікового запису сховища](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="88237-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="88237-111">Докладніше про те, як знайти ім'я облікового запису й ключ облікового запису сховища Azure Data Lake Gen2, див. тут: [Керування параметрами облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="88237-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="88237-112">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="88237-112">Select **Next**.</span></span>

1. <span data-ttu-id="88237-113">Установіть прапорець поруч із кожною із сутностей, які ви хочете експортувати до цього призначення.</span><span class="sxs-lookup"><span data-stu-id="88237-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="88237-114">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="88237-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="88237-115">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="88237-115">Export the data</span></span>

<span data-ttu-id="88237-116">Ви можете [експортувати дані вручну](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="88237-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="88237-117">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="88237-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>