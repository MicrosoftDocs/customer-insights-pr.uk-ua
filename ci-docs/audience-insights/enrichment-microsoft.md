---
title: Збагачуйте профілі клієнтів за рахунок даних Майкрософт
description: Використовуйте фірмові дані Майкрософт для збагачення даних клієнтів за рахунок їхнього доповнення брендами та уподобаннями в області інтересів.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245732"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="13743-103">Збагачення профілів клієнтів близькими брендами й інтересами (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="13743-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="13743-104">Використовуйте фірмові дані Майкрософт для збагачення даних клієнтів за рахунок їхнього доповнення брендами та уподобаннями в області інтересів.</span><span class="sxs-lookup"><span data-stu-id="13743-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="13743-105">Ця близькість визначається на основі даних людей із такими самими демографічними особливостями, як у ваших клієнтів.</span><span class="sxs-lookup"><span data-stu-id="13743-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="13743-106">Ця інформація допомагає вам краще зрозуміти й сегментувати своїх клієнтів на основі їхньої близькості до конкретних брендів та інтересів.</span><span class="sxs-lookup"><span data-stu-id="13743-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="13743-107">У аналізі аудиторії виберіть **Дані** > **Збагачення**, щоб [налаштувати та переглянути збагачення](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="13743-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="13743-108">Щоб налаштувати збагачення на основі прихильності до брендів, перейдіть на вкладку **Виявлення** і виберіть **Збагатити мої дані** на плитці **Бренди**.</span><span class="sxs-lookup"><span data-stu-id="13743-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="13743-109">Щоб налаштувати збагачення на основі близьких інтересів, перейдіть на вкладку **Виявлення** і виберіть **Збагатити мої дані** на плитці **Інтереси**.</span><span class="sxs-lookup"><span data-stu-id="13743-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="13743-110">![Плитка брендів та інтересів](media/BrandsInterest-tile-Hub.png "Плитка брендів та інтересів")</span><span class="sxs-lookup"><span data-stu-id="13743-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="13743-111">Як ми визначаємо уподобання</span><span class="sxs-lookup"><span data-stu-id="13743-111">How we determine affinities</span></span>

<span data-ttu-id="13743-112">Ми користуємося даними онлайнового пошуку Майкрософт, щоб знайти уподобання щодо брендів та інтересів у різних демографічних сегментах (що визначаються віком, статтю або розташуванням).</span><span class="sxs-lookup"><span data-stu-id="13743-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="13743-113">Обсяг онлайн-пошуку бренду або інтересу визначає, наскільки близький демографічний сегмент, порівняно з іншими сегментами, до певного бренду або інтересу.</span><span class="sxs-lookup"><span data-stu-id="13743-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="13743-114">Рівень та оцінка відповідності</span><span class="sxs-lookup"><span data-stu-id="13743-114">Affinity level and score</span></span>

<span data-ttu-id="13743-115">У кожному збагаченому профілі клієнта вказано два пов'язані значення — рівень відповідності та оцінка відповідності.</span><span class="sxs-lookup"><span data-stu-id="13743-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="13743-116">Ці значення допомагають визначити ступінь відповідності для демографічного сегмента профілю для бренда або інтересу порівняно із іншими демографічними сегментами.</span><span class="sxs-lookup"><span data-stu-id="13743-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="13743-117">*Рівень відповідності* оцінюється чотирма рівнями, а *оцінка відповідності* розраховується за 100-бальною шкалою, що зіставляється із рівнями відповідності.</span><span class="sxs-lookup"><span data-stu-id="13743-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="13743-118">Рівень відповідності</span><span class="sxs-lookup"><span data-stu-id="13743-118">Affinity level</span></span> |<span data-ttu-id="13743-119">Оцінка відповідності</span><span class="sxs-lookup"><span data-stu-id="13743-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="13743-120">Дуже багато</span><span class="sxs-lookup"><span data-stu-id="13743-120">Very high</span></span>     | <span data-ttu-id="13743-121">85—100</span><span class="sxs-lookup"><span data-stu-id="13743-121">85-100</span></span>       |
|<span data-ttu-id="13743-122">Високе</span><span class="sxs-lookup"><span data-stu-id="13743-122">High</span></span>     | <span data-ttu-id="13743-123">70—84</span><span class="sxs-lookup"><span data-stu-id="13743-123">70-84</span></span>        |
|<span data-ttu-id="13743-124">Середній</span><span class="sxs-lookup"><span data-stu-id="13743-124">Medium</span></span>     | <span data-ttu-id="13743-125">35—69</span><span class="sxs-lookup"><span data-stu-id="13743-125">35-69</span></span>        |
|<span data-ttu-id="13743-126">Низьке</span><span class="sxs-lookup"><span data-stu-id="13743-126">Low</span></span>     | <span data-ttu-id="13743-127">1—34</span><span class="sxs-lookup"><span data-stu-id="13743-127">1-34</span></span>        |

