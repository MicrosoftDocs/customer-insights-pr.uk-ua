---
title: Надбудова Картка клієнта для програм Dynamics 365
description: Відображайте дані аналізу аудиторії у програмах Dynamics 365 завдяки цій надбудові.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059613"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="b1a77-103">Надбудова «Картка клієнта» (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="b1a77-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b1a77-104">Отримайте повний огляд своїх клієнтів безпосередньо у програмах Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b1a77-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="b1a77-105">Якщо надбудову Картка клієнта інстальовано в підтримуваній програмі Dynamics 365, ви можете відображати демографічні дані, аналітичні огляди та часові шкали справ.</span><span class="sxs-lookup"><span data-stu-id="b1a77-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="b1a77-106">Надбудова отримає дані з Customer Insights, не впливаючи на дані у підключеній програмі Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b1a77-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b1a77-107">Вимоги</span><span class="sxs-lookup"><span data-stu-id="b1a77-107">Prerequisites</span></span>

- <span data-ttu-id="b1a77-108">Надбудова працює лише з модельними програмами Dynamics 365, наприклад Sales або Customer Service, версії 9.0 і вище.</span><span class="sxs-lookup"><span data-stu-id="b1a77-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="b1a77-109">Щоб дані Dynamics 365 зіставлялися із профілями клієнтів аналітики аудиторії, потрібно [отримати їх з програми Dynamics 365, використовуючи з’єднувач Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b1a77-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="b1a77-110">Усіх користувачів Dynamics 365, що використовуватимуть надбудову Картка клієнта, необхідно [додати як користувачів](permissions.md) до аналізу аудиторії, щоб вони могли бачити дані.</span><span class="sxs-lookup"><span data-stu-id="b1a77-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="b1a77-111">Для того, щоб працювала підстановка даних, необхідно [налаштувати можливості пошуку та фільтру](search-filter-index.md) в аналізі аудиторії.</span><span class="sxs-lookup"><span data-stu-id="b1a77-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="b1a77-112">Кожен елемент керування надбудови залежатиме від певних даних в аналізі аудиторії.</span><span class="sxs-lookup"><span data-stu-id="b1a77-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="b1a77-113">Елемент керування вимірюванням: потрібні [настроєні показники](measures.md).</span><span class="sxs-lookup"><span data-stu-id="b1a77-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="b1a77-114">Елемент керування «Аналітика»: потрібні дані, створені за допомогою [прогнозів](predictions.md) або [настроюваних моделей](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="b1a77-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="b1a77-115">Демографічний елемент керування: демографічні поля (наприклад вік або стать) доступні в уніфікованому профілі клієнта.</span><span class="sxs-lookup"><span data-stu-id="b1a77-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="b1a77-116">Елемент керування "Збагачення": обов'язково застосувати активні [збагачення](enrichment-hub.md) до профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="b1a77-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="b1a77-117">Елемент керування часовою шкалою: вимагає [Настроювання справ](activities.md).</span><span class="sxs-lookup"><span data-stu-id="b1a77-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="b1a77-118">Інсталяція надбудови «Картка клієнта»</span><span class="sxs-lookup"><span data-stu-id="b1a77-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="b1a77-119">Надбудова Картка клієнта — це рішення для програм взаємодії з клієнтами у Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b1a77-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="b1a77-120">Щоб інсталювати рішення, перейдіть до AppSource і виконайте пошук **Картка клієнта Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="b1a77-121">Виберіть [Надбудова «Картка клієнта» в AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) і натисніть кнопку **Завантажити зараз**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="b1a77-122">Вам слід увійти, використовуючи облікові дані адміністратора для програми Dynamics 365, щоб інсталювати це рішення.</span><span class="sxs-lookup"><span data-stu-id="b1a77-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="b1a77-123">Інсталяція рішення в середовище може тривати певний час.</span><span class="sxs-lookup"><span data-stu-id="b1a77-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="b1a77-124">Настроювання надбудови «Картка клієнта»</span><span class="sxs-lookup"><span data-stu-id="b1a77-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="b1a77-125">Із правами адміністратора перейдіть в розділ **Параметри** в Dynamics 365 і виберіть **Рішення**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="b1a77-126">Перейдіть за посиланням **Коротке ім’я** для рішення **Надбудова «Картка клієнта» (підготовча версія) Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1a77-127">![Вибір короткого імені](media/select-display-name.png "Вибір короткого імені")</span><span class="sxs-lookup"><span data-stu-id="b1a77-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="b1a77-128">Виберіть **Вхід** і введіть облікові дані для облікового запису адміністратора, за допомогою якого можна настроїти Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b1a77-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b1a77-129">Переконайтеся, що блокувальник спливаючих елементів браузера не блокує вікно автентифікації, коли ви натискаєте кнопку **Вхід**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="b1a77-130">Виберіть середовище Customer Insights, з якого потрібно отримати дані.</span><span class="sxs-lookup"><span data-stu-id="b1a77-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="b1a77-131">Визначте зіставлення полів із записами в програмі Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b1a77-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="b1a77-132">Залежно від даних у Customer Insights, ви можете вибрати зіставлення зазначених нижче параметрів.</span><span class="sxs-lookup"><span data-stu-id="b1a77-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="b1a77-133">Щоб зіставити з контактом, виберіть поле в сутності «Клієнт», що відповідає ідентифікатору сутності вашого контакту.</span><span class="sxs-lookup"><span data-stu-id="b1a77-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="b1a77-134">Щоб зіставити з обліковим записом, виберіть поле в сутності «Клієнт», що відповідає ідентифікатору сутності вашого облікового запису.</span><span class="sxs-lookup"><span data-stu-id="b1a77-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b1a77-135">![Поле ідентифікатора «Контактна особа»](media/contact-id-field.png "Поле ідентифікатора «Контактна особа»")</span><span class="sxs-lookup"><span data-stu-id="b1a77-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="b1a77-136">Щоб зберегти настройки, натисніть кнопку **Зберегти конфігурацію**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="b1a77-137">Потім потрібно призначити ролі безпеки в Dynamics 365, щоб користувачі могли настроювати й бачити картку клієнта.</span><span class="sxs-lookup"><span data-stu-id="b1a77-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="b1a77-138">У Dynamics 365 перейдіть до **Настройки** > **Безпека** > **Користувачі**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="b1a77-139">Виберіть користувачів для редагування ролей користувача, а потім виберіть **Керування ролями**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="b1a77-140">Призначте роль **Настроювач карток Customer Insights** користувачам, котрі настроюватимуть вміст, що відображатиметься на картці для усієї організації.</span><span class="sxs-lookup"><span data-stu-id="b1a77-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="b1a77-141">Додавання до форми елементів керування карти клієнта</span><span class="sxs-lookup"><span data-stu-id="b1a77-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="b1a77-142">Щоб додати елементи керування надбудови «Картка клієнта» до форми контактної особи, у Dynamics 365 виберіть **Настройки** > **Настроювання**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="b1a77-143">Виберіть **Налаштування системи**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="b1a77-144">Перейдіть до сутності **Контактна особа**, розгорніть її й виберіть **Форми**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="b1a77-145">Виберіть форму контактної особи, до якої потрібно додати елементи керування надбудови «Картка клієнта».</span><span class="sxs-lookup"><span data-stu-id="b1a77-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b1a77-146">![Виберіть форму «Контактна особа»](media/contact-active-forms.png "Виберіть форму «Контактна особа»")</span><span class="sxs-lookup"><span data-stu-id="b1a77-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="b1a77-147">Щоб додати елемент керування, у редакторі форм перетягніть будь-яке поле з **провідника полів** до місця, в якому потрібно розмістити елемент керування.</span><span class="sxs-lookup"><span data-stu-id="b1a77-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="b1a77-148">Виберіть у формі щойно додане поле й натисніть кнопку **Змінити властивості**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="b1a77-149">Перейдіть на вкладку **Елементи керування** та виберіть **Додати елемент керування**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="b1a77-150">Виберіть один із доступних настроюваних елементів керування та натисніть кнопку **Додати**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="b1a77-151">У діалоговому вікні **Властивості поля** зніміть прапорець **Відображати підпис у формі**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="b1a77-152">Виберіть параметр **Веб** для елемента керування.</span><span class="sxs-lookup"><span data-stu-id="b1a77-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="b1a77-153">Для елементу керування "Збагачення" виберіть тип збагачення, який необхідно відобразити, настроївши поле **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="b1a77-154">Додайте окремий елемент керування збагаченням для кожного типу збагачення.</span><span class="sxs-lookup"><span data-stu-id="b1a77-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="b1a77-155">Виберіть **Зберегти** й **Опублікувати**, щоб опублікувати оновлену форму контактної особи.</span><span class="sxs-lookup"><span data-stu-id="b1a77-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="b1a77-156">Виберіть опубліковану форму контактної особи.</span><span class="sxs-lookup"><span data-stu-id="b1a77-156">Go to the published contact form.</span></span> <span data-ttu-id="b1a77-157">Відобразиться новий доданий елемент керування.</span><span class="sxs-lookup"><span data-stu-id="b1a77-157">You'll see the newly added control.</span></span> <span data-ttu-id="b1a77-158">Можливо, знадобиться ввійти в обліковий запис під час його першого використання.</span><span class="sxs-lookup"><span data-stu-id="b1a77-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="b1a77-159">Щоб настроїти дані, які будуть відображатися в настроюваному елементі керування, натисніть кнопку редагування в правому верхньому кутку.</span><span class="sxs-lookup"><span data-stu-id="b1a77-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="b1a77-160">Оновлення надбудови «Картка клієнта»</span><span class="sxs-lookup"><span data-stu-id="b1a77-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="b1a77-161">Надбудова «Картка клієнта» не оновлюється автоматично.</span><span class="sxs-lookup"><span data-stu-id="b1a77-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="b1a77-162">Щоб оновити її до останньої версії, виконайте у програмі Dynamics 365, до якої інстальовано цю надбудову зазначені нижче дії.</span><span class="sxs-lookup"><span data-stu-id="b1a77-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="b1a77-163">У програмі Dynamics 365 відкрийте **Параметри** > **Настроювання** та виберіть **Рішення**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="b1a77-164">У таблиці надбудов знайдіть **CustomerInsightsCustomerCard** й виберіть рядок.</span><span class="sxs-lookup"><span data-stu-id="b1a77-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="b1a77-165">На панелі завдань виберіть **Застосувати оновлення рішення**.</span><span class="sxs-lookup"><span data-stu-id="b1a77-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Оновлення рішення в області настроювання програм Dynamics 365":::

1. <span data-ttu-id="b1a77-167">Після початку процесу оновлення ви побачите індикатор завантаження, який не зникне, доки оновлення не завершиться.</span><span class="sxs-lookup"><span data-stu-id="b1a77-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="b1a77-168">Якщо новішої версії немає, під час оновлення з'явиться повідомлення про помилку.</span><span class="sxs-lookup"><span data-stu-id="b1a77-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
