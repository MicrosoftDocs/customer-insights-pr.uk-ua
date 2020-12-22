---
title: Збагачення за допомогою збагачення третьої сторони Experian
description: Загальні відомості про стороннє збагачення Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668838"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="a73e2-103">Збагачення профілів клієнтів демографічними даними з Experian (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="a73e2-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="a73e2-104">Компанія Experian є світовим лідером у галузі звітування та маркетингу щодо споживчих та ділових кредитів.</span><span class="sxs-lookup"><span data-stu-id="a73e2-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="a73e2-105">За допомогою послуг компанії Experian щодо збагачення даних можна глибше розуміти своїх клієнтів, збагачуючи профілі клієнтів демографічними даними, такими як розмір сім'ї, прибуток тощо.</span><span class="sxs-lookup"><span data-stu-id="a73e2-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a73e2-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="a73e2-106">Prerequisites</span></span>

<span data-ttu-id="a73e2-107">Щоб настроїти Experian, слід виконати зазначені нижче передумови.</span><span class="sxs-lookup"><span data-stu-id="a73e2-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a73e2-108">Ви маєте активну передплату на Experian.</span><span class="sxs-lookup"><span data-stu-id="a73e2-108">You have an active Experian subscription.</span></span> <span data-ttu-id="a73e2-109">Щоб отримати передплату, [зв'яжіться безпосередньо з компанією Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="a73e2-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="a73e2-110">[Докладніше про збагачення даних Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="a73e2-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="a73e2-111">Ви маєте ідентифікатор користувача, ідентифікатор сторони і номер моделі для облікового запису Secure Transport (ST) із підтримкою SSH, який компанія Experian створила для вас.</span><span class="sxs-lookup"><span data-stu-id="a73e2-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="a73e2-112">Ви маєте дозволи [Адміністратора](permissions.md#administrator) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="a73e2-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="a73e2-113">Конфігурація</span><span class="sxs-lookup"><span data-stu-id="a73e2-113">Configuration</span></span>

1. <span data-ttu-id="a73e2-114">Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.</span><span class="sxs-lookup"><span data-stu-id="a73e2-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="a73e2-115">Виберіть елемент **Збагатити дані** на плитці Experian.</span><span class="sxs-lookup"><span data-stu-id="a73e2-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a73e2-116">![Плитка Experian](media/experian-tile.png "Плитка Experian")</span><span class="sxs-lookup"><span data-stu-id="a73e2-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="a73e2-117">Натисніть **Почати** і введіть ідентифікатор користувача, ідентифікатор сторони і номер моделі для облікового запису Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="a73e2-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="a73e2-118">Перегляньте та прийміть умови **конфіденційності й відповідності даних**, установивши прапорець **Приймаю**.</span><span class="sxs-lookup"><span data-stu-id="a73e2-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="a73e2-119">Підтвердьте всі введені дані, натиснувши **Застосувати**.</span><span class="sxs-lookup"><span data-stu-id="a73e2-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="a73e2-120">Зіставлення полів</span><span class="sxs-lookup"><span data-stu-id="a73e2-120">Map your fields</span></span>

1. <span data-ttu-id="a73e2-121">Натисніть **Додати дані** і виберіть ідентифікатори ключа з полів **Ім’я та адреса**, **Електронна пошта** або **Телефон**, щоб надіслати дані в Experian для визначення ідентичності.</span><span class="sxs-lookup"><span data-stu-id="a73e2-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="a73e2-122">Якщо надіслати в Experian більше атрибутів ідентифікаторів ключа, ймовірність отримати вищий показник збігу вища.</span><span class="sxs-lookup"><span data-stu-id="a73e2-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="a73e2-123">Натисніть **Далі** і зіставте відповідні атрибути з єдиної сутності клієнта для вибраних полів ідентифікаторів ключа.</span><span class="sxs-lookup"><span data-stu-id="a73e2-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="a73e2-124">Натисніть **Додати атрибути**, щоб зіставити будь-які додаткові атрибути, які ви хотіли б надіслати в Experian.</span><span class="sxs-lookup"><span data-stu-id="a73e2-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="a73e2-125">Натисніть кнопку **Зберегти**, щоб завершити зіставлення полів.</span><span class="sxs-lookup"><span data-stu-id="a73e2-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a73e2-126">![Зіставлення полів Experian](media/experian-field-mapping.png "Зіставлення полів Experian")</span><span class="sxs-lookup"><span data-stu-id="a73e2-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a73e2-127">Результати збагачення</span><span class="sxs-lookup"><span data-stu-id="a73e2-127">Enrichment results</span></span>

<span data-ttu-id="a73e2-128">Щоб почати процес збагачення, натисніть **Виконати** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="a73e2-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a73e2-129">Також можна дозволити системі автоматично запустити збагачення в рамках [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a73e2-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a73e2-130">Час обробки буде залежати від розміру даних клієнтів і процесів збагачення, встановлених для вашого облікового запису з боку Experian.</span><span class="sxs-lookup"><span data-stu-id="a73e2-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="a73e2-131">Після завершення процесу збагачення можна переглянути нові збагачені профілі клієнтів у розділі **Мої збагачення**.</span><span class="sxs-lookup"><span data-stu-id="a73e2-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="a73e2-132">Крім того, можна знайти час останнього оновлення та кількість збагачених профілів.</span><span class="sxs-lookup"><span data-stu-id="a73e2-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a73e2-133">Можна отримати доступ до докладного подання кожного збагаченого профілю, вибравши елемент **Переглянути збагачені дані**.</span><span class="sxs-lookup"><span data-stu-id="a73e2-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a73e2-134">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="a73e2-134">Next steps</span></span>

<span data-ttu-id="a73e2-135">Створюйте на основі збагачених даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="a73e2-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a73e2-136">Створіть [сегменти](segments.md), [міри](measures.md) та навіть [експортуйте дані](export-destinations.md), щоб надати клієнтам персоналізовані можливості.</span><span class="sxs-lookup"><span data-stu-id="a73e2-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a73e2-137">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="a73e2-137">Data privacy and compliance</span></span>

<span data-ttu-id="a73e2-138">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Experian можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="a73e2-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a73e2-139">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія Experian відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="a73e2-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a73e2-140">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a73e2-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a73e2-141">Ваш адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="a73e2-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
