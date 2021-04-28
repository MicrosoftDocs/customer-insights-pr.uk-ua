---
title: Злиття сутностей в уніфікації даних
description: Злиття сутностей для створення уніфікованих профілів клієнтів.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896536"
---
# <a name="merge-entities"></a><span data-ttu-id="25bd4-103">Об'єднання сутностями</span><span class="sxs-lookup"><span data-stu-id="25bd4-103">Merge entities</span></span>

<span data-ttu-id="25bd4-104">Фаза злиття — це остання фаза в процесі уніфікації даних.</span><span class="sxs-lookup"><span data-stu-id="25bd4-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="25bd4-105">Її мета — узгодження суперечливих даних.</span><span class="sxs-lookup"><span data-stu-id="25bd4-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="25bd4-106">Приклади суперечливих даних можуть містити ім’я клієнта, знайдене в двох наборах даних, яке відображається в кожному наборі по-різному (Grant Marshall і Grant Marshal) або номер телефону, який відрізняється форматом (617-803-091X і 617803091X).</span><span class="sxs-lookup"><span data-stu-id="25bd4-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="25bd4-107">Злиття цих конфліктуючих точок даних виконується на основі методу «атрибут за атрибутом».</span><span class="sxs-lookup"><span data-stu-id="25bd4-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="25bd4-108">Після завершення [фази пошуку відповідностей](match-entities.md) ви починаєте фазу злиття. Для цього виберіть плитку **Злиття** на сторінці **Уніфікувати**.</span><span class="sxs-lookup"><span data-stu-id="25bd4-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="25bd4-109">Перегляд системних рекомендацій</span><span class="sxs-lookup"><span data-stu-id="25bd4-109">Review system recommendations</span></span>

<span data-ttu-id="25bd4-110">На сторінці **Злиття** можна вибрати та вилучити атрибути, для яких необхідно виконати злиття в сутності уніфікованого профілю клієнта (результат процесу конфігурації).</span><span class="sxs-lookup"><span data-stu-id="25bd4-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="25bd4-111">Деякі атрибути автоматично об’єднуються системою.</span><span class="sxs-lookup"><span data-stu-id="25bd4-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="25bd4-112">Перегляд об’єднаних атрибутів</span><span class="sxs-lookup"><span data-stu-id="25bd4-112">View merged attributes</span></span>

<span data-ttu-id="25bd4-113">Щоб переглянути атрибути, додані до одного з автоматично об’єднаних атрибутів, виберіть цей об’єднаний атрибут.</span><span class="sxs-lookup"><span data-stu-id="25bd4-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="25bd4-114">Два атрибути, які утворюють об’єднаний атрибут, відображаються в двох нових рядках під об’єднаним атрибутом.</span><span class="sxs-lookup"><span data-stu-id="25bd4-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="25bd4-115">![Вибір об’єднаного атрибута](media/configure-data-merge-profile-attributes.png "Вибір об’єднаного атрибута")</span><span class="sxs-lookup"><span data-stu-id="25bd4-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="25bd4-116">Розділення об’єднаних атрибутів</span><span class="sxs-lookup"><span data-stu-id="25bd4-116">Separate merged attributes</span></span>

<span data-ttu-id="25bd4-117">Щоб розділити або скасувати об’єднання будь-якого з автоматично об’єднаних атрибутів, знайдіть цей атрибут у таблиці **Атрибути профілю**.</span><span class="sxs-lookup"><span data-stu-id="25bd4-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="25bd4-118">Виберіть кнопку «три крапки» (...).</span><span class="sxs-lookup"><span data-stu-id="25bd4-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="25bd4-119">У розкривному списку виберіть пункт **Розділити поля**.</span><span class="sxs-lookup"><span data-stu-id="25bd4-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="25bd4-120">Видалення об’єднаних атрибутів</span><span class="sxs-lookup"><span data-stu-id="25bd4-120">Remove merged attributes</span></span>

<span data-ttu-id="25bd4-121">Щоб виключити атрибут із кінцевої сутності профілю клієнта, знайдіть його в таблиці **Атрибути профілю**.</span><span class="sxs-lookup"><span data-stu-id="25bd4-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="25bd4-122">Виберіть кнопку «три крапки» (...).</span><span class="sxs-lookup"><span data-stu-id="25bd4-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="25bd4-123">У розкривному списку виберіть пункт **Не об’єднувати**.</span><span class="sxs-lookup"><span data-stu-id="25bd4-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="25bd4-124">Атрибут буде переміщено в розділ **Видалено із запису клієнта**.</span><span class="sxs-lookup"><span data-stu-id="25bd4-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="25bd4-125">Додавання об’єднаного атрибута вручну</span><span class="sxs-lookup"><span data-stu-id="25bd4-125">Manually add a merged attribute</span></span>

