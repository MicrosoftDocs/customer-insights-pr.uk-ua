---
title: Дії клієнта
description: Визначення дій клієнтів і перегляд їх у часовій шкалі клієнта.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667254"
---
# <a name="customer-activities"></a><span data-ttu-id="b5363-103">Дії клієнта</span><span class="sxs-lookup"><span data-stu-id="b5363-103">Customer activities</span></span>

<span data-ttu-id="b5363-104">Об'єднайте дії клієнтів з [різних джерел даних](data-sources.md) у Dynamics 365 Customer Insights, щоб створити часову шкалу для клієнта, в якому перелічені справи в хронологічній послідовності.</span><span class="sxs-lookup"><span data-stu-id="b5363-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="b5363-105">У програмах взаємодії з клієнтами в Dynamics 365 можна додати часову шкалу за допомогою [надбудови «Картка клієнта»](customer-card-add-in.md) або на приладній дошці Power BI.</span><span class="sxs-lookup"><span data-stu-id="b5363-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="b5363-106">Визначення справи</span><span class="sxs-lookup"><span data-stu-id="b5363-106">Define an activity</span></span>

<span data-ttu-id="b5363-107">Ваші джерела даних включають сутності з даними про транзакції та справи з кількох джерел даних.</span><span class="sxs-lookup"><span data-stu-id="b5363-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="b5363-108">Визначте ці сутності та виберіть справи, які потрібно переглянути на часовій шкалі клієнта.</span><span class="sxs-lookup"><span data-stu-id="b5363-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="b5363-109">Виберіть сутність, яка містить цільову справу або справи.</span><span class="sxs-lookup"><span data-stu-id="b5363-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="b5363-110">У розділі «Аналіз аудиторії» виберіть **Дані** > **Дії**.</span><span class="sxs-lookup"><span data-stu-id="b5363-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="b5363-111">Виберіть команду **Додати справу**.</span><span class="sxs-lookup"><span data-stu-id="b5363-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b5363-112">У сутності має бути принаймні один атрибут типу **Дата**, який слід включити до часової шкали. Ви не можете додавати сутності без полів **Дата**.</span><span class="sxs-lookup"><span data-stu-id="b5363-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="b5363-113">Елемент керування **Додати справу** буде вимкнуто, якщо не буде знайдено жодної такої сутності.</span><span class="sxs-lookup"><span data-stu-id="b5363-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="b5363-114">В області **Додати справу** задайте значення для вказаних нижче полів.</span><span class="sxs-lookup"><span data-stu-id="b5363-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="b5363-115">**Сутність**: виберіть сутність, яка містить дані про транзакції та справи.</span><span class="sxs-lookup"><span data-stu-id="b5363-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="b5363-116">**Первинний ключ**: виберіть поле, яке однозначно ідентифікує запис.</span><span class="sxs-lookup"><span data-stu-id="b5363-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="b5363-117">Він не має містити повторюваних значень, пустих або відсутніх значень.</span><span class="sxs-lookup"><span data-stu-id="b5363-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="b5363-118">**Позначка часу**: виберіть поле, яке представляє час початку справи.</span><span class="sxs-lookup"><span data-stu-id="b5363-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="b5363-119">**Подія**: виберіть поле, яке є подією для цієї справи.</span><span class="sxs-lookup"><span data-stu-id="b5363-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="b5363-120">**Веб-адреса**: виберіть поле, яке відповідає URL-адресі, що містить додаткову інформацію про цю справу.</span><span class="sxs-lookup"><span data-stu-id="b5363-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="b5363-121">Наприклад, транзакційна система, з якої походить ця справа.</span><span class="sxs-lookup"><span data-stu-id="b5363-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="b5363-122">Ця URL-адреса може бути будь-яким полем у джерелі даних, або для неї може створюватись нове поле із використанням засобів перетворення Power Query.</span><span class="sxs-lookup"><span data-stu-id="b5363-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="b5363-123">Дані цієї URL-адреси зберігатимуться в сутності «Універсальна справа», яку можна використовувати, отримуючи її з нижчої ланки виробничого процесу за допомогою API.</span><span class="sxs-lookup"><span data-stu-id="b5363-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="b5363-124">**Відомості**: крім того, виберіть поле, яке додається для введення додаткових відомостей.</span><span class="sxs-lookup"><span data-stu-id="b5363-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="b5363-125">**Піктограма**: можна вибрати піктограму, яка відповідає цій справі (необов’язково).</span><span class="sxs-lookup"><span data-stu-id="b5363-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="b5363-126">**Тип справи**: визначте посилання на тип справи у Common Data Model, який найкраще описує семантичне визначення справи.</span><span class="sxs-lookup"><span data-stu-id="b5363-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="b5363-127">У розділі **Налаштування зв’язку** настройте відомості про підключення даних про справи до відповідного клієнта.</span><span class="sxs-lookup"><span data-stu-id="b5363-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b5363-128">![Визначення зв’язку сутностей](media/activities-entities-define.png "Визначення зв’язку сутностей")</span><span class="sxs-lookup"><span data-stu-id="b5363-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="b5363-129">**Поле сутності справи**: виберіть поле в сутності справи, яке буде використовуватися для встановлення зв’язку з іншою сутністю.</span><span class="sxs-lookup"><span data-stu-id="b5363-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="b5363-130">**Сутність клієнта**: виберіть відповідну вихідну сутність клієнта, із якою буде зв’язано сутність справи.</span><span class="sxs-lookup"><span data-stu-id="b5363-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="b5363-131">Зв’язати можна лише ті вихідні сутності клієнта, які використовуються в процесі об’єднання даних.</span><span class="sxs-lookup"><span data-stu-id="b5363-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="b5363-132">**Поле сутності клієнта**: у цьому полі відображається первинний ключ вихідної сутності клієнта, вибраної в процесі зіставлення.</span><span class="sxs-lookup"><span data-stu-id="b5363-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="b5363-133">Це поле первинного ключа у вихідній сутності клієнта використовується для встановлення зв’язку із сутністю справи.</span><span class="sxs-lookup"><span data-stu-id="b5363-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="b5363-134">**Ім’я**: якщо зв’язок між цією сутністю справи і вибраною вихідною сутністю клієнта вже існує, ім’я зв’язку буде відображатися в режимі «лише для читання».</span><span class="sxs-lookup"><span data-stu-id="b5363-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="b5363-135">У разі відсутності такого зв’язку буде створено новий зв’язок з указаним тут іменем.</span><span class="sxs-lookup"><span data-stu-id="b5363-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="b5363-136">Натисніть кнопку **Зберегти**, щоб застосувати зміни.</span><span class="sxs-lookup"><span data-stu-id="b5363-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="b5363-137">На сторінці **Справи** виберіть команду **Виконати**.</span><span class="sxs-lookup"><span data-stu-id="b5363-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="b5363-138">Існує [шість типів станів](system.md#status-types) для завдань/процесів.</span><span class="sxs-lookup"><span data-stu-id="b5363-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b5363-139">Крім того, більшість процесів [залежать від інших низхідних процесів](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b5363-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b5363-140">Можна вибрати стан процесу, щоб переглянути докладні відомості про перебіг виконання всієї роботи.</span><span class="sxs-lookup"><span data-stu-id="b5363-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b5363-141">Після вибору **Переглянути відомості** для однієї з робіт завдання ви побачите додаткові відомості: час обробки, дата останньої обробки, а також усі помилки та попередження, пов'язані з завданням.</span><span class="sxs-lookup"><span data-stu-id="b5363-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="b5363-142">Редагування справи</span><span class="sxs-lookup"><span data-stu-id="b5363-142">Edit an activity</span></span>

