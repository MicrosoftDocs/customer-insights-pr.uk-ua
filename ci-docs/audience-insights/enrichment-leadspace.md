---
title: Збагачення профілів компанії за допомогою стороннього збагачення Leadspace
description: Загальні відомості про стороннє збагачення Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305227"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="7eb31-103">Збагачення профілів компанії за допомогою Leadspace (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="7eb31-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="7eb31-104">Leadspace — це компанія, яка займається наукою про дані та надає платформу даних для клієнтів B2B.</span><span class="sxs-lookup"><span data-stu-id="7eb31-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="7eb31-105">Вона дає змогу клієнтам з уніфікованими профілями клієнтів для компаній збагачувати свої дані.</span><span class="sxs-lookup"><span data-stu-id="7eb31-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="7eb31-106">Збагачення включають більше атрибутів, таких як розмір, розташування й галузь компанії, а також набагато більше.</span><span class="sxs-lookup"><span data-stu-id="7eb31-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7eb31-107">Вимоги</span><span class="sxs-lookup"><span data-stu-id="7eb31-107">Prerequisites</span></span>

<span data-ttu-id="7eb31-108">Для налаштування Leadspace повинні виконуватися нижчезазначені передумови.</span><span class="sxs-lookup"><span data-stu-id="7eb31-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="7eb31-109">У вас є активна ліцензія на Leadspace.</span><span class="sxs-lookup"><span data-stu-id="7eb31-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="7eb31-110">У вас є [уніфіковані профілі клієнтів](customer-profiles.md) для компаній.</span><span class="sxs-lookup"><span data-stu-id="7eb31-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="7eb31-111">Підключення Leadspace вже налаштоване адміністратором, або у вас є права [адміністратора](permissions.md#administrator) та «постійний ключ» (який також називають **Маркером Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="7eb31-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="7eb31-112">Щоб отримати докладніші відомості про продукт [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/), звертайтеся безпосередньо до компанії Leadspace.</span><span class="sxs-lookup"><span data-stu-id="7eb31-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="7eb31-113">Налаштуйте збагачення</span><span class="sxs-lookup"><span data-stu-id="7eb31-113">Configure the enrichment</span></span>

1. <span data-ttu-id="7eb31-114">У розділі «Аналіз аудиторії» виберіть **Дані** > **Збагачення**.</span><span class="sxs-lookup"><span data-stu-id="7eb31-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="7eb31-115">Виберіть **Збагачувати мої дані** на плитці Leadspace, потім виберіть **Почати**.</span><span class="sxs-lookup"><span data-stu-id="7eb31-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Скріншот плитки Leadspace.":::

1. <span data-ttu-id="7eb31-117">Виберіть [підключення](connections.md) з розкривного списку.</span><span class="sxs-lookup"><span data-stu-id="7eb31-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="7eb31-118">Якщо жодне підключення недоступне, зверніться до адміністратора.</span><span class="sxs-lookup"><span data-stu-id="7eb31-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="7eb31-119">Якщо ви є адміністратором, ви можете створити підключення, вибравши пункт **Додати підключення**, потім вибравши **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="7eb31-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="7eb31-120">Виберіть **Підключитися до Leadspace**, щоб підтвердити підключення.</span><span class="sxs-lookup"><span data-stu-id="7eb31-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="7eb31-121">Виберіть **Далі**, потім виберіть **Набір даних клієнта**, якщо ви бажаєте збагачувати систему за рахунок даних, отриманих від Leadspace.</span><span class="sxs-lookup"><span data-stu-id="7eb31-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="7eb31-122">Можна вибрати сутність **Клієнт**, щоб збагатити всі профілі клієнтів, або вибрати сутність сегмента для збагачення лише профілів клієнтів, що містяться в цьому сегменті.</span><span class="sxs-lookup"><span data-stu-id="7eb31-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Знімок екрана: вибір набору даних клієнта.":::

