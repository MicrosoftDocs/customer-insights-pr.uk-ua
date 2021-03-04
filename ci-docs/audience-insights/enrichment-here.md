---
title: Збагачення за допомогою стороннього збагачення HERE Technologies
description: Загальні відомості про стороннє збагачення HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269539"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="45337-103">Збагачення профілів клієнтів за допомогою HERE Technologies (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="45337-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="45337-104">HERE Technologies — це компанія платформи визначення місцеположення, що надає дані та послуги, орієнтовані на місцеположення.</span><span class="sxs-lookup"><span data-stu-id="45337-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="45337-105">За допомогою служб збагачення даних HERE Technologies можна отримати точніше розуміння відомостей про місцезнаходження клієнтів, використовуючи нормалізацію адрес, отримання довготи та широти тощо.</span><span class="sxs-lookup"><span data-stu-id="45337-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="45337-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="45337-106">Prerequisites</span></span>

<span data-ttu-id="45337-107">Для настроювання збагачення HERE Technologies необхідно виконати зазначені нижче передумови.</span><span class="sxs-lookup"><span data-stu-id="45337-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="45337-108">Ви повинні мати активну передплату на HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="45337-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="45337-109">Щоб отримати передплату, можна [зареєструватися тут](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) або [зв'язатися безпосередньо з HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="45337-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="45337-110">Дізнайтесь більше про збагачення даних про розташування HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="45337-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="45337-111">Ви маєте ключ API від HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="45337-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="45337-112">Ви маєте дозволи [Адміністратора](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="45337-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="45337-113">Конфігурація</span><span class="sxs-lookup"><span data-stu-id="45337-113">Configuration</span></span>

1. <span data-ttu-id="45337-114">Перейдіть до розділу **Дані** > **Збагачення**.</span><span class="sxs-lookup"><span data-stu-id="45337-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="45337-115">Виберіть параметр **Збагачення моїх даних** у плитці HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="45337-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="45337-116">![Плитка HERE Technologies](media/HERE-tile.png "Плитка HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="45337-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="45337-117">Введіть активний **Ключ API HERE Technologiesy**.</span><span class="sxs-lookup"><span data-stu-id="45337-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="45337-118">Перегляньте та прийміть умови **конфіденційності й відповідності даних**, установивши прапорець **Приймаю**.</span><span class="sxs-lookup"><span data-stu-id="45337-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="45337-119">Підтвердьте обидва введення, вибравши параметр **З'єднати з HERE**.</span><span class="sxs-lookup"><span data-stu-id="45337-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="45337-120">Виберіть **Додати дані** та виберіть **Набір даних клієнта**, який потрібно збагатити даними про розташування від HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="45337-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="45337-121">Можна вибрати сутність **Клієнт**, щоб збагатити всі профілі клієнтів, або вибрати сутність сегмента для збагачення лише профілів клієнтів, що містяться в цьому сегменті.</span><span class="sxs-lookup"><span data-stu-id="45337-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Знімок екрана: вибір набору даних клієнта.":::

1. <span data-ttu-id="45337-123">Виберіть, потрібно зіставити поля з основною чи додатковою адресою.</span><span class="sxs-lookup"><span data-stu-id="45337-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="45337-124">Можна задати зіставлення поля для обох адрес (наприклад, домашньої і ділової) і збагатити профілі для обох адрес окремо.</span><span class="sxs-lookup"><span data-stu-id="45337-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="45337-125">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="45337-125">Select **Next**.</span></span>

1. <span data-ttu-id="45337-126">Визначте, які поля з ваших уніфікованих профілів слід використовувати для пошуку відповідних даних щодо розташування у HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="45337-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="45337-127">Поля **Вулиця 1** і **Поштовий індекс** необхідні для вибраних основної та додаткової адрес.</span><span class="sxs-lookup"><span data-stu-id="45337-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="45337-128">Для підвищення точності зіставлення можна додати більше полів.</span><span class="sxs-lookup"><span data-stu-id="45337-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="45337-129">![Сторінка налаштування збагачення HERE Technologies](media/enrichment-HERE-configuration.png "Сторінка налаштування збагачення HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="45337-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="45337-130">Натисніть **Застосувати**, щоб заповнити поля, що зіставляються.</span><span class="sxs-lookup"><span data-stu-id="45337-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="45337-131">Результати збагачення</span><span class="sxs-lookup"><span data-stu-id="45337-131">Enrichment results</span></span>

<span data-ttu-id="45337-132">Щоб почати процес збагачення, натисніть **Виконати** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="45337-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="45337-133">Також можна дозволити системі автоматично запустити збагачення в рамках [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="45337-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="45337-134">Час обробки буде залежати від розміру даних клієнтів і часу відгуку API з HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="45337-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="45337-135">Після завершення процесу збагачення можна переглянути нові збагачені профілі клієнтів у розділі **Мої збагачення**.</span><span class="sxs-lookup"><span data-stu-id="45337-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="45337-136">Крім того, можна знайти час останнього оновлення та кількість збагачених профілів.</span><span class="sxs-lookup"><span data-stu-id="45337-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="45337-137">Можна отримати доступ до докладного подання кожного збагаченого профілю, вибравши елемент **Переглянути збагачені дані**.</span><span class="sxs-lookup"><span data-stu-id="45337-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="45337-138">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="45337-138">Next steps</span></span>

<span data-ttu-id="45337-139">Створюйте на основі збагачених даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="45337-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="45337-140">Створіть [сегменти](segments.md), [міри](measures.md) та навіть [експортуйте дані](export-destinations.md), щоб надати клієнтам персоналізовані можливості.</span><span class="sxs-lookup"><span data-stu-id="45337-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="45337-141">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="45337-141">Data privacy and compliance</span></span>

<span data-ttu-id="45337-142">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до HERE Technologies можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="45337-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="45337-143">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб HERE Technologies відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="45337-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="45337-144">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="45337-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="45337-145">Ваш адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="45337-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]