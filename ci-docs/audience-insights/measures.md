---
title: Створення показників і керування ними
description: Визначте показники для аналізу та відображення ефективності діяльності компанії.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654757"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="d0ca0-103">Визначення показників і керування ними</span><span class="sxs-lookup"><span data-stu-id="d0ca0-103">Define and manage measures</span></span>

<span data-ttu-id="d0ca0-104">Показники допомагають краще зрозуміти поведінку клієнтів і ефективність бізнесу, отримуючи відповідні значення з [уніфікованих профілів](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="d0ca0-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="d0ca0-105">Наприклад, компанія хоче дізнатись *загальну суму витрат для клієнта*, щоб зрозуміти історію придбань окремого клієнта.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="d0ca0-106">Або виміряти *загальний обсяг збуту компанії*, щоб оцінити сукупний дохід всього бізнесу.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="d0ca0-107">Показники створюються за допомогою конструктора показників, платформи запитів даних з різними операторами та простими параметрами зіставлення.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="d0ca0-108">Вона дозволяє фільтрувати дані, групувати результати, виявляти [шляхи зв'язків сутностей](relationships.md) і здійснювати попередній перегляд результатів.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="d0ca0-109">Використовуйте конструктор показників для планування бізнес-діяльності, виконуючи запити даних клієнтів і отримуючи аналітичні висновки.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="d0ca0-110">Наприклад, створення показника для *загальної суми витрат для клієнта* та *загальної суми повернень для клієнта* допомагає визначити групу клієнтів із високими витратами, але ж і великою кількістю повернень.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="d0ca0-111">Можна [створити сегмент](segments.md), щоб скеровувати найкращі подальші дії.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="d0ca0-112">Створення показника</span><span class="sxs-lookup"><span data-stu-id="d0ca0-112">Create a measure</span></span>

<span data-ttu-id="d0ca0-113">У цьому розділі ми навчимося створювати показник з нуля.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="d0ca0-114">Ви можете створити показник із атрибутами даних з сутностей даних, що мають налаштований зв'язок для підключення до сутності «Клієнт».</span><span class="sxs-lookup"><span data-stu-id="d0ca0-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="d0ca0-115">У розділі «Аналіз аудиторії» виберіть **Показники**.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="d0ca0-116">Виберіть **Створити**.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-116">Select **New**.</span></span>

1. <span data-ttu-id="d0ca0-117">Виберіть **Редагувати ім’я** та вкажіть **Ім’я** для показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="d0ca0-118">Якщо нова конфігурація показника містить лише два поля, наприклад, CustomerID і одне обчислення, результати буде додано як новий стовпець до створеної системою сутності під назвою Customer_Measure (показник клієнта).</span><span class="sxs-lookup"><span data-stu-id="d0ca0-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="d0ca0-119">І ви зможете бачити значення цього показника уніфікованому профілі клієнта.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="d0ca0-120">Інші показники також створюватимуть власні сутності.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="d0ca0-121">В області налаштування виберіть агрегатну функцію з розкривного меню **Вибір функції**.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="d0ca0-122">Агрегатні функції перелічено нижче.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="d0ca0-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="d0ca0-123">**Sum**</span></span>
   - <span data-ttu-id="d0ca0-124">**Середнє**</span><span class="sxs-lookup"><span data-stu-id="d0ca0-124">**Average**</span></span>
   - <span data-ttu-id="d0ca0-125">**Кількість**</span><span class="sxs-lookup"><span data-stu-id="d0ca0-125">**Count**</span></span>
   - <span data-ttu-id="d0ca0-126">**Кількість унікальних**</span><span class="sxs-lookup"><span data-stu-id="d0ca0-126">**Count Unique**</span></span>
   - <span data-ttu-id="d0ca0-127">**Максимальна**</span><span class="sxs-lookup"><span data-stu-id="d0ca0-127">**Max**</span></span>
   - <span data-ttu-id="d0ca0-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="d0ca0-128">**Min**</span></span>
   - <span data-ttu-id="d0ca0-129">**Перше**: відбирає перше значення запису даних</span><span class="sxs-lookup"><span data-stu-id="d0ca0-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="d0ca0-130">**Останнє**: відбирає останнє значення, додане до запису даних</span><span class="sxs-lookup"><span data-stu-id="d0ca0-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Оператори для розрахунків показників.":::

1. <span data-ttu-id="d0ca0-132">Виберіть **Додати атрибут**, щоб вибрати дані, потрібні для створення цього показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="d0ca0-133">Виберіть вкладку **Атрибути**.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="d0ca0-134">Сутність даних: виберіть сутність, що містить атрибут, який потрібно вимірювати.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="d0ca0-135">Атрибут даних: виберіть атрибут, який потрібно використовувати в агрегатній функції для обчислення показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="d0ca0-136">Можна вибрати лише однин атрибут за раз.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="d0ca0-137">Також можна вибрати атрибут даних із наявного показника, вибравши вкладку **Показники**. Також можна знайти сутність або показник, виконавши пошук за іменем.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="d0ca0-138">Виберіть **Додати**, щоб додати вибраний атрибут до показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Виберіть атрибут, який використовуватиметься в обчисленнях.":::

1. <span data-ttu-id="d0ca0-140">Для створення складніших показників ви можете додавати більше атрибутів або використовувати математичні операції у функції для показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Створіть складний показник, використовуючи математичні операції.":::

1. <span data-ttu-id="d0ca0-142">Щоб додати фільтри, виберіть **Фільтр** в області налаштування.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="d0ca0-143">У розділі **Додати атрибут** в області **Фільтри** виберіть атрибут, який потрібно використовувати при створенні фільтрів.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="d0ca0-144">Установіть оператори фільтру, щоб визначити фільтр для кожного вибраного атрибута.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="d0ca0-145">Виберіть **Застосувати**, щоб додати фільтри до показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="d0ca0-146">Щоб додати виміри, виберіть **Вимір** в області налаштування.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="d0ca0-147">Виміри відображатимуться як стовпці у сутності виводу показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="d0ca0-148">Виберіть **Редагувати виміри**, щоб додати атрибути даних, за якими потрібно групувати значення показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="d0ca0-149">Наприклад, місто або стать.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-149">For example, city or gender.</span></span> <span data-ttu-id="d0ca0-150">За замовчуванням вибрано вимір *CustomerID* для створення *показників на рівні клієнта*.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="d0ca0-151">Якщо потрібно створити *показники на рівні компанії*, ви можете вибрати стандартний вимір.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="d0ca0-152">Виберіть **Готово**, щоб додати виміри до показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="d0ca0-153">Якщо між зіставленою сутністю даних і сутністю *«Клієнт»* є кілька шляхів, слід вибрати один із визначених [шляхів зв'язку сутностей](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="d0ca0-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="d0ca0-154">Результати показників можуть біти різними залежно від вибраного шляху.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="d0ca0-155">Виберіть **Параметри даних** і виберіть шлях сутності, який слід використовувати для ідентифікації вашого показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="d0ca0-156">Якщо існує лише один шлях до сутності *Клієнт*, цей елемент керування не відображатиметься.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="d0ca0-157">Виберіть **Готово**, щоб підтвердити вибір.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Виберіть шлях сутності для показника.":::

1. <span data-ttu-id="d0ca0-159">Щоб додати інші обчислення для показника, виберіть **Нове обчислення**.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="d0ca0-160">Для нових обчислень можна використовувати сутності лише за тим самим шляхом сутності.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="d0ca0-161">Додаткові обчислення відображатимуться як нові стовпці у сутності виводу показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="d0ca0-162">Виберіть **...** для обчислення, щоб **Дублювати**, **Перейменувати** або **Видалити** обчислення з показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="d0ca0-163">В області **Попередній перегляд** ви побачите схему даних сутності виводу показника, зокрема фільтри та виміри.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="d0ca0-164">Попередній перегляд динамічно реагує на зміни налаштувань.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="d0ca0-165">Виберіть **Виконати**, щоб обчислити результати для налаштованого показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="d0ca0-166">Виберіть **Зберегти та закрити**, якщо потрібно зберегти поточну конфігурацію та запустити показник пізніше.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="d0ca0-167">Перейдіть до розділу **Показники**, щоб переглянути новостворений показник у списку.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="d0ca0-168">Керування показниками</span><span class="sxs-lookup"><span data-stu-id="d0ca0-168">Manage your measures</span></span>

<span data-ttu-id="d0ca0-169">Після [створення показника](#create-a-measure) на сторінці **Показники** відображатиметься список показників.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="d0ca0-170">Ви знайдете відомості про тип, автора, дату створення, статус і стан показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="d0ca0-171">Вибравши показник зі списку, ви можете побачити попередній перегляд результатів та завантажити .CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="d0ca0-172">Щоб оновити всі показники одночасно, натисніть кнопку **Оновити все**, не вибираючи певний показник.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d0ca0-173">![Дії з керування окремими показниками](media/measure-actions.png "Дії з керування окремими показниками")</span><span class="sxs-lookup"><span data-stu-id="d0ca0-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="d0ca0-174">Виберіть показник зі списку, щоб побачити доступні варіанти дій.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="d0ca0-175">Виберіть ім’я показника, щоб переглянути відомості про нього.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="d0ca0-176">**Змініть** настроювання показника.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="d0ca0-177">**Оновіть** показник із урахуванням останніх даних.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="d0ca0-178">**Перейменуйте** показник.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-178">**Rename** the measure.</span></span>
- <span data-ttu-id="d0ca0-179">**Видаліть** показник.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-179">**Delete** the measure.</span></span>
- <span data-ttu-id="d0ca0-180">**Активуйте** або **Вимкніть**.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="d0ca0-181">Неактивні показники не оновлюватимуться під час [оновлення за розкладом](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d0ca0-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="d0ca0-182">Існує [шість типів станів](system.md#status-types) для завдань/процесів.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d0ca0-183">Крім того, більшість процесів [залежать від інших низхідних процесів](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d0ca0-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d0ca0-184">Можна вибрати стан процесу, щоб переглянути докладні відомості про перебіг виконання всієї роботи.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d0ca0-185">Після вибору **Переглянути відомості** для однієї з робіт завдання ви побачите додаткові відомості: час обробки, дата останньої обробки, а також усі помилки та попередження, пов'язані з завданням.</span><span class="sxs-lookup"><span data-stu-id="d0ca0-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="d0ca0-186">Наступний крок</span><span class="sxs-lookup"><span data-stu-id="d0ca0-186">Next step</span></span>

<span data-ttu-id="d0ca0-187">Використовуючи наявні показники, ви можете створити [сегмент клієнтів](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d0ca0-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]