---
title: Зразок вказівок для прогнозу відтоку транзакцій
description: За допомогою зразку вказівок можна випробувати готову модель прогнозування відтоку транзакцій.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 251bc26246cee16952e8e4cb08e2ed7aa4d18488
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595451"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="24e30-103">Зразок вказівок для прогнозу відтоку транзакцій (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="24e30-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="24e30-104">Ці вказівки пояснить вам повний приклад прогнозу відтоку транзакцій у Customer Insights за допомогою даних, наданих нижче.</span><span class="sxs-lookup"><span data-stu-id="24e30-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="24e30-105">Усі дані, що використовуються в цьому посібнику, не є реальними даними про клієнтів і є частиною набору даних Сontoso, що містяться в *Демонстраційному* середовищі, в рамках передплати на Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="24e30-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="24e30-106">Сценарій</span><span class="sxs-lookup"><span data-stu-id="24e30-106">Scenario</span></span>

<span data-ttu-id="24e30-107">Contoso — компанія, яка випускає високоякісну каву та кавомашини, які вони продають на веб-сайті компанії Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="24e30-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="24e30-108">Їхня ціль — дізнатися, які клієнти, що зазвичай купують їхню продукцію на регулярній основі, припинять бути активними клієнтами протягом наступних 60 днів.</span><span class="sxs-lookup"><span data-stu-id="24e30-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="24e30-109">Знання того, які з їхніх клієнтів **можуть бути втраченими**, може допомогти їм зекономити маркетингові зусилля, зосередивши увагу на їх збереженні.</span><span class="sxs-lookup"><span data-stu-id="24e30-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="24e30-110">Вимоги</span><span class="sxs-lookup"><span data-stu-id="24e30-110">Prerequisites</span></span>

- <span data-ttu-id="24e30-111">Принаймні [дозволи співавтора](permissions.md) у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="24e30-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="24e30-112">Радимо виконати зазначені нижче кроки [в новому середовищі](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="24e30-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="24e30-113">Завдання 1 — прийом даних</span><span class="sxs-lookup"><span data-stu-id="24e30-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="24e30-114">Перегляньте статті [про приймання даних](data-sources.md) і [імпортування джерел даних за допомогою з'єднувачів Power Query](connect-power-query.md) зокрема.</span><span class="sxs-lookup"><span data-stu-id="24e30-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="24e30-115">Наведена нижче інформація передбачає, що ви загалом ознайомилися з прийомом даних.</span><span class="sxs-lookup"><span data-stu-id="24e30-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="24e30-116">Прийом даних клієнта з платформи eCommerce</span><span class="sxs-lookup"><span data-stu-id="24e30-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="24e30-117">Створіть джерело даних з іменем **eCommerce**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.</span><span class="sxs-lookup"><span data-stu-id="24e30-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="24e30-118">Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="24e30-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="24e30-119">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="24e30-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="24e30-120">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="24e30-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="24e30-121">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="24e30-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="24e30-122">**CreatedOn**: дата/час/зона</span><span class="sxs-lookup"><span data-stu-id="24e30-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="24e30-123">![Змініть DoB на Date](media/ecommerce-dob-date.PNG "зміна дати народження на дату")</span><span class="sxs-lookup"><span data-stu-id="24e30-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="24e30-124">У полі **Ім'я** в області праворуч перейменуйте джерело даних **Запит** на **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="24e30-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="24e30-125">Збережіть джерело даних</span><span class="sxs-lookup"><span data-stu-id="24e30-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="24e30-126">Прийом даних про придбання онлайн</span><span class="sxs-lookup"><span data-stu-id="24e30-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="24e30-127">Додайте ще один набір даних до того самого джерела даних **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="24e30-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="24e30-128">Виберіть знову з'єднувач **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="24e30-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="24e30-129">Введіть URL-адресу для даних про **Онлайн-придбання** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="24e30-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="24e30-130">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="24e30-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="24e30-131">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="24e30-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="24e30-132">**PurchasedOn**: дата/час</span><span class="sxs-lookup"><span data-stu-id="24e30-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="24e30-133">**TotalPrice**: грошова одиниця</span><span class="sxs-lookup"><span data-stu-id="24e30-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="24e30-134">У полі **Ім'я** в області праворуч перейменуйте джерело даних **Запит** на **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="24e30-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="24e30-135">Збережіть джерело даних</span><span class="sxs-lookup"><span data-stu-id="24e30-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="24e30-136">Прийом даних про клієнта зі схеми лояльності</span><span class="sxs-lookup"><span data-stu-id="24e30-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="24e30-137">Створіть джерело даних з іменем **LoyaltyScheme**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.</span><span class="sxs-lookup"><span data-stu-id="24e30-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="24e30-138">Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="24e30-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="24e30-139">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="24e30-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="24e30-140">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="24e30-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="24e30-141">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="24e30-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="24e30-142">**RewardsPoints**: загальна кількість</span><span class="sxs-lookup"><span data-stu-id="24e30-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="24e30-143">**CreatedOn**: дата/час</span><span class="sxs-lookup"><span data-stu-id="24e30-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="24e30-144">У полі **Ім'я** в області праворуч перейменуйте джерело даних **Запит** на **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="24e30-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="24e30-145">Збережіть джерело даних</span><span class="sxs-lookup"><span data-stu-id="24e30-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="24e30-146">Завдання 2 — уніфікація даних</span><span class="sxs-lookup"><span data-stu-id="24e30-146">Task 2 - Data unification</span></span>

