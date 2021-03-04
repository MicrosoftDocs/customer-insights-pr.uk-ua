---
title: Перегляд профілів клієнтів
description: Отримайте комбінований перегляд ваших уніфікованих даних клієнтів.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a5d928ae518f3cb1afbf8e2b197e51b27665f6e0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269769"
---
# <a name="customer-profiles"></a><span data-ttu-id="16483-103">Профілі клієнтів</span><span class="sxs-lookup"><span data-stu-id="16483-103">Customer profiles</span></span>

<span data-ttu-id="16483-104">На сторінці **Клієнти** відображено комбінований вигляд ваших клієнтів на основі даних профілю, зібраних з [усіх джерел даних](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="16483-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="16483-105">Профілі клієнтів доступні відразу після [створення уніфікованої сутності «Клієнт»](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="16483-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="16483-106">Переконайтеся, що ви виконали процес уніфікації даних, щоб отримувати докладніше подання клієнтів.</span><span class="sxs-lookup"><span data-stu-id="16483-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="16483-107">Сторінка також дає змогу виконувати пошук клієнтів.</span><span class="sxs-lookup"><span data-stu-id="16483-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="16483-108">Клієнтами можуть бути фізичні особи або організації (попередній перегляд).</span><span class="sxs-lookup"><span data-stu-id="16483-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="16483-109">Кожний профіль клієнта або організації представлений плиткою.</span><span class="sxs-lookup"><span data-stu-id="16483-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="16483-110">Виберіть плитку для перегляду додаткових відомостей про певного клієнта або організацію.</span><span class="sxs-lookup"><span data-stu-id="16483-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="16483-111">Скористайтеся елементами керування нумерацією сторінок в нижній частині сторінки, щоб переглянути додаткові записи.</span><span class="sxs-lookup"><span data-stu-id="16483-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="16483-112">![Профілі клієнта B2C](media/profiles-customers.png "Профілі клієнта B2C")</span><span class="sxs-lookup"><span data-stu-id="16483-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="16483-113">Організації (Попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="16483-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="16483-114">![Профілі клієнта B2B](media/profile-customers-b2b.png "Профілі клієнта B2B")</span><span class="sxs-lookup"><span data-stu-id="16483-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="16483-115">Якщо ці плитки не відображаються під час вибору **Клієнти** в області переходів, адміністратор має [визначити принаймні один атрибут для пошуку](search-filter-index.md) в **покажчику «Пошук і фільтрація»**.</span><span class="sxs-lookup"><span data-stu-id="16483-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="16483-116">Пошук клієнтів</span><span class="sxs-lookup"><span data-stu-id="16483-116">Search for customers</span></span>

<span data-ttu-id="16483-117">Виконуйте пошук клієнтів шляхом введення імені або іншого атрибуту в поле пошуку.</span><span class="sxs-lookup"><span data-stu-id="16483-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="16483-118">Пошук працює лише в рамках сутності «Профіль клієнта», створеного під час процесу уніфікації даних.</span><span class="sxs-lookup"><span data-stu-id="16483-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="16483-119">Адміністратор може налаштувати атрибути, доступні для пошуку за допомогою сторінки **Покажчик «Пошук і фільтрація»**.</span><span class="sxs-lookup"><span data-stu-id="16483-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="16483-120">Додаткові відомості див. в розділі [Покажчик «Пошук і фільтрація»](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="16483-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="16483-121">Фільтрування клієнтів</span><span class="sxs-lookup"><span data-stu-id="16483-121">Filter customers</span></span>

<span data-ttu-id="16483-122">Можна фільтрувати клієнтів за полями сутності «Профіль клієнта».</span><span class="sxs-lookup"><span data-stu-id="16483-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="16483-123">Як і під час пошуку, адміністратор спочатку має визначити поля як доступні для фільтрування за допомогою сторінки **Покажчик «Пошук і фільтрація»**.</span><span class="sxs-lookup"><span data-stu-id="16483-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="16483-124">Виберіть пункт **Фільтр** на сторінці **Клієнти**.</span><span class="sxs-lookup"><span data-stu-id="16483-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="16483-125">Установіть прапорці поруч із атрибутами, за якими потрібно відфільтрувати клієнтів.</span><span class="sxs-lookup"><span data-stu-id="16483-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="16483-126">![Профілі клієнтів](media/profiles-customers3.png "Профілі клієнтів")</span><span class="sxs-lookup"><span data-stu-id="16483-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="16483-127">Видаліть фільтри, вибравши параметр **Очистити фільтри** на сторінці **Клієнти**.</span><span class="sxs-lookup"><span data-stu-id="16483-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="16483-128">Сторінка відомостей про клієнта</span><span class="sxs-lookup"><span data-stu-id="16483-128">Customer details page</span></span>

<span data-ttu-id="16483-129">Виберіть будь-який із файлів клієнта, щоб відкрити **сторінку відомостей про клієнта**.</span><span class="sxs-lookup"><span data-stu-id="16483-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="16483-130">Це подання містить уніфіковані відомості про вибраного клієнта.</span><span class="sxs-lookup"><span data-stu-id="16483-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="16483-131">Відомості про клієнта містять:</span><span class="sxs-lookup"><span data-stu-id="16483-131">Customer details include:</span></span>

-   <span data-ttu-id="16483-132">**Плитка профілю клієнта**: на цій плитці відображаються різні значення з єдиної сутності профілю клієнта.</span><span class="sxs-lookup"><span data-stu-id="16483-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="16483-133">Ці відомості можуть містити адресу електронної пошти, ім'я, місто тощо.</span><span class="sxs-lookup"><span data-stu-id="16483-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="16483-134">**Потенційні інтереси, потенційні бренди:** відображається, чи налаштували ви власне збагачення.</span><span class="sxs-lookup"><span data-stu-id="16483-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="16483-135">Представляє потенційні інтереси та перспективи, які може мати клієнт з профілем. аналогічним цьому клієнту.</span><span class="sxs-lookup"><span data-stu-id="16483-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="16483-136">Для отримання додаткових відомостей див. розділ [Поповніть профілі клієнтів за рахунок подібності інтересів та брендів](enrichment-microsoft-graph.md)/</span><span class="sxs-lookup"><span data-stu-id="16483-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="16483-137">**Заходи:** відображається, якщо було настроєно один або кілька показників певного типу: показники облікового запису клієнта.</span><span class="sxs-lookup"><span data-stu-id="16483-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="16483-138">Вони включають в себе розраховані KPI для клієнтів на окремому рівні клієнта.</span><span class="sxs-lookup"><span data-stu-id="16483-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="16483-139">Для отримання додаткових відомостей див. [розділ «Визначення та керування показниками»](measures.md).</span><span class="sxs-lookup"><span data-stu-id="16483-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="16483-140">**Часова шкала для справ:** відображається за наявності настроєних справ.</span><span class="sxs-lookup"><span data-stu-id="16483-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="16483-141">Подання часової шкали містить хронологічно впорядковані справи цього клієнта, починаючи з останньої справи.</span><span class="sxs-lookup"><span data-stu-id="16483-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="16483-142">Додаткові відомості див. в розділі [Справи клієнта](activities.md).</span><span class="sxs-lookup"><span data-stu-id="16483-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="16483-143">Виберіть **Повернутися до клієнтів**, щоб повернутися до сторінки пошуку клієнтів.</span><span class="sxs-lookup"><span data-stu-id="16483-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="16483-144">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="16483-144">Next steps</span></span>

<span data-ttu-id="16483-145">[Додайте інші джерела даних](data-sources.md) або [створіть сегменти клієнта](segments.md).</span><span class="sxs-lookup"><span data-stu-id="16483-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]