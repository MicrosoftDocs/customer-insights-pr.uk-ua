---
title: Пропозиції сегментів на основі справ.
description: Покличте на допомогу машинне навчання, щоб знаходити цікаві сегменти на основі справ клієнтів.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034125"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="b6f51-103">Пропозиції сегментів на основі даних справ (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="b6f51-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="b6f51-104">Знаходьте цікаві сегменти клієнтів залежно від даних справ клієнтів, отриманих у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b6f51-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="b6f51-105">Прикладами даних справ є транзакції, тривалість виклику підтримки, покупки або повернення.</span><span class="sxs-lookup"><span data-stu-id="b6f51-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="b6f51-106">Щоб пропонувати сегменти, дані справи аналізуються для визначення їх свіжості, частоти та грошової вартості (або тривалості).</span><span class="sxs-lookup"><span data-stu-id="b6f51-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="b6f51-107">Крім того, ви можете створювати [пропоновані сегменти, щоб покращити показник або краще зрозуміти, що впливає на певний атрибут](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="b6f51-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Вкладка пропозицій сегментів, де відображаються пропозиції сегментів на основі справ і атрибутів.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="b6f51-109">Категоризація клієнтів за справами</span><span class="sxs-lookup"><span data-stu-id="b6f51-109">Categorize customers by activity</span></span>

<span data-ttu-id="b6f51-110">За допомогою [даних справ](activities.md), доступних в Customer Insights, можна створювати пропозиції, які представляють групи клієнтів:</span><span class="sxs-lookup"><span data-stu-id="b6f51-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="b6f51-111">найактивніші клієнти</span><span class="sxs-lookup"><span data-stu-id="b6f51-111">most active customers</span></span> 
- <span data-ttu-id="b6f51-112">клієнти, які здійснили найбільше покупок</span><span class="sxs-lookup"><span data-stu-id="b6f51-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="b6f51-113">клієнти, які генерують найвищий дохід</span><span class="sxs-lookup"><span data-stu-id="b6f51-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="b6f51-114">клієнти, які не були активні останнім часом</span><span class="sxs-lookup"><span data-stu-id="b6f51-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="b6f51-115">клієнти, які часто взаємодіють із вашою компанією</span><span class="sxs-lookup"><span data-stu-id="b6f51-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="b6f51-116">Якщо ви займаєтеся роздрібною торгівлею, ви можете дізнатись, які з ваших клієнтів приносять вам найвищий дохід та нагородити їх, надавши їм купон.</span><span class="sxs-lookup"><span data-stu-id="b6f51-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="b6f51-117">Або ви можете відшукати клієнтів, що купляють рідко й запропонувати їм приєднатися до програми винагород, щоб вони частіше зверталися до вашої компанії.</span><span class="sxs-lookup"><span data-stu-id="b6f51-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="b6f51-118">Якщо ви працюєте у сфері охорони здоров’я, надаючи загальнодоступні медичні послуги, і ваша ціль — скоротити витрати для окремих пацієнтів.</span><span class="sxs-lookup"><span data-stu-id="b6f51-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="b6f51-119">Це можна зробити, якщо зменшити кількість повторюваних візитів, надаючи найкращі послуги за найменшу кількість відвідувань.</span><span class="sxs-lookup"><span data-stu-id="b6f51-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="b6f51-120">У цьому разі ваша ціль полягає в тому, щоб частота відвідувань не зростала, а повторювана вартість для пацієнтів була мінімальною.</span><span class="sxs-lookup"><span data-stu-id="b6f51-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="b6f51-121">Або ж ви можете визначити сегменти пацієнтів, які часто відвідують вас та несуть багато повторюваних витрат, та проаналізувати відповідні інциденти, щоб краще лікувати кожну окрему особу.</span><span class="sxs-lookup"><span data-stu-id="b6f51-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="b6f51-122">Обов’язкові дані</span><span class="sxs-lookup"><span data-stu-id="b6f51-122">Required data</span></span>

<span data-ttu-id="b6f51-123">Пропозиції генеруються на основі вибраних вхідних даних.</span><span class="sxs-lookup"><span data-stu-id="b6f51-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="b6f51-124">Профілі клієнтів: усі клієнти або учасники певного сегменту.</span><span class="sxs-lookup"><span data-stu-id="b6f51-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="b6f51-125">Період часу: останній місяць, останній рік або будь-які настроювані часові рамки.</span><span class="sxs-lookup"><span data-stu-id="b6f51-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="b6f51-126">Тип справи: покупки, роздрібні транзакції, онлайн-транзакції, інциденти служби підтримки клієнтів, передплати тощо.</span><span class="sxs-lookup"><span data-stu-id="b6f51-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="b6f51-127">Сутність в Customer Insights, що містить дані справ: сутність UnifiedActivity або сутність для певної справи.</span><span class="sxs-lookup"><span data-stu-id="b6f51-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="b6f51-128">Виміри, які слід додати: свіжість, частота, або грошовий вимір, залежно від потреб вашого бізнесу.</span><span class="sxs-lookup"><span data-stu-id="b6f51-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="b6f51-129">Створення сегментів з пропозицій</span><span class="sxs-lookup"><span data-stu-id="b6f51-129">Generate suggested segments</span></span>

1. <span data-ttu-id="b6f51-130">Перейдіть до розділу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="b6f51-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="b6f51-131">Виберіть вкладку **Пропозиції (підготовча версія)**.</span><span class="sxs-lookup"><span data-stu-id="b6f51-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="b6f51-132">Виберіть **Знайти нові пропозиції** та виберіть **Перегляд або прогнозування поведінки клієнта**.</span><span class="sxs-lookup"><span data-stu-id="b6f51-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="b6f51-133">Виберіть **Пуск**, щоб запустити інтерфейс із підказками.</span><span class="sxs-lookup"><span data-stu-id="b6f51-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Перший крок майстра налаштування для запропонованого сегмента на основі справи.":::

1. <span data-ttu-id="b6f51-135">Надайте необхідні вхідні дані та виберіть продовжити **Далі**.</span><span class="sxs-lookup"><span data-stu-id="b6f51-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="b6f51-136">Виберіть клієнтів: додайте всіх клієнтів або певний сегмент.</span><span class="sxs-lookup"><span data-stu-id="b6f51-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="b6f51-137">Виберіть справу: виберіть тип справи та сутності, що описують цю справу.</span><span class="sxs-lookup"><span data-stu-id="b6f51-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="b6f51-138">Уподобання: установіть періоду часу, що враховуватиметься і фактори для пропозицій, а також зіставте атрибути.</span><span class="sxs-lookup"><span data-stu-id="b6f51-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="b6f51-139">Перевірте введені дані та виберіть **Виконати**, щоб запустити модель і створити пропозиції.</span><span class="sxs-lookup"><span data-stu-id="b6f51-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="b6f51-140">Залежно від кількості профілів клієнтів і вибраних справ виконання може зайняти кілька хвилин.</span><span class="sxs-lookup"><span data-stu-id="b6f51-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="b6f51-141">Після створення пропозицій ви можете фільтрувати їх за виміром або значенням, що цікавлять вас найбільше.</span><span class="sxs-lookup"><span data-stu-id="b6f51-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="b6f51-142">Перегляд подробиць про пропозицію сегмента</span><span class="sxs-lookup"><span data-stu-id="b6f51-142">View details of a suggested segment</span></span>

<span data-ttu-id="b6f51-143">Після створення пропозицій ви знайдете їх, якщо відкриєте **Сегменти** > **Пропозиції (підготовча версія)** у розділі **Пропозиції на основі справ**.</span><span class="sxs-lookup"><span data-stu-id="b6f51-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Розгорнута бічна область, в якій відображаються докладні відомості запропонованого сегмента.":::

<span data-ttu-id="b6f51-145">Виберіть **Переглянути пропозицію** для запропонованого сегмента, щоб побачити докладні відомості про цей сегмент.</span><span class="sxs-lookup"><span data-stu-id="b6f51-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="b6f51-146">На бічній панелі наведено докладні відомості, такі як ступінь кожного з вимірів у порівнянні з цільовою групою.</span><span class="sxs-lookup"><span data-stu-id="b6f51-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="b6f51-147">Також на ній виділено кількість потенційних учасників сегмента та відповідний відсоток від загальної кількості клієнтів.</span><span class="sxs-lookup"><span data-stu-id="b6f51-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="b6f51-148">Щоб зберегти пропозицію як сегмент, виберіть **Створити сегмент**.</span><span class="sxs-lookup"><span data-stu-id="b6f51-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="b6f51-149">Збереження пропозиції у вигляді сегмента</span><span class="sxs-lookup"><span data-stu-id="b6f51-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="b6f51-150">Послідовно відкрийте **Сегменти** > **Пропозиції (підготовча версія)**.</span><span class="sxs-lookup"><span data-stu-id="b6f51-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="b6f51-151">Виберіть сегмент, який потрібно зберегти.</span><span class="sxs-lookup"><span data-stu-id="b6f51-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="b6f51-152">На бічній панелі виберіть **Створити сегмент**.</span><span class="sxs-lookup"><span data-stu-id="b6f51-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="b6f51-153">Після збереження сегмента він відобразиться у списку сегментів на вкладці **Усі сегменти**. Тепер його можна [оновити або видалити, як і будь-який інший сегмент](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b6f51-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="b6f51-154">Відомості про сегмент редагувати не можна.</span><span class="sxs-lookup"><span data-stu-id="b6f51-154">You can't edit the segment details.</span></span> <span data-ttu-id="b6f51-155">Проте можна змінювати вхідні умови для пропозицій і створювати різні пропозиції.</span><span class="sxs-lookup"><span data-stu-id="b6f51-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="b6f51-156">Оновлення або редагування набору пропозицій</span><span class="sxs-lookup"><span data-stu-id="b6f51-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="b6f51-157">Відкрийте **Сегменти** > **Пропозиції (підготовча версія)** і знайдіть сегмент у розділі **Пропозиції на основі справ**.</span><span class="sxs-lookup"><span data-stu-id="b6f51-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="b6f51-158">Виберіть **Оновити пропозиції**, щоб оновити пропозиції зі збереженням налаштованих атрибутів.</span><span class="sxs-lookup"><span data-stu-id="b6f51-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="b6f51-159">Або виберіть **Редагувати пропозиції**, щоб змінити налаштовані атрибути.</span><span class="sxs-lookup"><span data-stu-id="b6f51-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="b6f51-160">Система повторно запустить процес, створить пропозиції сегментів на основі найновіших даних і замінить поточні пропозиції.</span><span class="sxs-lookup"><span data-stu-id="b6f51-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
