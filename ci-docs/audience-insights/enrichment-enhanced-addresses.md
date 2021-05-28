---
title: Збагачення із покращенням адреси
description: Збагачуйте та нормалізуйте відомості про адресу у профілях клієнтів, використовуючи моделі Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965603"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="2b7bd-103">Збагачення профілів клієнтів вдосконаленими адресами</span><span class="sxs-lookup"><span data-stu-id="2b7bd-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="2b7bd-104">Адреси в даних можуть бути неструктуровані, неповні або неправильні.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="2b7bd-105">Використовуйте моделі Microsoft, щоб нормалізувати та збагатити адреси, привівши їх до [формату Common Data Model](/common-data-model/schema/core/applicationcommon/address) для забезпечення вищої точності та якості аналітичних висновків.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="2b7bd-106">Процедура вдосконалення адрес</span><span class="sxs-lookup"><span data-stu-id="2b7bd-106">How we enhance addresses</span></span>

<span data-ttu-id="2b7bd-107">Для вдосконалення адреси наша модель проходить два кроки.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="2b7bd-108">Спочатку вона розпізнає адресу, щоб визначити її компоненти та перевести їх у структурований формат.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="2b7bd-109">Потім ми використовуємо штучний інтелект, щоб виправити, доповнити та стандартизувати значення у адресі.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="2b7bd-110">Приклад</span><span class="sxs-lookup"><span data-stu-id="2b7bd-110">Example</span></span>

<span data-ttu-id="2b7bd-111">Відомості про адресу можуть мати не стандартний формат і містити орфографічні помилки.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="2b7bd-112">Модель може виправити ці проблеми та створити узгоджені адреси в уніфікованих профілях клієнтів.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="2b7bd-113">Обмеження</span><span class="sxs-lookup"><span data-stu-id="2b7bd-113">Limitations</span></span>

<span data-ttu-id="2b7bd-114">Удосконалені адреси працюють лише зі значеннями, які вже існують у ваших отриманих даних.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="2b7bd-115">Модель не може:</span><span class="sxs-lookup"><span data-stu-id="2b7bd-115">The model doesn't:</span></span> 

1. <span data-ttu-id="2b7bd-116">Перевіряти, чи є адреса дійсною.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="2b7bd-117">Перевіряти правильність будь-яких значень, наприклад поштових індексів або назв вулиць.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="2b7bd-118">Змінювати значення, які їй не вдається розпізнати.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="2b7bd-119">Для вдосконалення адрес використовуються методи на основі машинного навчання.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="2b7bd-120">Хоча ми застосовуємо граничні значення для високої достовірності при зміні вхідних значень моделлю, як і в будь-якій іншій моделі машинного навчання, точність 100 % не гарантується.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="2b7bd-121">Підтримувані країни або регіони</span><span class="sxs-lookup"><span data-stu-id="2b7bd-121">Supported countries or regions</span></span>

<span data-ttu-id="2b7bd-122">Наразі збагачення адрес підтримується у перелічених нижче країнах або регіонах.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="2b7bd-123">Австралія</span><span class="sxs-lookup"><span data-stu-id="2b7bd-123">Australia</span></span>
- <span data-ttu-id="2b7bd-124">Канада</span><span class="sxs-lookup"><span data-stu-id="2b7bd-124">Canada</span></span>
- <span data-ttu-id="2b7bd-125">Сполучене Королівство</span><span class="sxs-lookup"><span data-stu-id="2b7bd-125">United Kingdom</span></span>
- <span data-ttu-id="2b7bd-126">Сполучені Штати</span><span class="sxs-lookup"><span data-stu-id="2b7bd-126">United States</span></span>

<span data-ttu-id="2b7bd-127">Адреси повинні містити значення країни або регіону.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="2b7bd-128">Ми не опрацьовуємо адреси в країнах або регіонах, що не підтримуються, а також адреси, для яких на зазначено країни/регіону.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="2b7bd-129">Налаштуйте збагачення</span><span class="sxs-lookup"><span data-stu-id="2b7bd-129">Configure the enrichment</span></span>

1. <span data-ttu-id="2b7bd-130">Перейдіть до розділу **Дані** > **Збагачення**.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="2b7bd-131">Виберіть **Збагатити мої дані** на плитці **Удосконалені адреси**.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Знімок екрана: плитка «Удосконалені адреси».":::

1. <span data-ttu-id="2b7bd-133">Виберіть **Набір даних клієнта** та виберіть сутність, що містить адреси, які потрібно збагатити.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="2b7bd-134">Можна вибрати сутність *Клієнт*, щоб збагатити адреси в усіх профілях клієнтів, або вибрати сутність сегмента, щоб збагатити адреси лише в профілях клієнтів, що містяться в певному сегменті.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="2b7bd-135">Виберіть спосіб форматування адрес у наборі даних.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="2b7bd-136">Виберіть **Адреса з одним атрибутом**, якщо адреси в даних використовують одне поле.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="2b7bd-137">Виберіть **Адреса з кількома атрибутами**, якщо адреси в даних використовують більше одного поля даних.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2b7bd-138">Країна/регіон є обов'язковим значенням як в адресі з одним атрибутом, так і в адресі із кількома атрибутами.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="2b7bd-139">Адреси, які не містять припустимого або підтримуваного значення країни/регіону, не збагачуватимуться.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="2b7bd-140">Зіставте поля адреси з уніфікованої сутності клієнта.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Сторінка зіставлення полів удосконаленої адреси.":::

1. <span data-ttu-id="2b7bd-142">Виберіть **Далі**, щоб завершити зіставлення полів.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="2b7bd-143">Зазначте ім'я збагачення та вихідну сутність.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="2b7bd-144">Виберіть пункт **Зберегти збагачення** після того, як переглянете доступні вам варіанти вибору.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2b7bd-145">Результати збагачення</span><span class="sxs-lookup"><span data-stu-id="2b7bd-145">Enrichment results</span></span>

<span data-ttu-id="2b7bd-146">Щоб почати процес збагачення, натисніть **Виконати** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="2b7bd-147">Також можна дозволити системі автоматично запустити збагачення в рамках [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2b7bd-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2b7bd-148">Час обробки залежить від розміру даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="2b7bd-149">Після завершення процесу збагачення можна переглянути нові збагачені профілі клієнтів у розділі **Мої збагачення**.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="2b7bd-150">Крім того, можна знайти час останнього оновлення та кількість збагачених профілів.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2b7bd-151">Можна отримати доступ до докладного подання кожного збагаченого профілю, вибравши елемент **Переглянути збагачені дані**.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2b7bd-152">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="2b7bd-152">Next steps</span></span>

<span data-ttu-id="2b7bd-153">Створюйте на основі збагачених даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2b7bd-154">Створіть [сегменти](segments.md), [міри](measures.md) та навіть [експортуйте дані](export-destinations.md), щоб надати клієнтам персоналізовані можливості.</span><span class="sxs-lookup"><span data-stu-id="2b7bd-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
