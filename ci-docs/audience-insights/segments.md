---
title: Створення сегментів і керування ними
description: Створюйте сегменти клієнтів, щоб групувати їх відповідно до різних атрибутів.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597088"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="77975-103">Створення сегментів і керування ними</span><span class="sxs-lookup"><span data-stu-id="77975-103">Create and manage segments</span></span>

<span data-ttu-id="77975-104">Сегменти дають змогу групувати клієнтів згідно з демографічними та поведінковими атрибутами, а також за особливостями транзакцій.</span><span class="sxs-lookup"><span data-stu-id="77975-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="77975-105">За допомогою сегментів можна використовувати цільові рекламні кампанії, торгівельну діяльність та дії з підтримки клієнтів для досягнення своїх бізнес-цілей.</span><span class="sxs-lookup"><span data-stu-id="77975-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="77975-106">Ви можете задати складні фільтри для сутності «Профіль клієнта» та пов’язаних із нею сутностей.</span><span class="sxs-lookup"><span data-stu-id="77975-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="77975-107">Кожен сегмент, після обробки, створює набір записів клієнтів, які можна експортувати та для яких можна вжити заходів.</span><span class="sxs-lookup"><span data-stu-id="77975-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="77975-108">Застосовуються деякі [ліміти послуг](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="77975-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="77975-109">Якщо не вказано інше, усі сегменти — це **динамічні сегменти**, які регулярно оновлюються за розкладом.</span><span class="sxs-lookup"><span data-stu-id="77975-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="77975-110">У наведеному нижче прикладі показано використання сегментів.</span><span class="sxs-lookup"><span data-stu-id="77975-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="77975-111">Ми визначили сегмент для клієнтів, які замовили товари принаймні на 500 доларів США за останні 90 днів *і* які мали відношення до звернень до служби підтримки клієнтів, пріоритет яких було підвищено.</span><span class="sxs-lookup"><span data-stu-id="77975-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77975-112">![Кілька груп](media/segmentation-group1-2.png "Кілька груп")</span><span class="sxs-lookup"><span data-stu-id="77975-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="77975-113">Створення нового сегмента</span><span class="sxs-lookup"><span data-stu-id="77975-113">Create a new segment</span></span>

<span data-ttu-id="77975-114">Ви можете керувати сегментами на сторінці **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="77975-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="77975-115">У аналізу аудиторій відкрийте сторінку **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="77975-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="77975-116">Виберіть **Новий** > **Пустий сегмент**.</span><span class="sxs-lookup"><span data-stu-id="77975-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="77975-117">В області **Новий сегмент** виберіть тип сегмента та введіть **Ім’я**.</span><span class="sxs-lookup"><span data-stu-id="77975-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="77975-118">Крім того, можна вказати коротке ім’я та опис, які допоможуть ідентифікувати сегмент.</span><span class="sxs-lookup"><span data-stu-id="77975-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="77975-119">Натисніть кнопку **Далі**, щоб перейти на сторінку **Конструктор сегментів**, на якій необхідно визначити групу.</span><span class="sxs-lookup"><span data-stu-id="77975-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="77975-120">Група — це сукупність клієнтів.</span><span class="sxs-lookup"><span data-stu-id="77975-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="77975-121">Виберіть сутність, яка включає атрибут, за яким потрібно виконати сегментацію.</span><span class="sxs-lookup"><span data-stu-id="77975-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="77975-122">Виберіть атрибут для сегментації за певним параметром.</span><span class="sxs-lookup"><span data-stu-id="77975-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="77975-123">Цей атрибут може мати один із чотирьох типів значень: числовий, рядок, дата або логічний.</span><span class="sxs-lookup"><span data-stu-id="77975-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="77975-124">Виберіть оператор і значення для вибраного атрибута.</span><span class="sxs-lookup"><span data-stu-id="77975-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77975-125">![Користувацький фільтр](media/customer-group-numbers.png "Фільтр групи «Клієнт»")</span><span class="sxs-lookup"><span data-stu-id="77975-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="77975-126">Номер</span><span class="sxs-lookup"><span data-stu-id="77975-126">Number</span></span> |<span data-ttu-id="77975-127">Визначення</span><span class="sxs-lookup"><span data-stu-id="77975-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="77975-128">1</span><span class="sxs-lookup"><span data-stu-id="77975-128">1</span></span>     |<span data-ttu-id="77975-129">Entity</span><span class="sxs-lookup"><span data-stu-id="77975-129">Entity</span></span>          |
   |<span data-ttu-id="77975-130">2</span><span class="sxs-lookup"><span data-stu-id="77975-130">2</span></span>     |<span data-ttu-id="77975-131">Атрибут</span><span class="sxs-lookup"><span data-stu-id="77975-131">Attribute</span></span>          |
   |<span data-ttu-id="77975-132">3</span><span class="sxs-lookup"><span data-stu-id="77975-132">3</span></span>    |<span data-ttu-id="77975-133">Оператор</span><span class="sxs-lookup"><span data-stu-id="77975-133">Operator</span></span>         |
   |<span data-ttu-id="77975-134">4</span><span class="sxs-lookup"><span data-stu-id="77975-134">4</span></span>    |<span data-ttu-id="77975-135">Значення</span><span class="sxs-lookup"><span data-stu-id="77975-135">Value</span></span>         |

8. <span data-ttu-id="77975-136">Якщо сутність підключена до уніфікованої сутності клієнта за допомогою [зв’язків](relationships.md), необхідно визначити шлях зв’язку, щоб створити припустимий сегмент.</span><span class="sxs-lookup"><span data-stu-id="77975-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="77975-137">Додавайте сутності зі шляху до зв’язку, доки не зможете вибрати сутність **Клієнт: CustomerInsights** із розкривного списку.</span><span class="sxs-lookup"><span data-stu-id="77975-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="77975-138">Потім виберіть **Усі записи** для кожної умови.</span><span class="sxs-lookup"><span data-stu-id="77975-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77975-139">![Шлях до зв’язку під час створення сегмента](media/segments-multiple-relationships.png "Шлях до зв’язку під час створення сегмента")</span><span class="sxs-lookup"><span data-stu-id="77975-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="77975-140">За замовчуванням сегменти створюють вихідну сутність, яка містить усі атрибути профілів клієнтів, які відповідають визначеним фільтрам.</span><span class="sxs-lookup"><span data-stu-id="77975-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="77975-141">Якщо сегмент базується на інших сутностях, ніж сутність *Клієнт*, до вихідної сутності можна додати інші атрибути з цих сутностей.</span><span class="sxs-lookup"><span data-stu-id="77975-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="77975-142">Натисніть **Атрибути проекту**, щоб вибрати атрибути, які будуть додані до вихідної сутності.</span><span class="sxs-lookup"><span data-stu-id="77975-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="77975-143">Приклад: сегмент базується на сутності, що містить дані справи клієнта, пов'язані з сутністю *Клієнт*.</span><span class="sxs-lookup"><span data-stu-id="77975-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="77975-144">Сегмент шукає всіх клієнтів, які протягом останніх 60 днів телефонували до служби підтримки.</span><span class="sxs-lookup"><span data-stu-id="77975-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="77975-145">Можна додати тривалість виклику та кількість викликів до всіх відповідних записів клієнтів у вихідній сутності.</span><span class="sxs-lookup"><span data-stu-id="77975-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="77975-146">Ці відомості можуть знадобитися для надсилання повідомлення електронної пошти з корисними посиланнями на статті онлайнової довідки та поширені запитання клієнтам, які часто телефонують.</span><span class="sxs-lookup"><span data-stu-id="77975-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="77975-147">Натисніть кнопку **Зберегти**, щоб зберегти сегмент.</span><span class="sxs-lookup"><span data-stu-id="77975-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="77975-148">Ваш сегмент буде збережено та оброблено, якщо він буде відповідати всім вимогам.</span><span class="sxs-lookup"><span data-stu-id="77975-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="77975-149">В іншому разі його буде збережено як чернетку.</span><span class="sxs-lookup"><span data-stu-id="77975-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="77975-150">Виберіть **Повернутися до сегментів**, щоб повернутися на сторінку **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="77975-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="77975-151">Керування наявними сегментами</span><span class="sxs-lookup"><span data-stu-id="77975-151">Manage existing segments</span></span>

<span data-ttu-id="77975-152">На сторінці **Сегменти** можна переглянути всі збережені сегменти та керувати ними.</span><span class="sxs-lookup"><span data-stu-id="77975-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="77975-153">Кожен сегмент представлено рядком, який містить додаткові відомості про цей сегмент.</span><span class="sxs-lookup"><span data-stu-id="77975-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="77975-154">Можна відсортувати сегменти в стовпці, вибравши заголовок стовпця.</span><span class="sxs-lookup"><span data-stu-id="77975-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="77975-155">Щоб відфільтрувати сегменти, скористайтеся полем **Пошук** у верхньому правому куті.</span><span class="sxs-lookup"><span data-stu-id="77975-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77975-156">![Параметри для керування наявним сегментом](media/segments-selected-segment.png "Параметри для керування наявним сегментом")</span><span class="sxs-lookup"><span data-stu-id="77975-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="77975-157">У разі вибору сегмента можна виконати зазначені нижче дії.</span><span class="sxs-lookup"><span data-stu-id="77975-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="77975-158">**Переглянути** відомості про сегмент, включно з тенденцією кількості учасників для попереднього перегляду учасників сегмента.</span><span class="sxs-lookup"><span data-stu-id="77975-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="77975-159">**Змінити** сегмент, щоб змінити його властивості.</span><span class="sxs-lookup"><span data-stu-id="77975-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="77975-160">**Створити повтор** сегмента.</span><span class="sxs-lookup"><span data-stu-id="77975-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="77975-161">Тут можна змінити його властивості одразу або просто зберегти повтор.</span><span class="sxs-lookup"><span data-stu-id="77975-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="77975-162">**Оновити** сегмент, щоб додати останні дані.</span><span class="sxs-lookup"><span data-stu-id="77975-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="77975-163">**Активувати** або **Вимкнути** сегмент.</span><span class="sxs-lookup"><span data-stu-id="77975-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="77975-164">Сегменти мають два можливі стани — активний або неактивний.</span><span class="sxs-lookup"><span data-stu-id="77975-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="77975-165">Ці стани зручно змінювати під час редагування сегмента.</span><span class="sxs-lookup"><span data-stu-id="77975-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="77975-166">Для неактивних сегментів для визначення сегмента існує, але ще не містить жодного клієнта.</span><span class="sxs-lookup"><span data-stu-id="77975-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="77975-167">Під час активації сегмента його стан змінюється з «неактивний» на «активний», і він починає шукати клієнтів, які відповідають визначенню сегмента.</span><span class="sxs-lookup"><span data-stu-id="77975-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="77975-168">Якщо [заплановане оновлення](system.md#schedule-tab) настроєно, неактивні сегменти мають **Статус**, зазначений у списку **Пропущено**, що свідчить про те, що оновлення ще не було виконано.</span><span class="sxs-lookup"><span data-stu-id="77975-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="77975-169">Під час активації неактивного сегмента він оновиться, і його буде додано до запланованого оновлення.</span><span class="sxs-lookup"><span data-stu-id="77975-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="77975-170">Крім того, можна використовувати функцію **Запланувати пізніше** з розкривного списку **Активувати / Деактивувати**, щоб задати дату та час у майбутньому для активації та деактивації певного сегмента.</span><span class="sxs-lookup"><span data-stu-id="77975-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="77975-171">**Перейменувати** сегмент.</span><span class="sxs-lookup"><span data-stu-id="77975-171">**Rename** the segment.</span></span>
- <span data-ttu-id="77975-172">**Завантажити** список учасників у вигляді CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="77975-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="77975-173">Параметр **Додати до** надсилає список ідентифікаторів клієнтів у сегменті для обробки в іншій програмі.</span><span class="sxs-lookup"><span data-stu-id="77975-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="77975-174">**Видалити** сегмент.</span><span class="sxs-lookup"><span data-stu-id="77975-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="77975-175">Оновлення сегментів</span><span class="sxs-lookup"><span data-stu-id="77975-175">Refresh segments</span></span>

<span data-ttu-id="77975-176">Можна оновити всі сегменти одночасно, вибравши **Оновити все** на сторінці **Сегменти**, або оновити один або кілька сегментів, якщо вибрати їх, а потім вибрати **Оновити** в параметрах.</span><span class="sxs-lookup"><span data-stu-id="77975-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="77975-177">Крім того, можна настроїти повторюване оновлення в розділі **Адміністратор** > **Система** > **Розклад**.</span><span class="sxs-lookup"><span data-stu-id="77975-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="77975-178">Існує [шість типів станів](system.md#status-types) для завдань/процесів.</span><span class="sxs-lookup"><span data-stu-id="77975-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="77975-179">Крім того, більшість процесів [залежать від інших низхідних процесів](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="77975-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="77975-180">Можна вибрати стан процесу, щоб переглянути докладні відомості про перебіг виконання всієї роботи.</span><span class="sxs-lookup"><span data-stu-id="77975-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="77975-181">Після вибору **Переглянути відомості** для однієї з робіт завдання ви побачите додаткові відомості: час обробки, дата останньої обробки, а також усі помилки та попередження, пов'язані з завданням.</span><span class="sxs-lookup"><span data-stu-id="77975-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="77975-182">Завантаження та експорт сегментів</span><span class="sxs-lookup"><span data-stu-id="77975-182">Download and export segments</span></span>

<span data-ttu-id="77975-183">Можна завантажити сегменти до CSV-файлу або експортувати їх у Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="77975-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="77975-184">Завантаження сегментів до CSV-файлу</span><span class="sxs-lookup"><span data-stu-id="77975-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="77975-185">У аналізу аудиторій відкрийте сторінку **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="77975-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="77975-186">Виберіть три крапки на плитці певного сегмента.</span><span class="sxs-lookup"><span data-stu-id="77975-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="77975-187">Виберіть **Завантажити у форматі CSV** з розкривного списку дій.</span><span class="sxs-lookup"><span data-stu-id="77975-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="77975-188">Експорт сегментів у Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="77975-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="77975-189">Перед експортуванням сегментів у Dynamics 365 Sales адміністратор має [створити призначення експорту](export-destinations.md) для Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="77975-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="77975-190">У аналізу аудиторій відкрийте сторінку **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="77975-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="77975-191">Виберіть три крапки на плитці певного сегмента.</span><span class="sxs-lookup"><span data-stu-id="77975-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="77975-192">У розкривному списку дій виберіть **Додати до**, а потім виберіть призначення експорту, куди потрібно надіслати дані.</span><span class="sxs-lookup"><span data-stu-id="77975-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="77975-193">Режим чернетки для сегментів</span><span class="sxs-lookup"><span data-stu-id="77975-193">Draft mode for segments</span></span>

<span data-ttu-id="77975-194">Якщо виконуються не всі вимоги до обробки сегмента, цей сегмент можна зберегти як чернетку та отримати доступ до нього на сторінці **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="77975-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="77975-195">Він буде збережений як неактивний сегмент, і його не можна буде активувати, доки він не буде припустимим.</span><span class="sxs-lookup"><span data-stu-id="77975-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="77975-196">Додавання додаткових умов до групи</span><span class="sxs-lookup"><span data-stu-id="77975-196">Add more conditions to a group</span></span>

<span data-ttu-id="77975-197">Щоб додати додаткові умови до групи, ви можете використовувати два логічних оператора:</span><span class="sxs-lookup"><span data-stu-id="77975-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="77975-198">Оператор **AND**: обидві умови мають бути виконані в рамках процесу сегментації.</span><span class="sxs-lookup"><span data-stu-id="77975-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="77975-199">Цей параметр найкорисніший, якщо ви визначаєте умови, що стосуються різних сутностей.</span><span class="sxs-lookup"><span data-stu-id="77975-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="77975-200">Оператор **OR**: одна з умов має бути виконана в рамках процесу сегментації.</span><span class="sxs-lookup"><span data-stu-id="77975-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="77975-201">Цей параметр найкорисніший, якщо ви визначаєте кілька умов для однієї сутності.</span><span class="sxs-lookup"><span data-stu-id="77975-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77975-202">![Оператор OR, у разі використання якого має бути виконано будь-яку одну умову](media/segmentation-either-condition.png "Оператор OR, у разі використання якого має бути виконано будь-яку одну умову")</span><span class="sxs-lookup"><span data-stu-id="77975-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="77975-203">Наразі можна вкладати оператор **OR** в умову з оператором **AND**, але не навпаки.</span><span class="sxs-lookup"><span data-stu-id="77975-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="77975-204">Поєднання кількох груп</span><span class="sxs-lookup"><span data-stu-id="77975-204">Combine multiple groups</span></span>

<span data-ttu-id="77975-205">Кожна група створює певний набір клієнтів.</span><span class="sxs-lookup"><span data-stu-id="77975-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="77975-206">Ці групи можна поєднати, щоб додати клієнтів, необхідних для вашої бізнес-операції.</span><span class="sxs-lookup"><span data-stu-id="77975-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="77975-207">У аналізі аудиторій відкрийте сторінку **Сегменти** та виберіть сегмент.</span><span class="sxs-lookup"><span data-stu-id="77975-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="77975-208">Виберіть елемент **Додати групу**.</span><span class="sxs-lookup"><span data-stu-id="77975-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77975-209">![Група клієнта, додати групу](media/customer-group-add-group.png "Група клієнта, додати групу")</span><span class="sxs-lookup"><span data-stu-id="77975-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="77975-210">Виберіть один із зазначених нижче операторів набору: **Об’єднання**, **Перетин** або **Окрім**.</span><span class="sxs-lookup"><span data-stu-id="77975-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="77975-211">![Група клієнта, додати об’єднання](media/customer-group-union.png "Група клієнта, додати об’єднання")</span><span class="sxs-lookup"><span data-stu-id="77975-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="77975-212">Виберіть встановленого оператора, щоб визначити нову групу.</span><span class="sxs-lookup"><span data-stu-id="77975-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="77975-213">Збережіть різні групи, щоб визначити, які дані будуть зберігатися:</span><span class="sxs-lookup"><span data-stu-id="77975-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="77975-214">**Об’єднання** об’єднує дві групи.</span><span class="sxs-lookup"><span data-stu-id="77975-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="77975-215">**Перетин** перекриває дві групи.</span><span class="sxs-lookup"><span data-stu-id="77975-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="77975-216">У об’єднаній групі зберігатимуться лише такі дані, що *є загальними* для обох груп.</span><span class="sxs-lookup"><span data-stu-id="77975-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="77975-217">**Окрім** об’єднує дві групи.</span><span class="sxs-lookup"><span data-stu-id="77975-217">**Except** combines the two groups.</span></span> <span data-ttu-id="77975-218">Зберігатимуться лише такі дані у групі А, що *не є характерними* для групи Б.</span><span class="sxs-lookup"><span data-stu-id="77975-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="77975-219">Перегляд журналу обробки та учасників сегмента</span><span class="sxs-lookup"><span data-stu-id="77975-219">View processing history and segment members</span></span>

<span data-ttu-id="77975-220">Ви можете побачити консолідовані дані про сегмент, переглянувши докладні відомості про нього.</span><span class="sxs-lookup"><span data-stu-id="77975-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="77975-221">На сторінці **Сегменти** виберіть сегмент, який потрібно переглянути.</span><span class="sxs-lookup"><span data-stu-id="77975-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="77975-222">У верхній частині сторінки міститься графік тенденції, який візуалізує зміни в кількості учасників.</span><span class="sxs-lookup"><span data-stu-id="77975-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="77975-223">Наводьте курсор на точки даних, щоб бачити кількість учасників на певну дату.</span><span class="sxs-lookup"><span data-stu-id="77975-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="77975-224">Ви можете оновити часові рамки графічного відображення.</span><span class="sxs-lookup"><span data-stu-id="77975-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77975-225">![Часові рамки сегмента](media/segment-time-range.png "Часові рамки сегмента")</span><span class="sxs-lookup"><span data-stu-id="77975-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="77975-226">Нижня частина містить список учасників сегмента.</span><span class="sxs-lookup"><span data-stu-id="77975-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="77975-227">Поля, що відображаються в цьому списку, базуються на атрибутах сутностей вашого сегмента.</span><span class="sxs-lookup"><span data-stu-id="77975-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="77975-228">Список — це попередній перегляд відповідних учасників сегмента. Він показує перші 100 записів вашого сегмента. Це дає змогу швидко оцінити його та за потреби переглянути його визначення.</span><span class="sxs-lookup"><span data-stu-id="77975-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="77975-229">Щоб переглянути всі відповідні записи, потрібно [експортувати цей сегмент](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="77975-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="77975-230">Швидкі сегменти</span><span class="sxs-lookup"><span data-stu-id="77975-230">Quick segments</span></span>

<span data-ttu-id="77975-231">На додачу до конструктора сегментів, існує ще один шлях створити сегмент.</span><span class="sxs-lookup"><span data-stu-id="77975-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="77975-232">Швидкі сегменти дозволяють створювати прості сегменти з одним оператором швидко та з миттєвими аналітичними висновками.</span><span class="sxs-lookup"><span data-stu-id="77975-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="77975-233">На сторінці **Сегменти** виберіть **Новий** > **Швидко створити з**.</span><span class="sxs-lookup"><span data-stu-id="77975-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="77975-234">Виберіть параметр **Профілі**, щоб створити сегмент, який базується на уніфікованій сутності «Клієнт».</span><span class="sxs-lookup"><span data-stu-id="77975-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="77975-235">Виберіть параметр **Показники**, щоб створити сегмент навколо кожного типу показників «Атрибут клієнта», який раніше було створено на сторінці **Показники**.</span><span class="sxs-lookup"><span data-stu-id="77975-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="77975-236">Виберіть параметр **Аналітика**, щоб створити сегмент навколо однієї з вихідних сутностей, які ви отримали за допомогою функції **Прогнози** або **Настроювані моделі**.</span><span class="sxs-lookup"><span data-stu-id="77975-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="77975-237">У діалоговому вікні **Швидко створити сегмент** виберіть атрибут у розкривному списку **Поле**.</span><span class="sxs-lookup"><span data-stu-id="77975-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="77975-238">Система надасть деякі додаткові аналітичні огляди, які допоможуть вам створити кращі сегменти клієнтів.</span><span class="sxs-lookup"><span data-stu-id="77975-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="77975-239">Для категоріальних полів ми покажемо 10 найкращих підрахунків клієнтів.</span><span class="sxs-lookup"><span data-stu-id="77975-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="77975-240">Виберіть елементи **Значення** та **Переглянути**.</span><span class="sxs-lookup"><span data-stu-id="77975-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="77975-241">Для числового атрибута система відображатиме, яке значення атрибута підпадає під процентиль кожного клієнта.</span><span class="sxs-lookup"><span data-stu-id="77975-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="77975-242">Виберіть елементи **Оператор** і **Значення**, а потім виберіть **Переглянути**.</span><span class="sxs-lookup"><span data-stu-id="77975-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="77975-243">Система покаже вам **Орієнтовний розмір сегмента**.</span><span class="sxs-lookup"><span data-stu-id="77975-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="77975-244">Ви можете вибрати, чи слід створити визначений сегмент або спочатку повторно переглянути, щоб отримати інший розмір сегмента.</span><span class="sxs-lookup"><span data-stu-id="77975-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77975-245">![Ім’я та оцінка для швидко створеного сегмента](media/quick-segment-name.png "Ім’я та оцінка для швидко створеного сегмента")</span><span class="sxs-lookup"><span data-stu-id="77975-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="77975-246">Заповніть поле **Ім’я** для вашого сегмента.</span><span class="sxs-lookup"><span data-stu-id="77975-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="77975-247">Крім того, введіть **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="77975-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="77975-248">Натисніть кнопку **Зберегти**, щоб створити сегмент.</span><span class="sxs-lookup"><span data-stu-id="77975-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="77975-249">Після того, як сегмент завершить обробку ви можете переглянути його, як і будь-який інший сегмент, створений вами.</span><span class="sxs-lookup"><span data-stu-id="77975-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="77975-250">Для описаних далі сценаріїв радимо використовувати конструктор сегментів, а не можливість «Рекомендовані сегменти».</span><span class="sxs-lookup"><span data-stu-id="77975-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="77975-251">Створення сегментів із фільтрами в категоріальних полях, в яких інший оператор, ніж **Is**</span><span class="sxs-lookup"><span data-stu-id="77975-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="77975-252">Створення сегментів із фільтрами в числових полях, в яких оператор інший, ніж **Між**, **Більше** і **Менше**</span><span class="sxs-lookup"><span data-stu-id="77975-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="77975-253">Створення сегментів із фільтрами в полях типу «Дата»</span><span class="sxs-lookup"><span data-stu-id="77975-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="77975-254">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="77975-254">Next steps</span></span>

<span data-ttu-id="77975-255">[Експортуйте сегмент](export-destinations.md) та дослідіть [Картку клієнта](customer-card-add-in.md) та [З’єднувачі](export-power-bi.md), щоб отримувати аналітичні огляди на рівні клієнта.</span><span class="sxs-lookup"><span data-stu-id="77975-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]