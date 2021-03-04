---
title: З’єднувач Power Apps
description: Підключення до Power Apps і Power Automate.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268941"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="d8cc0-103">З’єднувач Microsoft Power Apps (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="d8cc0-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="d8cc0-104">Додавайте уніфіковані профілі клієнтів до персоналізованих програм за допомогою Power Apps.</span><span class="sxs-lookup"><span data-stu-id="d8cc0-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="d8cc0-105">Підключення до Power Apps і Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d8cc0-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="d8cc0-106">Customer Insights – це одне із багатьох [доступних джерел даних у Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="d8cc0-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="d8cc0-107">Див. документацію Power Apps, щоб дізнатися, як [додати зв’язок даних до програми](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="d8cc0-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="d8cc0-108">Рекомендуємо також переглянути статтю про те, [як Power Apps використовує делегування для роботи із великими наборами даних у компонованих програмах](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="d8cc0-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="d8cc0-109">Доступні сутності</span><span class="sxs-lookup"><span data-stu-id="d8cc0-109">Available entities</span></span>

<span data-ttu-id="d8cc0-110">Після додавання Customer Insights як зв’язку даних можна вибрати зазначені нижче сутності в Power Apps.</span><span class="sxs-lookup"><span data-stu-id="d8cc0-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="d8cc0-111">Клієнт: для використання даних з [уніфікованого профілю клієнта](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d8cc0-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="d8cc0-112">UnifiedActivity: для відображення [часової шкали справ](activities.md) для програми.</span><span class="sxs-lookup"><span data-stu-id="d8cc0-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="d8cc0-113">Обмеження</span><span class="sxs-lookup"><span data-stu-id="d8cc0-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="d8cc0-114">Сутності, які можна отримувати</span><span class="sxs-lookup"><span data-stu-id="d8cc0-114">Retrievable entities</span></span>

<span data-ttu-id="d8cc0-115">За допомогою з'єднувача Power Apps можна отримувати лише сутності **Клієнт**, **UnifiedActivity** і **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="d8cc0-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="d8cc0-116">Інші сутності відображаються, оскільки з’єднувач, що лежить в основі, підтримує їх за допомогою тригерів у Power Automate.</span><span class="sxs-lookup"><span data-stu-id="d8cc0-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="d8cc0-117">Делегування</span><span class="sxs-lookup"><span data-stu-id="d8cc0-117">Delegation</span></span>

<span data-ttu-id="d8cc0-118">Делегація працює для сутності клієнта та об'єкта UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="d8cc0-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="d8cc0-119">Делегування сутності **Клієнт**: щоб використати делегування для цієї сутності, поля потрібно проіндексувати в розділі [Покажчик фільтра & пошуку](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="d8cc0-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="d8cc0-120">Делегування для **UnifiedActivity**: делегування для цієї сутності працює лише для полів **ActivityId** і **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="d8cc0-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="d8cc0-121">Для отримання додаткових відомостей про делегування див. [Функції та операції Power Apps, які підлягають делегуванню](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="d8cc0-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="d8cc0-122">Приклад елемента керування «Галерея»</span><span class="sxs-lookup"><span data-stu-id="d8cc0-122">Example gallery control</span></span>

<span data-ttu-id="d8cc0-123">Наприклад, можна додати профілі клієнтів до [елемента керування «галерея»](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="d8cc0-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="d8cc0-124">Додайте елемент керування **«Галерея»** до програми, яку ви створюєте.</span><span class="sxs-lookup"><span data-stu-id="d8cc0-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d8cc0-125">![Додавання елемента галереї](media/connector-powerapps9.png "Додавання елемента галереї")</span><span class="sxs-lookup"><span data-stu-id="d8cc0-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="d8cc0-126">Виберіть елемент **Клієнт** як джерело даних для елементів.</span><span class="sxs-lookup"><span data-stu-id="d8cc0-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d8cc0-127">![Вибір джерела даних](media/choose-datasource-powerapps.png "Вибір джерела даних")</span><span class="sxs-lookup"><span data-stu-id="d8cc0-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="d8cc0-128">Панель даних можна змінити праворуч, щоб вибрати поле для сутності клієнта, яке відображатиметься в колекції.</span><span class="sxs-lookup"><span data-stu-id="d8cc0-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="d8cc0-129">Якщо потрібно відобразити будь-яке поле з вибраного клієнта в колекції, введіть у властивості тексту підпис: **{Name_of_the_gallery}.Вибрано.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="d8cc0-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="d8cc0-130">Приклад: Gallery1.Вибрано.address1_city</span><span class="sxs-lookup"><span data-stu-id="d8cc0-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="d8cc0-131">Щоб відобразити уніфіковану часову шкалу для клієнта, додайте елемент «Колекція», а потім додайте властивість «Items» **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="d8cc0-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="d8cc0-132">Приклад: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="d8cc0-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]