---
title: Збагачення за допомогою збагачення третьої сторони Experian
description: Загальні відомості про стороннє збагачення Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896398"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="83635-103">Збагачення профілів клієнтів демографічними даними з Experian (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="83635-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="83635-104">Компанія Experian є світовим лідером у галузі звітування та маркетингу щодо споживчих та ділових кредитів.</span><span class="sxs-lookup"><span data-stu-id="83635-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="83635-105">За допомогою послуг компанії Experian щодо збагачення даних можна глибше розуміти своїх клієнтів, збагачуючи профілі клієнтів демографічними даними, такими як розмір сім'ї, прибуток тощо.</span><span class="sxs-lookup"><span data-stu-id="83635-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="83635-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="83635-106">Prerequisites</span></span>

<span data-ttu-id="83635-107">Щоб настроїти Experian, слід виконати зазначені нижче передумови.</span><span class="sxs-lookup"><span data-stu-id="83635-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="83635-108">Ви маєте активну передплату на Experian.</span><span class="sxs-lookup"><span data-stu-id="83635-108">You have an active Experian subscription.</span></span> <span data-ttu-id="83635-109">Щоб отримати передплату, [зв'яжіться безпосередньо з компанією Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="83635-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="83635-110">[Докладніше про збагачення даних Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="83635-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="83635-111">Підключення Experian вже налаштоване адміністратором *або* ви маєте права [адміністратора](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="83635-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="83635-112">Вам також знадобиться ідентифікатор користувача, ідентифікатор сторони й номер моделі для свого облікового запису для безпечного транспортування (ST), який підтримує SSH і який Experian для вас створив.</span><span class="sxs-lookup"><span data-stu-id="83635-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="83635-113">Налаштуйте збагачення</span><span class="sxs-lookup"><span data-stu-id="83635-113">Configure the enrichment</span></span>

1. <span data-ttu-id="83635-114">Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.</span><span class="sxs-lookup"><span data-stu-id="83635-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="83635-115">Виберіть елемент **Збагатити дані** на плитці Experian.</span><span class="sxs-lookup"><span data-stu-id="83635-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="83635-116">![Плитка Experian](media/experian-tile.png "Плитка Experian")</span><span class="sxs-lookup"><span data-stu-id="83635-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="83635-117">Виберіть [підключення](connections.md) з розкривного списку.</span><span class="sxs-lookup"><span data-stu-id="83635-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="83635-118">Якщо жодне підключення недоступне, зверніться до адміністратора.</span><span class="sxs-lookup"><span data-stu-id="83635-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="83635-119">Якщо ви є адміністратором, ви можете створити підключення способом вибору пункту **Додати підключення**, а потім вибравши Experian із розкривного списку.</span><span class="sxs-lookup"><span data-stu-id="83635-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="83635-120">Виберіть **Підключитися до Experian**, щоб підтвердити вибір підключення.</span><span class="sxs-lookup"><span data-stu-id="83635-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="83635-121">Виберіть **Далі**, потім виберіть **Набір даних клієнта**, якщо ви бажаєте збагачувати систему за рахунок демографічних даних, отриманих від Experian.</span><span class="sxs-lookup"><span data-stu-id="83635-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="83635-122">Можна вибрати сутність **Клієнт**, щоб збагатити всі профілі клієнтів, або вибрати сутність сегмента для збагачення лише профілів клієнтів, що містяться в цьому сегменті.</span><span class="sxs-lookup"><span data-stu-id="83635-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Знімок екрана: вибір набору даних клієнта.":::

1. <span data-ttu-id="83635-124">Виберіть пункт **Далі** й визначте, поля якого типу з ваших єдиних профілів слід використовувати при пошуку відповідних демографічних даних у Experian.</span><span class="sxs-lookup"><span data-stu-id="83635-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="83635-125">Обов’язковим є принаймні одне з наведених далі полів: **Ім'я та адреса**, **Телефон** або **Ел. пошта**.</span><span class="sxs-lookup"><span data-stu-id="83635-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="83635-126">Задля більшої точності збігів можна додати до двох інших полів.</span><span class="sxs-lookup"><span data-stu-id="83635-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="83635-127">Цей вибір впливатиме на поля збігів, до яких ви матимете доступ на наступному кроці.</span><span class="sxs-lookup"><span data-stu-id="83635-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="83635-128">Якщо надіслати в Experian більше атрибутів ідентифікаторів ключа, ймовірність отримати вищий показник збігу вища.</span><span class="sxs-lookup"><span data-stu-id="83635-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="83635-129">Виберіть **Далі**, щоб почати зіставлення полів.</span><span class="sxs-lookup"><span data-stu-id="83635-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="83635-130">Визначте, поля якого типу з ваших єдиних профілів слід використовувати при пошуку відповідних демографічних даних у Experian.</span><span class="sxs-lookup"><span data-stu-id="83635-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="83635-131">Обов’язкові поля позначаються.</span><span class="sxs-lookup"><span data-stu-id="83635-131">Required fields are marked.</span></span>

1. <span data-ttu-id="83635-132">Зазначте ім'я збагачення та ім'я вихідної сутності.</span><span class="sxs-lookup"><span data-stu-id="83635-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="83635-133">Виберіть пункт **Зберегти збагачення** після того, як переглянете доступні вам варіанти вибору.</span><span class="sxs-lookup"><span data-stu-id="83635-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="83635-134">Налаштуйте підключення для Experian</span><span class="sxs-lookup"><span data-stu-id="83635-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="83635-135">Щоб налаштувати підключення ви маєте бути адміністратором.</span><span class="sxs-lookup"><span data-stu-id="83635-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="83635-136">Виберіть **Додати підключення** під час налаштування збагачення *або* перейдіть до розділу **Адміністратор** > **Підключення** й виберіть пункт **Налаштувати** на плитці Experian.</span><span class="sxs-lookup"><span data-stu-id="83635-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="83635-137">Виберіть **Почати роботу**.</span><span class="sxs-lookup"><span data-stu-id="83635-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="83635-138">Введіть ім'я підключення в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="83635-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="83635-139">Введіть дійсний ідентифікатор користувача, ідентифікатор сторони та номер моделі для облікового запису безпечного транспорту Experian.</span><span class="sxs-lookup"><span data-stu-id="83635-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="83635-140">Перегляньте статтю **Конфіденційність даних і нормативно-правова відповідність** та надайте згоду способом установлення прапорця в полі **Погоджуюся**</span><span class="sxs-lookup"><span data-stu-id="83635-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="83635-141">Виберіть **Підтвердити**, щоб підтвердити конфігурацію.</span><span class="sxs-lookup"><span data-stu-id="83635-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="83635-142">Після завершення перевірки виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="83635-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Область налаштування підключення Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="83635-144">Результати збагачення</span><span class="sxs-lookup"><span data-stu-id="83635-144">Enrichment results</span></span>

<span data-ttu-id="83635-145">Щоб почати процес збагачення, натисніть **Виконати** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="83635-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="83635-146">Також можна дозволити системі автоматично запустити збагачення в рамках [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="83635-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="83635-147">Час обробки буде залежати від розміру даних клієнтів і процесів збагачення, встановлених для вашого облікового запису з боку Experian.</span><span class="sxs-lookup"><span data-stu-id="83635-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="83635-148">Після завершення процесу збагачення можна переглянути нові збагачені профілі клієнтів у розділі **Мої збагачення**.</span><span class="sxs-lookup"><span data-stu-id="83635-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="83635-149">Крім того, можна знайти час останнього оновлення та кількість збагачених профілів.</span><span class="sxs-lookup"><span data-stu-id="83635-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="83635-150">Можна отримати доступ до докладного подання кожного збагаченого профілю, вибравши елемент **Переглянути збагачені дані**.</span><span class="sxs-lookup"><span data-stu-id="83635-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="83635-151">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="83635-151">Next steps</span></span>

<span data-ttu-id="83635-152">Створюйте на основі збагачених даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="83635-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="83635-153">Створіть [сегменти](segments.md), [міри](measures.md) та навіть [експортуйте дані](export-destinations.md), щоб надати клієнтам персоналізовані можливості.</span><span class="sxs-lookup"><span data-stu-id="83635-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="83635-154">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="83635-154">Data privacy and compliance</span></span>

<span data-ttu-id="83635-155">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Experian можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="83635-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="83635-156">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія Experian відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="83635-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="83635-157">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="83635-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="83635-158">Ваш адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="83635-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
