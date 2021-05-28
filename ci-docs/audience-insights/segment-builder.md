---
title: Створення сегментів і керування ними
description: Створюйте сегменти клієнтів, щоб групувати їх відповідно до різних атрибутів.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064962"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="47711-103">Створення сегментів і керування ними</span><span class="sxs-lookup"><span data-stu-id="47711-103">Create and manage segments</span></span>

<span data-ttu-id="47711-104">Визначайте складні фільтри для уніфікованої сутності клієнта та пов'язаних із нею сутностей.</span><span class="sxs-lookup"><span data-stu-id="47711-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="47711-105">Кожен сегмент, після обробки, створює набір записів клієнтів, які можна експортувати та для яких можна вжити заходів.</span><span class="sxs-lookup"><span data-stu-id="47711-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="47711-106">Ви можете керувати сегментами на сторінці **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="47711-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="47711-107">У наведеному нижче прикладі показано використання сегментів.</span><span class="sxs-lookup"><span data-stu-id="47711-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="47711-108">Ми визначили сегмент для клієнтів, які замовили товари принаймні на 500 доларів США за останні 90 днів *і* які мали відношення до звернень до служби підтримки клієнтів, пріоритет яких було підвищено.</span><span class="sxs-lookup"><span data-stu-id="47711-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Знімок екрана: інтерфейс конструктора сегментів із двома групами, що визначають сегмент клієнтів.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="47711-110">Створення нового сегмента</span><span class="sxs-lookup"><span data-stu-id="47711-110">Create a new segment</span></span>

