---
title: Зразок посібника з прогнозування оцінки життєвого циклу клієнта
description: Скористайтеся цим зразком посібника, щоб випробувати модель прогнозування оцінки життєвого циклу клієнта.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306374"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="cf7e0-103">Зразок посібника з прогнозування оцінки життєвого циклу клієнта (CLV)</span><span class="sxs-lookup"><span data-stu-id="cf7e0-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="cf7e0-104">У цьому посібнику крок за кроком, від початку до кінця, розглядається процес прогнозування оцінки життєвого циклу клієнта (CLV) для зразків даних в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="cf7e0-105">Сценарій</span><span class="sxs-lookup"><span data-stu-id="cf7e0-105">Scenario</span></span>

<span data-ttu-id="cf7e0-106">Contoso – це компанія, яка виробляє каву високої якості, а також кавоварки.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="cf7e0-107">Вони продають продукти на власному веб-сайті Кава Contoso.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="cf7e0-108">Компанія хоче зрозуміти, яку суму (дохід) можна отримати від клієнтів протягом наступних 12 місяців.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="cf7e0-109">Якщо вони знатимуть орієнтовну цінність клієнтів протягом 12 місяців, це допоможе скерувати маркетингові зусилля на роботу із найціннішими клієнтами.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cf7e0-110">Вимоги</span><span class="sxs-lookup"><span data-stu-id="cf7e0-110">Prerequisites</span></span>

