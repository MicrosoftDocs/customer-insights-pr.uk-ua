---
title: Створення та редагування показників
description: Визначайте пов’язані з клієнтом показники для аналізу та відображення продуктивності певних бізнес-сфер.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407275"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="28314-103">Визначення показників і керування ними</span><span class="sxs-lookup"><span data-stu-id="28314-103">Define and manage measures</span></span>

<span data-ttu-id="28314-104">**Показники** являють собою ключові показники ефективності (KPI), які відображають продуктивність та стан певних бізнес-сфер.</span><span class="sxs-lookup"><span data-stu-id="28314-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="28314-105">Аналізи аудиторії забезпечують інтуїтивний спосіб створення різних типів показників за допомогою інструменту створення запиту, який не вимагає від вас кодування або перевірки ваших показників вручну.</span><span class="sxs-lookup"><span data-stu-id="28314-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="28314-106">Ви можете відстежувати бізнес-показники на сторінці **Головна**, переглядати показники для певних клієнтів на **Картці клієнта**, а також використовувати показники для визначення сегментів клієнтів на сторінці **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="28314-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="28314-107">Створення показника</span><span class="sxs-lookup"><span data-stu-id="28314-107">Create a measure</span></span>

<span data-ttu-id="28314-108">У цьому розділі можна ознайомитися з процесом створення показника з нуля.</span><span class="sxs-lookup"><span data-stu-id="28314-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="28314-109">Ви можете створювати показники з даними з кількох джерел даних, зв’язаних через сутність «Клієнт».</span><span class="sxs-lookup"><span data-stu-id="28314-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="28314-110">Застосовуються деякі [ліміти послуг](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="28314-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="28314-111">У розділі «Аналіз аудиторії» виберіть **Показники**.</span><span class="sxs-lookup"><span data-stu-id="28314-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="28314-112">Виберіть елемент **Створити показник**.</span><span class="sxs-lookup"><span data-stu-id="28314-112">Select **New measure**.</span></span>

3. <span data-ttu-id="28314-113">Виберіть **Тип** показника:</span><span class="sxs-lookup"><span data-stu-id="28314-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="28314-114">**Атрибут клієнта**: одне поле для клієнта, в якому відображаються бали, значення або стан клієнта.</span><span class="sxs-lookup"><span data-stu-id="28314-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="28314-115">Атрибути клієнта створюються як атрибути у новій сутності, створеній системою, під назвою **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="28314-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="28314-116">**Показник клієнта**: аналітичні огляди щодо поведінки клієнта з розбивкою на вибрані виміри.</span><span class="sxs-lookup"><span data-stu-id="28314-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="28314-117">Для кожного показника створюється нова сутність, яка потенційно може мати кілька записів для одного клієнта.</span><span class="sxs-lookup"><span data-stu-id="28314-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="28314-118">**Бізнес-показник**: відстежує продуктивність бізнесу та стан бізнесу.</span><span class="sxs-lookup"><span data-stu-id="28314-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="28314-119">Бізнес-показники можуть мати два різних результати: числове подання, яке відображається на сторінці **Головна** або нову сутність, яку можна знайти на сторінці **Сутності**.</span><span class="sxs-lookup"><span data-stu-id="28314-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="28314-120">Укажіть **Ім’я** та необов’язкове **Коротке ім’я**, а потім натисніть кнопку **Далі**.</span><span class="sxs-lookup"><span data-stu-id="28314-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="28314-121">У розділі **Сутності** виберіть першу сутність із розкривного списку.</span><span class="sxs-lookup"><span data-stu-id="28314-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="28314-122">На цьому етапі слід вирішити, чи потрібні додаткові сутності в межах визначення показника.</span><span class="sxs-lookup"><span data-stu-id="28314-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="28314-123">![Визначення показника](media/measure-definition.png "Визначення вимірювання")</span><span class="sxs-lookup"><span data-stu-id="28314-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="28314-124">Щоб додати інші сутності, виберіть команду **Додати сутність** та виберіть сутності, які необхідно використовувати для показника.</span><span class="sxs-lookup"><span data-stu-id="28314-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="28314-125">Ви можете вибрати лише сутності, які мають зв’язки з початковою сутністю.</span><span class="sxs-lookup"><span data-stu-id="28314-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="28314-126">Додаткову інформацію про встановлення зв’язків див. в розділі [Зв'язки](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="28314-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="28314-127">Крім того, ви можете налаштувати змінні.</span><span class="sxs-lookup"><span data-stu-id="28314-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="28314-128">У розділі **Змінні** виберіть елемент **Створити змінну**.</span><span class="sxs-lookup"><span data-stu-id="28314-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="28314-129">Змінні — це розрахунки, що виконуються для кожного з вибраних записів.</span><span class="sxs-lookup"><span data-stu-id="28314-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="28314-130">Наприклад, підсумки збуту з точок продаж (POS) та в Інтернеті для кожного із записів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="28314-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="28314-131">Заповніть поле **Назва** для змінної.</span><span class="sxs-lookup"><span data-stu-id="28314-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="28314-132">В області **Вираз** виберіть поле, з якого потрібно починати обчислення.</span><span class="sxs-lookup"><span data-stu-id="28314-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="28314-133">Уведіть вираз в області **Вираз** і виберіть кілька полів, які необхідно включити до обчислення.</span><span class="sxs-lookup"><span data-stu-id="28314-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="28314-134">Наразі підтримуються лише арифметичні вирази.</span><span class="sxs-lookup"><span data-stu-id="28314-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="28314-135">Крім того, обчислення сутностей не підтримується з різних [шляхів сутності](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="28314-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="28314-136">Виберіть **Готово**.</span><span class="sxs-lookup"><span data-stu-id="28314-136">Select **Done**.</span></span>

11. <span data-ttu-id="28314-137">У розділі **Визначення показника** визначте, як вибрані сутності та обчислені змінні об’єднуються в нову сутність або атрибут.</span><span class="sxs-lookup"><span data-stu-id="28314-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="28314-138">Виберіть **Створити вимір**.</span><span class="sxs-lookup"><span data-stu-id="28314-138">Select **New dimension**.</span></span> <span data-ttu-id="28314-139">Вимір можна вважати функцією *групування за*.</span><span class="sxs-lookup"><span data-stu-id="28314-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="28314-140">Вихідні дані сутності або атрибута «Показник» буде згруповано за всіма визначеними вами вимірами.</span><span class="sxs-lookup"><span data-stu-id="28314-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="28314-141">![Вибір об’єднаного циклу](media/measures-businessreport-measure-definition2.png "Вибір об’єднаного циклу")</span><span class="sxs-lookup"><span data-stu-id="28314-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="28314-142">Виберіть або введіть зазначені нижче відомості як частину визначення вимірів.</span><span class="sxs-lookup"><span data-stu-id="28314-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="28314-143">**Сутність**: якщо ви визначаєте сутність «Показник», вона має містити принаймні один атрибут.</span><span class="sxs-lookup"><span data-stu-id="28314-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="28314-144">Якщо ви визначаєте атрибут «Показник», він включатиме лише один атрибут за замовчуванням.</span><span class="sxs-lookup"><span data-stu-id="28314-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="28314-145">Цей вибір містить відомості про вибір сутності, що містить цей атрибут.</span><span class="sxs-lookup"><span data-stu-id="28314-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="28314-146">**Поле**: виберіть певний атрибут, який слід включити до сутності або атрибута «Показник».</span><span class="sxs-lookup"><span data-stu-id="28314-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="28314-147">**Блок**: виберіть, потрібні вам об’єднані дані на щоденній, щомісячній або щорічній основі.</span><span class="sxs-lookup"><span data-stu-id="28314-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="28314-148">Це обов’язковий вибір, лише якщо вибрано атрибут типу дати.</span><span class="sxs-lookup"><span data-stu-id="28314-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="28314-149">**Як**. визначає ім’я нового поля.</span><span class="sxs-lookup"><span data-stu-id="28314-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="28314-150">**Коротке ім’я**: визначає коротке ім’я поля.</span><span class="sxs-lookup"><span data-stu-id="28314-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28314-151">Ваш бізнес-показник буде збережено як однозначну сутність. Він відображатиметься на **Головній** сторінці буде відображатися, якщо ви не додасте інші виміри до показника.</span><span class="sxs-lookup"><span data-stu-id="28314-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="28314-152">Якщо додати інші виміри, показник *не* відображатиметься на **Головній** сторінці.</span><span class="sxs-lookup"><span data-stu-id="28314-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="28314-153">Крім того, можна додати функції агрегації.</span><span class="sxs-lookup"><span data-stu-id="28314-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="28314-154">Будь-яка агрегація, створена вами, призводить до появи нового значення в сутності або атрибуті «Показник».</span><span class="sxs-lookup"><span data-stu-id="28314-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="28314-155">Підтримувані функції агрегації: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (бере перший запис значення виміру) і **Last** (бере останній запис, доданий до значення виміру).</span><span class="sxs-lookup"><span data-stu-id="28314-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="28314-156">Натисніть кнопку **Зберегти**, щоб застосувати зміни до показника.</span><span class="sxs-lookup"><span data-stu-id="28314-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="28314-157">Керування показниками</span><span class="sxs-lookup"><span data-stu-id="28314-157">Manage your measures</span></span>

<span data-ttu-id="28314-158">Після створення принаймні одного показника відобразиться список показників на сторінці **Показники**.</span><span class="sxs-lookup"><span data-stu-id="28314-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="28314-159">Ви знайдете відомості про тип, автора, дату та час створення, дату та час останнього редагування, стан (незалежно від того, чи активний, неактивний або пошкоджений показник) показника, а також дата та час останнього оновлення.</span><span class="sxs-lookup"><span data-stu-id="28314-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="28314-160">Під час вибору показника в списку можна переглянути попередній його результат.</span><span class="sxs-lookup"><span data-stu-id="28314-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="28314-161">Щоб оновити всі показники одночасно, натисніть кнопку **Оновити все**, не вибираючи певний показник.</span><span class="sxs-lookup"><span data-stu-id="28314-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="28314-162">![Дії з керування окремими показниками](media/measure-actions.png "Дії з керування окремими показниками")</span><span class="sxs-lookup"><span data-stu-id="28314-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="28314-163">Можна також вибрати в списку показник і виконати одну із зазначених нижче дій.</span><span class="sxs-lookup"><span data-stu-id="28314-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="28314-164">Виберіть ім’я показника, щоб переглянути відомості про нього.</span><span class="sxs-lookup"><span data-stu-id="28314-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="28314-165">**Змініть** настроювання показника.</span><span class="sxs-lookup"><span data-stu-id="28314-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="28314-166">**Перейменуйте** показник.</span><span class="sxs-lookup"><span data-stu-id="28314-166">**Rename** the measure.</span></span>
- <span data-ttu-id="28314-167">**Видаліть** показник.</span><span class="sxs-lookup"><span data-stu-id="28314-167">**Delete** the measure.</span></span>
- <span data-ttu-id="28314-168">Виберіть три крапки (...), а потім натисніть **Оновити**, щоб почати процес оновлення для показника.</span><span class="sxs-lookup"><span data-stu-id="28314-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="28314-169">Виберіть три крапки (...), а потім натисніть **Завантажити**, щоб завантажити CSV-файл показника.</span><span class="sxs-lookup"><span data-stu-id="28314-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="28314-170">Існує [шість типів станів](system.md#status-types) для завдань/процесів.</span><span class="sxs-lookup"><span data-stu-id="28314-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="28314-171">Крім того, більшість процесів [залежать від інших низхідних процесів](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="28314-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="28314-172">Можна вибрати стан процесу, щоб переглянути докладні відомості про перебіг виконання всієї роботи.</span><span class="sxs-lookup"><span data-stu-id="28314-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="28314-173">Після вибору **Переглянути відомості** для однієї з робіт завдання ви побачите додаткові відомості: час обробки, дата останньої обробки, а також усі помилки та попередження, пов'язані з завданням.</span><span class="sxs-lookup"><span data-stu-id="28314-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="28314-174">Наступний крок</span><span class="sxs-lookup"><span data-stu-id="28314-174">Next step</span></span>

<span data-ttu-id="28314-175">Ви можете використовувати наявні показники для створення першого сегмента клієнта на сторінці **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="28314-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="28314-176">Додаткові відомості див. в розділі [Сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="28314-176">For more information, see [Segments](segments.md).</span></span>
