---
title: Встановлення та налаштування надбудови «Картка клієнта».
description: Інсталяція та налаштування надбудови «Картка клієнта» для Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268069"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="fd0e3-103">Надбудова «Картка клієнта» (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="fd0e3-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="fd0e3-104">Отримайте повний огляд своїх клієнтів безпосередньо у програмах Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="fd0e3-105">Переглядайте демографічні дані, аналітичні огляди та часові шкали дій за допомогою надбудови «Картка клієнта».</span><span class="sxs-lookup"><span data-stu-id="fd0e3-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd0e3-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="fd0e3-106">Prerequisites</span></span>

- <span data-ttu-id="fd0e3-107">Програма Dynamics 365 (наприклад, Центр збуту або Центр підтримки клієнтів) версії 9.0 або пізнішої, із увімкненим єдиним інтерфейсом.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="fd0e3-108">Профілі клієнтів [прийняті з програми Dynamics 365 за допомогою Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="fd0e3-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="fd0e3-109">Користувачі надбудови «Картка клієнта» мають бути [додані як користувачі](permissions.md) у аналізі аудиторії.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="fd0e3-110">[Настроєні можливості пошуку та фільтрації](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="fd0e3-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="fd0e3-111">Демографічний елемент керування: демографічні поля (наприклад вік або стать) доступні в уніфікованому профілі клієнта.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="fd0e3-112">Елемент керування "Збагачення": обов'язково застосувати активні [збагачення](enrichment-hub.md) до профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="fd0e3-113">Інтелектуальний елемент керування: потрібні дані, згенеровані за допомогою машинного навчання Azure ([Прогнози](predictions.md) або [настроювані моделі](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="fd0e3-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="fd0e3-114">Елемент керування вимірюванням: потрібні [настроєні показники](measures.md).</span><span class="sxs-lookup"><span data-stu-id="fd0e3-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="fd0e3-115">Елемент керування часовою шкалою: вимагає [Настроювання справ](activities.md).</span><span class="sxs-lookup"><span data-stu-id="fd0e3-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="fd0e3-116">Інсталяція надбудови «Картка клієнта»</span><span class="sxs-lookup"><span data-stu-id="fd0e3-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="fd0e3-117">Надбудова Картка клієнта — це рішення для програм взаємодії з клієнтами у Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="fd0e3-118">Щоб інсталювати рішення, перейдіть до AppSource і виконайте пошук **Картка клієнта Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="fd0e3-119">Виберіть [Надбудова «Картка клієнта» в AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) і натисніть кнопку **Завантажити зараз**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="fd0e3-120">Вам слід увійти, використовуючи облікові дані адміністратора для програми Dynamics 365, щоб інсталювати це рішення.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="fd0e3-121">Інсталяція рішення в середовище може тривати певний час.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="fd0e3-122">Настроювання надбудови «Картка клієнта»</span><span class="sxs-lookup"><span data-stu-id="fd0e3-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="fd0e3-123">Із правами адміністратора перейдіть в розділ **Параметри** в Dynamics 365 і виберіть **Рішення**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="fd0e3-124">Перейдіть за посиланням **Коротке ім’я** для рішення **Надбудова «Картка клієнта» (підготовча версія) Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd0e3-125">![Вибір короткого імені](media/select-display-name.png "Вибір короткого імені")</span><span class="sxs-lookup"><span data-stu-id="fd0e3-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="fd0e3-126">Виберіть **Вхід** і введіть облікові дані для облікового запису адміністратора, за допомогою якого можна настроїти Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fd0e3-127">Переконайтеся, що блокувальник спливаючих елементів браузера не блокує вікно автентифікації, коли ви натискаєте кнопку **Вхід**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="fd0e3-128">Виберіть середовище, з якого вам потрібно отримати дані.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="fd0e3-129">Визначте зіставлення полів із записами в програмі Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="fd0e3-130">Щоб зіставити з контактом, виберіть поле в сутності «Клієнт», що відповідає ідентифікатору сутності вашого контакту.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="fd0e3-131">Щоб зіставити з обліковим записом, виберіть поле в сутності «Клієнт», що відповідає ідентифікатору сутності вашого облікового запису.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd0e3-132">![Поле ідентифікатора «Контактна особа»](media/contact-id-field.png "Поле ідентифікатора «Контактна особа»")</span><span class="sxs-lookup"><span data-stu-id="fd0e3-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="fd0e3-133">Щоб зберегти настройки, натисніть кнопку **Зберегти конфігурацію**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="fd0e3-134">Потім потрібно призначити ролі безпеки в Dynamics 365, щоб користувачі могли настроювати й бачити картку клієнта.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="fd0e3-135">У Dynamics 365 перейдіть до **Настройки** > **Безпека** > **Користувачі**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="fd0e3-136">Виберіть користувачів для редагування ролей користувача, а потім виберіть **Керування ролями**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="fd0e3-137">Призначте роль **Настроювач карток Customer Insights** користувачам, котрі настроюватимуть вміст, що відображатиметься на картці для усієї організації.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="fd0e3-138">Додавання до форми елементів керування карти клієнта</span><span class="sxs-lookup"><span data-stu-id="fd0e3-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="fd0e3-139">Щоб додати елементи керування надбудови «Картка клієнта» до форми контактної особи, у Dynamics 365 виберіть **Настройки** > **Настроювання**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="fd0e3-140">Виберіть **Налаштування системи**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="fd0e3-141">Перейдіть до сутності **Контактна особа**, розгорніть її й виберіть **Форми**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="fd0e3-142">Виберіть форму контактної особи, до якої потрібно додати елементи керування надбудови «Картка клієнта».</span><span class="sxs-lookup"><span data-stu-id="fd0e3-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fd0e3-143">![Виберіть форму «Контактна особа»](media/contact-active-forms.png "Виберіть форму «Контактна особа»")</span><span class="sxs-lookup"><span data-stu-id="fd0e3-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="fd0e3-144">Щоб додати елемент керування, у редакторі форм перетягніть будь-яке поле з **провідника полів** до місця, в якому потрібно розмістити елемент керування.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="fd0e3-145">Виберіть у формі щойно додане поле й натисніть кнопку **Змінити властивості**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="fd0e3-146">Перейдіть на вкладку **Елементи керування** та виберіть **Додати елемент керування**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="fd0e3-147">Виберіть один із доступних настроюваних елементів керування та натисніть кнопку **Додати**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="fd0e3-148">У діалоговому вікні **Властивості поля** зніміть прапорець **Відображати підпис у формі**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="fd0e3-149">Виберіть параметр **Веб** для елемента керування.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="fd0e3-150">Для елементу керування "Збагачення" виберіть тип збагачення, який необхідно відобразити, настроївши поле **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="fd0e3-151">Додайте окремий елемент керування збагаченням для кожного типу збагачення.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="fd0e3-152">Виберіть **Зберегти** й **Опублікувати**, щоб опублікувати оновлену форму контактної особи.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="fd0e3-153">Виберіть опубліковану форму контактної особи.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-153">Go to the published contact form.</span></span> <span data-ttu-id="fd0e3-154">Відобразиться новий доданий елемент керування.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-154">You'll see the newly added control.</span></span> <span data-ttu-id="fd0e3-155">Можливо, знадобиться ввійти в обліковий запис під час його першого використання.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="fd0e3-156">Щоб настроїти дані, які будуть відображатися в настроюваному елементі керування, натисніть кнопку редагування в правому верхньому кутку.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="fd0e3-157">Оновлення надбудови «Картка клієнта»</span><span class="sxs-lookup"><span data-stu-id="fd0e3-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="fd0e3-158">Надбудова «Картка клієнта» не оновлюється автоматично.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="fd0e3-159">Щоб оновити її до останньої версії, виконайте у програмі Dynamics 365, до якої інстальовано цю надбудову зазначені нижче дії.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="fd0e3-160">У програмі Dynamics 365 відкрийте **Параметри** > **Настроювання** та виберіть **Рішення**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="fd0e3-161">У таблиці надбудов знайдіть **CustomerInsightsCustomerCard** й виберіть рядок.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="fd0e3-162">На панелі завдань виберіть **Застосувати оновлення рішення**.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Оновлення рішення в області настроювання програм Dynamics 365":::

1. <span data-ttu-id="fd0e3-164">Після початку процесу оновлення ви побачите індикатор завантаження, який не зникне, доки оновлення не завершиться.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="fd0e3-165">Якщо новішої версії немає, під час оновлення з'явиться повідомлення про помилку.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]