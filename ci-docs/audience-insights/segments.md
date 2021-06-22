---
title: Сегменти в аналізі аудиторії
description: Огляд сегментів, способи їх створення та керування ними.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111412"
---
# <a name="segments-overview"></a><span data-ttu-id="54d7e-103">Огляд сегментів</span><span class="sxs-lookup"><span data-stu-id="54d7e-103">Segments overview</span></span>

<span data-ttu-id="54d7e-104">Сегменти дають змогу групувати клієнтів згідно з демографічними та поведінковими атрибутами, а також за особливостями транзакцій.</span><span class="sxs-lookup"><span data-stu-id="54d7e-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="54d7e-105">За допомогою сегментів можна використовувати цільові рекламні кампанії, торгівельну діяльність та дії з підтримки клієнтів для досягнення своїх бізнес-цілей.</span><span class="sxs-lookup"><span data-stu-id="54d7e-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="54d7e-106">Профілі клієнтів, які відповідають фільтрам визначення сегмента, називаються *учасниками* сегмента.</span><span class="sxs-lookup"><span data-stu-id="54d7e-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="54d7e-107">Застосовуються деякі [ліміти послуг](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="54d7e-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="54d7e-108">Створення нового сегмента</span><span class="sxs-lookup"><span data-stu-id="54d7e-108">Create a new segment</span></span>

