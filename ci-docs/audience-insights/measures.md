---
title: Створення показників і керування ними
description: Визначте показники для аналізу та відображення ефективності діяльності компанії.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049275"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="550f3-103">Визначення показників і керування ними</span><span class="sxs-lookup"><span data-stu-id="550f3-103">Define and manage measures</span></span>

<span data-ttu-id="550f3-104">Показники допомагають краще розуміти поведінку користувачів та ефективність бізнесу.</span><span class="sxs-lookup"><span data-stu-id="550f3-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="550f3-105">Вони оцінюють відповідні значення з [уніфікованих профілів](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="550f3-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="550f3-106">Наприклад, компанія хоче бачити *загальний обсяг витрат для кожного клієнта*, щоб зрозуміти історію покупок окремого клієнта або виміряти *загальний обсяг збуту компанії*, щоб зрозуміти сукупний дохід у всій компанії.</span><span class="sxs-lookup"><span data-stu-id="550f3-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="550f3-107">Показники створюються за допомогою конструктора показників, платформи запитів даних з різними операторами та простими параметрами зіставлення.</span><span class="sxs-lookup"><span data-stu-id="550f3-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="550f3-108">Вона дозволяє фільтрувати дані, групувати результати, виявляти [шляхи зв'язків сутностей](relationships.md) і здійснювати попередній перегляд результатів.</span><span class="sxs-lookup"><span data-stu-id="550f3-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="550f3-109">Використовуйте конструктор показників для планування бізнес-діяльності, виконуючи запити даних клієнтів і отримуючи аналітичні висновки.</span><span class="sxs-lookup"><span data-stu-id="550f3-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="550f3-110">Наприклад, створення показника для *загальної суми витрат для клієнта* та *загальної суми повернень для клієнта* допомагає визначити групу клієнтів із високими витратами, але ж і великою кількістю повернень.</span><span class="sxs-lookup"><span data-stu-id="550f3-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="550f3-111">Можна [створити сегмент](segments.md), щоб скеровувати найкращі подальші дії.</span><span class="sxs-lookup"><span data-stu-id="550f3-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="550f3-112">Створення власного показника з нуля</span><span class="sxs-lookup"><span data-stu-id="550f3-112">Build your own measure from scratch</span></span>

<span data-ttu-id="550f3-113">У цьому розділі ми навчимося створювати показник з нуля.</span><span class="sxs-lookup"><span data-stu-id="550f3-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="550f3-114">Ви можете створити показник із атрибутами даних з сутностей даних, що мають налаштований зв'язок для підключення до сутності «Клієнт».</span><span class="sxs-lookup"><span data-stu-id="550f3-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="550f3-115">У розділі «Аналіз аудиторії» виберіть **Показники**.</span><span class="sxs-lookup"><span data-stu-id="550f3-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="550f3-116">Виберіть **Створити**, а тоді виберіть **Створити власний**.</span><span class="sxs-lookup"><span data-stu-id="550f3-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="550f3-117">Виберіть **Редагувати ім’я** та вкажіть **Ім’я** для показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="550f3-118">Якщо конфігурація нового показника містить лише два поля, наприклад CustomerID і одне обчислення, результат буде додано як новий стовпець до створеної системою сутності, що називається Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="550f3-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="550f3-119">І ви зможете бачити значення цього показника уніфікованому профілі клієнта.</span><span class="sxs-lookup"><span data-stu-id="550f3-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="550f3-120">Інші показники також створюватимуть власні сутності.</span><span class="sxs-lookup"><span data-stu-id="550f3-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="550f3-121">В області налаштування виберіть агрегатну функцію з розкривного меню **Вибір функції**.</span><span class="sxs-lookup"><span data-stu-id="550f3-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="550f3-122">Агрегатні функції перелічено нижче.</span><span class="sxs-lookup"><span data-stu-id="550f3-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="550f3-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="550f3-123">**Sum**</span></span>
   - <span data-ttu-id="550f3-124">**Середнє**</span><span class="sxs-lookup"><span data-stu-id="550f3-124">**Average**</span></span>
   - <span data-ttu-id="550f3-125">**Кількість**</span><span class="sxs-lookup"><span data-stu-id="550f3-125">**Count**</span></span>
   - <span data-ttu-id="550f3-126">**Кількість унікальних**</span><span class="sxs-lookup"><span data-stu-id="550f3-126">**Count Unique**</span></span>
   - <span data-ttu-id="550f3-127">**Максимальна**</span><span class="sxs-lookup"><span data-stu-id="550f3-127">**Max**</span></span>
   - <span data-ttu-id="550f3-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="550f3-128">**Min**</span></span>
   - <span data-ttu-id="550f3-129">**Перше**: відбирає перше значення запису даних</span><span class="sxs-lookup"><span data-stu-id="550f3-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="550f3-130">**Останнє**: відбирає останнє значення, додане до запису даних</span><span class="sxs-lookup"><span data-stu-id="550f3-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Оператори для розрахунків показників.":::

1. <span data-ttu-id="550f3-132">Виберіть **Додати атрибут**, щоб вибрати дані, потрібні для створення цього показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="550f3-133">Виберіть вкладку **Атрибути**.</span><span class="sxs-lookup"><span data-stu-id="550f3-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="550f3-134">Сутність даних: виберіть сутність, що містить атрибут, який потрібно вимірювати.</span><span class="sxs-lookup"><span data-stu-id="550f3-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="550f3-135">Атрибут даних: виберіть атрибут, який потрібно використовувати в агрегатній функції для обчислення показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="550f3-136">Можна вибрати лише однин атрибут за раз.</span><span class="sxs-lookup"><span data-stu-id="550f3-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="550f3-137">Також можна вибрати атрибут даних із наявного показника, вибравши вкладку **Показники**. Також можна знайти сутність або показник, виконавши пошук за іменем.</span><span class="sxs-lookup"><span data-stu-id="550f3-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="550f3-138">Виберіть **Додати**, щоб додати вибраний атрибут до показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Виберіть атрибут, який використовуватиметься в обчисленнях.":::

1. <span data-ttu-id="550f3-140">Для створення складніших показників ви можете додавати більше атрибутів або використовувати математичні операції у функції для показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Створіть складний показник, використовуючи математичні операції.":::

1. <span data-ttu-id="550f3-142">Щоб додати фільтри, виберіть **Фільтр** в області налаштування.</span><span class="sxs-lookup"><span data-stu-id="550f3-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="550f3-143">У розділі **Додати атрибут** в області **Фільтри** виберіть атрибут, який потрібно використовувати при створенні фільтрів.</span><span class="sxs-lookup"><span data-stu-id="550f3-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="550f3-144">Установіть оператори фільтру, щоб визначити фільтр для кожного вибраного атрибута.</span><span class="sxs-lookup"><span data-stu-id="550f3-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="550f3-145">Виберіть **Застосувати**, щоб додати фільтри до показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="550f3-146">Щоб додати виміри, виберіть **Вимір** в області налаштування.</span><span class="sxs-lookup"><span data-stu-id="550f3-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="550f3-147">Виміри відображатимуться як стовпці у сутності виводу показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="550f3-148">Виберіть **Редагувати виміри**, щоб додати атрибути даних, за якими потрібно групувати значення показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="550f3-149">Наприклад, місто або стать.</span><span class="sxs-lookup"><span data-stu-id="550f3-149">For example, city or gender.</span></span> <span data-ttu-id="550f3-150">За замовчуванням вибрано вимір *CustomerID* для створення *показників на рівні клієнта*.</span><span class="sxs-lookup"><span data-stu-id="550f3-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="550f3-151">Якщо потрібно створити *показники на рівні компанії*, ви можете вибрати стандартний вимір.</span><span class="sxs-lookup"><span data-stu-id="550f3-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="550f3-152">Виберіть **Готово**, щоб додати виміри до показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="550f3-153">Якщо в даних присутні значення, які потрібно замінити цілими числами, наприклад, замінити значення *null* на *0*, виберіть **Правила**.</span><span class="sxs-lookup"><span data-stu-id="550f3-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="550f3-154">Налаштуйте правило та переконайтеся, що в якості замін вибрано лише цілі числа.</span><span class="sxs-lookup"><span data-stu-id="550f3-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="550f3-155">Якщо між зіставленою сутністю даних і сутністю *«Клієнт»* є кілька шляхів, слід вибрати один із визначених [шляхів зв'язку сутностей](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="550f3-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="550f3-156">Результати показників можуть біти різними залежно від вибраного шляху.</span><span class="sxs-lookup"><span data-stu-id="550f3-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="550f3-157">Виберіть **Параметри даних** і виберіть шлях сутності, який слід використовувати для ідентифікації вашого показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="550f3-158">Якщо існує лише один шлях до сутності *Клієнт*, цей елемент керування не відображатиметься.</span><span class="sxs-lookup"><span data-stu-id="550f3-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="550f3-159">Виберіть **Готово**, щоб підтвердити вибір.</span><span class="sxs-lookup"><span data-stu-id="550f3-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Виберіть шлях сутності для показника.":::

1. <span data-ttu-id="550f3-161">Щоб додати інші обчислення для показника, виберіть **Нове обчислення**.</span><span class="sxs-lookup"><span data-stu-id="550f3-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="550f3-162">Для нових обчислень можна використовувати сутності лише за тим самим шляхом сутності.</span><span class="sxs-lookup"><span data-stu-id="550f3-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="550f3-163">Додаткові обчислення відображатимуться як нові стовпці у сутності виводу показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="550f3-164">Виберіть **...** для обчислення, щоб **Дублювати**, **Перейменувати** або **Видалити** обчислення з показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="550f3-165">В області **Попередній перегляд** ви побачите схему даних сутності виводу показника, зокрема фільтри та виміри.</span><span class="sxs-lookup"><span data-stu-id="550f3-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="550f3-166">Попередній перегляд динамічно реагує на зміни налаштувань.</span><span class="sxs-lookup"><span data-stu-id="550f3-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="550f3-167">Виберіть **Виконати**, щоб обчислити результати для налаштованого показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="550f3-168">Виберіть **Зберегти та закрити**, якщо потрібно зберегти поточну конфігурацію та запустити показник пізніше.</span><span class="sxs-lookup"><span data-stu-id="550f3-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="550f3-169">Перейдіть до розділу **Показники**, щоб переглянути новостворений показник у списку.</span><span class="sxs-lookup"><span data-stu-id="550f3-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="550f3-170">Створення показника за допомогою шаблону</span><span class="sxs-lookup"><span data-stu-id="550f3-170">Use a template to build a measure</span></span>

<span data-ttu-id="550f3-171">Для створення часто використовуваних показників ви можете використовувати шаблони.</span><span class="sxs-lookup"><span data-stu-id="550f3-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="550f3-172">Детальні описи шаблонів та підказки інтерфейсу допоможуть вам швидко та зручно створювати показники.</span><span class="sxs-lookup"><span data-stu-id="550f3-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="550f3-173">Шаблони працюють, використовуючи зіставлені дані з сутності *Уніфікована справа*.</span><span class="sxs-lookup"><span data-stu-id="550f3-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="550f3-174">Тому перед створенням показника з шаблону переконайтесь, що ви налаштували [справи клієнтів](activities.md).</span><span class="sxs-lookup"><span data-stu-id="550f3-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="550f3-175">Доступні шаблони показників зазначено нижче.</span><span class="sxs-lookup"><span data-stu-id="550f3-175">Available measure templates:</span></span> 
- <span data-ttu-id="550f3-176">Середня вартість транзакції (ATV)</span><span class="sxs-lookup"><span data-stu-id="550f3-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="550f3-177">Загальна вартість транзакції</span><span class="sxs-lookup"><span data-stu-id="550f3-177">Total transaction value</span></span>
- <span data-ttu-id="550f3-178">Середній щоденний прибуток</span><span class="sxs-lookup"><span data-stu-id="550f3-178">Average daily revenue</span></span>
- <span data-ttu-id="550f3-179">Середній річний прибуток</span><span class="sxs-lookup"><span data-stu-id="550f3-179">Average yearly revenue</span></span>
- <span data-ttu-id="550f3-180">Кількість транзакцій</span><span class="sxs-lookup"><span data-stu-id="550f3-180">Transaction count</span></span>
- <span data-ttu-id="550f3-181">Отримані бали за лояльність</span><span class="sxs-lookup"><span data-stu-id="550f3-181">Loyalty points earned</span></span>
- <span data-ttu-id="550f3-182">Використані бали за лояльність</span><span class="sxs-lookup"><span data-stu-id="550f3-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="550f3-183">Баланс балів за лояльність</span><span class="sxs-lookup"><span data-stu-id="550f3-183">Loyalty points balance</span></span>
- <span data-ttu-id="550f3-184">Активний життєвий цикл клієнта</span><span class="sxs-lookup"><span data-stu-id="550f3-184">Active customer lifespan</span></span>
- <span data-ttu-id="550f3-185">Тривалість участі в програмі лояльності</span><span class="sxs-lookup"><span data-stu-id="550f3-185">Loyalty membership duration</span></span>
- <span data-ttu-id="550f3-186">Час з останньої покупки</span><span class="sxs-lookup"><span data-stu-id="550f3-186">Time since last purchase</span></span>

<span data-ttu-id="550f3-187">Наведена нижче процедура описує кроки створення нового показника із використанням шаблону.</span><span class="sxs-lookup"><span data-stu-id="550f3-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="550f3-188">У розділі «Аналіз аудиторії» виберіть **Показники**.</span><span class="sxs-lookup"><span data-stu-id="550f3-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="550f3-189">Виберіть **Створити**, а тоді — **Виберіть шаблон**.</span><span class="sxs-lookup"><span data-stu-id="550f3-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Знімок екрана: розкривне меню під час створення нового показника, де виділено шаблон.":::

1. <span data-ttu-id="550f3-191">Знайдіть шаблон, який відповідає вашим потребам, і виберіть **Вибрати шаблон**.</span><span class="sxs-lookup"><span data-stu-id="550f3-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="550f3-192">Перегляньте потрібні дані та виберіть **Почати**, якщо всі дані присутні.</span><span class="sxs-lookup"><span data-stu-id="550f3-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="550f3-193">В області **Редагування імені** встановіть ім'я показника та вихідну сутність.</span><span class="sxs-lookup"><span data-stu-id="550f3-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="550f3-194">Виберіть **Готово**.</span><span class="sxs-lookup"><span data-stu-id="550f3-194">Select **Done**.</span></span>

1. <span data-ttu-id="550f3-195">У розділі **Установити період часу** визначте часові рамки для даних, які слід використовувати.</span><span class="sxs-lookup"><span data-stu-id="550f3-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="550f3-196">Виберіть **Увесь час**, якщо потрібно, щоб новий показник враховував увесь набір даних.</span><span class="sxs-lookup"><span data-stu-id="550f3-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="550f3-197">Або якщо потрібно, щоб показник був зосереджений на **Певному періоді часу**.</span><span class="sxs-lookup"><span data-stu-id="550f3-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Знімок екрана: розділ періоду часу при настроюванні показника на основі шаблону.":::

1. <span data-ttu-id="550f3-199">У наступному розділі виберіть **Додати дані**, щоб вибрати справи та зіставити відповідні дані з вашої сутності *Уніфікована справа*.</span><span class="sxs-lookup"><span data-stu-id="550f3-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="550f3-200">Крок 1 із 2: у розділі **Тип справи** виберіть тип сутності, який потрібно використовувати.</span><span class="sxs-lookup"><span data-stu-id="550f3-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="550f3-201">У пункті **Справи** виберіть сутності, які потрібно зіставити.</span><span class="sxs-lookup"><span data-stu-id="550f3-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="550f3-202">Крок 2 із 2: виберіть атрибут з сутності *Уніфікована справа* для компонента, що потрібен за формулою.</span><span class="sxs-lookup"><span data-stu-id="550f3-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="550f3-203">Наприклад, для параметра «Середня вартість транзакції» це атрибут, що представляє вартість транзакції.</span><span class="sxs-lookup"><span data-stu-id="550f3-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="550f3-204">У полі **Позначка часу справи** виберіть атрибут з сутності «Уніфікована справа», який представляє дату й час справи.</span><span class="sxs-lookup"><span data-stu-id="550f3-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="550f3-205">Після успішного зіставлення даних відобразиться стан **Завершено**, а також імена зіставлених справ і атрибутів.</span><span class="sxs-lookup"><span data-stu-id="550f3-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Знімок екрана: завершена конфігурація шаблону показника.":::

1. <span data-ttu-id="550f3-207">Тепер можна вибрати команду **Виконати**, щоб обчислити результати для показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="550f3-208">Щоб уточнити його пізніше, виберіть **Зберегти чернетку**.</span><span class="sxs-lookup"><span data-stu-id="550f3-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="550f3-209">Керування показниками</span><span class="sxs-lookup"><span data-stu-id="550f3-209">Manage your measures</span></span>

<span data-ttu-id="550f3-210">Список показників можна знайти на сторінці **Показники**.</span><span class="sxs-lookup"><span data-stu-id="550f3-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="550f3-211">Ви знайдете відомості про тип, автора, дату створення, статус і стан показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="550f3-212">Вибравши показник зі списку, ви можете побачити попередній перегляд результатів та завантажити .CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="550f3-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="550f3-213">Щоб оновити всі показники одночасно, натисніть кнопку **Оновити все**, не вибираючи певний показник.</span><span class="sxs-lookup"><span data-stu-id="550f3-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="550f3-214">![Дії з керування окремими показниками](media/measure-actions.png "Дії з керування окремими показниками")</span><span class="sxs-lookup"><span data-stu-id="550f3-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="550f3-215">Виберіть показник зі списку, щоб побачити доступні варіанти дій.</span><span class="sxs-lookup"><span data-stu-id="550f3-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="550f3-216">Виберіть ім’я показника, щоб переглянути відомості про нього.</span><span class="sxs-lookup"><span data-stu-id="550f3-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="550f3-217">**Змініть** настроювання показника.</span><span class="sxs-lookup"><span data-stu-id="550f3-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="550f3-218">**Оновіть** показник із урахуванням останніх даних.</span><span class="sxs-lookup"><span data-stu-id="550f3-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="550f3-219">**Перейменуйте** показник.</span><span class="sxs-lookup"><span data-stu-id="550f3-219">**Rename** the measure.</span></span>
- <span data-ttu-id="550f3-220">**Видаліть** показник.</span><span class="sxs-lookup"><span data-stu-id="550f3-220">**Delete** the measure.</span></span>
- <span data-ttu-id="550f3-221">**Активуйте** або **Вимкніть**.</span><span class="sxs-lookup"><span data-stu-id="550f3-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="550f3-222">Неактивні показники не оновлюватимуться під час [оновлення за розкладом](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="550f3-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="550f3-223">Існує [шість типів станів](system.md#status-types) для завдань/процесів.</span><span class="sxs-lookup"><span data-stu-id="550f3-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="550f3-224">Крім того, більшість процесів [залежать від інших низхідних процесів](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="550f3-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="550f3-225">Можна вибрати стан процесу, щоб переглянути докладні відомості про перебіг виконання всієї роботи.</span><span class="sxs-lookup"><span data-stu-id="550f3-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="550f3-226">Після вибору **Переглянути відомості** для однієї з робіт завдання ви побачите додаткові відомості: час обробки, дата останньої обробки, а також усі помилки та попередження, пов'язані з завданням.</span><span class="sxs-lookup"><span data-stu-id="550f3-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="550f3-227">Наступний крок</span><span class="sxs-lookup"><span data-stu-id="550f3-227">Next step</span></span>

<span data-ttu-id="550f3-228">Використовуючи наявні показники, ви можете створити [сегмент клієнтів](segments.md).</span><span class="sxs-lookup"><span data-stu-id="550f3-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
