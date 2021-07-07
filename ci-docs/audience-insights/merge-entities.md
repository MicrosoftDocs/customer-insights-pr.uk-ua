---
title: Злиття сутностей в уніфікації даних
description: Злиття сутностей для створення уніфікованих профілів клієнтів.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305683"
---
# <a name="merge-entities"></a><span data-ttu-id="591b1-103">Об'єднання сутностями</span><span class="sxs-lookup"><span data-stu-id="591b1-103">Merge entities</span></span>

<span data-ttu-id="591b1-104">Фаза злиття — це остання фаза в процесі уніфікації даних.</span><span class="sxs-lookup"><span data-stu-id="591b1-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="591b1-105">Її мета — узгодження суперечливих даних.</span><span class="sxs-lookup"><span data-stu-id="591b1-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="591b1-106">Приклади суперечливих даних можуть містити ім’я клієнта, знайдене в двох наборах даних, яке відображається в кожному наборі по-різному (Grant Marshall і Grant Marshal) або номер телефону, який відрізняється форматом (617-803-091X і 617803091X).</span><span class="sxs-lookup"><span data-stu-id="591b1-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="591b1-107">Злиття цих конфліктуючих точок даних виконується на основі методу «атрибут за атрибутом».</span><span class="sxs-lookup"><span data-stu-id="591b1-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Сторінка злиття у процесі уніфікації даних, де відображається таблиця із об’єднаними полями, які визначають уніфікований профіль клієнта.":::

<span data-ttu-id="591b1-109">Після завершення [фази пошуку відповідностей](match-entities.md) ви починаєте фазу злиття. Для цього виберіть плитку **Злиття** на сторінці **Уніфікувати**.</span><span class="sxs-lookup"><span data-stu-id="591b1-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="591b1-110">Перегляд системних рекомендацій</span><span class="sxs-lookup"><span data-stu-id="591b1-110">Review system recommendations</span></span>

<span data-ttu-id="591b1-111">У розділі **Дані** > **Уніфікація** > **Злиття** ви вибираєте та виключаєте атрибути для злиття у межах вашої сутності уніфікованого профілю клієнта.</span><span class="sxs-lookup"><span data-stu-id="591b1-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="591b1-112">Уніфікований профіль клієнта є результатом процесу уніфікації даних.</span><span class="sxs-lookup"><span data-stu-id="591b1-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="591b1-113">Деякі атрибути автоматично об’єднуються системою.</span><span class="sxs-lookup"><span data-stu-id="591b1-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="591b1-114">Щоб переглянути атрибути, включені до одного з автоматично об’єднаних атрибутів, виберіть цей об’єднаний атрибут на вкладці **Поля клієнта** у таблиці.</span><span class="sxs-lookup"><span data-stu-id="591b1-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="591b1-115">Атрибути, які утворюють об’єднаний атрибут, відображаються у двох нових рядках під об’єднаним атрибутом.</span><span class="sxs-lookup"><span data-stu-id="591b1-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="591b1-116">Розділення, перейменування, виключення та редагування об'єднаних полів</span><span class="sxs-lookup"><span data-stu-id="591b1-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="591b1-117">Ви можете змінювати об’єднання атрибутів, виконане системними процесами для створення уніфікованого профілю клієнта.</span><span class="sxs-lookup"><span data-stu-id="591b1-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="591b1-118">Виберіть **Показати більше** і оберіть елементи, які потрібно змінити.</span><span class="sxs-lookup"><span data-stu-id="591b1-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Параметри в розкривному меню «Показати більше», щоб керувати об'єднаними атрибутами.":::

<span data-ttu-id="591b1-120">Для отримання додаткових відомостей див. наступні розділи.</span><span class="sxs-lookup"><span data-stu-id="591b1-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="591b1-121">Розділення об’єднаних полів</span><span class="sxs-lookup"><span data-stu-id="591b1-121">Separate merged fields</span></span>

<span data-ttu-id="591b1-122">Щоб розділити об'єднані поля, знайдіть потрібний атрибут у таблиці.</span><span class="sxs-lookup"><span data-stu-id="591b1-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="591b1-123">Роз’єднані поля відображаються як окремі точки даних в уніфікованому профілі клієнта.</span><span class="sxs-lookup"><span data-stu-id="591b1-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="591b1-124">Виберіть об’єднане поле.</span><span class="sxs-lookup"><span data-stu-id="591b1-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="591b1-125">Виберіть **Показати більше** та оберіть **Розділити поля**.</span><span class="sxs-lookup"><span data-stu-id="591b1-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="591b1-126">Підтвердьте розділення.</span><span class="sxs-lookup"><span data-stu-id="591b1-126">Confirm the separation.</span></span>

