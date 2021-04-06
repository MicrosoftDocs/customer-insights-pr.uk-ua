---
title: Зразок вказівок для прогнозу рекомендації продуктів
description: За допомогою зразку вказівок можна випробувати готову модель прогнозу рекомендації продуктів.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595298"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="86476-103">Зразок вказівок для прогнозу рекомендації продуктів (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="86476-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="86476-104">Ці вказівки дозволять розглянути повний приклад прогнозу рекомендації продуктів за допомогою зразків даних, наданих нижче.</span><span class="sxs-lookup"><span data-stu-id="86476-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="86476-105">Сценарій</span><span class="sxs-lookup"><span data-stu-id="86476-105">Scenario</span></span>

<span data-ttu-id="86476-106">Contoso — компанія, яка випускає високоякісну каву та кавомашини, які вони продають на веб-сайті компанії Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="86476-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="86476-107">Їх мета — зрозуміти, які продукти слід рекомендувати своїм клієнтам, що звертаються до них повторно.</span><span class="sxs-lookup"><span data-stu-id="86476-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="86476-108">Відомості щодо того, що клієнти, найімовірніше, **можуть придбати**, допоможе заощадити зусилля на маркетинг та зосередитись на конкретних товарах.</span><span class="sxs-lookup"><span data-stu-id="86476-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86476-109">Вимоги</span><span class="sxs-lookup"><span data-stu-id="86476-109">Prerequisites</span></span>

- <span data-ttu-id="86476-110">Принаймні [дозволи співавтора](permissions.md) у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="86476-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="86476-111">Радимо виконати зазначені нижче кроки [в новому середовищі](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="86476-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="86476-112">Завдання 1 — прийом даних</span><span class="sxs-lookup"><span data-stu-id="86476-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="86476-113">Перегляньте статті [про приймання даних](data-sources.md) і [імпортування джерел даних за допомогою з'єднувачів Power Query](connect-power-query.md) зокрема.</span><span class="sxs-lookup"><span data-stu-id="86476-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="86476-114">Наведена нижче інформація передбачає, що ви загалом ознайомилися з прийомом даних.</span><span class="sxs-lookup"><span data-stu-id="86476-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="86476-115">Прийом даних клієнта з платформи eCommerce</span><span class="sxs-lookup"><span data-stu-id="86476-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="86476-116">Створіть джерело даних з іменем **eCommerce**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.</span><span class="sxs-lookup"><span data-stu-id="86476-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="86476-117">Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="86476-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="86476-118">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="86476-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="86476-119">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="86476-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="86476-120">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="86476-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="86476-121">**CreatedOn**: дата/час/зона</span><span class="sxs-lookup"><span data-stu-id="86476-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Зміна дати народження на дату.":::

5. <span data-ttu-id="86476-123">У полі «Ім'я» в області праворуч перейменуйте джерело даних, **Запит** на **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="86476-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="86476-124">**Збережіть** джерело даних.</span><span class="sxs-lookup"><span data-stu-id="86476-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="86476-125">Прийом даних про придбання онлайн</span><span class="sxs-lookup"><span data-stu-id="86476-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="86476-126">Додайте ще один набір даних до того самого джерела даних **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="86476-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="86476-127">Виберіть знову з'єднувач **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="86476-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="86476-128">Введіть URL-адресу для даних про **Онлайн-придбання** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="86476-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="86476-129">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="86476-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="86476-130">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="86476-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="86476-131">**PurchasedOn**: дата/час</span><span class="sxs-lookup"><span data-stu-id="86476-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="86476-132">**TotalPrice**: грошова одиниця</span><span class="sxs-lookup"><span data-stu-id="86476-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="86476-133">У полі **Ім'я** в бічній області перейменуйте джерело даних **Запит** на **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="86476-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="86476-134">Збережіть джерело даних</span><span class="sxs-lookup"><span data-stu-id="86476-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="86476-135">Прийом даних про клієнта зі схеми лояльності</span><span class="sxs-lookup"><span data-stu-id="86476-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="86476-136">Створіть джерело даних з іменем **LoyaltyScheme**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.</span><span class="sxs-lookup"><span data-stu-id="86476-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="86476-137">Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="86476-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="86476-138">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="86476-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="86476-139">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="86476-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="86476-140">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="86476-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="86476-141">**RewardsPoints**: загальна кількість</span><span class="sxs-lookup"><span data-stu-id="86476-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="86476-142">**CreatedOn**: дата/час</span><span class="sxs-lookup"><span data-stu-id="86476-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="86476-143">У полі **Ім'я** в області праворуч перейменуйте джерело даних **Запит** на **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="86476-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="86476-144">Збережіть джерело даних</span><span class="sxs-lookup"><span data-stu-id="86476-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="86476-145">Завдання 2 — уніфікація даних</span><span class="sxs-lookup"><span data-stu-id="86476-145">Task 2 - Data unification</span></span>

