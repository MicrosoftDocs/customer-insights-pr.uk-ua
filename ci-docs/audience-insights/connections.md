---
title: Підключення з Customer Insights до інших служб.
description: Надавайте іншим службам спільний доступ до даних.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896122"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="489a3-103">Огляд підключень (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="489a3-103">Connections (preview) overview</span></span>

<span data-ttu-id="489a3-104">Підключення є основним компонентом, який забезпечує передавання даних до Customer Insights і з Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="489a3-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="489a3-105">Кожне підключення встановлює обмін даними з певною службою.</span><span class="sxs-lookup"><span data-stu-id="489a3-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="489a3-106">Підключення є фундаментом для [налаштування сторонніх доповнень](enrichment-hub.md), а також [налаштування експорту](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="489a3-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="489a3-107">Одне й те саме підключення можна використовувати багато разів.</span><span class="sxs-lookup"><span data-stu-id="489a3-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="489a3-108">Наприклад, одне підключення до Dynamics 365 Marketing працює для неодноразового експорту даних, а одне підключення до Leadspace можна використовувати для кількох доповнень.</span><span class="sxs-lookup"><span data-stu-id="489a3-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="489a3-109">Перейдіть до розділу **Адміністратор** > **Підключення**, щоб створювати й переглядати підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="489a3-110">На вкладці **Підключення** відображаються всі активні підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="489a3-111">У цьому списку для кожного підключення відображається один рядок.</span><span class="sxs-lookup"><span data-stu-id="489a3-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="489a3-112">Отримайте швидкий огляд і опис, а також з’ясуйте, що саме ви можете зробити з кожним параметром розширення на вкладці **Виявити**.</span><span class="sxs-lookup"><span data-stu-id="489a3-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="489a3-113">Експорт</span><span class="sxs-lookup"><span data-stu-id="489a3-113">Exports</span></span>

<span data-ttu-id="489a3-114">Нові підключення можуть налаштовувати лише адміністратори, але вони можуть надати доступ авторам, які користуватимуться наявними підключеннями.</span><span class="sxs-lookup"><span data-stu-id="489a3-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="489a3-115">Адміністратори керують тим, куди можуть відправлятися дані, при цьому автори визначають навантаження та частоту з урахуванням своїх потреб.</span><span class="sxs-lookup"><span data-stu-id="489a3-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="489a3-116">Докладніші відомості див. у розділі [Дозвольте авторам використовувати підключення для експорту](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="489a3-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="489a3-117">Збагачення</span><span class="sxs-lookup"><span data-stu-id="489a3-117">Enrichments</span></span>

<span data-ttu-id="489a3-118">Тільки адміністратори можуть налаштовувати нові підключення, але створені підключення завжди доступні як для адміністраторів, так і для авторів.</span><span class="sxs-lookup"><span data-stu-id="489a3-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="489a3-119">Адміністратори керують обліковими даними й надають згоду на передавання даних.</span><span class="sxs-lookup"><span data-stu-id="489a3-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="489a3-120">Після цього підключення можуть використовуватися для доповнень як адміністраторами, так і авторами.</span><span class="sxs-lookup"><span data-stu-id="489a3-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="489a3-121">Додайте нове підключення</span><span class="sxs-lookup"><span data-stu-id="489a3-121">Add a new connection</span></span>

<span data-ttu-id="489a3-122">Щоб додавати підключення, ви повинні мати [дозволи адміністратора](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="489a3-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="489a3-123">Якщо ви підключаєтеся до інших служб Майкрософт, ми припускаємо, що обидві служби перебувають у одній і тій самій організації.</span><span class="sxs-lookup"><span data-stu-id="489a3-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="489a3-124">Перейдіть до розділу **Адміністратор** > **Підключення (підготовча версія)**.</span><span class="sxs-lookup"><span data-stu-id="489a3-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="489a3-125">Перейдіть на вкладку **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="489a3-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="489a3-126">Виберіть **Додати підключення**, щоб створити нове підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="489a3-127">У розкривному меню виберіть тип підключення, який ви бажаєте створити.</span><span class="sxs-lookup"><span data-stu-id="489a3-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="489a3-128">У області **Налаштування підключення** введіть необхідні докладні відомості.</span><span class="sxs-lookup"><span data-stu-id="489a3-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="489a3-129">Поля **Коротке ім’я** та тип підключення описують підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="489a3-130">Ми рекомендуємо вибирати ім’я, яке роз’яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="489a3-131">Якими саме будуть поля залежить від того, до якої служби ви підключаєтеся.</span><span class="sxs-lookup"><span data-stu-id="489a3-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="489a3-132">Докладніше про певний тип з'єднання можна дізнатися в статті про цільову службу.</span><span class="sxs-lookup"><span data-stu-id="489a3-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="489a3-133">Щоб створити підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="489a3-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="489a3-134">Крім того, можна вибрати параметр **Налаштування** на плитці на вкладці **Виявлення**.</span><span class="sxs-lookup"><span data-stu-id="489a3-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="489a3-135">Надайте авторам дозвіл на використання підключення для експорту</span><span class="sxs-lookup"><span data-stu-id="489a3-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="489a3-136">Коли ви налаштовуєте або редагуєте підключення для експорту, ви вибираєте, яким саме користувачам можна дозволити користуватися саме цим підключенням для визначення [експорту](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="489a3-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="489a3-137">За промовчанням підключення доступне для користувачів із роллю адміністратора.</span><span class="sxs-lookup"><span data-stu-id="489a3-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="489a3-138">Ви можете змінити це налаштування в розділі **Вибрати користувачів, які можуть використовувати це підключення** й дозволити користувачам, які мають роль автора, користуватися цим підключенням.</span><span class="sxs-lookup"><span data-stu-id="489a3-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="489a3-139">Автори не зможуть переглядати або редагувати підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="489a3-140">При створенні експорту вони бачитимуть лише коротке ім’я й тип підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="489a3-141">Способом надання спільного доступу до підключення ви надаєте дозвіл авторам використовувати підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="489a3-142">При налаштуванні експорту автори бачитимуть спільні підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="489a3-143">Вони зможуть бачити кожен експорт, що здійснюється з використанням конкретно цього підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="489a3-144">Ви можете змінити це налаштування, але при цьому зберегти експорт, який вже було визначено авторами.</span><span class="sxs-lookup"><span data-stu-id="489a3-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="489a3-145">Редагуйте підключення</span><span class="sxs-lookup"><span data-stu-id="489a3-145">Edit a connection</span></span>

1. <span data-ttu-id="489a3-146">Перейдіть до розділу **Адміністратор** > **Підключення (підготовча версія)**.</span><span class="sxs-lookup"><span data-stu-id="489a3-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="489a3-147">Перейдіть на вкладку **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="489a3-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="489a3-148">Виберіть вертикальні три крапки для підключення, яке ви бажаєте редагувати.</span><span class="sxs-lookup"><span data-stu-id="489a3-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="489a3-149">Виберіть **Редагування**.</span><span class="sxs-lookup"><span data-stu-id="489a3-149">Select **Edit**.</span></span>

1. <span data-ttu-id="489a3-150">Змініть потрібні значення, а тоді виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="489a3-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="489a3-151">Видаліть підключення</span><span class="sxs-lookup"><span data-stu-id="489a3-151">Remove a connection</span></span>

<span data-ttu-id="489a3-152">Якщо підключення, яке ви видаляєте, використовується збагаченнями або експортом, спочатку вам буде потрібно їх від’єднати або видалити.</span><span class="sxs-lookup"><span data-stu-id="489a3-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="489a3-153">Діалогове вікно видалення спрямує вас до відповідних доповнень або експорту.</span><span class="sxs-lookup"><span data-stu-id="489a3-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="489a3-154">Відокремлені збагачення й експорт стають неактивними.</span><span class="sxs-lookup"><span data-stu-id="489a3-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="489a3-155">Ви можете їх повторно активувати способом додавання до них ще одного підключення на сторінці [Збагачення](enrichment-hub.md) або [Експорт](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="489a3-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="489a3-156">Перейдіть до розділу **Адміністратор** > **Підключення (підготовча версія)**.</span><span class="sxs-lookup"><span data-stu-id="489a3-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="489a3-157">Перейдіть на вкладку **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="489a3-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="489a3-158">Виберіть вертикальні три крапки для підключення, яке ви бажаєте видалити.</span><span class="sxs-lookup"><span data-stu-id="489a3-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="489a3-159">У розкривному меню виберіть **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="489a3-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="489a3-160">З’явиться діалогове вікно підтвердження.</span><span class="sxs-lookup"><span data-stu-id="489a3-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="489a3-161">Якщо є збагачення або експорт, які використовують це підключення, виберіть кнопку, щоб побачити, для якої саме операції використовується це підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="489a3-162">**Експорт:** Ви можете на свій вибір видалити або відключити експорт, щоб мати змогу видалити підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="489a3-163">Щоб відключити експорт, адміністратори можуть скористатися справою **Відключити**.</span><span class="sxs-lookup"><span data-stu-id="489a3-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="489a3-164">Ця справа доступна як для окремих, так і для кількох вибраних операцій експорту.</span><span class="sxs-lookup"><span data-stu-id="489a3-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="489a3-165">При відключенні ви зберігаєте налаштування експорту, але вони не запускатимуться, доки не буде додано ще одне підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="489a3-166">**Збагачення:** ви можете на свій вибір видалити або деактивувати збагачення, щоб мати змогу видалити підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="489a3-167">Коли підключення більше не матиме залежностей, поверніться до розділу **Адміністратор** > **Підключення** й повторіть спробу видалити підключення.</span><span class="sxs-lookup"><span data-stu-id="489a3-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="489a3-168">Щоб підтвердити видалення, виберіть **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="489a3-168">To confirm the deletion select **Remove**.</span></span>

