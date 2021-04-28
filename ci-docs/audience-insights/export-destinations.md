---
title: Експорт даних з Customer Insights
description: Керування експортом для надання спільного доступу до даних.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896168"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="ed551-103">Огляд експорту (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="ed551-103">Exports (preview) overview</span></span>

<span data-ttu-id="ed551-104">На сторінці **Експорти** буде показано всі налаштовані експорти.</span><span class="sxs-lookup"><span data-stu-id="ed551-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="ed551-105">Експорти дозволяють надати спільний доступ до певних даних різноманітним програмам.</span><span class="sxs-lookup"><span data-stu-id="ed551-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="ed551-106">До таких даних можуть входити профілі або сутності клієнтів, схеми та відомості про зіставлення.</span><span class="sxs-lookup"><span data-stu-id="ed551-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="ed551-107">Для кожного експорту потрібне [підключення, настроєне адміністратором, щоб керувати автентифікацією та доступом](connections.md).</span><span class="sxs-lookup"><span data-stu-id="ed551-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ed551-108">До березня 2021 року експорти автоматично створювали підключення до відповідної послуги.</span><span class="sxs-lookup"><span data-stu-id="ed551-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="ed551-109">Тепер для того, щоб створювати експорти, потрібне [підключення, створене та надане для спільного доступу адміністратором](connections.md).</span><span class="sxs-lookup"><span data-stu-id="ed551-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="ed551-110">Відкрийте послідовно **Дані** > **Експорти**, щоб переглянути сторінку експортів.</span><span class="sxs-lookup"><span data-stu-id="ed551-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="ed551-111">Усі ролі користувачів мають доступ до перегляду налаштованих експортів.</span><span class="sxs-lookup"><span data-stu-id="ed551-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="ed551-112">Використовуйте поле пошуку на панелі команд, щоб знайти експорти за іменем, іменем підключення або типом підключення.</span><span class="sxs-lookup"><span data-stu-id="ed551-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="ed551-113">Налаштування нового експорту</span><span class="sxs-lookup"><span data-stu-id="ed551-113">Set up a new export</span></span>

<span data-ttu-id="ed551-114">Щоб налаштувати або відредагувати експорт, потрібно мати доступ до підключень.</span><span class="sxs-lookup"><span data-stu-id="ed551-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="ed551-115">Підключення залежатимуть від [ролі користувача](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="ed551-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="ed551-116">Адміністратори мають доступ до всіх підключень.</span><span class="sxs-lookup"><span data-stu-id="ed551-116">Administrators have access to all connections.</span></span> <span data-ttu-id="ed551-117">Вони також можуть створювати нові підключення під час налаштування експорту.</span><span class="sxs-lookup"><span data-stu-id="ed551-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="ed551-118">Співавтори можуть мати доступ до певних підключень.</span><span class="sxs-lookup"><span data-stu-id="ed551-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="ed551-119">Вони залежать від того, які підключення налаштували та надали для спільного доступу адміністратори.</span><span class="sxs-lookup"><span data-stu-id="ed551-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="ed551-120">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ed551-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="ed551-121">Глядачі можуть лише переглядати наявні експорти, і не можуть створювати їх.</span><span class="sxs-lookup"><span data-stu-id="ed551-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="ed551-122">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="ed551-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ed551-123">Виберіть **Додати експорт**, щоб створити нове призначення експорту.</span><span class="sxs-lookup"><span data-stu-id="ed551-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="ed551-124">В області **Настроювання експорту** виберіть, яке підключення слід використовувати.</span><span class="sxs-lookup"><span data-stu-id="ed551-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="ed551-125">Керування [Підключеннями](connections.md) виконують адміністратори.</span><span class="sxs-lookup"><span data-stu-id="ed551-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="ed551-126">Укажіть потрібні відомості та виберіть **Зберегти**, щоб створити експорт.</span><span class="sxs-lookup"><span data-stu-id="ed551-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="ed551-127">Редагування експорту</span><span class="sxs-lookup"><span data-stu-id="ed551-127">Edit an export</span></span>

1. <span data-ttu-id="ed551-128">Виберіть вертикальні «три крапки» для призначення експорту, яке необхідно відредагувати.</span><span class="sxs-lookup"><span data-stu-id="ed551-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="ed551-129">У розкривному меню виберіть пункт **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="ed551-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="ed551-130">Змініть потрібні значення, а тоді виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="ed551-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="ed551-131">Перегляд експортів і відомостей про експорт</span><span class="sxs-lookup"><span data-stu-id="ed551-131">View Exports and export details</span></span>

<span data-ttu-id="ed551-132">Після створення призначень експорту вони відобразяться в розділі **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="ed551-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="ed551-133">Усі користувачі зможуть побачити, до яких даних надано спільний доступ, а також останній стан даних.</span><span class="sxs-lookup"><span data-stu-id="ed551-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="ed551-134">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="ed551-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ed551-135">Користувачі, які не мають дозволів на редагування, для перегляду відомостей експорту повинні вибирати **Перегляд** замість **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="ed551-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="ed551-136">На цій бічній панелі показано налаштування цього експорту.</span><span class="sxs-lookup"><span data-stu-id="ed551-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="ed551-137">Без дозволів на редагування змінювати значення не можна.</span><span class="sxs-lookup"><span data-stu-id="ed551-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="ed551-138">Виберіть **Закрити**, щоб повернутися до сторінки експортів.</span><span class="sxs-lookup"><span data-stu-id="ed551-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="ed551-139">Запуск експортів на вимогу</span><span class="sxs-lookup"><span data-stu-id="ed551-139">Run exports on demand</span></span>

<span data-ttu-id="ed551-140">Після налаштування експорту він виконуватиметься при кожному [запланованому оновленні](system.md#schedule-tab), якщо має робоче підключення.</span><span class="sxs-lookup"><span data-stu-id="ed551-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="ed551-141">Щоб експортувати дані, не чекаючи запланованого оновлення, відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="ed551-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="ed551-142">Існує два способи.</span><span class="sxs-lookup"><span data-stu-id="ed551-142">You have two options:</span></span>

- <span data-ttu-id="ed551-143">Щоб виконати всі експорти, виберіть **Виконати все** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="ed551-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="ed551-144">Щоб виконати один експорт, виберіть три крапки (...) для елемента списку, а потім виберіть **Виконати**.</span><span class="sxs-lookup"><span data-stu-id="ed551-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="ed551-145">Видалення експорту</span><span class="sxs-lookup"><span data-stu-id="ed551-145">Remove an Export</span></span>

1. <span data-ttu-id="ed551-146">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="ed551-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ed551-147">Виберіть вертикальні «три крапки» для Експорту, яке ви бажаєте видалити.</span><span class="sxs-lookup"><span data-stu-id="ed551-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="ed551-148">У розкривному меню виберіть **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="ed551-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="ed551-149">Щоб підтвердити видалення, виберіть **Видалити** на екрані підтвердження.</span><span class="sxs-lookup"><span data-stu-id="ed551-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