1. <span data-ttu-id="b5363-143">У розділі «Аналіз аудиторії» виберіть **Дані** > **Дії**.</span><span class="sxs-lookup"><span data-stu-id="b5363-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="b5363-144">Виберіть сутність справи, яку потрібно відредагувати, і натисніть кнопку **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="b5363-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="b5363-145">Також можна навести курсор на рядок сутності та вибрати піктограму **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="b5363-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="b5363-146">Клацніть піктограму **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="b5363-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="b5363-147">В області **Змінити справу** оновіть значення та натисніть кнопку **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="b5363-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="b5363-148">На сторінці **Справи** виберіть команду **Виконати**.</span><span class="sxs-lookup"><span data-stu-id="b5363-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="b5363-149">Видалення справи</span><span class="sxs-lookup"><span data-stu-id="b5363-149">Delete an activity</span></span>

1. <span data-ttu-id="b5363-150">У розділі «Аналіз аудиторії» виберіть **Дані** > **Дії**.</span><span class="sxs-lookup"><span data-stu-id="b5363-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="b5363-151">Виберіть сутність справи, яку потрібно видалити, і натисніть кнопку **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="b5363-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="b5363-152">Також можна навести курсор на рядок сутності та вибрати піктограму **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="b5363-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="b5363-153">Крім того, можна вибрати кілька сутностей справ, які потрібно видалити одночасно.</span><span class="sxs-lookup"><span data-stu-id="b5363-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b5363-154">![Редагування або видалення зв’язку сутностей](media/activities-entities-edit-delete.png "Редагування або видалення зв’язку сутностей")</span><span class="sxs-lookup"><span data-stu-id="b5363-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="b5363-155">Натисніть піктограму **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="b5363-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="b5363-156">Підтвердьте видалення.</span><span class="sxs-lookup"><span data-stu-id="b5363-156">Confirm your deletion.</span></span>