- <span data-ttu-id="cf7e0-111">Щонайменше [дозволи співавтора](permissions.md) в аналізі аудиторії.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="cf7e0-112">Радимо виконати зазначені нижче кроки [в новому середовищі](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="cf7e0-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="cf7e0-113">Завдання 1 — прийом даних</span><span class="sxs-lookup"><span data-stu-id="cf7e0-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="cf7e0-114">Перегляньте статті про [отримання даних](data-sources.md) та [імпортування джерел даних за допомогою з’єднувачів Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="cf7e0-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="cf7e0-115">Наведена нижче інформація передбачає, що ви загалом ознайомилися з прийомом даних.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="cf7e0-116">Прийом даних клієнта з платформи eCommerce</span><span class="sxs-lookup"><span data-stu-id="cf7e0-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="cf7e0-117">Створіть джерело даних з іменем **eCommerce**, виберіть імпорт, а тоді виберіть з'єднувач **Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="cf7e0-118">Введіть URL-адресу для контактів eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="cf7e0-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="cf7e0-119">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="cf7e0-120">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="cf7e0-121">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="cf7e0-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="cf7e0-122">**CreatedOn**: дата/час/зона</span><span class="sxs-lookup"><span data-stu-id="cf7e0-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Зміна дати народження на дату.":::

1. <span data-ttu-id="cf7e0-124">У полі «Ім'я» в області праворуч перейменуйте джерело даних, **Запит** на **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="cf7e0-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="cf7e0-125">**Збережіть** джерело даних.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="cf7e0-126">Прийом даних про придбання онлайн</span><span class="sxs-lookup"><span data-stu-id="cf7e0-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="cf7e0-127">Додайте ще один набір даних до того самого джерела даних **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="cf7e0-128">Виберіть знову з'єднувач **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="cf7e0-129">Введіть URL-адресу для даних про **Онлайн-придбання** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="cf7e0-130">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="cf7e0-131">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="cf7e0-132">**PurchasedOn**: дата/час</span><span class="sxs-lookup"><span data-stu-id="cf7e0-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="cf7e0-133">**TotalPrice**: грошова одиниця</span><span class="sxs-lookup"><span data-stu-id="cf7e0-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="cf7e0-134">У полі **Ім'я** в бічній області перейменуйте джерело даних **Запит** на **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="cf7e0-135">**Збережіть** джерело даних.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="cf7e0-136">Прийом даних про клієнта зі схеми лояльності</span><span class="sxs-lookup"><span data-stu-id="cf7e0-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="cf7e0-137">Створіть джерело даних з іменем **LoyaltyScheme**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="cf7e0-138">Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="cf7e0-139">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="cf7e0-140">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="cf7e0-141">**DateOfBirth**: дата</span><span class="sxs-lookup"><span data-stu-id="cf7e0-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="cf7e0-142">**RewardsPoints**: загальна кількість</span><span class="sxs-lookup"><span data-stu-id="cf7e0-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="cf7e0-143">**CreatedOn**: дата/час</span><span class="sxs-lookup"><span data-stu-id="cf7e0-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="cf7e0-144">У полі **Ім'я** в області праворуч перейменуйте джерело даних **Запит** на **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="cf7e0-145">**Збережіть** джерело даних.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="cf7e0-146">Прийом дані клієнта з оглядів веб-сайтів</span><span class="sxs-lookup"><span data-stu-id="cf7e0-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="cf7e0-147">Створіть джерело даних з іменем **Веб-сайт**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="cf7e0-148">Введіть URL-адресу для контактів eCommerce https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="cf7e0-149">Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="cf7e0-150">Оновіть тип даних для стовпців, зазначених нижче.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="cf7e0-151">**ReviewRating**: десяткове число</span><span class="sxs-lookup"><span data-stu-id="cf7e0-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="cf7e0-152">**ReviewDate**: дата</span><span class="sxs-lookup"><span data-stu-id="cf7e0-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="cf7e0-153">У полі «Ім'я» в області праворуч перейменуйте джерело даних з **Запит** на **Рецензії**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="cf7e0-154">**Збережіть** джерело даних.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="cf7e0-155">Завдання 2 — уніфікація даних</span><span class="sxs-lookup"><span data-stu-id="cf7e0-155">Task 2 - Data unification</span></span>

<span data-ttu-id="cf7e0-156">Після отримання даних ми розпочинаємо процес уніфікації даних для створення уніфікованого профілю клієнта.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="cf7e0-157">Для отримання додаткових відомостей див. розділ [Уніфікація даних](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="cf7e0-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="cf7e0-158">Зіставлення</span><span class="sxs-lookup"><span data-stu-id="cf7e0-158">Map</span></span>

1. <span data-ttu-id="cf7e0-159">Після отримання даних зіставте контакти з eCommerce і Loyalty з загальними типами даних.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="cf7e0-160">Перейдіть до меню **Дані** > **Уніфікувати** > **Зіставити**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="cf7e0-161">Виберіть сутності, які відображають профіль клієнта — **ecomerecotactts** і **lolocustomer**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="cf7e0-162">Після цього виберіть **Застосувати**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-162">Then, select **Apply**.</span></span>

   ![уніфікація джерел даних електронної комерції і лояльності.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="cf7e0-164">Виберіть **ContactId** як первинний ключ для **eCommerceContacts** і **LoyaltyID** як первинний ключ для **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Уніфікація LoyaltyId як первинного ключа.](media/unify-loyaltyid.png)

1. <span data-ttu-id="cf7e0-166">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="cf7e0-167">Збіг</span><span class="sxs-lookup"><span data-stu-id="cf7e0-167">Match</span></span>

1. <span data-ttu-id="cf7e0-168">Перейдіть на вкладку **Пошук відповідностей** і натисніть **Встановлення порядку**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="cf7e0-169">У розкривному списку **Основний** виберіть **eCommerceContacts : eCommerce** у якості основного джерела, й включіть до нього всі записи.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="cf7e0-170">У розкривному списку **Сутність 2** виберіть **loyCustomers : LoyaltyScheme** і включіть усі записи.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Уніфікація пошуку відповідностей електронної комерції і лояльності.](media/unify-match-order.png)

1. <span data-ttu-id="cf7e0-172">Виберіть **Додати правило**</span><span class="sxs-lookup"><span data-stu-id="cf7e0-172">Select **Add rule**</span></span>

1. <span data-ttu-id="cf7e0-173">Додайте першу умову за допомогою FullName.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="cf7e0-174">У розкривному списку для сутності CommerceContacts виберіть значення **FullName**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="cf7e0-175">У розкривному списку для сутності loyCustomers виберіть значення **FullName**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="cf7e0-176">Виберіть розкривне меню **Нормалізувати**, потім виберіть **Тип (Телефон, Ім’я, Адреса, ...)**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="cf7e0-177">Встановіть для параметру **Рівень точності** значення **Базовий** і для параметру **Значення** значення **Висока**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="cf7e0-178">Введіть ім'я **FullName, адреса електронної пошти** для нового правила.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="cf7e0-179">Додайте другу умову для адреси електронної пошти, вибравши параметр **Додати умову**</span><span class="sxs-lookup"><span data-stu-id="cf7e0-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="cf7e0-180">У розкривному списку для сутності eCommerceContacts виберіть значення **Ел. пошта**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="cf7e0-181">У розкривному списку для сутності loyCustomers виберіть значення **Ел. пошта**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="cf7e0-182">Залиште поле Normalize пустим.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="cf7e0-183">Встановіть для параметру **Рівень точності** значення **Базовий** і для параметру **Значення** значення **Висока**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Уніфікація правила зіставлення для імені та електронної пошти.](media/unify-match-rule.png)

1. <span data-ttu-id="cf7e0-185">Виберіть **Готово**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-185">Select **Done**.</span></span>

1. <span data-ttu-id="cf7e0-186">Натисніть **Зберегти** та **Запустити**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="cf7e0-187">Злиття</span><span class="sxs-lookup"><span data-stu-id="cf7e0-187">Merge</span></span>

1. <span data-ttu-id="cf7e0-188">Перейдіть до таблиці **Злиття**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="cf7e0-189">У полі **ContactId** для сутності **loyCustomers** змініть коротке ім'я на **ContactIdLOYALTY**, щоб відрізняти від інших прийнятих ідентифікаторів.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![перейменуйте contactid з ідентифікатора лояльності.](media/unify-merge-contactid.png)

1. <span data-ttu-id="cf7e0-191">Виберіть **Зберегти** та **Виконати злиття та низхідні процеси**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="cf7e0-192">Завдання 3 – налаштування прогнозування цінності життєвого циклу клієнта</span><span class="sxs-lookup"><span data-stu-id="cf7e0-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="cf7e0-193">Тепер, коли уніфіковані профілі клієнтів готові, ми можемо запустити прогнозування цінності життєвого циклу клієнта.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="cf7e0-194">Докладні кроки див. тут: [Прогнозування цінності життєвого циклі клієнта (підготовча версія)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="cf7e0-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="cf7e0-195">Відкрийте **Аналітика**  > **Прогнози** та виберіть **Модель цінності життєвого циклу клієнта**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="cf7e0-196">Продивіться відомості на бічній панелі та виберіть **Почати**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="cf7e0-197">Назвіть модель **OOB eCommerce CLV Prediction** («Прогноз CLV OOB eCommerce») та вихідну сутність **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="cf7e0-198">Визначте параметри моделі для моделі CLV.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="cf7e0-199">**Часовий період прогнозу**: **12 місяців або 1 рік**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="cf7e0-200">Цей параметр визначає, на який термін у майбутньому прогнозуватиметься цінність життєвого циклу клієнта.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="cf7e0-201">**Активні клієнти**: зазначте, який клієнт вважається активним у вашій компанії.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="cf7e0-202">Установіть часові рамки в минулому, в межах яких клієнт повинен мати принаймні одну транзакцію, щоб вважатися активним.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="cf7e0-203">Модель прогнозуватиме CLV лише для активних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="cf7e0-204">Виберіть з двох варіантів – дозвольте моделі обчислити період часу на основі ретроспективних даних транзакцій або ж задайте певні часові рамки.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="cf7e0-205">У цьому зразку посібника ми **дозволяємо моделі обчислити інтервал придбання**, і це є варіантом за замовчуванням.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="cf7e0-206">**Важливі клієнти**: визначте важливих клієнтів як процентиль клієнтів, що платять найбільше.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="cf7e0-207">Модель використовує це значення, щоб надавати результати, які відповідатимуть вашому визначенню важливих клієнтів.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="cf7e0-208">Ви можете дозволити моделі визначити важливих клієнтів.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="cf7e0-209">При цьому для виведення процентиля використовується евристичне правило.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="cf7e0-210">Ви можете також визначити важливих клієнтів як процентиль клієнтів, що у майбутньому платитимуть найбільше.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="cf7e0-211">У цьому зразку посібника ми вручну визначаємо важливих клієнтів як **перші 30 % від клієнтів, що активно платять**, і переходимо **Далі**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Крок параметрів в інтерфейсі з підказками для моделі CLV.":::

1. <span data-ttu-id="cf7e0-213">На кроці **Необхідні дані** виберіть **Додати дані**, щоб надати дані журналу транзакцій.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="cf7e0-214">Додайте сутність **eCommercePurchases : eCommerce** та зіставте атрибути, необхідні для моделі.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="cf7e0-215">Ідентифікатор транзакції: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="cf7e0-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="cf7e0-216">Дата транзакції: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="cf7e0-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="cf7e0-217">Сума транзакції: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="cf7e0-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="cf7e0-218">Ідентифікатор продукту: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="cf7e0-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="cf7e0-219">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-219">Select **Next**.</span></span>

1. <span data-ttu-id="cf7e0-220">Установіть зв'язок між сутністю **eCommercePurchases : eCommerce** та **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="cf7e0-221">На кроці **Додаткові дані (необов'язково)** ви можете додати інші дані справ клієнтів.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="cf7e0-222">Ці дані дозволять отримати більше аналітичних відомостей щодо взаємодій клієнтів із вашою компанією, що може вплинути на CLV.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="cf7e0-223">Додавання таких ключових взаємодій клієнтів, як, наприклад веб-журналів, журналів обслуговування клієнтів або ретроспективних даних про участь в програмах винагород може підвищити точність прогнозування.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="cf7e0-224">Виберіть **Додати дані**, щоб додати інші дані справ клієнтів.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="cf7e0-225">Додайте сутність справи клієнта та зіставте імена її полів із відповідними полями, необхідними для моделі:</span><span class="sxs-lookup"><span data-stu-id="cf7e0-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="cf7e0-226">Сутність справи клієнта: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="cf7e0-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="cf7e0-227">Первинний ключ: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="cf7e0-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="cf7e0-228">Позначка часу: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="cf7e0-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="cf7e0-229">Подія (назва справи): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="cf7e0-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="cf7e0-230">Докладні відомості (сума або значення): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="cf7e0-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="cf7e0-231">Виберіть **Далі** та налаштуйте справу і зв'язок між даними транзакції та даними клієнта, як показано нижче.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="cf7e0-232">Тип справи: виберіть наявний</span><span class="sxs-lookup"><span data-stu-id="cf7e0-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="cf7e0-233">Мітка справи: Рецензія</span><span class="sxs-lookup"><span data-stu-id="cf7e0-233">Activity label: Review</span></span>
   - <span data-ttu-id="cf7e0-234">Відповідний підпис: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="cf7e0-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="cf7e0-235">Сутність клієнта: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="cf7e0-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="cf7e0-236">Зв'язок: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="cf7e0-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="cf7e0-237">Натисніть **Далі**, щоб задати розклад моделі.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="cf7e0-238">Модель має постійно навчатися, щоб дізнаватись про нові шаблони, якщо з’являтимуться нові дані.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="cf7e0-239">У нашому прикладі виберіть **Щомісяця**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="cf7e0-240">Переглянувши всі відомості, виберіть **Зберегти та запустити**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="cf7e0-241">Завдання 4 — перегляд результатів моделі та пояснення</span><span class="sxs-lookup"><span data-stu-id="cf7e0-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="cf7e0-242">Нехай модель завершить навчання і оцінити дані.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="cf7e0-243">Тепер ви можете переглянути результати роботи моделі CLV із поясненнями.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="cf7e0-244">Для отримання додаткових відомостей див. розділ [Перегляд стану та результатів прогнозу](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="cf7e0-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="cf7e0-245">Завдання 5 – створення сегмента з важливих клієнтів</span><span class="sxs-lookup"><span data-stu-id="cf7e0-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="cf7e0-246">При запуску моделі створюється нова сутність, яку можна побачити в розділі **Дані** > **Сутності**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="cf7e0-247">Ви можете створити новий сегмент на основі сутності, створеної моделлю.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="cf7e0-248">Перейдіть до розділу **Сегменти**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="cf7e0-249">Виберіть **Створити** і натисніть **Створити з** > **Аналітика**.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Створення сегмента з виходом моделі.](media/segment-intelligence.png)

1. <span data-ttu-id="cf7e0-251">Виберіть сутність **OOBeCommerceCLVPrediction** і визначте сегмент, як показано нижче.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="cf7e0-252">Поле: CLVScore</span><span class="sxs-lookup"><span data-stu-id="cf7e0-252">Field: CLVScore</span></span>
  - <span data-ttu-id="cf7e0-253">Оператор: більше ніж</span><span class="sxs-lookup"><span data-stu-id="cf7e0-253">Operator: greater than</span></span>
  - <span data-ttu-id="cf7e0-254">Значення: 1500</span><span class="sxs-lookup"><span data-stu-id="cf7e0-254">Value: 1500</span></span>

1. <span data-ttu-id="cf7e0-255">Виберіть **Переглянути**, а тоді **Збережіть** сегмент.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="cf7e0-256">Тепер у вас є сегмент, в якому визначено клієнтів, що, згідно прогнозу, створять більше, ніж $ 1500 доходу протягом наступних 12 місяців.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="cf7e0-257">Цей сегмент динамічно оновлюється при отриманні нових даних.</span><span class="sxs-lookup"><span data-stu-id="cf7e0-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="cf7e0-258">Додаткові відомості див. в розділі [Створення сегментів і керування ними](segments.md).</span><span class="sxs-lookup"><span data-stu-id="cf7e0-258">For more information, see [Create and manage segments](segments.md).</span></span>
