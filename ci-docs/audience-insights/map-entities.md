---
title: Зіставлення сутностей для уніфікації даних
description: Зіставлення даних для створення уніфікованих профілів клієнтів.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407269"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="7c604-103">Зіставлення сутностей і атрибутів</span><span class="sxs-lookup"><span data-stu-id="7c604-103">Map entities and attributes</span></span>

<span data-ttu-id="7c604-104">**Зіставлення** — це перший етап процесу уніфікації даних аналізу аудиторії.</span><span class="sxs-lookup"><span data-stu-id="7c604-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="7c604-105">Зіставлення складається з трьох етапів, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="7c604-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="7c604-106">*Вибір сутності*: визначте доступні для комбінування сутності, які ведуть до набору даних із більш повними відомостями про клієнтів.</span><span class="sxs-lookup"><span data-stu-id="7c604-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="7c604-107">*Вибір атрибута*: для кожної сутності визначте стовпці, які потрібно поєднати та узгодити у фазах *пошук відповідностей* та *злиття*.</span><span class="sxs-lookup"><span data-stu-id="7c604-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="7c604-108">Ці стовпці називаються *Атрибути*.</span><span class="sxs-lookup"><span data-stu-id="7c604-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="7c604-109">*Вибір первинного ключа та семантичного типу*: для кожної сутності визначте атрибут, який потрібно визначити в якості первинного ключа для цієї сутності, а також для кожного атрибута визначте семантичний тип, що описує цей атрибут найкращим чином.</span><span class="sxs-lookup"><span data-stu-id="7c604-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="7c604-110">Додаткові відомості про загальний потік уніфікації даних див. в розділі [Уніфікація](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="7c604-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="7c604-111">Вибір перших сутностей</span><span class="sxs-lookup"><span data-stu-id="7c604-111">Select the first entities</span></span>

1. <span data-ttu-id="7c604-112">У розділі «Аналіз аудиторії» відкрийте **Дані** > **Уніфікувати** > **Зіставити**.</span><span class="sxs-lookup"><span data-stu-id="7c604-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="7c604-113">Щоб почати фазу зіставлення, виберіть **Вибрати сутності**.</span><span class="sxs-lookup"><span data-stu-id="7c604-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="7c604-114">Виберіть сутності та атрибути, які будуть використовуватися на фазах *зіставлення* та *злиття*.</span><span class="sxs-lookup"><span data-stu-id="7c604-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="7c604-115">Можна вибрати необхідні атрибути з сутності окремо або включити всі атрибути сутності, установивши прапорець **Включити всі поля** на рівні сутності.</span><span class="sxs-lookup"><span data-stu-id="7c604-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="7c604-116">Рекомендовано вибрати щонайменше дві сутності для того, щоб скористатися можливостями процесу уніфікації даних.</span><span class="sxs-lookup"><span data-stu-id="7c604-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7c604-117">![Приклад додавання сутностей](media/data-manager-configure-map-add-entities-example.png "Приклад додавання сутностей")</span><span class="sxs-lookup"><span data-stu-id="7c604-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="7c604-118">У цьому прикладі ми додаємо сутності **eCommerceContacts** і **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7c604-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="7c604-119">Вибираючи ці сутності, можна отримати аналітичні висновки щодо того, які з онлайн-клієнтів бізнесу є учасниками програми лояльності.</span><span class="sxs-lookup"><span data-stu-id="7c604-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="7c604-120">Можна шукати за ключовими словами в усіх атрибутах і сутностях, щоб вибрати атрибути для зіставлення.</span><span class="sxs-lookup"><span data-stu-id="7c604-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7c604-121">![Приклад пошуку полів](media/data-manager-configure-map-search-fields-example.png "Приклад пошуку полів")</span><span class="sxs-lookup"><span data-stu-id="7c604-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="7c604-122">Виберіть **Застосовувати**, щоб підтвердити вибір.</span><span class="sxs-lookup"><span data-stu-id="7c604-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="7c604-123">Вибір первинного ключа та семантичного типу для атрибутів</span><span class="sxs-lookup"><span data-stu-id="7c604-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="7c604-124">Після вибору сутностей список доступний для рецензування на сторінці **Зіставити**.</span><span class="sxs-lookup"><span data-stu-id="7c604-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="7c604-125">Визначте первинний ключа для сутності та визначте семантичний типу атрибута у сутності.</span><span class="sxs-lookup"><span data-stu-id="7c604-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="7c604-126">**Первинний ключ**: виберіть один атрибут як первинний ключ для кожної сутності.</span><span class="sxs-lookup"><span data-stu-id="7c604-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="7c604-127">Атрибут, який має стати дійсним первинним ключем, не повинен мати повторюваних значень, відсутніх значень або значень null.</span><span class="sxs-lookup"><span data-stu-id="7c604-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="7c604-128">Атрибути типу даних «рядок», «ціле число» та «GUID» можна використовувати в якості первинних ключів; вони відображатимуться в полі для вибору.</span><span class="sxs-lookup"><span data-stu-id="7c604-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="7c604-129">**Семантичний тип атрибута**: категорії атрибутів (наприклад, адреса електронної пошти або ім’я).</span><span class="sxs-lookup"><span data-stu-id="7c604-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="7c604-130">Щоб використовувати моделі ШІ для інтелектуального прогнозування семантики, економії часу та покращення точності, встановіть для параметра **Інтелектуальне зіставлення** значення **Увімк.**.</span><span class="sxs-lookup"><span data-stu-id="7c604-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="7c604-131">Інтелектуальне зіставлення виділяє рекомендацію семантики на основі ШІ в полі **Тип**.</span><span class="sxs-lookup"><span data-stu-id="7c604-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="7c604-132">Якщо встановити значення **Вимк.**, ви побачите наші стандартні рекомендації із зіставлення.</span><span class="sxs-lookup"><span data-stu-id="7c604-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="7c604-133">Можна вибрати будь-який семантичний тип із доступного списку параметрів і перевизначити запропонований вибір.</span><span class="sxs-lookup"><span data-stu-id="7c604-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7c604-134">![Тип атрибута та семантичний прогноз](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Тип атрибута та семантичний прогноз")</span><span class="sxs-lookup"><span data-stu-id="7c604-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="7c604-135">Крім того, можна додати настроюваний семантичний тип.</span><span class="sxs-lookup"><span data-stu-id="7c604-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="7c604-136">Виберіть поле типу для атрибута та введіть ім’я настроюваного семантичного типу.</span><span class="sxs-lookup"><span data-stu-id="7c604-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="7c604-137">Таким чином, також можна змінити типи атрибутів, визначені системою.</span><span class="sxs-lookup"><span data-stu-id="7c604-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="7c604-138">Усі атрибути, для яких автоматично визначаються семантичні типи, згруповані в розділі **Перегляд зіставлених полів**.</span><span class="sxs-lookup"><span data-stu-id="7c604-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="7c604-139">Перегляньте ці атрибути та їх семантичні типи, оскільки вони використовуватимуться для поєднання сутностей на етапі злиття процесу уніфікації даних.</span><span class="sxs-lookup"><span data-stu-id="7c604-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="7c604-140">Атрибути, які не було автоматично зіставлено із семантичними типами, згруповані в розділі **Визначте дані у незіставлених полях**.</span><span class="sxs-lookup"><span data-stu-id="7c604-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="7c604-141">Виберіть поле семантичного типу для незіставлених атрибутів або введіть ім'я настроюваного типу атрибута.</span><span class="sxs-lookup"><span data-stu-id="7c604-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7c604-142">![Первинний ключ і тип атрибута](media/data-manager-configure-map-add-attributes.png "Первинний ключ і тип атрибута")</span><span class="sxs-lookup"><span data-stu-id="7c604-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="7c604-143">Одне поле має бути зіставленим із семантичним типом Person.FullName для відображення імені клієнта на картці клієнта.</span><span class="sxs-lookup"><span data-stu-id="7c604-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="7c604-144">В іншому разі картка клієнта відображатиметься без імені.</span><span class="sxs-lookup"><span data-stu-id="7c604-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="7c604-145">Додавання та вилучення атрибутів і сутностей</span><span class="sxs-lookup"><span data-stu-id="7c604-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="7c604-146">У розділі **Уніфікація** > **Зіставлення** виберіть **Редагувати поля**.</span><span class="sxs-lookup"><span data-stu-id="7c604-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="7c604-147">В області **Редагувати поля** додайте або вилучіть атрибути та сутності.</span><span class="sxs-lookup"><span data-stu-id="7c604-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="7c604-148">Скористайтеся пошуком або прокрутіть, щоб знайти та вибрати потрібні вам атрибути та сутності.</span><span class="sxs-lookup"><span data-stu-id="7c604-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="7c604-149">Якщо атрибут або сутність вже зіставлено, їх не можна видалити.</span><span class="sxs-lookup"><span data-stu-id="7c604-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7c604-150">![Додавання або видалення атрибутів](media/configure-data-map-edit.png "Додавання або видалення атрибутів")</span><span class="sxs-lookup"><span data-stu-id="7c604-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="7c604-151">Виберіть **Застосувати**.</span><span class="sxs-lookup"><span data-stu-id="7c604-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="7c604-152">Додавання зображень до профілів</span><span class="sxs-lookup"><span data-stu-id="7c604-152">Add images to profiles</span></span>

<span data-ttu-id="7c604-153">Якщо сутність містить URL-адреси загальнодоступних зображень або логотипів профілів, їх можна додати до уніфікованого профілю клієнта.</span><span class="sxs-lookup"><span data-stu-id="7c604-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="7c604-154">Виберіть сутність і знайдіть поле, яке містить URL-адресу зображення профілю.</span><span class="sxs-lookup"><span data-stu-id="7c604-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="7c604-155">У поле вводу **Тип** вручну введіть таке значення:</span><span class="sxs-lookup"><span data-stu-id="7c604-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="7c604-156">Для людини: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="7c604-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="7c604-157">Для організації: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="7c604-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="7c604-158">Продовжуйте виконання кроків із уніфікації, та обов’язково переконайтеся, що на кроці [Злиття](merge-entities.md) додано серед інших атрибут, який містить URL-адресу зображення.</span><span class="sxs-lookup"><span data-stu-id="7c604-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="7c604-159">Налаштування атрибутів для організацій</span><span class="sxs-lookup"><span data-stu-id="7c604-159">Set attributes for organizations</span></span>

<span data-ttu-id="7c604-160">Для організацій (підготовча версія) тип атрибута має бути зіставлений з «Organization.Name»</span><span class="sxs-lookup"><span data-stu-id="7c604-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="7c604-161">![Первинний ключ і тип атрибута B2B](media/configure-data-map-edit-b2b.png "Первинний ключ і тип атрибута B2B")</span><span class="sxs-lookup"><span data-stu-id="7c604-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="7c604-162">Наступний крок...</span><span class="sxs-lookup"><span data-stu-id="7c604-162">Next step</span></span>

<span data-ttu-id="7c604-163">У рамках процесу уніфікації даних перейдіть на сторінку **Пошук відповідностей**.</span><span class="sxs-lookup"><span data-stu-id="7c604-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="7c604-164">Ознайомтеся з розділом [**Пошук відповідностей**](match-entities.md), щоб дізнатися про цю фазу.</span><span class="sxs-lookup"><span data-stu-id="7c604-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="7c604-165">Перегляньте таке відео: [Початок роботи: створення уніфікованого профілю клієнта](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="7c604-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