<span data-ttu-id="24e30-147">Після прийому даних починається процес **Зіставлення, пошук відповідностей, злиття** для створення уніфікованого профілю клієнта.</span><span class="sxs-lookup"><span data-stu-id="24e30-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="24e30-148">Для отримання додаткових відомостей див. розділ [Уніфікація даних](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="24e30-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="24e30-149">Зіставлення</span><span class="sxs-lookup"><span data-stu-id="24e30-149">Map</span></span>

1. <span data-ttu-id="24e30-150">Після отримання даних зіставте контакти з eCommerce і Loyalty з загальними типами даних.</span><span class="sxs-lookup"><span data-stu-id="24e30-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="24e30-151">Перейдіть до меню **Дані** > **Уніфікувати** > **Зіставити**.</span><span class="sxs-lookup"><span data-stu-id="24e30-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="24e30-152">Виберіть сутності, які відображають профіль клієнта — **ecomerecotactts** і **lolocustomer**.</span><span class="sxs-lookup"><span data-stu-id="24e30-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="уніфікація джерел даних електронної комерції і лояльності.":::

1. <span data-ttu-id="24e30-154">Виберіть **ContactId** як первинний ключ для **eCommerceContacts** і **LoyaltyID** як первинний ключ для **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="24e30-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Уніфікація LoyaltyId як первинного ключа.":::

### <a name="match"></a><span data-ttu-id="24e30-156">Знайти відповідності</span><span class="sxs-lookup"><span data-stu-id="24e30-156">Match</span></span>

1. <span data-ttu-id="24e30-157">Перейдіть на вкладку **Пошук відповідностей** і натисніть **Встановлення порядку**.</span><span class="sxs-lookup"><span data-stu-id="24e30-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="24e30-158">У розкривному списку **Основне** виберіть **eCommerceContacts : eCommerce** як первинне джерело та включайте всі записи.</span><span class="sxs-lookup"><span data-stu-id="24e30-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="24e30-159">У розкривному списку **Сутність 2** виберіть **loyCustomers : LoyaltyScheme** і включіть всі записи.</span><span class="sxs-lookup"><span data-stu-id="24e30-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Уніфікація пошуку відповідностей електронної комерції і лояльності.":::

