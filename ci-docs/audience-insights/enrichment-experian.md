---
title: Збагачення за допомогою збагачення третьої сторони Experian
description: Загальні відомості про стороннє збагачення Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597812"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="2378d-103">Збагачення профілів клієнтів демографічними даними з Experian (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="2378d-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="2378d-104">Компанія Experian є світовим лідером у галузі звітування та маркетингу щодо споживчих та ділових кредитів.</span><span class="sxs-lookup"><span data-stu-id="2378d-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="2378d-105">За допомогою послуг компанії Experian щодо збагачення даних можна глибше розуміти своїх клієнтів, збагачуючи профілі клієнтів демографічними даними, такими як розмір сім'ї, прибуток тощо.</span><span class="sxs-lookup"><span data-stu-id="2378d-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2378d-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="2378d-106">Prerequisites</span></span>

<span data-ttu-id="2378d-107">Щоб настроїти Experian, слід виконати зазначені нижче передумови.</span><span class="sxs-lookup"><span data-stu-id="2378d-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="2378d-108">Ви маєте активну передплату на Experian.</span><span class="sxs-lookup"><span data-stu-id="2378d-108">You have an active Experian subscription.</span></span> <span data-ttu-id="2378d-109">Щоб отримати передплату, [зв'яжіться безпосередньо з компанією Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="2378d-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="2378d-110">[Докладніше про збагачення даних Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="2378d-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="2378d-111">Ви маєте ідентифікатор користувача, ідентифікатор сторони і номер моделі для облікового запису Secure Transport (ST) із підтримкою SSH, який компанія Experian створила для вас.</span><span class="sxs-lookup"><span data-stu-id="2378d-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="2378d-112">Ви маєте дозволи [Адміністратора](permissions.md#administrator) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="2378d-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="2378d-113">Конфігурація</span><span class="sxs-lookup"><span data-stu-id="2378d-113">Configuration</span></span>

1. <span data-ttu-id="2378d-114">Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.</span><span class="sxs-lookup"><span data-stu-id="2378d-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="2378d-115">Виберіть елемент **Збагатити дані** на плитці Experian.</span><span class="sxs-lookup"><span data-stu-id="2378d-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2378d-116">![Плитка Experian](media/experian-tile.png "Плитка Experian")</span><span class="sxs-lookup"><span data-stu-id="2378d-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="2378d-117">Натисніть **Почати** і введіть ідентифікатор користувача, ідентифікатор сторони і номер моделі для облікового запису Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="2378d-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="2378d-118">Перегляньте та прийміть умови **конфіденційності й відповідності даних**, установивши прапорець **Приймаю**.</span><span class="sxs-lookup"><span data-stu-id="2378d-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="2378d-119">Підтвердьте всі введені дані, натиснувши **Застосувати**.</span><span class="sxs-lookup"><span data-stu-id="2378d-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="2378d-120">Зіставлення полів</span><span class="sxs-lookup"><span data-stu-id="2378d-120">Map your fields</span></span>

1.  <span data-ttu-id="2378d-121">Виберіть **Додати дані** та виберіть **Набір даних клієнта**, який потрібно збагатити демографічними даними від Experian.</span><span class="sxs-lookup"><span data-stu-id="2378d-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="2378d-122">Можна вибрати сутність **Клієнт**, щоб збагатити всі профілі клієнтів, або вибрати сутність сегмента для збагачення лише профілів клієнтів, що містяться в цьому сегменті.</span><span class="sxs-lookup"><span data-stu-id="2378d-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="2378d-123">Виберіть ключові ідентифікатори з **Ім'я та Адреса**, **Електронна пошта** або **Телефон**, що надсилатимуться Experian для отримання рішення щодо посвідчення.</span><span class="sxs-lookup"><span data-stu-id="2378d-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="2378d-124">Якщо надіслати в Experian більше атрибутів ідентифікаторів ключа, ймовірність отримати вищий показник збігу вища.</span><span class="sxs-lookup"><span data-stu-id="2378d-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="2378d-125">Натисніть **Далі** і зіставте відповідні атрибути з єдиної сутності клієнта для вибраних полів ідентифікаторів ключа.</span><span class="sxs-lookup"><span data-stu-id="2378d-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="2378d-126">Натисніть **Додати атрибути**, щоб зіставити будь-які додаткові атрибути, які ви хотіли б надіслати в Experian.</span><span class="sxs-lookup"><span data-stu-id="2378d-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="2378d-127">Натисніть кнопку **Зберегти**, щоб завершити зіставлення полів.</span><span class="sxs-lookup"><span data-stu-id="2378d-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2378d-128">![Зіставлення полів Experian](media/experian-field-mapping.png "Зіставлення полів Experian")</span><span class="sxs-lookup"><span data-stu-id="2378d-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2378d-129">Результати збагачення</span><span class="sxs-lookup"><span data-stu-id="2378d-129">Enrichment results</span></span>

<span data-ttu-id="2378d-130">Щоб почати процес збагачення, натисніть **Виконати** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="2378d-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="2378d-131">Також можна дозволити системі автоматично запустити збагачення в рамках [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2378d-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2378d-132">Час обробки буде залежати від розміру даних клієнтів і процесів збагачення, встановлених для вашого облікового запису з боку Experian.</span><span class="sxs-lookup"><span data-stu-id="2378d-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="2378d-133">Після завершення процесу збагачення можна переглянути нові збагачені профілі клієнтів у розділі **Мої збагачення**.</span><span class="sxs-lookup"><span data-stu-id="2378d-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="2378d-134">Крім того, можна знайти час останнього оновлення та кількість збагачених профілів.</span><span class="sxs-lookup"><span data-stu-id="2378d-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2378d-135">Можна отримати доступ до докладного подання кожного збагаченого профілю, вибравши елемент **Переглянути збагачені дані**.</span><span class="sxs-lookup"><span data-stu-id="2378d-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2378d-136">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="2378d-136">Next steps</span></span>

<span data-ttu-id="2378d-137">Створюйте на основі збагачених даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="2378d-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2378d-138">Створіть [сегменти](segments.md), [міри](measures.md) та навіть [експортуйте дані](export-destinations.md), щоб надати клієнтам персоналізовані можливості.</span><span class="sxs-lookup"><span data-stu-id="2378d-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2378d-139">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="2378d-139">Data privacy and compliance</span></span>

<span data-ttu-id="2378d-140">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Experian можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="2378d-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2378d-141">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія Experian відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="2378d-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2378d-142">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2378d-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2378d-143">Ваш адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="2378d-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]