<span data-ttu-id="47711-111">Існує кілька способів створити новий сегмент.</span><span class="sxs-lookup"><span data-stu-id="47711-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="47711-112">У цьому розділі описано створення *пустого сегмента* з нуля.</span><span class="sxs-lookup"><span data-stu-id="47711-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="47711-113">Також можна створити *швидкий сегмент* на основі наявних сутностей або використати моделі машинного навчання, щоб отримати *запропоновані сегменти*.</span><span class="sxs-lookup"><span data-stu-id="47711-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="47711-114">Додаткові відомості: [Огляд сегментів](segments.md).</span><span class="sxs-lookup"><span data-stu-id="47711-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="47711-115">Під час створення сегмента можна зберегти чернетку.</span><span class="sxs-lookup"><span data-stu-id="47711-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="47711-116">ЇЇ буде збережено як неактивний сегмент, що не можна буде активувати, поки налаштування не буде завершено належним чином..</span><span class="sxs-lookup"><span data-stu-id="47711-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="47711-117">Перейдіть на сторінку **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="47711-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="47711-118">Виберіть **Новий** > **Пустий сегмент**.</span><span class="sxs-lookup"><span data-stu-id="47711-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="47711-119">В області **Новий сегмент** виберіть тип сегмента.</span><span class="sxs-lookup"><span data-stu-id="47711-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="47711-120">**Динамічні сегменти** [оновлюються](segments.md#refresh-segments) за повторюваним розкладом.</span><span class="sxs-lookup"><span data-stu-id="47711-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="47711-121">**Статичні сегменти** запускаються один раз при створенні.</span><span class="sxs-lookup"><span data-stu-id="47711-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="47711-122">Укажіть **Ім'я вихідної сутності** для сегмента.</span><span class="sxs-lookup"><span data-stu-id="47711-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="47711-123">Крім того, можна вказати коротке ім’я та опис, які допоможуть ідентифікувати сегмент.</span><span class="sxs-lookup"><span data-stu-id="47711-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="47711-124">Натисніть кнопку **Далі**, щоб перейти на сторінку **Конструктор сегментів**, на якій необхідно визначити групу.</span><span class="sxs-lookup"><span data-stu-id="47711-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="47711-125">Група — це сукупність клієнтів.</span><span class="sxs-lookup"><span data-stu-id="47711-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="47711-126">Виберіть сутність, яка включає атрибут, за яким потрібно виконати сегментацію.</span><span class="sxs-lookup"><span data-stu-id="47711-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="47711-127">Виберіть атрибут для сегментації за певним параметром.</span><span class="sxs-lookup"><span data-stu-id="47711-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="47711-128">Цей атрибут може мати один із чотирьох типів значень: числовий, рядок, дата або логічний.</span><span class="sxs-lookup"><span data-stu-id="47711-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="47711-129">Виберіть оператор і значення для вибраного атрибута.</span><span class="sxs-lookup"><span data-stu-id="47711-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="47711-130">![Користувацький фільтр](media/customer-group-numbers.png "Фільтр групи «Клієнт»")</span><span class="sxs-lookup"><span data-stu-id="47711-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="47711-131">Число</span><span class="sxs-lookup"><span data-stu-id="47711-131">Number</span></span> |<span data-ttu-id="47711-132">Визначення</span><span class="sxs-lookup"><span data-stu-id="47711-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="47711-133">1</span><span class="sxs-lookup"><span data-stu-id="47711-133">1</span></span>     |<span data-ttu-id="47711-134">Entity</span><span class="sxs-lookup"><span data-stu-id="47711-134">Entity</span></span>          |
   |<span data-ttu-id="47711-135">2</span><span class="sxs-lookup"><span data-stu-id="47711-135">2</span></span>     |<span data-ttu-id="47711-136">Атрибут</span><span class="sxs-lookup"><span data-stu-id="47711-136">Attribute</span></span>          |
   |<span data-ttu-id="47711-137">3</span><span class="sxs-lookup"><span data-stu-id="47711-137">3</span></span>    |<span data-ttu-id="47711-138">Оператор</span><span class="sxs-lookup"><span data-stu-id="47711-138">Operator</span></span>         |
   |<span data-ttu-id="47711-139">4</span><span class="sxs-lookup"><span data-stu-id="47711-139">4</span></span>    |<span data-ttu-id="47711-140">Значення</span><span class="sxs-lookup"><span data-stu-id="47711-140">Value</span></span>         |

   1. <span data-ttu-id="47711-141">Щоб додати додаткові умови до групи, ви можете використовувати два логічних оператора:</span><span class="sxs-lookup"><span data-stu-id="47711-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="47711-142">Оператор **AND**: обидві умови мають бути виконані в рамках процесу сегментації.</span><span class="sxs-lookup"><span data-stu-id="47711-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="47711-143">Цей параметр найкорисніший, якщо ви визначаєте умови, що стосуються різних сутностей.</span><span class="sxs-lookup"><span data-stu-id="47711-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="47711-144">Оператор **OR**: одна з умов має бути виконана в рамках процесу сегментації.</span><span class="sxs-lookup"><span data-stu-id="47711-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="47711-145">Цей параметр найкорисніший, якщо ви визначаєте кілька умов для однієї сутності.</span><span class="sxs-lookup"><span data-stu-id="47711-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="47711-146">![Оператор OR, у разі використання якого має бути виконано будь-яку одну умову](media/segmentation-either-condition.png "Оператор OR, у разі використання якого має бути виконано будь-яку одну умову")</span><span class="sxs-lookup"><span data-stu-id="47711-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="47711-147">Наразі можна вкладати оператор **OR** в умову з оператором **AND**, але не навпаки.</span><span class="sxs-lookup"><span data-stu-id="47711-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="47711-148">Кожна група відповідає набору клієнтів.</span><span class="sxs-lookup"><span data-stu-id="47711-148">Each group matches set of customers.</span></span> <span data-ttu-id="47711-149">Групи можна об'єднувати, щоб включати необхідних для певного бізнес-сценарію користувачів.</span><span class="sxs-lookup"><span data-stu-id="47711-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="47711-150">Виберіть елемент **Додати групу**.</span><span class="sxs-lookup"><span data-stu-id="47711-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="47711-151">![Група клієнта, додати групу](media/customer-group-add-group.png "Група клієнта, додати групу")</span><span class="sxs-lookup"><span data-stu-id="47711-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="47711-152">Виберіть одну з операцій з множинами: **Об'єднання**, **Перетин** або **Окрім**.</span><span class="sxs-lookup"><span data-stu-id="47711-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="47711-153">![Група клієнта, додати об’єднання](media/customer-group-union.png "Група клієнта, додати об’єднання")</span><span class="sxs-lookup"><span data-stu-id="47711-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="47711-154">**Об’єднання** об’єднує дві групи.</span><span class="sxs-lookup"><span data-stu-id="47711-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="47711-155">**Перетин** перекриває дві групи.</span><span class="sxs-lookup"><span data-stu-id="47711-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="47711-156">У об’єднаній групі зберігатимуться лише такі дані, що *є загальними* для обох груп.</span><span class="sxs-lookup"><span data-stu-id="47711-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="47711-157">**Окрім** об’єднує дві групи.</span><span class="sxs-lookup"><span data-stu-id="47711-157">**Except** combines the two groups.</span></span> <span data-ttu-id="47711-158">Зберігатимуться лише такі дані у групі А, що *не є характерними* для групи Б.</span><span class="sxs-lookup"><span data-stu-id="47711-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="47711-159">Якщо сутність підключена до уніфікованої сутності клієнта за допомогою [зв’язків](relationships.md), необхідно визначити шлях зв’язку, щоб створити припустимий сегмент.</span><span class="sxs-lookup"><span data-stu-id="47711-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="47711-160">Додавайте сутності зі шляху до зв’язку, доки не зможете вибрати сутність **Клієнт: CustomerInsights** із розкривного списку.</span><span class="sxs-lookup"><span data-stu-id="47711-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="47711-161">Потім виберіть **Усі записи** на кожному кроці.</span><span class="sxs-lookup"><span data-stu-id="47711-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="47711-162">![Шлях до зв’язку під час створення сегмента](media/segments-multiple-relationships.png "Шлях до зв’язку під час створення сегмента")</span><span class="sxs-lookup"><span data-stu-id="47711-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="47711-163">За замовчуванням сегменти створюють вихідну сутність, яка містить усі атрибути профілів клієнтів, які відповідають визначеним фільтрам.</span><span class="sxs-lookup"><span data-stu-id="47711-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="47711-164">Якщо сегмент базується на інших сутностях, ніж сутність *Клієнт*, до вихідної сутності можна додати інші атрибути з цих сутностей.</span><span class="sxs-lookup"><span data-stu-id="47711-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="47711-165">Натисніть **Атрибути проекту**, щоб вибрати атрибути, які будуть додані до вихідної сутності.</span><span class="sxs-lookup"><span data-stu-id="47711-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="47711-166">Приклад: сегмент базується на сутності, що містить дані справи клієнта, пов'язані з сутністю *Клієнт*.</span><span class="sxs-lookup"><span data-stu-id="47711-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="47711-167">Сегмент шукає всіх клієнтів, які протягом останніх 60 днів телефонували до служби підтримки.</span><span class="sxs-lookup"><span data-stu-id="47711-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="47711-168">Можна додати тривалість виклику та кількість викликів до всіх відповідних записів клієнтів у вихідній сутності.</span><span class="sxs-lookup"><span data-stu-id="47711-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="47711-169">Ці відомості можуть знадобитися для надсилання повідомлення електронної пошти з корисними посиланнями на статті онлайнової довідки та поширені запитання клієнтам, які часто телефонують.</span><span class="sxs-lookup"><span data-stu-id="47711-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="47711-170">Прогнозовані атрибути працюють лише для сутностей, які мають зв'язки один до багатьох із сутністю клієнта.</span><span class="sxs-lookup"><span data-stu-id="47711-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="47711-171">Наприклад, один клієнт може мати кілька передплат.</span><span class="sxs-lookup"><span data-stu-id="47711-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="47711-172">Можна прогнозувати атрибути лише з сутності, яка використовується в кожній групі запиту сегмента, який ви створюєте.</span><span class="sxs-lookup"><span data-stu-id="47711-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="47711-173">Прогнозовані атрибути враховуються при використанні операцій з множинами.</span><span class="sxs-lookup"><span data-stu-id="47711-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="47711-174">Натисніть кнопку **Зберегти**, щоб зберегти сегмент.</span><span class="sxs-lookup"><span data-stu-id="47711-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="47711-175">Ваш сегмент буде збережено та оброблено, якщо він буде відповідати всім вимогам.</span><span class="sxs-lookup"><span data-stu-id="47711-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="47711-176">В іншому разі його буде збережено як чернетку.</span><span class="sxs-lookup"><span data-stu-id="47711-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="47711-177">Виберіть **Повернутися до сегментів**, щоб повернутися на сторінку **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="47711-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="47711-178">Швидкі сегменти</span><span class="sxs-lookup"><span data-stu-id="47711-178">Quick segments</span></span>

