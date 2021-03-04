---
title: Збагачення профілів компанії за допомогою стороннього збагачення Leadspace
description: Загальні відомості про стороннє збагачення Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269447"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="b18c9-103">Збагачення профілів компанії за допомогою Leadspace (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="b18c9-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="b18c9-104">Leadspace — це компанія, яка займається наукою про дані та надає платформу даних для клієнтів B2B.</span><span class="sxs-lookup"><span data-stu-id="b18c9-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="b18c9-105">Вона дає змогу клієнтам з уніфікованими профілями клієнтів для компаній збагачувати свої дані.</span><span class="sxs-lookup"><span data-stu-id="b18c9-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="b18c9-106">Збагачення містять додаткові атрибути, зокрема відомості про розміри компаній, їхні розташування, галузі тощо.</span><span class="sxs-lookup"><span data-stu-id="b18c9-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b18c9-107">Вимоги</span><span class="sxs-lookup"><span data-stu-id="b18c9-107">Prerequisites</span></span>

<span data-ttu-id="b18c9-108">Для налаштування Leadspace повинні виконуватися нижчезазначені передумови.</span><span class="sxs-lookup"><span data-stu-id="b18c9-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b18c9-109">Ви маєте активну ліцензію Leadspace і «безтерміновий ключ» (що згадується як **Маркер Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="b18c9-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="b18c9-110">Зв'яжіться безпосередньо з [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/), щоб дізнатися більше про їхній продукт.</span><span class="sxs-lookup"><span data-stu-id="b18c9-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="b18c9-111">Ви маєте дозволи [Адміністратора](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="b18c9-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="b18c9-112">У вас є [уніфіковані профілі клієнтів](customer-profiles.md) для компаній.</span><span class="sxs-lookup"><span data-stu-id="b18c9-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="b18c9-113">Конфігурація</span><span class="sxs-lookup"><span data-stu-id="b18c9-113">Configuration</span></span>

1. <span data-ttu-id="b18c9-114">У розділі «Аналіз аудиторії» виберіть **Дані** > **Збагачення**.</span><span class="sxs-lookup"><span data-stu-id="b18c9-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="b18c9-115">Виберіть **Збагатити дані** на плитці Leadspace.</span><span class="sxs-lookup"><span data-stu-id="b18c9-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Скріншот плитки Leadspace.":::

1. <span data-ttu-id="b18c9-117">Виберіть **Початок роботи**, а потім введіть активний **маркер Leadspace** (безтерміновий ключ).</span><span class="sxs-lookup"><span data-stu-id="b18c9-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="b18c9-118">Перегляньте та прийміть умови **конфіденційності й відповідності даних**, установивши прапорець **Приймаю**.</span><span class="sxs-lookup"><span data-stu-id="b18c9-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="b18c9-119">Підтвердьте обидва введення, вибравши параметр **З'єднати з Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="b18c9-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="b18c9-120">Виберіть **Зіставити дані** та виберіть набір даних клієнта, який потрібно збагатити даними про компанії від Leadspace.</span><span class="sxs-lookup"><span data-stu-id="b18c9-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="b18c9-121">Можна вибрати сутність *Клієнт*, щоб збагатити всі профілі клієнтів, або вибрати сутність сегмента для збагачення лише профілів клієнтів, що містяться в цьому сегменті.</span><span class="sxs-lookup"><span data-stu-id="b18c9-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Вибирайте між збагаченням профілів клієнтів та сегментами.":::

1. <span data-ttu-id="b18c9-123">Клацніть **Далі** і визначте, які поля з ваших уніфікованих профілів слід використовувати для пошуку відповідності даних компанії з Leadspace.</span><span class="sxs-lookup"><span data-stu-id="b18c9-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="b18c9-124">Поле **Назва компанії** є обов'язковим.</span><span class="sxs-lookup"><span data-stu-id="b18c9-124">The **Name of company** field is required.</span></span> <span data-ttu-id="b18c9-125">Для більш високої точності зіставлення можна додати до двох інших полів, **Веб-сайт компанії** та **Місцезнаходження компанії**.</span><span class="sxs-lookup"><span data-stu-id="b18c9-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Область зіставлення полів Leadspace.":::
   
1. <span data-ttu-id="b18c9-127">Натисніть **Застосувати**, щоб заповнити поля, що зіставляються.</span><span class="sxs-lookup"><span data-stu-id="b18c9-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="b18c9-128">Виберіть команду **Виконати**, щоб збагатити профілі компанії.</span><span class="sxs-lookup"><span data-stu-id="b18c9-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="b18c9-129">Тривалість збагачення залежить від кількості уніфікованих профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="b18c9-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b18c9-130">Результати збагачення</span><span class="sxs-lookup"><span data-stu-id="b18c9-130">Enrichment results</span></span>

<span data-ttu-id="b18c9-131">Після оновлення збагачення ви можете переглянути нові збагачені дані компаній у розділі [Мої збагачення](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="b18c9-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="b18c9-132">Там також можна переглянути час останнього оновлення та кількість збагачених профілів.</span><span class="sxs-lookup"><span data-stu-id="b18c9-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b18c9-133">Можна отримати доступ до докладного подання кожного збагаченого профілю, вибравши елемент **Переглянути збагачені дані**.</span><span class="sxs-lookup"><span data-stu-id="b18c9-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="b18c9-134">Для отримання додаткових відомостей див. розділ [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="b18c9-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b18c9-135">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="b18c9-135">Next steps</span></span>

<span data-ttu-id="b18c9-136">Створюйте на основі збагачених даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="b18c9-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b18c9-137">Створіть [сегменти](segments.md), [міри](measures.md) та навіть [експортуйте дані](export-destinations.md), щоб надати клієнтам персоналізовані можливості.</span><span class="sxs-lookup"><span data-stu-id="b18c9-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b18c9-138">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="b18c9-138">Data privacy and compliance</span></span>

<span data-ttu-id="b18c9-139">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Leadspace можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="b18c9-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b18c9-140">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія Leadspace відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="b18c9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b18c9-141">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b18c9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b18c9-142">Ваш адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="b18c9-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]