<span data-ttu-id="86476-146">Після прийому даних починається процес **Зіставлення, пошук відповідностей, злиття** для створення уніфікованого профілю клієнта.</span><span class="sxs-lookup"><span data-stu-id="86476-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="86476-147">Для отримання додаткових відомостей див. розділ [Уніфікація даних](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="86476-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="86476-148">Зіставлення</span><span class="sxs-lookup"><span data-stu-id="86476-148">Map</span></span>

1. <span data-ttu-id="86476-149">Після отримання даних зіставте контакти з eCommerce і Loyalty з загальними типами даних.</span><span class="sxs-lookup"><span data-stu-id="86476-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="86476-150">Перейдіть до меню **Дані** > **Уніфікувати** > **Зіставити**.</span><span class="sxs-lookup"><span data-stu-id="86476-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="86476-151">Виберіть сутності, які відображають профіль клієнта — **ecomerecotactts** і **lolocustomer**.</span><span class="sxs-lookup"><span data-stu-id="86476-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![уніфікація джерел даних електронної комерції і лояльності.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="86476-153">Виберіть **ContactId** як первинний ключ для **eCommerceContacts** і **LoyaltyID** як первинний ключ для **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="86476-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Уніфікація LoyaltyId як первинного ключа.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="86476-155">Знайти відповідності</span><span class="sxs-lookup"><span data-stu-id="86476-155">Match</span></span>

1. <span data-ttu-id="86476-156">Перейдіть на вкладку **Пошук відповідностей** і натисніть **Встановлення порядку**.</span><span class="sxs-lookup"><span data-stu-id="86476-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="86476-157">У розкривному списку **Основне** виберіть **eCommerceContacts : eCommerce** як первинне джерело та включайте всі записи.</span><span class="sxs-lookup"><span data-stu-id="86476-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="86476-158">У розкривному списку **Сутність 2** виберіть **loyCustomers : LoyaltyScheme** і включіть всі записи.</span><span class="sxs-lookup"><span data-stu-id="86476-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Уніфікація пошуку відповідностей електронної комерції і лояльності.](media/unify-match-order.png)