1. <span data-ttu-id="591b1-127">Виберіть **Зберегти** та **Виконати**, щоб обробити зміни.</span><span class="sxs-lookup"><span data-stu-id="591b1-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="591b1-128">Перейменування об’єднаних полів</span><span class="sxs-lookup"><span data-stu-id="591b1-128">Rename merged fields</span></span>

<span data-ttu-id="591b1-129">Змініть коротке ім'я об’єднаних атрибутів.</span><span class="sxs-lookup"><span data-stu-id="591b1-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="591b1-130">Ім’я вихідної сутності змінювати не можна.</span><span class="sxs-lookup"><span data-stu-id="591b1-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="591b1-131">Виберіть об’єднане поле.</span><span class="sxs-lookup"><span data-stu-id="591b1-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="591b1-132">Виберіть **Показати більше** та оберіть **Перейменувати**.</span><span class="sxs-lookup"><span data-stu-id="591b1-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="591b1-133">Підтвердьте зміну короткого імені.</span><span class="sxs-lookup"><span data-stu-id="591b1-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="591b1-134">Виберіть **Зберегти** та **Виконати**, щоб обробити зміни.</span><span class="sxs-lookup"><span data-stu-id="591b1-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="591b1-135">Виключення об’єднаних полів</span><span class="sxs-lookup"><span data-stu-id="591b1-135">Exclude merged fields</span></span>

<span data-ttu-id="591b1-136">Виключіть атрибут з уніфікованого профілю клієнта.</span><span class="sxs-lookup"><span data-stu-id="591b1-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="591b1-137">Якщо поле використовується в інших процесах, наприклад у сегменті, перед виключенням із профілю клієнта видаліть його з цих процесів.</span><span class="sxs-lookup"><span data-stu-id="591b1-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="591b1-138">Виберіть об’єднане поле.</span><span class="sxs-lookup"><span data-stu-id="591b1-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="591b1-139">Виберіть **Показати більше** та оберіть **Виключити**.</span><span class="sxs-lookup"><span data-stu-id="591b1-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="591b1-140">Підтвердьте виключення.</span><span class="sxs-lookup"><span data-stu-id="591b1-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="591b1-141">Виберіть **Зберегти** та **Виконати**, щоб обробити зміни.</span><span class="sxs-lookup"><span data-stu-id="591b1-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="591b1-142">На сторінці **Злиття** виберіть **Виключені поля**, щоб переглянути список усіх виключених полів.</span><span class="sxs-lookup"><span data-stu-id="591b1-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="591b1-143">У цій області можна повернути виключені поля.</span><span class="sxs-lookup"><span data-stu-id="591b1-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="591b1-144">Поєднання полів вручну</span><span class="sxs-lookup"><span data-stu-id="591b1-144">Manually combine fields</span></span>

<span data-ttu-id="591b1-145">Укажіть об'єднаний атрибут вручну.</span><span class="sxs-lookup"><span data-stu-id="591b1-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="591b1-146">На сторінці **Злиття** виберіть **Поєднати поля**.</span><span class="sxs-lookup"><span data-stu-id="591b1-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="591b1-147">Укажіть **Ім'я** та **Ім'я вихідного поля**.</span><span class="sxs-lookup"><span data-stu-id="591b1-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="591b1-148">Оберіть поле, яке потрібно додати.</span><span class="sxs-lookup"><span data-stu-id="591b1-148">Choose a field to add.</span></span> <span data-ttu-id="591b1-149">Виберіть **Додати поля**, щоб поєднати більше полів.</span><span class="sxs-lookup"><span data-stu-id="591b1-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="591b1-150">Підтвердьте виключення.</span><span class="sxs-lookup"><span data-stu-id="591b1-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="591b1-151">Виберіть **Зберегти** та **Виконати**, щоб обробити зміни.</span><span class="sxs-lookup"><span data-stu-id="591b1-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="591b1-152">Змінення порядку полів</span><span class="sxs-lookup"><span data-stu-id="591b1-152">Change the order of fields</span></span>

