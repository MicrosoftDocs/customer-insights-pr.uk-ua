---
title: Збагачення за допомогою стороннього збагачення HERE Technologies
description: Загальні відомості про стороннє збагачення HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896076"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="72625-103">Збагачення профілів клієнтів за допомогою HERE Technologies (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="72625-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="72625-104">HERE Technologies — це компанія платформи визначення місцеположення, що надає дані та послуги, орієнтовані на місцеположення.</span><span class="sxs-lookup"><span data-stu-id="72625-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="72625-105">За допомогою служб збагачення даних HERE Technologies можна отримати точніше розуміння відомостей про місцезнаходження клієнтів, використовуючи нормалізацію адрес, отримання довготи та широти тощо.</span><span class="sxs-lookup"><span data-stu-id="72625-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="72625-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="72625-106">Prerequisites</span></span>

<span data-ttu-id="72625-107">Для настроювання збагачення HERE Technologies необхідно виконати зазначені нижче передумови.</span><span class="sxs-lookup"><span data-stu-id="72625-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="72625-108">Ви повинні мати активну передплату на HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="72625-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="72625-109">Щоб отримати передплату, можна [зареєструватися тут](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) або [зв'язатися безпосередньо з HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="72625-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="72625-110">Дізнайтесь більше про збагачення даних про розташування HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="72625-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="72625-111">Є доступне підключення [HERE](connections.md) *або* у вас є права [адміністратора](permissions.md#administrator)та ключ API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="72625-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="72625-112">Налаштуйте збагачення</span><span class="sxs-lookup"><span data-stu-id="72625-112">Configure the enrichment</span></span>

1. <span data-ttu-id="72625-113">Перейдіть до розділу **Дані** > **Збагачення**.</span><span class="sxs-lookup"><span data-stu-id="72625-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="72625-114">Виберіть **Збагачувати мої дані** на плитці HERE Technologies, потім виберіть **Почати**.</span><span class="sxs-lookup"><span data-stu-id="72625-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="72625-115">![Плитка HERE Technologies](media/HERE-tile.png "Плитка HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="72625-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="72625-116">Виберіть [підключення](connections.md) з розкривного списку.</span><span class="sxs-lookup"><span data-stu-id="72625-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="72625-117">Якщо жодне підключення недоступне, зверніться до адміністратора.</span><span class="sxs-lookup"><span data-stu-id="72625-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="72625-118">Якщо ви є адміністратором, ви можете створити підключення, вибравши пункт **Додати підключення**.</span><span class="sxs-lookup"><span data-stu-id="72625-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="72625-119">Із розкривного списку виберіть **HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="72625-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="72625-120">Щоб підтвердити свій вибір, виберіть пункт **Підключитися до HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="72625-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="72625-121">Виберіть **Далі**, потім виберіть **Набір даних клієнта**, якщо ви бажаєте збагачувати систему за рахунок даних, отриманих від HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="72625-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="72625-122">Можна вибрати сутність **Клієнт**, щоб збагатити всі профілі клієнтів, або вибрати сутність сегмента для збагачення лише профілів клієнтів, що містяться в цьому сегменті.</span><span class="sxs-lookup"><span data-stu-id="72625-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Знімок екрана: вибір набору даних клієнта.":::

1. <span data-ttu-id="72625-124">Виберіть, потрібно зіставити поля з основною чи додатковою адресою.</span><span class="sxs-lookup"><span data-stu-id="72625-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="72625-125">Ви можете зазначити зіставлення полів для обох адрес і окремо збагачувати профілі для обох адрес.</span><span class="sxs-lookup"><span data-stu-id="72625-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="72625-126">Наприклад, за наявності домашньої та робочої адреси.</span><span class="sxs-lookup"><span data-stu-id="72625-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="72625-127">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="72625-127">Select **Next**.</span></span>

1. <span data-ttu-id="72625-128">Визначте, які поля з ваших уніфікованих профілів слід використовувати для пошуку відповідних даних щодо розташування у HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="72625-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="72625-129">Поля **Вулиця 1** і **Поштовий індекс** необхідні для вибраних основної та додаткової адрес.</span><span class="sxs-lookup"><span data-stu-id="72625-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="72625-130">Для підвищення точності зіставлення можна додати більше полів.</span><span class="sxs-lookup"><span data-stu-id="72625-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="72625-131">![Сторінка налаштування збагачення HERE Technologies](media/enrichment-HERE-configuration.png "Сторінка налаштування збагачення HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="72625-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="72625-132">Виберіть **Далі**, щоб завершити зіставлення полів.</span><span class="sxs-lookup"><span data-stu-id="72625-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="72625-133">Введіть ім’я збагачення.</span><span class="sxs-lookup"><span data-stu-id="72625-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="72625-134">1. Виберіть пункт **Зберегти збагачення** після того, як переглянете доступні вам варіанти вибору.</span><span class="sxs-lookup"><span data-stu-id="72625-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="72625-135">Налаштуйте підключення для HERE technologies</span><span class="sxs-lookup"><span data-stu-id="72625-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="72625-136">Щоб налаштувати підключення ви маєте бути адміністратором.</span><span class="sxs-lookup"><span data-stu-id="72625-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="72625-137">Виберіть **Додати підключення** під час налаштування збагачення *або* перейдіть до розділу **Адміністратор** > **Підключення** й виберіть пункт **Налаштувати** на плитці HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="72625-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="72625-138">Введіть ім'я підключення в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="72625-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="72625-139">Зазначте дійсний ключ API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="72625-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="72625-140">Перегляньте статтю **Конфіденційність даних і нормативно-правова відповідність** та надайте згоду способом установлення прапорця в полі **Погоджуюся**</span><span class="sxs-lookup"><span data-stu-id="72625-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="72625-141">Виберіть **Підтвердити**, щоб підтвердити конфігурацію.</span><span class="sxs-lookup"><span data-stu-id="72625-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="72625-142">Після завершення перевірки виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="72625-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="72625-143">![Сторінка налаштування підключення HERE Technologies](media/enrichment-HERE-connection.png "Сторінка налаштування підключення HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="72625-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="72625-144">Результати збагачення</span><span class="sxs-lookup"><span data-stu-id="72625-144">Enrichment results</span></span>

<span data-ttu-id="72625-145">Щоб почати процес збагачення, натисніть **Виконати** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="72625-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="72625-146">Також можна дозволити системі автоматично запустити збагачення в рамках [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="72625-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="72625-147">Час обробки буде залежати від розміру даних клієнтів і часу відгуку API з HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="72625-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="72625-148">Після завершення процесу збагачення можна переглянути нові збагачені профілі клієнтів у розділі **Мої збагачення**.</span><span class="sxs-lookup"><span data-stu-id="72625-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="72625-149">Крім того, можна знайти час останнього оновлення та кількість збагачених профілів.</span><span class="sxs-lookup"><span data-stu-id="72625-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="72625-150">Можна отримати доступ до докладного подання кожного збагаченого профілю, вибравши елемент **Переглянути збагачені дані**.</span><span class="sxs-lookup"><span data-stu-id="72625-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="72625-151">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="72625-151">Next steps</span></span>

<span data-ttu-id="72625-152">Створюйте на основі збагачених даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="72625-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="72625-153">Створіть [сегменти](segments.md), [міри](measures.md) та навіть [експортуйте дані](export-destinations.md), щоб надати клієнтам персоналізовані можливості.</span><span class="sxs-lookup"><span data-stu-id="72625-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="72625-154">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="72625-154">Data privacy and compliance</span></span>

<span data-ttu-id="72625-155">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до HERE Technologies можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="72625-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="72625-156">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб HERE Technologies відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="72625-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="72625-157">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="72625-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="72625-158">Ваш адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="72625-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
