---
title: Знайдіть схожих клієнтів, використовуючи штучний інтелект
description: Знайдіть схожі сегменти клієнтів, використовуючи штучний інтелект.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596800"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="bdc1b-103">Схожі клієнти (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="bdc1b-103">Similar Customers (preview)</span></span>

<span data-ttu-id="bdc1b-104">Ця функція дозволяє знаходити схожих клієнтів в базі клієнтів, використовуючи штучний інтелект.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="bdc1b-105">Щоб скористатися цією функцією, потрібно мати принаймні один сегмент.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="bdc1b-106">Встановлюючи більш загальні умови для наявного сегмента, ви зможете знайти клієнтів, які схожі на цей сегмент.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="bdc1b-107">*Пошук схожих клієнтів* використовує автоматизовані засоби для оцінки даних і прогнозування на основі цих даних, і, отже, має потенціал для використання в якості методу профілювання, у сенсі, якому цей термін визначається Генеральним регламентом із захисту персональних даних («GDPR»).</span><span class="sxs-lookup"><span data-stu-id="bdc1b-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="bdc1b-108">Використання клієнтом цієї функції для оброблення даних може регулюватися положеннями GDPR або інших законів чи постанов.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="bdc1b-109">Ви несете відповідальність за те, що використання Dynamics 365 Customer Insights, включаючи прогнози, відповідає всім чинним законам і нормативним актам, зокрема законам, пов'язаним з конфіденційністю, персональними даними, біометричними даними, захистом даних і конфіденційністю комунікацій.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="bdc1b-110">Пошук схожих клієнтів</span><span class="sxs-lookup"><span data-stu-id="bdc1b-110">Finding similar customers</span></span>

1. <span data-ttu-id="bdc1b-111">У розділі «аналіз аудиторії» відкрийте пункт **Сегменти** й виберіть сегмент, на основі якого потрібно створити новий сегмент.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="bdc1b-112">Це буде ваш *вихідний сегмент*.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="bdc1b-113">На панелі інструментів «Дії» виберіть **Пошук схожих клієнтів**.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="bdc1b-114">Перегляньте запропоноване ім'я для нового сегмента і змініть його в разі потреби.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="bdc1b-115">Перегляньте поля, які визначатимуть ваш новий сегмент.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="bdc1b-116">Ці поля визначають основу, ґрунтуючись на якій система спробує знайти клієнтів, подібних до учасників вихідного сегмента.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="bdc1b-117">Система за замовчуванням відбере рекомендовані поля.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="bdc1b-118">Зазначені нижче поля, які можуть суттєво зменшити продуктивність моделі, буде автоматично виключено.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="bdc1b-119">Поля з такими типами даних: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="bdc1b-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="bdc1b-120">Поля із кратністю (кількістю елементів у полі), що є меншою 2 або більшою 30</span><span class="sxs-lookup"><span data-stu-id="bdc1b-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="bdc1b-121">Виберіть, чи потрібно внести до нового сегмента **Усіх клієнтів**, або лише тих клієнтів, що належать до **Певного наявного сегмента**.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="bdc1b-122">Виключіть учасників вихідного сегмента, вибравши прапорець **Виключити усіх учасників вихідного сегмента**.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="bdc1b-123">За замовчуванням система пропонує обмежити вивід до 20% від розміру цільової аудиторій.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="bdc1b-124">За потреби змініть це граничне значення.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-124">Edit this threshold as needed.</span></span> <span data-ttu-id="bdc1b-125">Збільшення цього граничного значення призведе до зниження точності.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="bdc1b-126">Виберіть **Виконати** в нижній частині сторінки, щоб почати завдання двійкової класифікації (методика машинного навчання), яке проаналізує набір даних.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="bdc1b-127">Перегляд подібного сегмента</span><span class="sxs-lookup"><span data-stu-id="bdc1b-127">View the similar segment</span></span>

