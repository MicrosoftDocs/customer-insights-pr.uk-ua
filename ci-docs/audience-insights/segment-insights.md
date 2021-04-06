---
title: Аналітичні огляди сегментів для наявних сегментів
description: Отримуйте аналітичні висновки щодо наявних сегментів, щоб побачити відмінності та схожість.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 90ebcaab896c628b04e751ad9857e924749895e7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595359"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="7aa8f-103">Аналітичні висновки для сегментів (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="7aa8f-103">Segment insights (preview)</span></span>

<span data-ttu-id="7aa8f-104">Отримайте додаткові відомості та аналітичні висновки, що стосуються ваших наявних сегментів.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="7aa8f-105">З'ясуйте, що відрізняє один сегмент від іншого, і що між ними спільного.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="7aa8f-106">Перекриття сегментів</span><span class="sxs-lookup"><span data-stu-id="7aa8f-106">Segment overlap</span></span>

<span data-ttu-id="7aa8f-107">Аналіз перекриття сегментів показує, які клієнти належать одразу до двох або більше сегментів, а також підраховує кількість таких клієнтів.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="7aa8f-108">Наприклад, наскільки сегмент постійних клієнтів співпадає з сегментом, що містить клієнтів, які задоволені вашими послугами або продукцією.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="7aa8f-109">Крім того, можна проаналізувати, як змінюється перекриття залежно від різних атрибутів.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="7aa8f-110">Виконання аналізу перекриття</span><span class="sxs-lookup"><span data-stu-id="7aa8f-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="7aa8f-111">Відкрийте **Сегменти** та виберіть вкладку **Аналітичні висновки (підготовча версія)**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="7aa8f-112">Виберіть **Створити** та виберіть пункт **Перекриття** в області **Виберіть тип аналітичного висновку**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="7aa8f-113">Виберіть сегменти, що вас цікавлять, а тоді виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="7aa8f-114">Крім того, виберіть одне або кілька полів, що вас цікавлять, щоб проаналізувати перекриття для усіх можливих значень цих полів, а тоді виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="7aa8f-115">Укажіть ім'я для цього аналізу перекриття, необов'язкове коротке ім’я та опис.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="7aa8f-116">Виберіть **Зберегти**, щоб розпочати аналіз.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="7aa8f-117">Аналіз перекриття буде готовий, коли стан зміниться з «Оновлюється» на «Успішно».</span><span class="sxs-lookup"><span data-stu-id="7aa8f-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="7aa8f-118">Перегляд і оптимізація аналізу перекриття</span><span class="sxs-lookup"><span data-stu-id="7aa8f-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="7aa8f-119">Після завершення аналізу знайдіть подробиці аналітичного висновку у розділі **Сегменти** > **Аналітичні висновки (підготовча версія)**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Подробиці аналітичного висновку щодо перекриття сегментів":::

<span data-ttu-id="7aa8f-121">Виберіть аналітичний висновок, щоб переглянути результати аналізу.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="7aa8f-122">Кількість учасників, що належать до сегментів, які брали участь в аналізі.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="7aa8f-123">Кількість учасників, включених до одного з сегментів, але відсутні в інших сегментах.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="7aa8f-124">Якщо під час налаштування аналізу перекриття було вибрано поля, ви можете знайти їх на відповідних вкладках.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="7aa8f-125">У розкривному списку фільтра можна вибрати будь-який рівень зацікавленості для атрибуту, і у таблиці в нижній частині відобразяться відповідні дані.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="7aa8f-126">Вирізняльні властивості сегмента</span><span class="sxs-lookup"><span data-stu-id="7aa8f-126">Segment differentiators</span></span>

<span data-ttu-id="7aa8f-127">Відмінності в сегментах дозволяють дізнатися, що відрізняє сегмент від інших користувачів або від іншого сегмента.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="7aa8f-128">Потрібно лише вибрати сегмент, а система визначить атрибути профілю та показники, які відрізняють вибраний сегмент.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="7aa8f-129">Виконання аналізу відмінностей</span><span class="sxs-lookup"><span data-stu-id="7aa8f-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="7aa8f-130">Відкрийте **Сегменти** та виберіть вкладку **Аналітичні висновки (підготовча версія)**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="7aa8f-131">Виберіть **Створити** та виберіть пункт **Перекриття** в області **Виберіть тип аналітичного висновку**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="7aa8f-132">Виберіть сегмент, який необхідно проаналізувати в якості **Первинного сегмента**, потім виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="7aa8f-133">Виберіть **Усі клієнти** або **Вторинний сегмент** для порівняння із первинним сегментом, й виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="7aa8f-134">Додатково ви можете вибрати одне або кілька полів, що вас цікавлять, щоб зосередити аналіз на певних атрибутах; після цього виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="7aa8f-135">Укажіть ім'я для цього аналізу перекриття, необов'язкове коротке ім’я та опис.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="7aa8f-136">Виберіть **Зберегти**, щоб розпочати аналіз.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="7aa8f-137">Аналіз перекриття буде готовий, коли стан зміниться з «Оновлюється» на «Успішно».</span><span class="sxs-lookup"><span data-stu-id="7aa8f-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="7aa8f-138">Перегляд і оптимізація аналізу відмінностей</span><span class="sxs-lookup"><span data-stu-id="7aa8f-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="7aa8f-139">Після завершення аналізу знайдіть подробиці аналітичного висновку у розділі **Сегменти** > **Аналітичні висновки (підготовча версія)**.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Подробиці аналітичного висновку щодо відмінностей сегментів":::

<span data-ttu-id="7aa8f-141">Виберіть аналітичний висновок, щоб переглянути результати аналізу.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="7aa8f-142">Аналіз відмінностей містить дві вкладки.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="7aa8f-143">На вкладці **Атрибути** перелічено атрибути профілю, що їх визначено як відмінності.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="7aa8f-144">На вкладці **Показники** перелічено відмінності.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="7aa8f-145">Кожна вкладка містить зазначені нижче відомості.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="7aa8f-146">Ранговий список відмінностей, відсортованих за оцінкою відмінності.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="7aa8f-147">**Оцінка відмінності** для кожної відмінності.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="7aa8f-148">Оцінка відмінності представляє ступінь відмінності для атрибута у двох сегментах.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="7aa8f-149">Чим вища оцінка відмінності, тим сильніше атрибути відрізняються у двох сегментах.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="7aa8f-150">Виберіть оцінку, щоб відкрити область **Оцінка відмінності**, де наведено розподіл значень для певного атрибуту.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="7aa8f-151">Керування аналітичними висновками щодо сегментів</span><span class="sxs-lookup"><span data-stu-id="7aa8f-151">Manage segment insights</span></span>

<span data-ttu-id="7aa8f-152">За допомогою панелі команд можна виконувати наведені нижче дії стосовно аналітичних висновків.</span><span class="sxs-lookup"><span data-stu-id="7aa8f-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="7aa8f-153">**Назад**, щоб повернутися до списку аналітичних висновків</span><span class="sxs-lookup"><span data-stu-id="7aa8f-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="7aa8f-154">**Оновити**, щоб знову виконати аналіз</span><span class="sxs-lookup"><span data-stu-id="7aa8f-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="7aa8f-155">**Видалити**, щоб видалити цей аналітичний висновок</span><span class="sxs-lookup"><span data-stu-id="7aa8f-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]