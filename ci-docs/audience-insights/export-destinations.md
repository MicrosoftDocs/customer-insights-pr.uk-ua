---
title: Призначення експорту
description: Експорт даних і керування напрямами експорту.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643888"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="852df-103">Призначення експорту (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="852df-103">Export destinations (preview)</span></span>

<span data-ttu-id="852df-104">На сторінці **Призначення експорту** відображаються всі розташування, які ви налаштували для експорту даних.</span><span class="sxs-lookup"><span data-stu-id="852df-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="852df-105">Також ви можете додати нові розташування для експорту.</span><span class="sxs-lookup"><span data-stu-id="852df-105">You can also add new destinations for export.</span></span> <span data-ttu-id="852df-106">Крім того, в ньому відображаються доступні параметри експорту.</span><span class="sxs-lookup"><span data-stu-id="852df-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="852df-107">Отримайте швидкий огляд і опис, щоб дізнатися, що можна зробити з кожним параметром розширюваності.</span><span class="sxs-lookup"><span data-stu-id="852df-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="852df-108">Експортуйте уніфіковані профілі, заходи та сегменти до підтримуваних програм, що є доречними для вашого бізнесу.</span><span class="sxs-lookup"><span data-stu-id="852df-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="852df-109">Перейдіть до розділу **Адміністратор** > **Призначення експорту**, щоб побачити наведені далі параметри розширюваності.</span><span class="sxs-lookup"><span data-stu-id="852df-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="852df-110">Надбудова Dynamics 365 у вигляді картки клієнта</span><span class="sxs-lookup"><span data-stu-id="852df-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="852df-111">З’єднувач Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="852df-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="852df-112">З’єднувач Power Automate</span><span class="sxs-lookup"><span data-stu-id="852df-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="852df-113">З’єднувач Power Apps</span><span class="sxs-lookup"><span data-stu-id="852df-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="852df-114">З’єднувач Power BI</span><span class="sxs-lookup"><span data-stu-id="852df-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="852df-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="852df-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="852df-116">Dynamics 365 for Sales</span><span class="sxs-lookup"><span data-stu-id="852df-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="852df-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="852df-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="852df-118">Сховище BLOB-об’єктів Azure</span><span class="sxs-lookup"><span data-stu-id="852df-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="852df-119">З’єднувач LiveRamp&reg;</span><span class="sxs-lookup"><span data-stu-id="852df-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="852df-120">Бот для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="852df-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="852df-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="852df-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="852df-122">API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="852df-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="852df-123">Додавання нового призначення експорту</span><span class="sxs-lookup"><span data-stu-id="852df-123">Add a new export destination</span></span>

<span data-ttu-id="852df-124">Щоб додати напрями експорту, ви маєте [дозволи адміністратора](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="852df-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="852df-125">Якщо ви експортуєте в служби Microsoft, ми припускаємо, що обидві служби працюють в межах однієї організації.</span><span class="sxs-lookup"><span data-stu-id="852df-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="852df-126">Відкрийте **Адміністрування** > **Призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="852df-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="852df-127">Перейдіть на вкладку **Мої призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="852df-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="852df-128">Виберіть **Додати призначення**, щоб створити нове призначення експорту.</span><span class="sxs-lookup"><span data-stu-id="852df-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="852df-129">В області **Додати призначення** виберіть у розкривному списку **Тип** призначення експорту.</span><span class="sxs-lookup"><span data-stu-id="852df-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="852df-130">Укажіть необхідні відомості та виберіть **Далі**, щоб створити призначення експорту.</span><span class="sxs-lookup"><span data-stu-id="852df-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="852df-131">Крім того, можна вибрати параметр **Налаштування** на плитці на вкладці **Виявлення**.</span><span class="sxs-lookup"><span data-stu-id="852df-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="852df-132">Перегляньте призначення експорту</span><span class="sxs-lookup"><span data-stu-id="852df-132">View Export destinations</span></span>

<span data-ttu-id="852df-133">Після створення призначень експорту, їх можна знайти в таблиці на вкладці **Мої призначення експорту**. Ця таблиці має три стовпці.</span><span class="sxs-lookup"><span data-stu-id="852df-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="852df-134">**Коротке ім'я**: ім'я, яке вводиться під час створення призначення</span><span class="sxs-lookup"><span data-stu-id="852df-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="852df-135">**Тип**: тип призначення експорту, вказаний вами під час створення призначення.</span><span class="sxs-lookup"><span data-stu-id="852df-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="852df-136">**Створено**: дата створення призначення.</span><span class="sxs-lookup"><span data-stu-id="852df-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="852df-137">Редагування призначення експорту</span><span class="sxs-lookup"><span data-stu-id="852df-137">Edit an export destination</span></span>

1. <span data-ttu-id="852df-138">Виберіть вертикальні «три крапки» для призначення експорту, яке необхідно відредагувати.</span><span class="sxs-lookup"><span data-stu-id="852df-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="852df-139">![Вертикальні «три крапки»](media/export-destinations-page-ellipsis.png "Вертикальні «три крапки»")</span><span class="sxs-lookup"><span data-stu-id="852df-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="852df-140">У розкривному меню виберіть **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="852df-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="852df-141">Змініть значення, які потребують оновлення, а тоді виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="852df-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="852df-142">Експорт даних вручну</span><span class="sxs-lookup"><span data-stu-id="852df-142">Export data on demand</span></span>

<span data-ttu-id="852df-143">Після налаштування з'єднувача для призначення експорту експорт виконуватиметься разом із кожним [запланованим оновленням](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="852df-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="852df-144">Щоб експортувати дані, не очікуючи запланованого оновлення, перейдіть на вкладку **Мої призначення експорту** у розділі **Адміністрування** > **Призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="852df-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="852df-145">![Вертикальні «три крапки»](media/export-destinations-page-ellipsis.png "Вертикальні «три крапки»")</span><span class="sxs-lookup"><span data-stu-id="852df-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="852df-146">Виберіть **Експортувати** над списком, щоб виконати експорт до усіх призначень експорту одночасно .</span><span class="sxs-lookup"><span data-stu-id="852df-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="852df-147">Виберіть три крапки (...) після елемента списку, а потім виберіть варіант **Експортувати**, щоб виконати експорт для одного призначення експорту.</span><span class="sxs-lookup"><span data-stu-id="852df-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="852df-148">Видалення призначення експорту</span><span class="sxs-lookup"><span data-stu-id="852df-148">Remove an Export destination</span></span>

<span data-ttu-id="852df-149">Щоб видалити призначення експорту, почніть з головної сторінки **Призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="852df-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="852df-150">Виберіть вертикальні «три крапки» для призначення Експорту, яке ви бажаєте видалити.</span><span class="sxs-lookup"><span data-stu-id="852df-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="852df-151">![Вертикальні «три крапки»](media/export-destinations-page-ellipsis.png "Вертикальні «три крапки»")</span><span class="sxs-lookup"><span data-stu-id="852df-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="852df-152">У розкривному меню виберіть **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="852df-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="852df-153">Щоб підтвердити видалення, виберіть **Видалити** на екрані підтвердження.</span><span class="sxs-lookup"><span data-stu-id="852df-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