<span data-ttu-id="13743-128">Залежно від потрібного вам рівня деталізації при вимірюванні відповідності ви можете використовувати рівень або оцінку відповідності.</span><span class="sxs-lookup"><span data-stu-id="13743-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="13743-129">Оцінка відповідності забезпечує вищу точність при роботі.</span><span class="sxs-lookup"><span data-stu-id="13743-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="13743-130">Країни або регіони, що підтримуються</span><span class="sxs-lookup"><span data-stu-id="13743-130">Supported countries/regions</span></span>

<span data-ttu-id="13743-131">Станом на сьогодні, ми підтримуємо такі варіанти країн або регіонів: Австралія, Канада (англійська), Франція, Німеччина, Сполучене Королівство або Сполучені Штати Америки (англійська).</span><span class="sxs-lookup"><span data-stu-id="13743-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="13743-132">Щоб вибрати країну, відкрийте **Збагачення брендів** або **Збагачення інтересів** та виберіть **Змінити** поруч із **Країна або регіон**.</span><span class="sxs-lookup"><span data-stu-id="13743-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="13743-133">У області **Налаштування країни або регіону** виберіть доступний варіант та виберіть **Застосувати**.</span><span class="sxs-lookup"><span data-stu-id="13743-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="13743-134">Наслідки, пов’язані із вибором країни/регіону</span><span class="sxs-lookup"><span data-stu-id="13743-134">Implications related to country selection</span></span>

