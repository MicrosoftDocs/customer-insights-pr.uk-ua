---
title: Зразок вказівок для прогнозу відтоку передплат
description: За допомогою зразку вказівок можна випробувати готову модель прогнозування відтоку передплат.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 324e5c19778230dd978b2f4e9156a2dd82b3d2bd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595543"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="c6581-103">Зразок вказівок для прогнозу відтоку передплат (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="c6581-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="c6581-104">Ці вказівки пояснить вам повний приклад прогнозу відтоку підписок у Customer Insights за допомогою зразків даних, наданих нижче.</span><span class="sxs-lookup"><span data-stu-id="c6581-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="c6581-105">Сценарій</span><span class="sxs-lookup"><span data-stu-id="c6581-105">Scenario</span></span>

<span data-ttu-id="c6581-106">Contoso — компанія, яка випускає високоякісну каву та кавомашини, які вони продають на веб-сайті компанії Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="c6581-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="c6581-107">Нещодавно вони почали діяльність за передплатою, щоб їхні клієнти могли отримувати каву регулярно.</span><span class="sxs-lookup"><span data-stu-id="c6581-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="c6581-108">Їхня ціль полягає в тому, щоб розуміти, які передплачені клієнти можуть скасувати передплату на найближчі кілька місяців.</span><span class="sxs-lookup"><span data-stu-id="c6581-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="c6581-109">Знання того, які з їхніх клієнтів **можуть бути втраченими**, може допомогти їм зекономити маркетингові зусилля, зосередивши увагу на їх збереженні.</span><span class="sxs-lookup"><span data-stu-id="c6581-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c6581-110">Вимоги</span><span class="sxs-lookup"><span data-stu-id="c6581-110">Prerequisites</span></span>