1. <span data-ttu-id="7eb31-124">Виберіть пункт **Далі** й визначте, поля якого типу з ваших єдиних профілів використовуються при пошуку відповідних даних компанії в Leadspace.</span><span class="sxs-lookup"><span data-stu-id="7eb31-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="7eb31-125">Поле **Назва компанії** є обов'язковим.</span><span class="sxs-lookup"><span data-stu-id="7eb31-125">The **Name of company** field is required.</span></span> <span data-ttu-id="7eb31-126">Для більш високої точності зіставлення можна додати до двох інших полів, **Веб-сайт компанії** та **Місцезнаходження компанії**.</span><span class="sxs-lookup"><span data-stu-id="7eb31-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Область зіставлення полів Leadspace.":::

1. <span data-ttu-id="7eb31-128">Виберіть **Далі**, щоб завершити зіставлення полів.</span><span class="sxs-lookup"><span data-stu-id="7eb31-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="7eb31-129">Зазначте ім’я вибраного вами збагачення, потім виберіть **Зберегти збагачення** після перегляду вибраних вами варіантів.</span><span class="sxs-lookup"><span data-stu-id="7eb31-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="7eb31-130">Налаштуйте підключення для Leadspace</span><span class="sxs-lookup"><span data-stu-id="7eb31-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="7eb31-131">Щоб налаштувати підключення ви маєте бути адміністратором.</span><span class="sxs-lookup"><span data-stu-id="7eb31-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="7eb31-132">Виберіть **Додати підключення** під час налаштування збагачення *або* перейдіть до розділу **Адміністратор** > **Підключення** й виберіть пункт **Налаштувати** на плитці Leadspace.</span><span class="sxs-lookup"><span data-stu-id="7eb31-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="7eb31-133">Виберіть **Почати роботу**.</span><span class="sxs-lookup"><span data-stu-id="7eb31-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="7eb31-134">Введіть ім'я підключення в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="7eb31-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="7eb31-135">Зазначте дійсний маркер Leadspace.</span><span class="sxs-lookup"><span data-stu-id="7eb31-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="7eb31-136">Перегляньте документ **Конфіденційність і відповідність даних** і надайте згоду з його вмістом способом вибору пункту **Погоджуюся**.</span><span class="sxs-lookup"><span data-stu-id="7eb31-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="7eb31-137">Виберіть **Підтвердити**, щоб підтвердити конфігурацію.</span><span class="sxs-lookup"><span data-stu-id="7eb31-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="7eb31-138">Після завершення перевірки виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="7eb31-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Сторінка налаштування підключення Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="7eb31-140">Результати збагачення</span><span class="sxs-lookup"><span data-stu-id="7eb31-140">Enrichment results</span></span>

<span data-ttu-id="7eb31-141">Після оновлення збагачення ви можете переглянути нові збагачені дані компаній у розділі [Мої збагачення](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="7eb31-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="7eb31-142">Там також можна переглянути час останнього оновлення та кількість збагачених профілів.</span><span class="sxs-lookup"><span data-stu-id="7eb31-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="7eb31-143">Можна отримати доступ до докладного подання кожного збагаченого профілю, вибравши елемент **Переглянути збагачені дані**.</span><span class="sxs-lookup"><span data-stu-id="7eb31-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="7eb31-144">Для отримання додаткових відомостей див. розділ [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="7eb31-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7eb31-145">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="7eb31-145">Next steps</span></span>

<span data-ttu-id="7eb31-146">Створюйте на основі збагачених даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="7eb31-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="7eb31-147">Створюйте [сегменти](segments.md) та [міри](measures.md) й навіть [експортуйте дані](export-destinations.md), щоб забезпечувати персоналізовану взаємодію з клієнтами.</span><span class="sxs-lookup"><span data-stu-id="7eb31-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7eb31-148">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="7eb31-148">Data privacy and compliance</span></span>

<span data-ttu-id="7eb31-149">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Leadspace можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="7eb31-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7eb31-150">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія Leadspace відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="7eb31-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7eb31-151">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7eb31-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7eb31-152">Адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити використання цієї функції.</span><span class="sxs-lookup"><span data-stu-id="7eb31-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