<span data-ttu-id="47711-179">Швидкі сегменти дозволяють створювати прості сегменти одним оператором для швидкого аналізу.</span><span class="sxs-lookup"><span data-stu-id="47711-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="47711-180">На сторінці **Сегменти** виберіть **Створити** > **Створити на основі**.</span><span class="sxs-lookup"><span data-stu-id="47711-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="47711-181">Виберіть пункт **Профілі**, щоб створити сегмент, оснований на *уніфікованій сутності клієнта*.</span><span class="sxs-lookup"><span data-stu-id="47711-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="47711-182">Виберіть пункт **Показники**, щоб побудувати сегмент на основі раніше створених показників.</span><span class="sxs-lookup"><span data-stu-id="47711-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="47711-183">Виберіть параметр **Аналітика**, щоб створити сегмент навколо однієї з вихідних сутностей, які ви отримали за допомогою функції **Прогнози** або **Настроювані моделі**.</span><span class="sxs-lookup"><span data-stu-id="47711-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="47711-184">У діалоговому вікні **Швидко створити сегмент** виберіть атрибут у розкривному списку **Поле**.</span><span class="sxs-lookup"><span data-stu-id="47711-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="47711-185">Система надасть деякі додаткові аналітичні огляди, які допоможуть вам створити кращі сегменти клієнтів.</span><span class="sxs-lookup"><span data-stu-id="47711-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="47711-186">Для категоріальних полів ми покажемо 10 найкращих підрахунків клієнтів.</span><span class="sxs-lookup"><span data-stu-id="47711-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="47711-187">Виберіть елементи **Значення** та **Переглянути**.</span><span class="sxs-lookup"><span data-stu-id="47711-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="47711-188">Для числового атрибута система відображатиме, яке значення атрибута підпадає під процентиль кожного клієнта.</span><span class="sxs-lookup"><span data-stu-id="47711-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="47711-189">Виберіть елементи **Оператор** і **Значення**, а потім виберіть **Переглянути**.</span><span class="sxs-lookup"><span data-stu-id="47711-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="47711-190">Система покаже вам **Орієнтовний розмір сегмента**.</span><span class="sxs-lookup"><span data-stu-id="47711-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="47711-191">Ви можете вибрати, чи слід створити визначений сегмент або спочатку повторно переглянути, щоб отримати інший розмір сегмента.</span><span class="sxs-lookup"><span data-stu-id="47711-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="47711-192">![Ім’я та оцінка для швидко створеного сегмента](media/quick-segment-name.png "Ім’я та оцінка для швидко створеного сегмента")</span><span class="sxs-lookup"><span data-stu-id="47711-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="47711-193">Заповніть поле **Ім’я** для вашого сегмента.</span><span class="sxs-lookup"><span data-stu-id="47711-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="47711-194">Крім того, введіть **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="47711-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="47711-195">Натисніть кнопку **Зберегти**, щоб створити сегмент.</span><span class="sxs-lookup"><span data-stu-id="47711-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="47711-196">Після того, як сегмент завершить обробку ви можете переглянути його, як і будь-який інший сегмент, створений вами.</span><span class="sxs-lookup"><span data-stu-id="47711-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="47711-197">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="47711-197">Next steps</span></span>

<span data-ttu-id="47711-198">[Експортуйте сегмент](export-destinations.md) та дослідіть [Картку клієнта](customer-card-add-in.md) та [З’єднувачі](export-power-bi.md), щоб отримувати аналітичні огляди на рівні клієнта.</span><span class="sxs-lookup"><span data-stu-id="47711-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