- <span data-ttu-id="c6581-111">Принаймні [дозволи співавтора](permissions.md) у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c6581-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="c6581-112">Радимо виконати зазначені нижче кроки [в новому середовищі](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="c6581-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="c6581-113">Завдання 1 — прийом даних</span><span class="sxs-lookup"><span data-stu-id="c6581-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="c6581-114">Перегляньте статті [про приймання даних](data-sources.md) і [імпортування джерел даних за допомогою з'єднувачів Power Query](connect-power-query.md) зокрема.</span><span class="sxs-lookup"><span data-stu-id="c6581-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="c6581-115">Наведена нижче інформація передбачає, що ви загалом ознайомилися з прийомом даних.</span><span class="sxs-lookup"><span data-stu-id="c6581-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="c6581-116">Прийом даних клієнта з платформи eCommerce</span><span class="sxs-lookup"><span data-stu-id="c6581-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="c6581-117">Створіть джерело даних з іменем **eCommerce**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c6581-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c6581-118">Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="c6581-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="c6581-119">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="c6581-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c6581-120">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="c6581-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c6581-121">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="c6581-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="c6581-122">**CreatedOn**: дата/час/зона</span><span class="sxs-lookup"><span data-stu-id="c6581-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Зміна дати народження на дату.":::

1. <span data-ttu-id="c6581-124">У полі **Ім'я** в області праворуч перейменуйте джерело даних **Запит** на **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="c6581-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="c6581-125">Збережіть джерело даних</span><span class="sxs-lookup"><span data-stu-id="c6581-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="c6581-126">Прийом даних про клієнта зі схеми лояльності</span><span class="sxs-lookup"><span data-stu-id="c6581-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="c6581-127">Створіть джерело даних з іменем **LoyaltyScheme**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c6581-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c6581-128">Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="c6581-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="c6581-129">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="c6581-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c6581-130">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="c6581-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c6581-131">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="c6581-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="c6581-132">**RewardsPoints**: загальна кількість</span><span class="sxs-lookup"><span data-stu-id="c6581-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="c6581-133">**CreatedOn**: дата/час</span><span class="sxs-lookup"><span data-stu-id="c6581-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="c6581-134">У полі **Ім'я** в області праворуч перейменуйте джерело даних **Запит** на **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c6581-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="c6581-135">Збережіть джерело даних</span><span class="sxs-lookup"><span data-stu-id="c6581-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="c6581-136">Відомості про передплату на приймання</span><span class="sxs-lookup"><span data-stu-id="c6581-136">Ingest subscription information</span></span>

1. <span data-ttu-id="c6581-137">Створіть джерело даних з іменем **SubscriptionHistory**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c6581-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c6581-138">Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="c6581-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="c6581-139">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="c6581-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c6581-140">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="c6581-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c6581-141">**SubscriptioID**: загальна кількість</span><span class="sxs-lookup"><span data-stu-id="c6581-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="c6581-142">**SubscriptionAmount**: грошова одиниця</span><span class="sxs-lookup"><span data-stu-id="c6581-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="c6581-143">**SubscriptionEndDate**: дата/час</span><span class="sxs-lookup"><span data-stu-id="c6581-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="c6581-144">**SubscriptionStartDate**: дата/час</span><span class="sxs-lookup"><span data-stu-id="c6581-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="c6581-145">**TransactionDate**: дата й час</span><span class="sxs-lookup"><span data-stu-id="c6581-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="c6581-146">**IsRecurring**: True/False</span><span class="sxs-lookup"><span data-stu-id="c6581-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="c6581-147">**Is_auto_renew** : true/false</span><span class="sxs-lookup"><span data-stu-id="c6581-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="c6581-148">**RecurringFrequencyInMonths**: ціле число</span><span class="sxs-lookup"><span data-stu-id="c6581-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="c6581-149">У полі **Ім'я** в області праворуч перейменуйте джерело даних **Запит** на **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="c6581-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="c6581-150">Збережіть джерело даних</span><span class="sxs-lookup"><span data-stu-id="c6581-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="c6581-151">Прийом дані клієнта з оглядів веб-сайтів</span><span class="sxs-lookup"><span data-stu-id="c6581-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="c6581-152">Створіть джерело даних з іменем **Веб-сайт**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c6581-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c6581-153">Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="c6581-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="c6581-154">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="c6581-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c6581-155">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="c6581-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c6581-156">**ReviewRating**: ціле число</span><span class="sxs-lookup"><span data-stu-id="c6581-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="c6581-157">**ReviewDate**: дата</span><span class="sxs-lookup"><span data-stu-id="c6581-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="c6581-158">У полі «Ім'я» в області праворуч перейменуйте джерело даних, **Запит** на **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="c6581-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="c6581-159">Завдання 2 — уніфікація даних</span><span class="sxs-lookup"><span data-stu-id="c6581-159">Task 2 - Data unification</span></span>

<span data-ttu-id="c6581-160">Після прийому даних починається процес **Зіставлення, пошук відповідностей, злиття** для створення уніфікованого профілю клієнта.</span><span class="sxs-lookup"><span data-stu-id="c6581-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="c6581-161">Для отримання додаткових відомостей див. розділ [Уніфікація даних](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="c6581-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="c6581-162">Зіставлення</span><span class="sxs-lookup"><span data-stu-id="c6581-162">Map</span></span>

1. <span data-ttu-id="c6581-163">Після отримання даних зіставте контакти з eCommerce і Loyalty з загальними типами даних.</span><span class="sxs-lookup"><span data-stu-id="c6581-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="c6581-164">Перейдіть до меню **Дані** > **Уніфікувати** > **Зіставити**.</span><span class="sxs-lookup"><span data-stu-id="c6581-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="c6581-165">Виберіть сутності, які відображають профіль клієнта — **ecomerecotactts** і **lolocustomer**.</span><span class="sxs-lookup"><span data-stu-id="c6581-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="уніфікація джерел даних електронної комерції і лояльності.":::

1. <span data-ttu-id="c6581-167">Виберіть **ContactId** як первинний ключ для **eCommerceContacts** і **LoyaltyID** як первинний ключ для **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c6581-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Уніфікація LoyaltyId як первинного ключа.":::

### <a name="match"></a><span data-ttu-id="c6581-169">Знайти відповідності</span><span class="sxs-lookup"><span data-stu-id="c6581-169">Match</span></span>

1. <span data-ttu-id="c6581-170">Перейдіть на вкладку **Пошук відповідностей** і натисніть **Встановлення порядку**.</span><span class="sxs-lookup"><span data-stu-id="c6581-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="c6581-171">У розкривному списку **Основне** виберіть **eCommerceContacts : eCommerce** як первинне джерело та включайте всі записи.</span><span class="sxs-lookup"><span data-stu-id="c6581-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="c6581-172">У розкривному списку **Сутність 2** виберіть **loyCustomers : LoyaltyScheme** і включіть всі записи.</span><span class="sxs-lookup"><span data-stu-id="c6581-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Уніфікація пошуку відповідностей електронної комерції і лояльності.":::

1. <span data-ttu-id="c6581-174">Виберіть **Створити нове правило**</span><span class="sxs-lookup"><span data-stu-id="c6581-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="c6581-175">Додайте першу умову за допомогою FullName.</span><span class="sxs-lookup"><span data-stu-id="c6581-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="c6581-176">Для eCommerceContacts виберіть **FullName** у розкривному списку.</span><span class="sxs-lookup"><span data-stu-id="c6581-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="c6581-177">Для loyCustomers виберіть **FullName** у розкривному списку.</span><span class="sxs-lookup"><span data-stu-id="c6581-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="c6581-178">Виберіть розкривне меню **Нормалізувати** і виберіть **Тип (телефон, ім'я, адреса,...)**.</span><span class="sxs-lookup"><span data-stu-id="c6581-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="c6581-179">Встановіть для параметру **Рівень точності** значення **Базовий** і для параметру **Значення** значення **Висока**.</span><span class="sxs-lookup"><span data-stu-id="c6581-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="c6581-180">Введіть ім'я **FullName, адреса електронної пошти** для нового правила.</span><span class="sxs-lookup"><span data-stu-id="c6581-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="c6581-181">Додайте другу умову для адреси електронної пошти, вибравши параметр **Додати умову**</span><span class="sxs-lookup"><span data-stu-id="c6581-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="c6581-182">Для сутності eCommerceContacts виберіть **EMail** у розкривному меню.</span><span class="sxs-lookup"><span data-stu-id="c6581-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="c6581-183">Для сутності loyCustomers виберіть **EMail** у розкривному меню.</span><span class="sxs-lookup"><span data-stu-id="c6581-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="c6581-184">Залиште поле Normalize пустим.</span><span class="sxs-lookup"><span data-stu-id="c6581-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="c6581-185">Встановіть для параметру **Рівень точності** значення **Базовий** і для параметру **Значення** значення **Висока**.</span><span class="sxs-lookup"><span data-stu-id="c6581-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Уніфікація правила зіставлення для імені та електронної пошти.":::

7. <span data-ttu-id="c6581-187">Натисніть **Зберегти** та **Запустити**.</span><span class="sxs-lookup"><span data-stu-id="c6581-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="c6581-188">Злиття</span><span class="sxs-lookup"><span data-stu-id="c6581-188">Merge</span></span>

1. <span data-ttu-id="c6581-189">Перейдіть до таблиці **Злиття**.</span><span class="sxs-lookup"><span data-stu-id="c6581-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="c6581-190">У полі **ContactId** для сутності **loyCustomers** змініть коротке ім'я на **ContactIdLOYALTY**, щоб відрізняти від інших прийнятих ідентифікаторів.</span><span class="sxs-lookup"><span data-stu-id="c6581-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="перейменуйте contactid з ідентифікатора лояльності.":::

1. <span data-ttu-id="c6581-192">Виберіть **Зберегти** та **Запустити**, щоб розпочати процес злиття.</span><span class="sxs-lookup"><span data-stu-id="c6581-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="c6581-193">Завдання 3 — настроювання прогнозу відтоку передплат</span><span class="sxs-lookup"><span data-stu-id="c6581-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="c6581-194">Маючи уніфіковані профілі клієнтів, ми можемо запустити прогноз відтоку підписок.</span><span class="sxs-lookup"><span data-stu-id="c6581-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="c6581-195">Для отримання детальних інструкцій див. статтю [Прогноз відтоку передплат (попередній перегляд)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="c6581-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="c6581-196">Перейдіть до розділу **Аналітика** > **Виявлення** та натисніть, щоб використати **Модель відтоку клієнтів**.</span><span class="sxs-lookup"><span data-stu-id="c6581-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="c6581-197">Виберіть параметр **Передплата** і натисніть **Почати**.</span><span class="sxs-lookup"><span data-stu-id="c6581-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="c6581-198">Назва моделі **OOB Subscription Churn Prediction** і вихідна сутність **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="c6581-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="c6581-199">Визначення двох умов для моделі відтоку:</span><span class="sxs-lookup"><span data-stu-id="c6581-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="c6581-200">**Кількість днів з кінця передплати**: **принаймні 60** днів.</span><span class="sxs-lookup"><span data-stu-id="c6581-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="c6581-201">Якщо клієнт не подовжує передплату протягом визначеного періоду після її завершення, він вважається втраченим.</span><span class="sxs-lookup"><span data-stu-id="c6581-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="c6581-202">**Визначення відтоку**: **принаймні 93** дні.</span><span class="sxs-lookup"><span data-stu-id="c6581-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="c6581-203">Модель передбачає тривалість відтоку клієнтів.</span><span class="sxs-lookup"><span data-stu-id="c6581-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="c6581-204">Чим далі в майбутнє ви дивитеся, тим менш точними будуть результати.</span><span class="sxs-lookup"><span data-stu-id="c6581-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Виберіть важелі моделі «Вікно прогнозу й визначення відтоку.":::

1. <span data-ttu-id="c6581-206">Натисніть **Додати обов'язкові дані** і виберіть параметр **Додати дані** до журналу передплат.</span><span class="sxs-lookup"><span data-stu-id="c6581-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="c6581-207">Додайте сутність **Передплата : SubscriptionHistory** і зіставте поля з eCommerce з відповідними полями, обов'язковими для моделі.</span><span class="sxs-lookup"><span data-stu-id="c6581-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="c6581-208">Приєднайтеся до сутності **Передплата: SubscriptionHistory** за допомогою **eCommerceContacts: електрона комерція**, назвіть зв'язки **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="c6581-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Приєднайте сутності електронної комерції.":::

1. <span data-ttu-id="c6581-210">У розділі «Справи клієнта» додайте сутність **webReviews: веб-сайт** і зіставте поля з webReviews з відповідними полями, обов'язковими для моделі.</span><span class="sxs-lookup"><span data-stu-id="c6581-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="c6581-211">Основний ключ: ReviewId</span><span class="sxs-lookup"><span data-stu-id="c6581-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="c6581-212">Позначка часу: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="c6581-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="c6581-213">Подія: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="c6581-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="c6581-214">Настроювання справи для перегляду веб-сайтів.</span><span class="sxs-lookup"><span data-stu-id="c6581-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="c6581-215">Виберіть справу **Перегляд** і приєднайтеся до сутності **webReviews : веб-сайт** **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="c6581-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="c6581-216">Натисніть **Далі**, щоб задати розклад моделі.</span><span class="sxs-lookup"><span data-stu-id="c6581-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="c6581-217">Моделі необхідно регулярно тренуватися, щоб вивчати нові моделі під час приймання нових даних.</span><span class="sxs-lookup"><span data-stu-id="c6581-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="c6581-218">Для цього прикладу виберіть **Щомісячно**.</span><span class="sxs-lookup"><span data-stu-id="c6581-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="c6581-219">Переглянувши всі відомості, виберіть **Зберегти та запустити**.</span><span class="sxs-lookup"><span data-stu-id="c6581-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="c6581-220">Завдання 4 — перегляд результатів моделі та пояснення</span><span class="sxs-lookup"><span data-stu-id="c6581-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="c6581-221">Нехай модель завершить навчання і оцінити дані.</span><span class="sxs-lookup"><span data-stu-id="c6581-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="c6581-222">Тепер можна ознайомитися з поясненнями моделі відтоку підписок.</span><span class="sxs-lookup"><span data-stu-id="c6581-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="c6581-223">Для отримання додаткових відомостей див. розділ [Перегляд стану та результатів прогнозу](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="c6581-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="c6581-224">Завдання 5 — створення сегмента клієнта з високою ймовірністю відтоку</span><span class="sxs-lookup"><span data-stu-id="c6581-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="c6581-225">Під час запуску моделі виробництва створюється нова сутність, яку можна переглянути в розділі **Дані** > **Сутності**.</span><span class="sxs-lookup"><span data-stu-id="c6581-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="c6581-226">Можна створити новий сегмент на основі сутності, створеній моделлю.</span><span class="sxs-lookup"><span data-stu-id="c6581-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="c6581-227">Перейдіть до розділу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="c6581-227">Go to **Segments**.</span></span> <span data-ttu-id="c6581-228">Виберіть пункт **Створити** і натисніть **Створити з** > **Аналітика**.</span><span class="sxs-lookup"><span data-stu-id="c6581-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Створення сегмента з виходом моделі.":::

1. <span data-ttu-id="c6581-230">Виберіть кінцеву точку **OOBSubscriptionChurnPrediction** і визначте сегмент:</span><span class="sxs-lookup"><span data-stu-id="c6581-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="c6581-231">Поле: Chünscore</span><span class="sxs-lookup"><span data-stu-id="c6581-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="c6581-232">Оператор: більше ніж</span><span class="sxs-lookup"><span data-stu-id="c6581-232">Operator: greater than</span></span>
   - <span data-ttu-id="c6581-233">Значення: 0,6</span><span class="sxs-lookup"><span data-stu-id="c6581-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Налаштування сегменту відтоку підписок.":::

<span data-ttu-id="c6581-235">Тепер у вас є сегмент, який динамічно оновлюється, що визначає клієнтів з високою ймовірністю відтоку для цього бізнесу за передплатою.</span><span class="sxs-lookup"><span data-stu-id="c6581-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="c6581-236">Додаткові відомості див. в розділі [Створення сегментів і керування ними](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c6581-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]