<span data-ttu-id="25bd4-126">Щоб додати об’єднаний атрибут, перейдіть на сторінку **Злиття**.</span><span class="sxs-lookup"><span data-stu-id="25bd4-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="25bd4-127">Виберіть елемент **Додати об’єднаний атрибут**.</span><span class="sxs-lookup"><span data-stu-id="25bd4-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="25bd4-128">Укажіть **Ім’я**, щоб впізнавати його на сторінці **Злиття** пізніше.</span><span class="sxs-lookup"><span data-stu-id="25bd4-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="25bd4-129">Крім того, можна вказати **Коротке ім’я** для відображення в сутності уніфікованого профілю клієнта.</span><span class="sxs-lookup"><span data-stu-id="25bd4-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="25bd4-130">Налаштуйте параметр **Вибрати дубльовані атрибути**, щоб вибрати атрибути, які потрібно об’єднати з відповідних сутностей.</span><span class="sxs-lookup"><span data-stu-id="25bd4-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="25bd4-131">Крім того, можна виконувати пошук атрибутів.</span><span class="sxs-lookup"><span data-stu-id="25bd4-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="25bd4-132">Налаштуйте параметр **Ранжувати за важливістю**, щоб визначити пріоритет одного атрибута над іншими.</span><span class="sxs-lookup"><span data-stu-id="25bd4-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="25bd4-133">Наприклад, якщо сутність *WebAccountCSV* містить найточніші дані про атрибут *Повні імена*, можна визначити пріоритет цієї сутності над *ContactCSV*, вибравши *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="25bd4-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="25bd4-134">У результаті цієї дії *WebAccountCSV* буде призначено першим пріоритетом, а *ContactCSV* призначено другим під час отримання значень атрибута *Повне ім’я*.</span><span class="sxs-lookup"><span data-stu-id="25bd4-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="25bd4-135">Виконання злиття</span><span class="sxs-lookup"><span data-stu-id="25bd4-135">Run your merge</span></span>

<span data-ttu-id="25bd4-136">Незалежно від того, чи можна об’єднати атрибути вручну або дозволити системі їх об’єднання, ви завжди можете виконати злиття.</span><span class="sxs-lookup"><span data-stu-id="25bd4-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="25bd4-137">Виберіть елемент **Виконати** на сторінці **Злиття**, щоб почати процес.</span><span class="sxs-lookup"><span data-stu-id="25bd4-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="25bd4-138">![Збереження та виконання злиття даних](media/configure-data-merge-save-run.png "Збереження та виконання злиття даних")</span><span class="sxs-lookup"><span data-stu-id="25bd4-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="25bd4-139">Щоб внести додаткові зміни й перезапустити крок, можна скасувати поточне злиття.</span><span class="sxs-lookup"><span data-stu-id="25bd4-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="25bd4-140">Виберіть **Оновлення...** й натисніть **Скасувати завдання** в бічній області, що відображається.</span><span class="sxs-lookup"><span data-stu-id="25bd4-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="25bd4-141">Після того як текст **Оновлення...** зміниться на **Успішно**, злиття буде завершено, а суперечності в даних усунено відповідно до визначених вами політик.</span><span class="sxs-lookup"><span data-stu-id="25bd4-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="25bd4-142">Злиті та незлиті атрибути додаються до сутності уніфікованого профілю.</span><span class="sxs-lookup"><span data-stu-id="25bd4-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="25bd4-143">Вилучені атрибути не додаються до сутності уніфікованого профілю.</span><span class="sxs-lookup"><span data-stu-id="25bd4-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="25bd4-144">Якщо ви не вперше успішно виконуєте злиття, усі низхідні процеси, зокрема збагачення, сегментація та показники, знову буде автоматично перезапущено.</span><span class="sxs-lookup"><span data-stu-id="25bd4-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="25bd4-145">Після перезапуску всіх низхідних процесів у профілях клієнтів відображатимуться всі внесені вами зміни.</span><span class="sxs-lookup"><span data-stu-id="25bd4-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="25bd4-146">Існує [шість типів станів](system.md#status-types) для завдань/процесів.</span><span class="sxs-lookup"><span data-stu-id="25bd4-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="25bd4-147">Крім того, більшість процесів [залежать від інших низхідних процесів](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="25bd4-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="25bd4-148">Можна вибрати стан процесу, щоб переглянути докладні відомості про перебіг виконання всієї роботи.</span><span class="sxs-lookup"><span data-stu-id="25bd4-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="25bd4-149">Після вибору **Переглянути відомості** для однієї з робіт завдання ви побачите додаткові відомості: час обробки, дата останньої обробки, а також усі помилки та попередження, пов'язані з завданням.</span><span class="sxs-lookup"><span data-stu-id="25bd4-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="25bd4-150">Наступний крок</span><span class="sxs-lookup"><span data-stu-id="25bd4-150">Next Step</span></span>

<span data-ttu-id="25bd4-151">Налаштуйте [справи](activities.md), [збагачення](enrichment-hub.md) або [зв’язки](relationships.md), щоб отримати більше аналітичних оглядів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="25bd4-151">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="25bd4-152">Якщо ви вже налаштували справи, збагачення або зв'язки чи якщо ви визначили сегменти, вони автоматично обробляються з використанням найновіших даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="25bd4-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]