<span data-ttu-id="54d7e-109">Існує кілька способів створити новий сегмент.</span><span class="sxs-lookup"><span data-stu-id="54d7e-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="54d7e-110">Складний сегмент у конструкторі сегментів: [Пустий сегмент](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="54d7e-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="54d7e-111">Прості сегменти за допомогою одного оператора: [Швидкий сегмент](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="54d7e-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="54d7e-112">Спосіб пошуку подібних клієнтів за допомогою ШІ: [Подібні клієнти](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="54d7e-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="54d7e-113">Пропозиції на основі ШІ залежно від показників або атрибутів: [Пропоновані сегменти для покращення показників](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="54d7e-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="54d7e-114">Пропозиції на основі справ: [Пропоновані сегменти на основі справ клієнта](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="54d7e-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="54d7e-115">Керування наявними сегментами</span><span class="sxs-lookup"><span data-stu-id="54d7e-115">Manage existing segments</span></span>

<span data-ttu-id="54d7e-116">Перейдіть на сторінку **Сегменти**, щоб переглянути всі збережені сегменти та керувати ними.</span><span class="sxs-lookup"><span data-stu-id="54d7e-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="54d7e-117">Кожен сегмент представлено рядком, який містить додаткові відомості про цей сегмент.</span><span class="sxs-lookup"><span data-stu-id="54d7e-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Вибраний сегмент з розкривним списком параметрів і доступними можливостями.":::

<span data-ttu-id="54d7e-119">У разі вибору сегмента можна виконати зазначені нижче дії.</span><span class="sxs-lookup"><span data-stu-id="54d7e-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="54d7e-120">**Переглянути** відомості про сегмент, включно з тенденцією кількості учасників для попереднього перегляду учасників сегмента.</span><span class="sxs-lookup"><span data-stu-id="54d7e-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="54d7e-121">**Змінити** сегмент, щоб змінити його властивості.</span><span class="sxs-lookup"><span data-stu-id="54d7e-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="54d7e-122">**Створити повтор** сегмента.</span><span class="sxs-lookup"><span data-stu-id="54d7e-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="54d7e-123">Тут можна змінити його властивості одразу або просто зберегти повтор.</span><span class="sxs-lookup"><span data-stu-id="54d7e-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="54d7e-124">**Оновити** сегмент, щоб додати останні дані.</span><span class="sxs-lookup"><span data-stu-id="54d7e-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="54d7e-125">**Активувати** або **Вимкнути** сегмент.</span><span class="sxs-lookup"><span data-stu-id="54d7e-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="54d7e-126">Сегменти мають два можливі стани — активний або неактивний.</span><span class="sxs-lookup"><span data-stu-id="54d7e-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="54d7e-127">Ці стани зручно змінювати під час редагування сегмента.</span><span class="sxs-lookup"><span data-stu-id="54d7e-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="54d7e-128">Для неактивних сегментів для визначення сегмента існує, але ще не містить жодного клієнта.</span><span class="sxs-lookup"><span data-stu-id="54d7e-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="54d7e-129">Під час активації сегмента його стан змінюється з «неактивний» на «активний», і він починає шукати клієнтів, які відповідають визначенню сегмента.</span><span class="sxs-lookup"><span data-stu-id="54d7e-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="54d7e-130">Якщо [заплановане оновлення](system.md#schedule-tab) настроєно, неактивні сегменти мають **Статус**, зазначений у списку **Пропущено**, що свідчить про те, що оновлення ще не було виконано.</span><span class="sxs-lookup"><span data-stu-id="54d7e-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="54d7e-131">Під час активації неактивного сегмента він оновиться, і його буде додано до запланованого оновлення.</span><span class="sxs-lookup"><span data-stu-id="54d7e-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="54d7e-132">Крім того, можна використовувати функцію **Запланувати пізніше** з розкривного списку **Активувати / Деактивувати**, щоб задати дату та час у майбутньому для активації та деактивації певного сегмента.</span><span class="sxs-lookup"><span data-stu-id="54d7e-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="54d7e-133">**Перейменувати** сегмент.</span><span class="sxs-lookup"><span data-stu-id="54d7e-133">**Rename** the segment.</span></span>
- <span data-ttu-id="54d7e-134">**Завантажити** список учасників у вигляді CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="54d7e-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="54d7e-135">**Керування експортами** для перегляду експортів, пов’язаних із сегментами, та керування ними.</span><span class="sxs-lookup"><span data-stu-id="54d7e-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="54d7e-136">Докладніше про експорти.</span><span class="sxs-lookup"><span data-stu-id="54d7e-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="54d7e-137">**Видалити** сегмент.</span><span class="sxs-lookup"><span data-stu-id="54d7e-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="54d7e-138">Оновлення сегментів</span><span class="sxs-lookup"><span data-stu-id="54d7e-138">Refresh segments</span></span>

<span data-ttu-id="54d7e-139">Можна оновити всі сегменти одночасно, вибравши **Оновити все** на сторінці **Сегменти**, або оновити один або кілька сегментів, якщо вибрати їх, а потім вибрати **Оновити** в параметрах.</span><span class="sxs-lookup"><span data-stu-id="54d7e-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="54d7e-140">Крім того, можна настроїти повторюване оновлення в розділі **Адміністратор** > **Система** > **Розклад**.</span><span class="sxs-lookup"><span data-stu-id="54d7e-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="54d7e-141">Існує [шість типів станів](system.md#status-types) для завдань/процесів.</span><span class="sxs-lookup"><span data-stu-id="54d7e-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="54d7e-142">Крім того, більшість процесів [залежать від інших низхідних процесів](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="54d7e-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="54d7e-143">Можна вибрати стан процесу, щоб переглянути докладні відомості про перебіг виконання всієї роботи.</span><span class="sxs-lookup"><span data-stu-id="54d7e-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="54d7e-144">Після вибору **Переглянути відомості** для однієї з робіт завдання ви побачите додаткові відомості: час обробки, дата останньої обробки, а також усі помилки та попередження, пов'язані з завданням.</span><span class="sxs-lookup"><span data-stu-id="54d7e-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="54d7e-145">Експорт сегментів</span><span class="sxs-lookup"><span data-stu-id="54d7e-145">Export segments</span></span>

<span data-ttu-id="54d7e-146">Сегмент можна експортувати зі сторінки сегментів або зі [сторінки експортів](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="54d7e-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="54d7e-147">Перейдіть на сторінку **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="54d7e-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="54d7e-148">Виберіть **Показати ще [...]** для сегмента, який потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="54d7e-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="54d7e-149">Виберіть **Керування експортами** у розкривному списку дій.</span><span class="sxs-lookup"><span data-stu-id="54d7e-149">Select **Manage exports** from the actions drop-down list.</span></span>

1. <span data-ttu-id="54d7e-150">Відкриється сторінка **Експорти (підготовча версія) для сегмента**.</span><span class="sxs-lookup"><span data-stu-id="54d7e-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="54d7e-151">Ви побачите усі налаштовані експорти, згруповані за експортами, що містять поточний сегмент або не містять його.</span><span class="sxs-lookup"><span data-stu-id="54d7e-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="54d7e-152">Щоб додати вибраний сегмент до експорту, виберіть експорт у списку, а тоді виберіть **Додати сегмент**.</span><span class="sxs-lookup"><span data-stu-id="54d7e-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="54d7e-153">Щоб створити новий експорт із вибраним сегментом, виберіть **Додати експорт**.</span><span class="sxs-lookup"><span data-stu-id="54d7e-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="54d7e-154">Для отримання додаткових відомостей про створення експортів див. [Налаштування нового експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="54d7e-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="54d7e-155">Виберіть **Назад**, щоб повернутися на основну сторінку сегментів.</span><span class="sxs-lookup"><span data-stu-id="54d7e-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="54d7e-156">Перегляд журналу обробки та учасників сегмента</span><span class="sxs-lookup"><span data-stu-id="54d7e-156">View processing history and segment members</span></span>

<span data-ttu-id="54d7e-157">Ви можете побачити консолідовані дані про сегмент, переглянувши докладні відомості про нього.</span><span class="sxs-lookup"><span data-stu-id="54d7e-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="54d7e-158">На сторінці **Сегменти** виберіть сегмент, який потрібно переглянути.</span><span class="sxs-lookup"><span data-stu-id="54d7e-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="54d7e-159">У верхній частині сторінки міститься графік тенденції, який візуалізує зміни в кількості учасників.</span><span class="sxs-lookup"><span data-stu-id="54d7e-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="54d7e-160">Наводьте курсор на точки даних, щоб бачити кількість учасників на певну дату.</span><span class="sxs-lookup"><span data-stu-id="54d7e-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="54d7e-161">Ви можете оновити часові рамки графічного відображення.</span><span class="sxs-lookup"><span data-stu-id="54d7e-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="54d7e-162">![Часові рамки сегмента](media/segment-time-range.png "Часові рамки сегмента")</span><span class="sxs-lookup"><span data-stu-id="54d7e-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="54d7e-163">Нижня частина містить список учасників сегмента.</span><span class="sxs-lookup"><span data-stu-id="54d7e-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="54d7e-164">Поля, що відображаються в цьому списку, базуються на атрибутах сутностей вашого сегмента.</span><span class="sxs-lookup"><span data-stu-id="54d7e-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="54d7e-165">Список — це попередній перегляд відповідних учасників сегмента. Він показує перші 100 записів вашого сегмента. Це дає змогу швидко оцінити його та за потреби переглянути його визначення.</span><span class="sxs-lookup"><span data-stu-id="54d7e-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="54d7e-166">Щоб переглянути всі відповідні записи, потрібно [експортувати цей сегмент](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="54d7e-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