4. <span data-ttu-id="86476-160">Виберіть **Створити нове правило**</span><span class="sxs-lookup"><span data-stu-id="86476-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="86476-161">Додайте першу умову за допомогою FullName.</span><span class="sxs-lookup"><span data-stu-id="86476-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="86476-162">Для eCommerceContacts виберіть **FullName** у розкривному списку.</span><span class="sxs-lookup"><span data-stu-id="86476-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="86476-163">Для loyCustomers виберіть **FullName** у розкривному списку.</span><span class="sxs-lookup"><span data-stu-id="86476-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="86476-164">Виберіть розкривне меню **Нормалізувати** і виберіть **Тип (телефон, ім'я, адреса,...)**.</span><span class="sxs-lookup"><span data-stu-id="86476-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="86476-165">Встановіть для параметру **Рівень точності** значення **Базовий** і для параметру **Значення** значення **Висока**.</span><span class="sxs-lookup"><span data-stu-id="86476-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="86476-166">Введіть ім'я **FullName, адреса електронної пошти** для нового правила.</span><span class="sxs-lookup"><span data-stu-id="86476-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="86476-167">Додайте другу умову для адреси електронної пошти, вибравши параметр **Додати умову**</span><span class="sxs-lookup"><span data-stu-id="86476-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="86476-168">Для сутності eCommerceContacts виберіть **EMail** у розкривному меню.</span><span class="sxs-lookup"><span data-stu-id="86476-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="86476-169">Для сутності loyCustomers виберіть **EMail** у розкривному меню.</span><span class="sxs-lookup"><span data-stu-id="86476-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="86476-170">Залиште поле Normalize пустим.</span><span class="sxs-lookup"><span data-stu-id="86476-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="86476-171">Встановіть для параметру **Рівень точності** значення **Базовий** і для параметру **Значення** значення **Висока**.</span><span class="sxs-lookup"><span data-stu-id="86476-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Уніфікація правила зіставлення для імені та електронної пошти.](media/unify-match-rule.png)

7. <span data-ttu-id="86476-173">Натисніть **Зберегти** та **Запустити**.</span><span class="sxs-lookup"><span data-stu-id="86476-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="86476-174">Злиття</span><span class="sxs-lookup"><span data-stu-id="86476-174">Merge</span></span>

1. <span data-ttu-id="86476-175">Перейдіть до таблиці **Злиття**.</span><span class="sxs-lookup"><span data-stu-id="86476-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="86476-176">У полі **ContactId** для сутності **loyCustomers** змініть коротке ім'я на **ContactIdLOYALTY**, щоб відрізняти від інших прийнятих ідентифікаторів.</span><span class="sxs-lookup"><span data-stu-id="86476-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![перейменуйте contactid з ідентифікатора лояльності.](media/unify-merge-contactid.png)

1. <span data-ttu-id="86476-178">Виберіть **Зберегти** та **Запустити**, щоб розпочати процес злиття.</span><span class="sxs-lookup"><span data-stu-id="86476-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="86476-179">Завдання 3 — настроювання прогнозу рекомендації продуктів</span><span class="sxs-lookup"><span data-stu-id="86476-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="86476-180">Маючи уніфіковані профілі клієнтів, ми можемо запустити прогноз відтоку підписок.</span><span class="sxs-lookup"><span data-stu-id="86476-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="86476-181">Відкрийте **Аналітика** > **Прогноз** та виберіть **Рекомендація продуктів**.</span><span class="sxs-lookup"><span data-stu-id="86476-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="86476-182">Виберіть **Почати роботу**.</span><span class="sxs-lookup"><span data-stu-id="86476-182">Select **Get started**.</span></span>

1. <span data-ttu-id="86476-183">Назвіть модель **OOB Модель прогнозу рекомендації продуктів**, а вихідну сутність — **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="86476-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="86476-184">Визначте три умови для моделі:</span><span class="sxs-lookup"><span data-stu-id="86476-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="86476-185">**Кількість продуктів**: установіть це значення як **5**.</span><span class="sxs-lookup"><span data-stu-id="86476-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="86476-186">Це налаштування визначає, скільки продуктів слід рекомендувати клієнтам.</span><span class="sxs-lookup"><span data-stu-id="86476-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="86476-187">**Пропонувати продукти, які нещодавно придбали клієнти?**: виберіть **Так**, щоб вказати, що потрібно включити до рекомендації продукти, які клієнти придбали раніше.</span><span class="sxs-lookup"><span data-stu-id="86476-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="86476-188">**Вікно ретроспективного аналізу:** виберіть щонайменше **365 днів**.</span><span class="sxs-lookup"><span data-stu-id="86476-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="86476-189">Це налаштування визначає, наскільки далеко модель зазиратиме у минуле в журналі справ клієнта, щоб знайти основу для створення індивідуальних рекомендацій.</span><span class="sxs-lookup"><span data-stu-id="86476-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Параметри моделі для моделі рекомендації продуктів.":::