<span data-ttu-id="591b1-153">Деякі сутності містять більше відомостей, ніж інші.</span><span class="sxs-lookup"><span data-stu-id="591b1-153">Some entities contain more details than others.</span></span> <span data-ttu-id="591b1-154">Якщо сутність містить найновіші дані про поле, ви можете підвищити її пріоритет відносно інших сутностей під час злиття полів.</span><span class="sxs-lookup"><span data-stu-id="591b1-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="591b1-155">Виберіть об’єднане поле.</span><span class="sxs-lookup"><span data-stu-id="591b1-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="591b1-156">Виберіть **Показати більше** та оберіть **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="591b1-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="591b1-157">В області **Поєднати поля** виберіть **Вгору/вниз**, щоб установити порядок або перетягніть поля на бажані позиції.</span><span class="sxs-lookup"><span data-stu-id="591b1-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="591b1-158">Підтвердьте зміни.</span><span class="sxs-lookup"><span data-stu-id="591b1-158">Confirm the change.</span></span>

1. <span data-ttu-id="591b1-159">Виберіть **Зберегти** та **Виконати**, щоб обробити зміни.</span><span class="sxs-lookup"><span data-stu-id="591b1-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="591b1-160">Виконання злиття</span><span class="sxs-lookup"><span data-stu-id="591b1-160">Run your merge</span></span>

<span data-ttu-id="591b1-161">Незалежно від того, чи можна об’єднати атрибути вручну або дозволити системі їх об’єднання, ви завжди можете виконати злиття.</span><span class="sxs-lookup"><span data-stu-id="591b1-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="591b1-162">Виберіть елемент **Виконати** на сторінці **Злиття**, щоб почати процес.</span><span class="sxs-lookup"><span data-stu-id="591b1-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="591b1-163">![Збереження та виконання злиття даних](media/configure-data-merge-save-run.png "Збереження та виконання злиття даних")</span><span class="sxs-lookup"><span data-stu-id="591b1-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="591b1-164">Виберіть **Виконати тільки злиття**, якщо потрібно, щоб результат відобразився тільки в уніфікованій сутності клієнта.</span><span class="sxs-lookup"><span data-stu-id="591b1-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="591b1-165">Подальші процеси буде оновлено відповідно до [визначеного розкладу оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="591b1-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="591b1-166">Виберіть **Виконати злиття та подальші процеси**, щоб оновити систему й внести до неї виконані зміни.</span><span class="sxs-lookup"><span data-stu-id="591b1-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="591b1-167">Усі процеси, зокрема збагачення, сегменти та показники автоматично запустяться повторно.</span><span class="sxs-lookup"><span data-stu-id="591b1-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="591b1-168">Після завершення всіх подальших процесів профілі клієнтів відображатимуть усі внесені вами зміни.</span><span class="sxs-lookup"><span data-stu-id="591b1-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="591b1-169">Щоб внести інші зміни та повторно виконати цей крок, ви можете скасувати усі злиття, що виконуються.</span><span class="sxs-lookup"><span data-stu-id="591b1-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="591b1-170">Виберіть **Оновлення...** й натисніть **Скасувати завдання** в бічній області, що відображається.</span><span class="sxs-lookup"><span data-stu-id="591b1-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="591b1-171">Існує [шість типів станів](system.md#status-types) для завдань/процесів.</span><span class="sxs-lookup"><span data-stu-id="591b1-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="591b1-172">Крім того, більшість процесів [залежать від інших низхідних процесів](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="591b1-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="591b1-173">Можна вибрати стан процесу, щоб переглянути докладні відомості про перебіг виконання всієї роботи.</span><span class="sxs-lookup"><span data-stu-id="591b1-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="591b1-174">Після вибору **Переглянути відомості** для однієї з робіт завдання ви побачите додаткові відомості: час обробки, дата останньої обробки, а також усі помилки та попередження, пов'язані з завданням.</span><span class="sxs-lookup"><span data-stu-id="591b1-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="591b1-175">Наступний крок</span><span class="sxs-lookup"><span data-stu-id="591b1-175">Next Step</span></span>

<span data-ttu-id="591b1-176">Налаштуйте [справи](activities.md), [збагачення](enrichment-hub.md) або [зв’язки](relationships.md), щоб отримати більше аналітичних оглядів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="591b1-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="591b1-177">Якщо справи, збагачення або сегменти вже налаштовано, вони оброблятимуться автоматично та використовуватимуть найновіші дані клієнтів.</span><span class="sxs-lookup"><span data-stu-id="591b1-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