- <span data-ttu-id="13743-135">При [виборі власних брендів](#define-your-brands-or-interests) система надаватиме пропозиції залежно від вибраної країни або регіону.</span><span class="sxs-lookup"><span data-stu-id="13743-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="13743-136">[Вибираючи галузь](#define-your-brands-or-interests), ви побачите найбільш відповідні бренди та інтереси для вибраної країни або регіону.</span><span class="sxs-lookup"><span data-stu-id="13743-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="13743-137">При [збагаченні профілів](#refresh-enrichment) збагачуватимуться профілі усіх клієнтів, для яких ми отримаємо дані щодо вибраних брендів та інтересів.</span><span class="sxs-lookup"><span data-stu-id="13743-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="13743-138">Включно з профілями, які не належать до вибраної країни або регіону.</span><span class="sxs-lookup"><span data-stu-id="13743-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="13743-139">Наприклад, якщо ви вибрали Німеччину, ми виконаємо збагачення профілів, розташованих у Сполучених Штатах, якщо матимемо доступні дані для вибраних брендів та інтересів у США.</span><span class="sxs-lookup"><span data-stu-id="13743-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="13743-140">Налаштування збагачення</span><span class="sxs-lookup"><span data-stu-id="13743-140">Configure Enrichment</span></span>

<span data-ttu-id="13743-141">Екскурсія під керівництвом екскурсовода допоможе пройти етапи налаштування збагачень.</span><span class="sxs-lookup"><span data-stu-id="13743-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="13743-142">Визначте свої бренди або інтереси</span><span class="sxs-lookup"><span data-stu-id="13743-142">Define your brands or interests</span></span>

<span data-ttu-id="13743-143">Виберіть до п'яти брендів або інтересів, використовуючи один або обидва з перелічених нижче варіантів.</span><span class="sxs-lookup"><span data-stu-id="13743-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="13743-144">**Галузь**: виберіть у розкривному списку свою галузь, а потім оберіть деякі із найважливіших брендів або інтересів для цієї галузі.</span><span class="sxs-lookup"><span data-stu-id="13743-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="13743-145">**Виберіть власний**: введіть бренд або інтерес, важливий для вашої організації, а потім оберіть пропозицію з-поміж тих, що відповідають умові.</span><span class="sxs-lookup"><span data-stu-id="13743-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="13743-146">Якщо в списку немає потрібного бренду або інтересу, надішліть нам відгук за допомогою посилання **Запропонувати**.</span><span class="sxs-lookup"><span data-stu-id="13743-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="13743-147">Перегляд параметрів збагачення</span><span class="sxs-lookup"><span data-stu-id="13743-147">Review enrichment preferences</span></span>

<span data-ttu-id="13743-148">Перегляньте параметри збагачень за замовчуванням і за потреби оновіть їх.</span><span class="sxs-lookup"><span data-stu-id="13743-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Знімок екрана із вікном параметрів збагачень.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="13743-150">Виберіть сутність для збагачення</span><span class="sxs-lookup"><span data-stu-id="13743-150">Select entity to enrich</span></span>

<span data-ttu-id="13743-151">Виберіть **Збагачену сутність**, потім виберіть набір даних, який ви бажаєте збагатити за рахунок корпоративних даних Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="13743-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="13743-152">Можна вибрати сутність «Клієнт», щоб збагатити всі профілі клієнтів, або вибрати сутність сегмента для збагачення лише профілів клієнтів, що містяться в цьому сегменті.</span><span class="sxs-lookup"><span data-stu-id="13743-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="13743-153">Зіставлення полів</span><span class="sxs-lookup"><span data-stu-id="13743-153">Map your fields</span></span>

<span data-ttu-id="13743-154">Зіставте поля з уніфікованої сутності клієнта, щоб визначити демографічний сегмент, який система має використовувати для збагачення даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="13743-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="13743-155">Зіставте країну або регіон і, принаймні, атрибути дати народження або статі.</span><span class="sxs-lookup"><span data-stu-id="13743-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="13743-156">Крім того, слід зіставити принаймні місто (і область/республіку) або поштовий індекс.</span><span class="sxs-lookup"><span data-stu-id="13743-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="13743-157">Виберіть елемент **Редагувати**, щоб зіставити поля. Коли завершите, натисніть копку **Застосувати**.</span><span class="sxs-lookup"><span data-stu-id="13743-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="13743-158">Натисніть кнопку **Зберегти**, щоб завершити зіставлення полів.</span><span class="sxs-lookup"><span data-stu-id="13743-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="13743-159">Підтримуються зазначені нижче значення та формати, регістр букв не має значення.</span><span class="sxs-lookup"><span data-stu-id="13743-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="13743-160">**Дата народження**: рекомендуємо під час приймання даних перетворити дату народження у тип Дата й час.</span><span class="sxs-lookup"><span data-stu-id="13743-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="13743-161">Або це може бути рядок у форматі «yyyy-MM-dd» або «yyyy-MM-ddTHH:mm:ssZ» згідно до [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).</span><span class="sxs-lookup"><span data-stu-id="13743-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="13743-162">**Стать**: чоловік, жінка, невідомо</span><span class="sxs-lookup"><span data-stu-id="13743-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="13743-163">**Поштовий індекс**: поштові індекси з п’яти цифр для Сполучених Штатів, стандартні поштові індекси для інших розташувань</span><span class="sxs-lookup"><span data-stu-id="13743-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="13743-164">**Місто**: назва міста англійською</span><span class="sxs-lookup"><span data-stu-id="13743-164">**City**: City name in English</span></span>
- <span data-ttu-id="13743-165">**Область/Республіка**: скорочення із двох літер для США та Канади.</span><span class="sxs-lookup"><span data-stu-id="13743-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="13743-166">Скорочення з двох або трьох літер для Австралії.</span><span class="sxs-lookup"><span data-stu-id="13743-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="13743-167">Не застосовується для Франції, Німеччини та Сполученого Королівства.</span><span class="sxs-lookup"><span data-stu-id="13743-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="13743-168">**Країна або регіон**:</span><span class="sxs-lookup"><span data-stu-id="13743-168">**Country/Region**:</span></span>

  - <span data-ttu-id="13743-169">US: Сполучені Штати Америки, Сполучені Штати, США, US, Америка</span><span class="sxs-lookup"><span data-stu-id="13743-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="13743-170">CA: Канада, CA</span><span class="sxs-lookup"><span data-stu-id="13743-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="13743-171">GB: Сполучене Королівство, UK, Велика Британія, GB, Сполучене Королівство Великої Британії та Північної Ірландії, Сполучене Королівство Великої Британії</span><span class="sxs-lookup"><span data-stu-id="13743-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="13743-172">AU: Австралія, AU, Австралійський Союз</span><span class="sxs-lookup"><span data-stu-id="13743-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="13743-173">FR: Франція, FR, Французька Республіка</span><span class="sxs-lookup"><span data-stu-id="13743-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="13743-174">DE: Німеччина, German, Deutschland, Allemagne, DE, Федеративна Республіка Німеччина, Республіка Німеччина</span><span class="sxs-lookup"><span data-stu-id="13743-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="13743-175">Перегляньте це збагачення та надайте йому ім’я</span><span class="sxs-lookup"><span data-stu-id="13743-175">Review and name the enrichment</span></span>

<span data-ttu-id="13743-176">Нарешті ви маєте переглянути інформацію та вказати ім'я для збагачення.</span><span class="sxs-lookup"><span data-stu-id="13743-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Сторінка перегляду й іменування інтересів.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="13743-178">Оновлення збагачень</span><span class="sxs-lookup"><span data-stu-id="13743-178">Refresh enrichment</span></span>

<span data-ttu-id="13743-179">Виконайте збагачення після настроювання брендів, інтересів і зіставлення полів для демографічних показників.</span><span class="sxs-lookup"><span data-stu-id="13743-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="13743-180">Щоб почати процес, виберіть **Виконати** на сторінці налаштування брендів та інтересів.</span><span class="sxs-lookup"><span data-stu-id="13743-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="13743-181">Додатково ви можете дозволити системі автоматично проводити збагачення в межах запланованого оновлення.</span><span class="sxs-lookup"><span data-stu-id="13743-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="13743-182">Завершення процесу збагачення може тривати кілька хвилин, залежно від розміру даних клієнта.</span><span class="sxs-lookup"><span data-stu-id="13743-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="13743-183">Існує [шість типів станів](system.md#status-types) для завдань/процесів.</span><span class="sxs-lookup"><span data-stu-id="13743-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="13743-184">Крім того, більшість процесів [залежать від інших низхідних процесів](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="13743-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="13743-185">Можна вибрати стан процесу, щоб переглянути докладні відомості про перебіг виконання всієї роботи.</span><span class="sxs-lookup"><span data-stu-id="13743-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="13743-186">Після вибору **Переглянути відомості** для однієї з робіт завдання ви побачите додаткові відомості: час обробки, дата останньої обробки, а також усі помилки та попередження, пов'язані з завданням.</span><span class="sxs-lookup"><span data-stu-id="13743-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="13743-187">Результати збагачення</span><span class="sxs-lookup"><span data-stu-id="13743-187">Enrichment results</span></span>

<span data-ttu-id="13743-188">Після запуску процесу збагачення перейдіть на сторінку **Мої збагачення**, щоб переглянути загальну кількість збагачених клієнтів і структуру брендів або інтересів у збагачених профілях клієнтів.</span><span class="sxs-lookup"><span data-stu-id="13743-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Зразок результатів для попереднього перегляду після збагачення":::

<span data-ttu-id="13743-190">Перегляньте збагачені дані, вибравши **Переглянути збагачені дані** на діаграмі.</span><span class="sxs-lookup"><span data-stu-id="13743-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="13743-191">Збагачені дані для брендів містяться в сутності **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="13743-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="13743-192">Дані для інтересів – у сутності **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="13743-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="13743-193">Ви також знайдете ці сутності в списку групи **Збагачення**, розташованої тут: **Дані** > **Сутності**.</span><span class="sxs-lookup"><span data-stu-id="13743-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="13743-194">Перегляд даних збагачення на картці клієнта</span><span class="sxs-lookup"><span data-stu-id="13743-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="13743-195">Інформацію про близькість до брендів та інтересів також можна переглядати на окремих картках клієнтів.</span><span class="sxs-lookup"><span data-stu-id="13743-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="13743-196">Перейдіть до розділу **Клієнти** та виберіть профіль клієнта.</span><span class="sxs-lookup"><span data-stu-id="13743-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="13743-197">У картці клієнта ви знайдете діаграми брендів або інтересів, які є близькими клієнтові згідно до його демографічного профілю.</span><span class="sxs-lookup"><span data-stu-id="13743-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Картка клієнта зі збагаченими даними":::

## <a name="next-steps"></a><span data-ttu-id="13743-199">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="13743-199">Next steps</span></span>

<span data-ttu-id="13743-200">Створюйте на основі збагачених даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="13743-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="13743-201">Створіть [сегменти](segments.md), [міри](measures.md) та навіть [експортуйте дані](export-destinations.md), щоб надати клієнтам персоналізовані можливості.</span><span class="sxs-lookup"><span data-stu-id="13743-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