1. <span data-ttu-id="86476-191">Виберіть **Обов'язкові дані**, а тоді виберіть **Додати дані** для журналу придбань.</span><span class="sxs-lookup"><span data-stu-id="86476-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="86476-192">Додайте сутність **eCommercePurchases : eCommerce** і зіставте поля з eCommerce з відповідними полями, обов'язковими для моделі.</span><span class="sxs-lookup"><span data-stu-id="86476-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="86476-193">Приєднайтеся до сутності **eCommercePurchases : eCommerce** з **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="86476-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Приєднайте сутності електронної комерції.](media/model-purchase-join.png)

1. <span data-ttu-id="86476-195">Натисніть **Далі**, щоб задати розклад моделі.</span><span class="sxs-lookup"><span data-stu-id="86476-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="86476-196">Моделі необхідно регулярно тренуватися, щоб вивчати нові моделі під час приймання нових даних.</span><span class="sxs-lookup"><span data-stu-id="86476-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="86476-197">Для цього прикладу виберіть **Щомісячно**.</span><span class="sxs-lookup"><span data-stu-id="86476-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="86476-198">Переглянувши всі відомості, виберіть **Зберегти та запустити**.</span><span class="sxs-lookup"><span data-stu-id="86476-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="86476-199">Завдання 4 — перегляд результатів моделі та пояснення</span><span class="sxs-lookup"><span data-stu-id="86476-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="86476-200">Нехай модель завершить навчання і оцінити дані.</span><span class="sxs-lookup"><span data-stu-id="86476-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="86476-201">Тепер можна ознайомитися з поясненнями моделі рекомендації продуктів.</span><span class="sxs-lookup"><span data-stu-id="86476-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="86476-202">Для отримання додаткових відомостей див. розділ [Перегляд стану та результатів прогнозу](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="86476-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="86476-203">Завдання 5 — створення сегменту товарів, які купляють часто</span><span class="sxs-lookup"><span data-stu-id="86476-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="86476-204">Під час запуску моделі виробництва створюється нова сутність, яку можна переглянути в розділі **Дані** > **Сутності**.</span><span class="sxs-lookup"><span data-stu-id="86476-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="86476-205">Можна створити новий сегмент на основі сутності, створеній моделлю.</span><span class="sxs-lookup"><span data-stu-id="86476-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="86476-206">Перейдіть до розділу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="86476-206">Go to **Segments**.</span></span> <span data-ttu-id="86476-207">Виберіть пункт **Створити** і натисніть **Створити з** > **Аналітика**.</span><span class="sxs-lookup"><span data-stu-id="86476-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Створення сегмента з виходом моделі.](media/segment-intelligence.png)

1. <span data-ttu-id="86476-209">Виберіть кінцеву точку **OOBProductRecommendationModelPrediction** і визначте сегмент:</span><span class="sxs-lookup"><span data-stu-id="86476-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="86476-210">Поле: ProductID</span><span class="sxs-lookup"><span data-stu-id="86476-210">Field: ProductID</span></span>
   - <span data-ttu-id="86476-211">Оператор: значення</span><span class="sxs-lookup"><span data-stu-id="86476-211">Operator: Value</span></span>
   - <span data-ttu-id="86476-212">Значення: виберіть три найважливіші ідентифікатори продуктів</span><span class="sxs-lookup"><span data-stu-id="86476-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Створіть сегмент з результатів моделі.":::

<span data-ttu-id="86476-214">Тепер у вас є сегмент, що динамічно оновлюється та визначає клієнтів, які більше за інших готові придбати три найбільш рекомендовані продукти</span><span class="sxs-lookup"><span data-stu-id="86476-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="86476-215">Додаткові відомості див. в розділі [Створення сегментів і керування ними](segments.md).</span><span class="sxs-lookup"><span data-stu-id="86476-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]