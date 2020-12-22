---
title: Створення сегментів і керування ними
description: Створюйте сегменти клієнтів, щоб групувати їх відповідно до різних атрибутів.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407284"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="d04b1-103">Створення сегментів і керування ними</span><span class="sxs-lookup"><span data-stu-id="d04b1-103">Create and manage segments</span></span>

<span data-ttu-id="d04b1-104">Сегменти дають змогу групувати клієнтів згідно з демографічними та поведінковими атрибутами, а також за особливостями транзакцій.</span><span class="sxs-lookup"><span data-stu-id="d04b1-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="d04b1-105">За допомогою сегментів можна використовувати цільові рекламні кампанії, торгівельну діяльність та дії з підтримки клієнтів для досягнення своїх бізнес-цілей.</span><span class="sxs-lookup"><span data-stu-id="d04b1-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="d04b1-106">Ви можете задати складні фільтри для сутності «Профіль клієнта» та пов’язаних із нею сутностей.</span><span class="sxs-lookup"><span data-stu-id="d04b1-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="d04b1-107">Кожен сегмент, після обробки, створює набір записів клієнтів, які можна експортувати та для яких можна вжити заходів.</span><span class="sxs-lookup"><span data-stu-id="d04b1-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="d04b1-108">Застосовуються деякі [ліміти послуг](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="d04b1-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="d04b1-109">Якщо не вказано інше, усі сегменти — це **динамічні сегменти**, які регулярно оновлюються за розкладом.</span><span class="sxs-lookup"><span data-stu-id="d04b1-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="d04b1-110">У наведеному нижче прикладі показано використання сегментів.</span><span class="sxs-lookup"><span data-stu-id="d04b1-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="d04b1-111">Ми визначили сегмент для клієнтів, які замовили товари принаймні на 500 доларів США за останні 90 днів *і* які мали відношення до звернень до служби підтримки клієнтів, пріоритет яких було підвищено.</span><span class="sxs-lookup"><span data-stu-id="d04b1-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d04b1-112">![Кілька груп](media/segmentation-group1-2.png "Кілька груп")</span><span class="sxs-lookup"><span data-stu-id="d04b1-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="d04b1-113">Створення нового сегмента</span><span class="sxs-lookup"><span data-stu-id="d04b1-113">Create a new segment</span></span>

<span data-ttu-id="d04b1-114">Ви можете керувати сегментами на сторінці **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="d04b1-115">У аналізу аудиторій відкрийте сторінку **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="d04b1-116">Виберіть **Новий** > **Пустий сегмент**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="d04b1-117">В області **Новий сегмент** виберіть тип сегмента та введіть **Ім’я**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="d04b1-118">Крім того, можна вказати коротке ім’я та опис, які допоможуть ідентифікувати сегмент.</span><span class="sxs-lookup"><span data-stu-id="d04b1-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="d04b1-119">Натисніть кнопку **Далі**, щоб перейти на сторінку **Конструктор сегментів**, на якій необхідно визначити групу.</span><span class="sxs-lookup"><span data-stu-id="d04b1-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="d04b1-120">Група — це сукупність клієнтів.</span><span class="sxs-lookup"><span data-stu-id="d04b1-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="d04b1-121">Виберіть сутність, яка включає атрибут, за яким потрібно виконати сегментацію.</span><span class="sxs-lookup"><span data-stu-id="d04b1-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="d04b1-122">Виберіть атрибут для сегментації за певним параметром.</span><span class="sxs-lookup"><span data-stu-id="d04b1-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="d04b1-123">Цей атрибут може мати один із чотирьох типів значень: числовий, рядок, дата або логічний.</span><span class="sxs-lookup"><span data-stu-id="d04b1-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="d04b1-124">Виберіть оператор і значення для вибраного атрибута.</span><span class="sxs-lookup"><span data-stu-id="d04b1-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d04b1-125">![Користувацький фільтр](media/customer-group-numbers.png "Фільтр групи «Клієнт»")</span><span class="sxs-lookup"><span data-stu-id="d04b1-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="d04b1-126">Номер</span><span class="sxs-lookup"><span data-stu-id="d04b1-126">Number</span></span> |<span data-ttu-id="d04b1-127">Визначення</span><span class="sxs-lookup"><span data-stu-id="d04b1-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="d04b1-128">1</span><span class="sxs-lookup"><span data-stu-id="d04b1-128">1</span></span>     |<span data-ttu-id="d04b1-129">Entity</span><span class="sxs-lookup"><span data-stu-id="d04b1-129">Entity</span></span>          |
   |<span data-ttu-id="d04b1-130">2</span><span class="sxs-lookup"><span data-stu-id="d04b1-130">2</span></span>     |<span data-ttu-id="d04b1-131">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d04b1-131">Attribute</span></span>          |
   |<span data-ttu-id="d04b1-132">3</span><span class="sxs-lookup"><span data-stu-id="d04b1-132">3</span></span>    |<span data-ttu-id="d04b1-133">Оператор</span><span class="sxs-lookup"><span data-stu-id="d04b1-133">Operator</span></span>         |
   |<span data-ttu-id="d04b1-134">4</span><span class="sxs-lookup"><span data-stu-id="d04b1-134">4</span></span>    |<span data-ttu-id="d04b1-135">Значення</span><span class="sxs-lookup"><span data-stu-id="d04b1-135">Value</span></span>         |

8. <span data-ttu-id="d04b1-136">Якщо сутність підключена до уніфікованої сутності клієнта за допомогою [зв’язків](relationships.md), необхідно визначити шлях зв’язку, щоб створити припустимий сегмент.</span><span class="sxs-lookup"><span data-stu-id="d04b1-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="d04b1-137">Додавайте сутності зі шляху до зв’язку, доки не зможете вибрати сутність **Клієнт: CustomerInsights** із розкривного списку.</span><span class="sxs-lookup"><span data-stu-id="d04b1-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="d04b1-138">Потім виберіть **Усі записи** для кожної умови.</span><span class="sxs-lookup"><span data-stu-id="d04b1-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d04b1-139">![Шлях до зв’язку під час створення сегмента](media/segments-multiple-relationships.png "Шлях до зв’язку під час створення сегмента")</span><span class="sxs-lookup"><span data-stu-id="d04b1-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="d04b1-140">Натисніть кнопку **Зберегти**, щоб зберегти сегмент.</span><span class="sxs-lookup"><span data-stu-id="d04b1-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="d04b1-141">Ваш сегмент буде збережено та оброблено, якщо він буде відповідати всім вимогам.</span><span class="sxs-lookup"><span data-stu-id="d04b1-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="d04b1-142">В іншому разі його буде збережено як чернетку.</span><span class="sxs-lookup"><span data-stu-id="d04b1-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="d04b1-143">Виберіть **Повернутися до сегментів**, щоб повернутися на сторінку **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="d04b1-144">Керування наявними сегментами</span><span class="sxs-lookup"><span data-stu-id="d04b1-144">Manage existing segments</span></span>

<span data-ttu-id="d04b1-145">На сторінці **Сегменти** можна переглянути всі збережені сегменти та керувати ними.</span><span class="sxs-lookup"><span data-stu-id="d04b1-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="d04b1-146">Кожен сегмент представлено рядком, який містить додаткові відомості про цей сегмент.</span><span class="sxs-lookup"><span data-stu-id="d04b1-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="d04b1-147">Можна відсортувати сегменти в стовпці, вибравши заголовок стовпця.</span><span class="sxs-lookup"><span data-stu-id="d04b1-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="d04b1-148">Щоб відфільтрувати сегменти, скористайтеся полем **Пошук** у верхньому правому куті.</span><span class="sxs-lookup"><span data-stu-id="d04b1-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d04b1-149">![Параметри для керування наявним сегментом](media/segments-selected-segment.png "Параметри для керування наявним сегментом")</span><span class="sxs-lookup"><span data-stu-id="d04b1-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="d04b1-150">У разі вибору сегмента можна виконати зазначені нижче дії.</span><span class="sxs-lookup"><span data-stu-id="d04b1-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="d04b1-151">**Переглянути** відомості про сегмент, включно з тенденцією кількості учасників для попереднього перегляду учасників сегмента.</span><span class="sxs-lookup"><span data-stu-id="d04b1-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="d04b1-152">**Змінити** сегмент, щоб змінити його властивості.</span><span class="sxs-lookup"><span data-stu-id="d04b1-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="d04b1-153">**Оновити** сегмент, щоб додати останні дані.</span><span class="sxs-lookup"><span data-stu-id="d04b1-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="d04b1-154">**Активувати** або **Вимкнути** сегмент.</span><span class="sxs-lookup"><span data-stu-id="d04b1-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="d04b1-155">Сегменти мають два можливі стани — активний або неактивний.</span><span class="sxs-lookup"><span data-stu-id="d04b1-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="d04b1-156">Ці стани зручно змінювати під час редагування сегмента.</span><span class="sxs-lookup"><span data-stu-id="d04b1-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="d04b1-157">Для неактивних сегментів для визначення сегмента існує, але ще не містить жодного клієнта.</span><span class="sxs-lookup"><span data-stu-id="d04b1-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="d04b1-158">Під час активації сегмента його стан змінюється з «неактивний» на «активний», і він починає шукати клієнтів, які відповідають визначенню сегмента.</span><span class="sxs-lookup"><span data-stu-id="d04b1-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="d04b1-159">Якщо [заплановане оновлення](system.md#schedule-tab) настроєно, неактивні сегменти мають **Статус**, зазначений у списку **Пропущено**, що свідчить про те, що оновлення ще не було виконано.</span><span class="sxs-lookup"><span data-stu-id="d04b1-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="d04b1-160">Під час активації неактивного сегмента він оновиться, і його буде додано до запланованого оновлення.</span><span class="sxs-lookup"><span data-stu-id="d04b1-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="d04b1-161">Крім того, можна використовувати функцію **Запланувати пізніше** з розкривного списку **Активувати / Деактивувати**, щоб задати дату та час у майбутньому для активації та деактивації певного сегмента.</span><span class="sxs-lookup"><span data-stu-id="d04b1-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="d04b1-162">**Перейменувати** сегмент.</span><span class="sxs-lookup"><span data-stu-id="d04b1-162">**Rename** the segment.</span></span>
- <span data-ttu-id="d04b1-163">**Завантажити** список учасників у вигляді CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="d04b1-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="d04b1-164">Параметр **Додати до** надсилає список ідентифікаторів клієнтів у сегменті для обробки в іншій програмі.</span><span class="sxs-lookup"><span data-stu-id="d04b1-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="d04b1-165">**Видалити** сегмент.</span><span class="sxs-lookup"><span data-stu-id="d04b1-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="d04b1-166">Оновлення сегментів</span><span class="sxs-lookup"><span data-stu-id="d04b1-166">Refresh segments</span></span>

<span data-ttu-id="d04b1-167">Можна оновити всі сегменти одночасно, вибравши **Оновити все** на сторінці **Сегменти**, або оновити один або кілька сегментів, якщо вибрати їх, а потім вибрати **Оновити** в параметрах.</span><span class="sxs-lookup"><span data-stu-id="d04b1-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="d04b1-168">Крім того, можна настроїти повторюване оновлення в розділі **Адміністратор** > **Система** > **Розклад**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="d04b1-169">Існує [шість типів станів](system.md#status-types) для завдань/процесів.</span><span class="sxs-lookup"><span data-stu-id="d04b1-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d04b1-170">Крім того, більшість процесів [залежать від інших низхідних процесів](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d04b1-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d04b1-171">Можна вибрати стан процесу, щоб переглянути докладні відомості про перебіг виконання всієї роботи.</span><span class="sxs-lookup"><span data-stu-id="d04b1-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d04b1-172">Після вибору **Переглянути відомості** для однієї з робіт завдання ви побачите додаткові відомості: час обробки, дата останньої обробки, а також усі помилки та попередження, пов'язані з завданням.</span><span class="sxs-lookup"><span data-stu-id="d04b1-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="d04b1-173">Завантаження та експорт сегментів</span><span class="sxs-lookup"><span data-stu-id="d04b1-173">Download and export segments</span></span>

<span data-ttu-id="d04b1-174">Можна завантажити сегменти до CSV-файлу або експортувати їх у Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="d04b1-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="d04b1-175">Завантаження сегментів до CSV-файлу</span><span class="sxs-lookup"><span data-stu-id="d04b1-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="d04b1-176">У аналізу аудиторій відкрийте сторінку **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="d04b1-177">Виберіть три крапки на плитці певного сегмента.</span><span class="sxs-lookup"><span data-stu-id="d04b1-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="d04b1-178">Виберіть **Завантажити у форматі CSV** з розкривного списку дій.</span><span class="sxs-lookup"><span data-stu-id="d04b1-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="d04b1-179">Експорт сегментів у Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="d04b1-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="d04b1-180">Перед експортуванням сегментів у Dynamics 365 Sales адміністратор має [створити призначення експорту](export-destinations.md) для Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="d04b1-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="d04b1-181">У аналізу аудиторій відкрийте сторінку **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="d04b1-182">Виберіть три крапки на плитці певного сегмента.</span><span class="sxs-lookup"><span data-stu-id="d04b1-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="d04b1-183">У розкривному списку дій виберіть **Додати до**, а потім виберіть призначення експорту, куди потрібно надіслати дані.</span><span class="sxs-lookup"><span data-stu-id="d04b1-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="d04b1-184">Режим чернетки для сегментів</span><span class="sxs-lookup"><span data-stu-id="d04b1-184">Draft mode for segments</span></span>

<span data-ttu-id="d04b1-185">Якщо виконуються не всі вимоги до обробки сегмента, цей сегмент можна зберегти як чернетку та отримати доступ до нього на сторінці **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="d04b1-186">Він буде збережений як неактивний сегмент, і його не можна буде активувати, доки він не буде припустимим.</span><span class="sxs-lookup"><span data-stu-id="d04b1-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="d04b1-187">Додавання додаткових умов до групи</span><span class="sxs-lookup"><span data-stu-id="d04b1-187">Add more conditions to a group</span></span>

<span data-ttu-id="d04b1-188">Щоб додати додаткові умови до групи, ви можете використовувати два логічних оператора:</span><span class="sxs-lookup"><span data-stu-id="d04b1-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="d04b1-189">Оператор **AND**: обидві умови мають бути виконані в рамках процесу сегментації.</span><span class="sxs-lookup"><span data-stu-id="d04b1-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="d04b1-190">Цей параметр найкорисніший, якщо ви визначаєте умови, що стосуються різних сутностей.</span><span class="sxs-lookup"><span data-stu-id="d04b1-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="d04b1-191">Оператор **OR**: одна з умов має бути виконана в рамках процесу сегментації.</span><span class="sxs-lookup"><span data-stu-id="d04b1-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="d04b1-192">Цей параметр найкорисніший, якщо ви визначаєте кілька умов для однієї сутності.</span><span class="sxs-lookup"><span data-stu-id="d04b1-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d04b1-193">![Оператор OR, у разі використання якого має бути виконано будь-яку одну умову](media/segmentation-either-condition.png "Оператор OR, у разі використання якого має бути виконано будь-яку одну умову")</span><span class="sxs-lookup"><span data-stu-id="d04b1-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="d04b1-194">Наразі можна вкладати оператор **OR** в умову з оператором **AND**, але не навпаки.</span><span class="sxs-lookup"><span data-stu-id="d04b1-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="d04b1-195">Поєднання кількох груп</span><span class="sxs-lookup"><span data-stu-id="d04b1-195">Combine multiple groups</span></span>

<span data-ttu-id="d04b1-196">Кожна група створює певний набір клієнтів.</span><span class="sxs-lookup"><span data-stu-id="d04b1-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="d04b1-197">Ці групи можна поєднати, щоб додати клієнтів, необхідних для вашої бізнес-операції.</span><span class="sxs-lookup"><span data-stu-id="d04b1-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="d04b1-198">У аналізі аудиторій відкрийте сторінку **Сегменти** та виберіть сегмент.</span><span class="sxs-lookup"><span data-stu-id="d04b1-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="d04b1-199">Виберіть елемент **Додати групу**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d04b1-200">![Група клієнта, додати групу](media/customer-group-add-group.png "Група клієнта, додати групу")</span><span class="sxs-lookup"><span data-stu-id="d04b1-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="d04b1-201">Виберіть один із зазначених нижче операторів набору: **Об’єднання**, **Перетин** або **Окрім**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d04b1-202">![Група клієнта, додати об’єднання](media/customer-group-union.png "Група клієнта, додати об’єднання")</span><span class="sxs-lookup"><span data-stu-id="d04b1-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="d04b1-203">Виберіть встановленого оператора, щоб визначити нову групу.</span><span class="sxs-lookup"><span data-stu-id="d04b1-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="d04b1-204">Збережіть різні групи, щоб визначити, які дані будуть зберігатися:</span><span class="sxs-lookup"><span data-stu-id="d04b1-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="d04b1-205">**Об’єднання** об’єднує дві групи.</span><span class="sxs-lookup"><span data-stu-id="d04b1-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="d04b1-206">**Перетин** перекриває дві групи.</span><span class="sxs-lookup"><span data-stu-id="d04b1-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="d04b1-207">У об’єднаній групі зберігатимуться лише такі дані, що *є загальними* для обох груп.</span><span class="sxs-lookup"><span data-stu-id="d04b1-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="d04b1-208">**Окрім** об’єднує дві групи.</span><span class="sxs-lookup"><span data-stu-id="d04b1-208">**Except** combines the two groups.</span></span> <span data-ttu-id="d04b1-209">Зберігатимуться лише такі дані у групі А, що *не є характерними* для групи Б.</span><span class="sxs-lookup"><span data-stu-id="d04b1-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="d04b1-210">Перегляд журналу обробки та учасників сегмента</span><span class="sxs-lookup"><span data-stu-id="d04b1-210">View processing history and segment members</span></span>

<span data-ttu-id="d04b1-211">Ви можете побачити консолідовані дані про сегмент, переглянувши докладні відомості про нього.</span><span class="sxs-lookup"><span data-stu-id="d04b1-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="d04b1-212">На сторінці **Сегменти** виберіть сегмент, який потрібно переглянути.</span><span class="sxs-lookup"><span data-stu-id="d04b1-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="d04b1-213">У верхній частині сторінки міститься графік тенденції, який візуалізує зміни в кількості учасників.</span><span class="sxs-lookup"><span data-stu-id="d04b1-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="d04b1-214">Наводьте курсор на точки даних, щоб бачити кількість учасників на певну дату.</span><span class="sxs-lookup"><span data-stu-id="d04b1-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="d04b1-215">Ви можете оновити часові рамки графічного відображення.</span><span class="sxs-lookup"><span data-stu-id="d04b1-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d04b1-216">![Часові рамки сегмента](media/segment-time-range.png "Часові рамки сегмента")</span><span class="sxs-lookup"><span data-stu-id="d04b1-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="d04b1-217">Нижня частина містить список учасників сегмента.</span><span class="sxs-lookup"><span data-stu-id="d04b1-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="d04b1-218">Поля, що відображаються в цьому списку, базуються на атрибутах сутностей вашого сегмента.</span><span class="sxs-lookup"><span data-stu-id="d04b1-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="d04b1-219">Список — це попередній перегляд відповідних учасників сегмента. Він показує перші 100 записів вашого сегмента. Це дає змогу швидко оцінити його та за потреби переглянути його визначення.</span><span class="sxs-lookup"><span data-stu-id="d04b1-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="d04b1-220">Щоб переглянути всі відповідні записи, потрібно [експортувати цей сегмент](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d04b1-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="d04b1-221">Швидкі сегменти</span><span class="sxs-lookup"><span data-stu-id="d04b1-221">Quick segments</span></span>

<span data-ttu-id="d04b1-222">На додачу до конструктора сегментів, існує ще один шлях створити сегмент.</span><span class="sxs-lookup"><span data-stu-id="d04b1-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="d04b1-223">Швидкі сегменти дозволяють створювати прості сегменти з одним оператором швидко та з миттєвими аналітичними висновками.</span><span class="sxs-lookup"><span data-stu-id="d04b1-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="d04b1-224">На сторінці **Сегменти** виберіть **Новий** > **Швидко створити з**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="d04b1-225">Виберіть параметр **Профілі**, щоб створити сегмент, який базується на уніфікованій сутності «Клієнт».</span><span class="sxs-lookup"><span data-stu-id="d04b1-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="d04b1-226">Виберіть параметр **Показники**, щоб створити сегмент навколо кожного типу показників «Атрибут клієнта», який раніше було створено на сторінці **Показники**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="d04b1-227">Виберіть параметр **Аналітика**, щоб створити сегмент навколо однієї з вихідних сутностей, які ви отримали за допомогою функції **Прогнози** або **Настроювані моделі**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="d04b1-228">У діалоговому вікні **Швидко створити сегмент** виберіть атрибут у розкривному списку **Поле**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="d04b1-229">Система надасть деякі додаткові аналітичні огляди, які допоможуть вам створити кращі сегменти клієнтів.</span><span class="sxs-lookup"><span data-stu-id="d04b1-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="d04b1-230">Для категоріальних полів ми покажемо 10 найкращих підрахунків клієнтів.</span><span class="sxs-lookup"><span data-stu-id="d04b1-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="d04b1-231">Виберіть елементи **Значення** та **Переглянути**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="d04b1-232">Для числового атрибута система відображатиме, яке значення атрибута підпадає під процентиль кожного клієнта.</span><span class="sxs-lookup"><span data-stu-id="d04b1-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="d04b1-233">Виберіть елементи **Оператор** і **Значення**, а потім виберіть **Переглянути**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="d04b1-234">Система покаже вам **Орієнтовний розмір сегмента**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="d04b1-235">Ви можете вибрати, чи слід створити визначений сегмент або спочатку повторно переглянути, щоб отримати інший розмір сегмента.</span><span class="sxs-lookup"><span data-stu-id="d04b1-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d04b1-236">![Ім’я та оцінка для швидко створеного сегмента](media/quick-segment-name.png "Ім’я та оцінка для швидко створеного сегмента")</span><span class="sxs-lookup"><span data-stu-id="d04b1-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="d04b1-237">Заповніть поле **Ім’я** для вашого сегмента.</span><span class="sxs-lookup"><span data-stu-id="d04b1-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="d04b1-238">Крім того, введіть **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="d04b1-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="d04b1-239">Натисніть кнопку **Зберегти**, щоб створити сегмент.</span><span class="sxs-lookup"><span data-stu-id="d04b1-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="d04b1-240">Після того, як сегмент завершить обробку ви можете переглянути його, як і будь-який інший сегмент, створений вами.</span><span class="sxs-lookup"><span data-stu-id="d04b1-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="d04b1-241">Для описаних далі сценаріїв радимо використовувати конструктор сегментів, а не можливість «Рекомендовані сегменти».</span><span class="sxs-lookup"><span data-stu-id="d04b1-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="d04b1-242">Створення сегментів із фільтрами в категоріальних полях, в яких інший оператор, ніж **Is**</span><span class="sxs-lookup"><span data-stu-id="d04b1-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="d04b1-243">Створення сегментів із фільтрами в числових полях, в яких оператор інший, ніж **Між**, **Більше** і **Менше**</span><span class="sxs-lookup"><span data-stu-id="d04b1-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="d04b1-244">Створення сегментів із фільтрами в полях типу «Дата»</span><span class="sxs-lookup"><span data-stu-id="d04b1-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="d04b1-245">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="d04b1-245">Next steps</span></span>

<span data-ttu-id="d04b1-246">[Експортуйте сегмент](export-destinations.md) та дослідіть [Картку клієнта](customer-card-add-in.md) та [З’єднувачі](export-power-bi.md), щоб отримувати аналітичні огляди на рівні клієнта.</span><span class="sxs-lookup"><span data-stu-id="d04b1-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
