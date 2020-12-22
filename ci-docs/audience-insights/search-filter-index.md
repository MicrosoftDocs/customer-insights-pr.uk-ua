---
title: Пошук та фільтрування профілів клієнтів
description: Швидко знаходьте відомості про уніфіковані профілі клієнтів та фільтруйте за вказаними атрибутами.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407279"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="21679-103">Профілі клієнтів: покажчик «Пошук і фільтрація»</span><span class="sxs-lookup"><span data-stu-id="21679-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="21679-104">Результатом об’єднання даних клієнтів є сутність профілю клієнта, яка надає уніфіковане подання в загальну базу клієнтів.</span><span class="sxs-lookup"><span data-stu-id="21679-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="21679-105">Щоб швидко [знаходити інформацію про певного клієнта або групу клієнтів](customer-profiles.md), можна налаштувати можливості **Пошук** та **Фільтрувати** на сторінці **Клієнти**.</span><span class="sxs-lookup"><span data-stu-id="21679-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="21679-106">Читайте розділ далі, щоб дізнатися про те, як адміністратори можуть редагувати ці атрибути на сторінці **Покажчик «Пошук і фільтрація»**, які доступні користувачам для пошуку та фільтрації.</span><span class="sxs-lookup"><span data-stu-id="21679-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="21679-107">![Фільтр пошуку](media/search-filter.png "Фільтр пошуку")</span><span class="sxs-lookup"><span data-stu-id="21679-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="21679-108">Додавання полів і визначення атрибутів</span><span class="sxs-lookup"><span data-stu-id="21679-108">Add fields and specify attributes</span></span>

<span data-ttu-id="21679-109">Якщо ви в перший раз визначаєте атрибути, доступні для пошуку, як адміністратор, спочатку слід визначити індексовані поля.</span><span class="sxs-lookup"><span data-stu-id="21679-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="21679-110">Радимо вибрати всі атрибути, за якими користувачі можуть шукати та фільтрувати клієнтів на сторінці **Клієнти**.</span><span class="sxs-lookup"><span data-stu-id="21679-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="21679-111">Можна вказати лише атрибути, які існують у сутності профілю клієнта, який було створено під час процесу уніфікації даних.</span><span class="sxs-lookup"><span data-stu-id="21679-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="21679-112">Відкрийте сторінку **Клієнти** та виберіть **Покажчик «Пошук і фільтрація»**.</span><span class="sxs-lookup"><span data-stu-id="21679-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="21679-113">Ми створюємо конфігурацію покажчика пошуку за замовчуванням, використовуючи доступні атрибути у сутності «Клієнт», з семантичних типів, зазначених нижче, як це визначено на сторінці «Зіставлення».</span><span class="sxs-lookup"><span data-stu-id="21679-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="21679-114">Ім'я, Прізвище, По батькові (друге ім'я), Повне ім'я особи</span><span class="sxs-lookup"><span data-stu-id="21679-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="21679-115">Назва організації</span><span class="sxs-lookup"><span data-stu-id="21679-115">Organization Name</span></span>
> - <span data-ttu-id="21679-116">Адреса електронної пошти</span><span class="sxs-lookup"><span data-stu-id="21679-116">Email address</span></span>
> - <span data-ttu-id="21679-117">Номер телефону</span><span class="sxs-lookup"><span data-stu-id="21679-117">Phone number</span></span>
> - <span data-ttu-id="21679-118">Відомості про розташування</span><span class="sxs-lookup"><span data-stu-id="21679-118">Location information</span></span>

2. <span data-ttu-id="21679-119">Виберіть **+ Додати**, щоб вказати індексовані поля.</span><span class="sxs-lookup"><span data-stu-id="21679-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="21679-120">Виберіть атрибути у списку, які необхідно додати як індексовані поля.</span><span class="sxs-lookup"><span data-stu-id="21679-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="21679-121">Щоб додати інші атрибути, виберіть елемент **Додати**.</span><span class="sxs-lookup"><span data-stu-id="21679-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="21679-122">Крім того, ви можете видалити будь-які вибрані атрибути, вибравши символ **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="21679-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="21679-123">Огляд таблиці індексованих полів клієнтів</span><span class="sxs-lookup"><span data-stu-id="21679-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="21679-124">В представленій таблиці міститься описана нижче інформація.</span><span class="sxs-lookup"><span data-stu-id="21679-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="21679-125">**Ім’я**: це ім’я атрибута, яке відображається в сутності профілю клієнта.</span><span class="sxs-lookup"><span data-stu-id="21679-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="21679-126">**Тип даних**: указує, чи є тип даних рядком, числом або датою.</span><span class="sxs-lookup"><span data-stu-id="21679-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="21679-127">**Включено в пошук**: указує, чи можна використовувати цей атрибут для пошуку клієнтів на сторінці **Клієнти** за допомогою поля **Пошук**.</span><span class="sxs-lookup"><span data-stu-id="21679-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="21679-128">**Додати фільтр**: елемент керування для визначення того, як цей атрибут можна використовувати для фільтрації на сторінці **Клієнти**.</span><span class="sxs-lookup"><span data-stu-id="21679-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="21679-129">Змінення параметрів фільтрації для певного атрибута</span><span class="sxs-lookup"><span data-stu-id="21679-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="21679-130">Меню **Фільтрувати** на сторінці **Клієнти** можна включати різну кількість рівнів атрибутів (наприклад, різні вікові групи, за якими можна фільтрувати клієнтів).</span><span class="sxs-lookup"><span data-stu-id="21679-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="21679-131">Виберіть елемент **Додати фільтр** для певного атрибута на сторінці **Покажчик «Пошук і фільтрація»**.</span><span class="sxs-lookup"><span data-stu-id="21679-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="21679-132">Можна задати кількість результатів і порядок, в якому їх буде організовано.</span><span class="sxs-lookup"><span data-stu-id="21679-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="21679-133">Залежно від типу даних атрибута відобразиться одна з зображених нижче областей.</span><span class="sxs-lookup"><span data-stu-id="21679-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="21679-134">Атрибути типу «рядок»: укажіть кількість бажаних результатів на панелі **Параметри фільтра рядків**, а також політику упорядкування, за якою вони будуть організовані.</span><span class="sxs-lookup"><span data-stu-id="21679-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="21679-135">Атрибути типу «число»: укажіть інтервали на панелі **Параметри числового фільтра**, а також політику упорядкування, за якою вони будуть організовані.</span><span class="sxs-lookup"><span data-stu-id="21679-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="21679-136">Атрибути типу «дата»: укажіть інтервали на панелі **Параметри фільтра даних**, а також політику упорядкування, за якою вони будуть організовані.</span><span class="sxs-lookup"><span data-stu-id="21679-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="21679-137">Натисніть кнопку **Зберегти**, щоб застосувати зміни.</span><span class="sxs-lookup"><span data-stu-id="21679-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="21679-138">Після закінчення виберіть команду **Виконати**, щоб застосовувати настройки.</span><span class="sxs-lookup"><span data-stu-id="21679-138">Select **Run** once you're ready to apply your settings.</span></span>