<span data-ttu-id="bdc1b-128">Після опрацювання подібного сегмента ви побачите новий сегмент на сторінці **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bdc1b-129">![Сегмент зі схожими клієнтами](media/expanded-segment.png "Сегмент зі схожими клієнтами")</span><span class="sxs-lookup"><span data-stu-id="bdc1b-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="bdc1b-130">Виберіть **Перегляд** на панелі інструментів «Дія», щоб відкрити відомості про сегмент.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="bdc1b-131">У цьому поданні містяться відомості про розподіл результатів за різними [оцінками подібності](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="bdc1b-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="bdc1b-132">Значення оцінки подібності також можна знайти в **попередньому перегляді учасників сегмента**.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="bdc1b-133">Використання результатів процедури створення подібного сегмента</span><span class="sxs-lookup"><span data-stu-id="bdc1b-133">Use the output of a similar segment</span></span>

<span data-ttu-id="bdc1b-134">Ви можете [працювати з результатами процедури створення подібного сегмента](segments.md) так само, як із іншими сегментами.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="bdc1b-135">Наприклад, експортуйте сегмент або створіть показник.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="bdc1b-136">Оновлення та редагування подібного сегмента</span><span class="sxs-lookup"><span data-stu-id="bdc1b-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="bdc1b-137">Щоб оновити подібний сегмент, виберіть його на сторінці **Сегменти** та виберіть **Оновити** на панелі інструментів «Дії».</span><span class="sxs-lookup"><span data-stu-id="bdc1b-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="bdc1b-138">При редагуванні подібного сегмента дані будуть опрацьовані повторно.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="bdc1b-139">Раніше створений сегмент буде доповнено новими даними.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="bdc1b-140">Щоб відредагувати подібний сегмент, виберіть його на сторінці **Сегменти** та виберіть **Редагувати** на панелі інструментів «Дії».</span><span class="sxs-lookup"><span data-stu-id="bdc1b-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="bdc1b-141">Застосуйте зміни та виберіть **Виконати**, щоб почати обробку.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="bdc1b-142">Видалення подібного сегмента</span><span class="sxs-lookup"><span data-stu-id="bdc1b-142">Delete a similar segment</span></span>

<span data-ttu-id="bdc1b-143">Виберіть сегмент на сторінці **Сегменти** та виберіть **Видалити** на панелі інструментів «Дії».</span><span class="sxs-lookup"><span data-stu-id="bdc1b-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="bdc1b-144">Тоді підтвердьте видалення.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="bdc1b-145">Відомості щодо оцінок подібності</span><span class="sxs-lookup"><span data-stu-id="bdc1b-145">About similarity scores</span></span>

<span data-ttu-id="bdc1b-146">Модель машинного навчання із застосуванням двійкової класифікації призначає клієнтам у подібному сегменті оцінки.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="bdc1b-147">Оцінка залежить від схожості на клієнтів з вихідного сегмента.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="bdc1b-148">Оцінки подібності нижче 0,55 виставляються клієнтам, які класифікуються системою як *не схожі* на клієнтів у вихідному сегменті</span><span class="sxs-lookup"><span data-stu-id="bdc1b-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="bdc1b-149">Оцінки подібності від 0,55 до 0,7 класифікуються як *дещо схожі*</span><span class="sxs-lookup"><span data-stu-id="bdc1b-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="bdc1b-150">Оцінки подібності від 0,7 до 0,85 класифікуються як *схожі*</span><span class="sxs-lookup"><span data-stu-id="bdc1b-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="bdc1b-151">Оцінки подібності від 0,85 до 1 призначаються клієнтам, які класифікуються системою як *дуже схожі*</span><span class="sxs-lookup"><span data-stu-id="bdc1b-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="bdc1b-152">Клієнти із оцінками подібності, що є нижчими за 0,4, не потрапляють до результатів роботи моделі.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="bdc1b-153">Система вважає їх недостатньо схожими на вихідний сегмент.</span><span class="sxs-lookup"><span data-stu-id="bdc1b-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]