1. <span data-ttu-id="24e30-161">Виберіть **Створити нове правило**</span><span class="sxs-lookup"><span data-stu-id="24e30-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="24e30-162">Додайте першу умову за допомогою FullName.</span><span class="sxs-lookup"><span data-stu-id="24e30-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="24e30-163">Для eCommerceContacts виберіть **FullName** у розкривному списку.</span><span class="sxs-lookup"><span data-stu-id="24e30-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="24e30-164">Для loyCustomers виберіть **FullName** у розкривному списку.</span><span class="sxs-lookup"><span data-stu-id="24e30-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="24e30-165">Виберіть розкривне меню **Нормалізувати** і виберіть **Тип (телефон, ім'я, адреса,...)**.</span><span class="sxs-lookup"><span data-stu-id="24e30-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="24e30-166">Встановіть для параметру **Рівень точності** значення **Базовий** і для параметру **Значення** значення **Висока**.</span><span class="sxs-lookup"><span data-stu-id="24e30-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="24e30-167">Введіть ім'я **FullName, адреса електронної пошти** для нового правила.</span><span class="sxs-lookup"><span data-stu-id="24e30-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="24e30-168">Додайте другу умову для адреси електронної пошти, вибравши параметр **Додати умову**</span><span class="sxs-lookup"><span data-stu-id="24e30-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="24e30-169">Для сутності eCommerceContacts виберіть **EMail** у розкривному меню.</span><span class="sxs-lookup"><span data-stu-id="24e30-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="24e30-170">Для сутності loyCustomers виберіть **EMail** у розкривному меню.</span><span class="sxs-lookup"><span data-stu-id="24e30-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="24e30-171">Залиште поле Normalize пустим.</span><span class="sxs-lookup"><span data-stu-id="24e30-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="24e30-172">Встановіть для параметру **Рівень точності** значення **Базовий** і для параметру **Значення** значення **Висока**.</span><span class="sxs-lookup"><span data-stu-id="24e30-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Уніфікація правила зіставлення для імені та електронної пошти.":::

7. <span data-ttu-id="24e30-174">Натисніть **Зберегти** та **Запустити**.</span><span class="sxs-lookup"><span data-stu-id="24e30-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="24e30-175">Злиття</span><span class="sxs-lookup"><span data-stu-id="24e30-175">Merge</span></span>

1. <span data-ttu-id="24e30-176">Перейдіть до таблиці **Злиття**.</span><span class="sxs-lookup"><span data-stu-id="24e30-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="24e30-177">У полі **ContactId** для сутності **loyCustomers** змініть коротке ім'я на **ContactIdLOYALTY**, щоб відрізняти від інших прийнятих ідентифікаторів.</span><span class="sxs-lookup"><span data-stu-id="24e30-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="перейменуйте contactid з ідентифікатора лояльності.":::

1. <span data-ttu-id="24e30-179">Виберіть **Зберегти** та **Запустити**, щоб розпочати процес злиття.</span><span class="sxs-lookup"><span data-stu-id="24e30-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="24e30-180">Завдання 3 — настроювання прогнозу відтоку транзакцій</span><span class="sxs-lookup"><span data-stu-id="24e30-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="24e30-181">Маючи уніфіковані профілі клієнтів, ми можемо запустити прогноз відтоку підписок.</span><span class="sxs-lookup"><span data-stu-id="24e30-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="24e30-182">Для отримання детальних інструкцій див. статтю [Прогноз відтоку передплат (попередній перегляд)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="24e30-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="24e30-183">Перейдіть до розділу **Аналітика** > **Виявлення** та натисніть, щоб використати **Модель відтоку клієнтів**.</span><span class="sxs-lookup"><span data-stu-id="24e30-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="24e30-184">Виберіть параметр **Транзакційний** і натисніть **Почати**.</span><span class="sxs-lookup"><span data-stu-id="24e30-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="24e30-185">Назва моделі **OOB eCommerce Transaction Churn Prediction** і вихідна сутність **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="24e30-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="24e30-186">Визначення двох умов для моделі відтоку:</span><span class="sxs-lookup"><span data-stu-id="24e30-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="24e30-187">**Вікно прогнозу**: **принаймні 60** днів.</span><span class="sxs-lookup"><span data-stu-id="24e30-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="24e30-188">Цей параметр визначає, наскільки далеко у майбутньому ми хочемо передбачити відтік клієнтів?</span><span class="sxs-lookup"><span data-stu-id="24e30-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="24e30-189">**Визначення відтоку**: **принаймні 60** днів.</span><span class="sxs-lookup"><span data-stu-id="24e30-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="24e30-190">Тривалість без придбання, після якого клієнт вважається втраченим.</span><span class="sxs-lookup"><span data-stu-id="24e30-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Виберіть важелі моделі «Вікно прогнозу й визначення відтоку.":::

1. <span data-ttu-id="24e30-192">Виберіть **Журнал придбання (обов'язково)** і виберіть параметр **Додати дані** для журналу придбань.</span><span class="sxs-lookup"><span data-stu-id="24e30-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="24e30-193">Додайте сутність **eCommercePurchases : eCommerce** і зіставте поля з eCommerce з відповідними полями, обов'язковими для моделі.</span><span class="sxs-lookup"><span data-stu-id="24e30-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="24e30-194">Приєднайтеся до сутності **eCommercePurchases : eCommerce** з **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="24e30-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Приєднайте сутності електронної комерції.":::

1. <span data-ttu-id="24e30-196">Натисніть **Далі**, щоб задати розклад моделі.</span><span class="sxs-lookup"><span data-stu-id="24e30-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="24e30-197">Моделі необхідно регулярно тренуватися, щоб вивчати нові моделі під час приймання нових даних.</span><span class="sxs-lookup"><span data-stu-id="24e30-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="24e30-198">Для цього прикладу виберіть **Щомісячно**.</span><span class="sxs-lookup"><span data-stu-id="24e30-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="24e30-199">Переглянувши всі відомості, виберіть **Зберегти та запустити**.</span><span class="sxs-lookup"><span data-stu-id="24e30-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="24e30-200">Завдання 4 — перегляд результатів моделі та пояснення</span><span class="sxs-lookup"><span data-stu-id="24e30-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="24e30-201">Нехай модель завершить навчання і оцінити дані.</span><span class="sxs-lookup"><span data-stu-id="24e30-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="24e30-202">Тепер можна ознайомитися з поясненнями моделі відтоку підписок.</span><span class="sxs-lookup"><span data-stu-id="24e30-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="24e30-203">Для отримання додаткових відомостей див. розділ [Перегляд стану та результатів прогнозу](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="24e30-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="24e30-204">Завдання 5 — створення сегмента клієнта з високою ймовірністю відтоку</span><span class="sxs-lookup"><span data-stu-id="24e30-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="24e30-205">Під час запуску моделі виробництва створюється нова сутність, яку можна переглянути в розділі **Дані** > **Сутності**.</span><span class="sxs-lookup"><span data-stu-id="24e30-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="24e30-206">Можна створити новий сегмент на основі сутності, створеній моделлю.</span><span class="sxs-lookup"><span data-stu-id="24e30-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="24e30-207">Перейдіть до розділу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="24e30-207">Go to **Segments**.</span></span> <span data-ttu-id="24e30-208">Виберіть пункт **Створити** і натисніть **Створити з** > **Аналітика**.</span><span class="sxs-lookup"><span data-stu-id="24e30-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Створення сегмента з виходом моделі.":::

1. <span data-ttu-id="24e30-210">Виберіть кінцеву точку **OOBSubscriptionChurnPrediction** і визначте сегмент:</span><span class="sxs-lookup"><span data-stu-id="24e30-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="24e30-211">Поле: Chünscore</span><span class="sxs-lookup"><span data-stu-id="24e30-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="24e30-212">Оператор: більше ніж</span><span class="sxs-lookup"><span data-stu-id="24e30-212">Operator: greater than</span></span>
   - <span data-ttu-id="24e30-213">Значення: 0,6</span><span class="sxs-lookup"><span data-stu-id="24e30-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Налаштування сегменту відтоку підписок.":::

<span data-ttu-id="24e30-215">Тепер у вас є сегмент, який динамічно оновлюється, що визначає клієнтів з високою ймовірністю відтоку для цього бізнесу за передплатою.</span><span class="sxs-lookup"><span data-stu-id="24e30-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="24e30-216">Додаткові відомості див. в розділі [Створення сегментів і керування ними](segments.md).</span><span class="sxs-lookup"><span data-stu-id="24e30-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]