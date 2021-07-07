---
title: Збагачення за допомогою стороннього постачальника Experian
description: Загальна інформація про стороннього постачальника Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309845"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="3d34f-103">Збагачуйте профілі клієнтів демографічними даними з Experian (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="3d34f-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="3d34f-104">Experian є глобальним лідером у сфері звітності споживчого та господарського кредитування й маркетингових послуг.</span><span class="sxs-lookup"><span data-stu-id="3d34f-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="3d34f-105">Завдяки службам збагачення даних Experian ви можете отримати глибше розуміння своїх клієнтів способом збагачення профілів клієнтів демографічними даними, таким як розмір домашнього господарства, дохід тощо.</span><span class="sxs-lookup"><span data-stu-id="3d34f-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3d34f-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="3d34f-106">Prerequisites</span></span>

<span data-ttu-id="3d34f-107">Щоб налаштувати Experian, необхідно виконати наведені далі передумови.</span><span class="sxs-lookup"><span data-stu-id="3d34f-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3d34f-108">У вас є активна передплата Experian.</span><span class="sxs-lookup"><span data-stu-id="3d34f-108">You have an active Experian subscription.</span></span> <span data-ttu-id="3d34f-109">Щоб оформити передплату, [звертайтеся безпосередньо до Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="3d34f-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="3d34f-110">[Дізнайтеся більше про збагачення даних Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="3d34f-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="3d34f-111">Адміністратор вже налаштував підключення Experian *або* ви маєте права [адміністратора](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="3d34f-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="3d34f-112">Для створеного для вас Experian облікового запису безпечного транспортування (ST) з підтримкою протоколу SSH вам також знадобиться ідентифікатор користувача, ідентифікатор сторони й номер моделі.</span><span class="sxs-lookup"><span data-stu-id="3d34f-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="3d34f-113">Країни або регіони, що підтримуються</span><span class="sxs-lookup"><span data-stu-id="3d34f-113">Supported countries/regions</span></span>

<span data-ttu-id="3d34f-114">На цей час збагачення профілів клієнтів підтримується лише в Сполучених Штатах.</span><span class="sxs-lookup"><span data-stu-id="3d34f-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="3d34f-115">Налаштуйте збагачення</span><span class="sxs-lookup"><span data-stu-id="3d34f-115">Configure the enrichment</span></span>

1. <span data-ttu-id="3d34f-116">Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.</span><span class="sxs-lookup"><span data-stu-id="3d34f-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="3d34f-117">Виберіть пункт **Збагатити мої дані** на плитці Experian.</span><span class="sxs-lookup"><span data-stu-id="3d34f-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3d34f-118">![Плитка Experian](media/experian-tile.png "Плитка Experian")</span><span class="sxs-lookup"><span data-stu-id="3d34f-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="3d34f-119">Виберіть [підключення](connections.md) з розкривного списку.</span><span class="sxs-lookup"><span data-stu-id="3d34f-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="3d34f-120">Якщо жодне підключення недоступне, зверніться до адміністратора.</span><span class="sxs-lookup"><span data-stu-id="3d34f-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="3d34f-121">Якщо ви адміністратор, ви можете створити підключення, якщо виберете пункт **Додати підключення**, а потім із розкривного списку виберете Experian.</span><span class="sxs-lookup"><span data-stu-id="3d34f-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="3d34f-122">Щоб підтвердити вибір підключення, виберіть пункт **Підключитися до Experian**.</span><span class="sxs-lookup"><span data-stu-id="3d34f-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="3d34f-123">Виберіть пункт **Далі**, потім виберіть **Набір даних клієнта**, який ви бажаєте збагатити з використанням демографічних даних із Experian.</span><span class="sxs-lookup"><span data-stu-id="3d34f-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="3d34f-124">Можна вибрати сутність **Клієнт**, щоб збагатити всі профілі клієнтів, або вибрати сутність сегмента для збагачення лише профілів клієнтів, що містяться в цьому сегменті.</span><span class="sxs-lookup"><span data-stu-id="3d34f-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Знімок екрана: вибір набору даних клієнта.":::

1. <span data-ttu-id="3d34f-126">Виберіть пункт **Далі**, потім виберіть, поля якого типу з ваших єдиних профілів слід використовувати для пошуку відповідних демографічних даних із Experian.</span><span class="sxs-lookup"><span data-stu-id="3d34f-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="3d34f-127">Обов’язковим є принаймні одне з наведених далі полів: **Ім'я та адреса**, **Телефон** або **Ел. пошта**.</span><span class="sxs-lookup"><span data-stu-id="3d34f-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="3d34f-128">Задля більшої точності збігів можна додати до двох інших полів.</span><span class="sxs-lookup"><span data-stu-id="3d34f-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="3d34f-129">Цей вибір впливатиме на поля збігів, до яких ви матимете доступ на наступному кроці.</span><span class="sxs-lookup"><span data-stu-id="3d34f-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="3d34f-130">Якщо надіслати більше характерних атрибутів Experian, буде більша вірогідність отримати вищий коефіцієнт зіставлення.</span><span class="sxs-lookup"><span data-stu-id="3d34f-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="3d34f-131">Виберіть **Далі**, щоб почати зіставлення полів.</span><span class="sxs-lookup"><span data-stu-id="3d34f-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="3d34f-132">Визначте, які поля з ваших єдиних профілів слід використовувати для пошуку відповідних демографічних даних Experian.</span><span class="sxs-lookup"><span data-stu-id="3d34f-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="3d34f-133">Обов’язкові поля позначаються.</span><span class="sxs-lookup"><span data-stu-id="3d34f-133">Required fields are marked.</span></span>

1. <span data-ttu-id="3d34f-134">Зазначте ім'я збагачення та ім'я вихідної сутності.</span><span class="sxs-lookup"><span data-stu-id="3d34f-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="3d34f-135">Виберіть пункт **Зберегти збагачення** після того, як переглянете доступні вам варіанти вибору.</span><span class="sxs-lookup"><span data-stu-id="3d34f-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="3d34f-136">Налаштуйте підключення для Experian</span><span class="sxs-lookup"><span data-stu-id="3d34f-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="3d34f-137">Щоб налаштувати підключення ви маєте бути адміністратором.</span><span class="sxs-lookup"><span data-stu-id="3d34f-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="3d34f-138">Виберіть пункт **Додати підключення** при налаштуванні збагачення *або* перейдіть до розділу **Адміністратор** > **Підключення**, потім виберіть пункт **Налаштувати** на плитці Experian.</span><span class="sxs-lookup"><span data-stu-id="3d34f-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="3d34f-139">Виберіть **Почати роботу**.</span><span class="sxs-lookup"><span data-stu-id="3d34f-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="3d34f-140">Введіть ім'я підключення в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="3d34f-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="3d34f-141">Для свого облікового запису безпечного транспорту Experian виберіть ідентифікатор користувача, ідентифікатор сторони й номер моделі.</span><span class="sxs-lookup"><span data-stu-id="3d34f-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="3d34f-142">Перегляньте документ **Конфіденційність і відповідність даних** і надайте згоду з його вмістом способом вибору пункту **Погоджуюся**.</span><span class="sxs-lookup"><span data-stu-id="3d34f-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="3d34f-143">Виберіть **Підтвердити**, щоб підтвердити конфігурацію.</span><span class="sxs-lookup"><span data-stu-id="3d34f-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="3d34f-144">Після завершення перевірки виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="3d34f-144">After completing the verification, select **Save**.</span></span>
   
   Область налаштування підключення :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="3d34f-146">Результати збагачення</span><span class="sxs-lookup"><span data-stu-id="3d34f-146">Enrichment results</span></span>

<span data-ttu-id="3d34f-147">Щоб почати процес збагачення, натисніть **Виконати** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="3d34f-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3d34f-148">Також можна дозволити системі автоматично запустити збагачення в рамках [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3d34f-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3d34f-149">Час, який буде витрачено на обробку, буде залежати від розміру даних клієнта та процесів збагачення, налаштованих Experian для вашого облікового запису.</span><span class="sxs-lookup"><span data-stu-id="3d34f-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="3d34f-150">Після завершення процесу збагачення можна переглянути нові збагачені профілі клієнтів у розділі **Мої збагачення**.</span><span class="sxs-lookup"><span data-stu-id="3d34f-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="3d34f-151">Крім того, можна знайти час останнього оновлення та кількість збагачених профілів.</span><span class="sxs-lookup"><span data-stu-id="3d34f-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3d34f-152">Можна отримати доступ до докладного подання кожного збагаченого профілю, вибравши елемент **Переглянути збагачені дані**.</span><span class="sxs-lookup"><span data-stu-id="3d34f-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3d34f-153">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="3d34f-153">Next steps</span></span>

<span data-ttu-id="3d34f-154">Створюйте на основі збагачених даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="3d34f-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3d34f-155">Створюйте [сегменти](segments.md) та [міри](measures.md) й навіть [експортуйте дані](export-destinations.md), щоб забезпечувати персоналізовану взаємодію з клієнтами.</span><span class="sxs-lookup"><span data-stu-id="3d34f-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3d34f-156">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="3d34f-156">Data privacy and compliance</span></span>

<span data-ttu-id="3d34f-157">Коли ви вмикаєте Dynamics 365 Customer Insights для передавання даних до Experian, ви дозволяєте передавання даних поза межі кордонів відповідності для Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, такими як особисті дані.</span><span class="sxs-lookup"><span data-stu-id="3d34f-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3d34f-158">Майкрософт виконає передавання таких даних за вашою вказівкою, але ви несете відповідальність за забезпечення того, щоб Experian відповідала зобов’язанням щодо конфіденційності або безпеки, які можуть у вас бути.</span><span class="sxs-lookup"><span data-stu-id="3d34f-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3d34f-159">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3d34f-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3d34f-160">Адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити використання цієї функції.</span><span class="sxs-lookup"><span data-stu-id="3d34f-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
