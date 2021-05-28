---
title: Експорт даних Customer Insights до Facebook Ads Manager
description: Дізнайтеся, як налаштувати підключення та експорт до Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976067"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="edd9f-103">Експорт списку сегментів до Facebook Ads Manager (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="edd9f-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="edd9f-104">Експортуйте сегменти уніфікованих профілів клієнтів до Менеджера реклами Facebook, щоб створити кампанії у Facebook та Instagram.</span><span class="sxs-lookup"><span data-stu-id="edd9f-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="edd9f-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="edd9f-105">Prerequisites for connection</span></span>

- <span data-ttu-id="edd9f-106">Вам необхідно мати [**Рекламний обліковий запис Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), який містить [**корпоративний обліковий запис Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="edd9f-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="edd9f-107">Потрібно бути адміністратором [Рекламного облікового запису **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)..</span><span class="sxs-lookup"><span data-stu-id="edd9f-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="edd9f-108">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="edd9f-108">Known limitations</span></span>

- <span data-ttu-id="edd9f-109">До 10 мільйонів профілів клієнтів на один експорт до Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="edd9f-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="edd9f-110">Експорт до Facebook Ads Manager обмежено сегментами.</span><span class="sxs-lookup"><span data-stu-id="edd9f-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="edd9f-111">Створюйте та оновлюйте у Facebook настроювані аудиторії лише типу *список клієнтів*.</span><span class="sxs-lookup"><span data-stu-id="edd9f-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="edd9f-112">Експортування сегментів загальною кількістю 10 мільйонів профілів може тривати до 90 хвилин.</span><span class="sxs-lookup"><span data-stu-id="edd9f-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="edd9f-113">Налаштування підключення до Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="edd9f-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="edd9f-114">Щоб користувачі могли створювати експорти, адміністратор повинен налаштувати підключення до послуги та дозволити співавторам використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="edd9f-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="edd9f-115">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="edd9f-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="edd9f-116">Виберіть **Додати підключення** та оберіть **Facebook Ads Manager**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="edd9f-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="edd9f-117">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="edd9f-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="edd9f-118">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="edd9f-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="edd9f-119">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="edd9f-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="edd9f-120">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="edd9f-120">Choose who can use this connection.</span></span> <span data-ttu-id="edd9f-121">Якщо не вжити жодних дій, за замовчуванням це будуть **Адміністратори**.</span><span class="sxs-lookup"><span data-stu-id="edd9f-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="edd9f-122">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="edd9f-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="edd9f-123">Пройдіть автентифікацію на Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="edd9f-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="edd9f-124">Виберіть **Продовжити у Facebook**, щоб увійти до рекламного облікового запису Facebook.</span><span class="sxs-lookup"><span data-stu-id="edd9f-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="edd9f-125">Надайте дозвіл **ads_management** після автентифікація за допомогою Facebook.</span><span class="sxs-lookup"><span data-stu-id="edd9f-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="edd9f-126">Виберіть **Рекламний обліковий запис Facebook**, в якому потрібно працювати.</span><span class="sxs-lookup"><span data-stu-id="edd9f-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="edd9f-127">Виберіть **Наявну настроювану аудиторію** з розкривного списку або створіть **Нову настроювану аудиторію**.</span><span class="sxs-lookup"><span data-stu-id="edd9f-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="edd9f-128">Для отримання додаткових відомостей див. [**Аудиторія у Менеджері реклами Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="edd9f-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="edd9f-129">За допомогою цього експорту можна створювати або оновлювати на Facebook настроювані аудиторії лише типу *список клієнтів*.</span><span class="sxs-lookup"><span data-stu-id="edd9f-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="edd9f-130">У деяких випадках у розкривному списку відображатимуться настроювані аудиторії різних типів.</span><span class="sxs-lookup"><span data-stu-id="edd9f-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="edd9f-131">Якщо вибрати тип, відмінний від *списку клієнтів*, експорт не вдасться.</span><span class="sxs-lookup"><span data-stu-id="edd9f-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="edd9f-132">Перегляньте декларацію про **Конфіденційність і відповідність даних** і виберіть **Приймаю**.</span><span class="sxs-lookup"><span data-stu-id="edd9f-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="edd9f-133">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="edd9f-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="edd9f-134">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="edd9f-134">Configure an export</span></span>

<span data-ttu-id="edd9f-135">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="edd9f-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="edd9f-136">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="edd9f-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="edd9f-137">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="edd9f-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="edd9f-138">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="edd9f-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="edd9f-139">Відкрийте **Підключення для експорту** і виберіть підключення в розділі **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="edd9f-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="edd9f-140">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="edd9f-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="edd9f-141">У полі **Вибір основного ідентифікатора**, виберіть **Повідомлення електронної пошти**, **Ім'я та адреса** або **Телефон**, щоб надсилати до Менеджера реклами Facebook.</span><span class="sxs-lookup"><span data-stu-id="edd9f-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="edd9f-142">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="edd9f-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="edd9f-143">Зіставте відповідні атрибути з об’єднаної сутності клієнта для вибраного ідентифікатора ключа.</span><span class="sxs-lookup"><span data-stu-id="edd9f-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="edd9f-144">Порада. Кращі шанси на відповідність будуть тоді, коли вибрати **електронну пошту** як основний ідентифікатор.</span><span class="sxs-lookup"><span data-stu-id="edd9f-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="edd9f-145">Зіставлення може покращитися, якщо додавати додаткові ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="edd9f-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="edd9f-146">Виберіть **Додати атрибут**, щоб зіставити інші атрибути, що надсилатимуться до Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="edd9f-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="edd9f-147">Атрибути з Facebook Ads Manager зіставляються з такими зрозумілими іменами: **FN** = **Ім'я**, **LN** = **Прізвище**, **FI** = **Ініціали**, **PHONE** = **Телефон**, **GEN** = **Стать**, **DOB** = **Дата народження**, **ST** = **Область**, **CT** = **Місто**, **ZIP** = **Поштовий індекс**, **COUNTRY** = **Країна**</span><span class="sxs-lookup"><span data-stu-id="edd9f-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="edd9f-148">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="edd9f-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="edd9f-149">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="edd9f-149">Select **Save**.</span></span>

<span data-ttu-id="edd9f-150">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="edd9f-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="edd9f-151">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="edd9f-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="edd9f-152">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="edd9f-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="edd9f-153">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="edd9f-153">Data privacy and compliance</span></span>

<span data-ttu-id="edd9f-154">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Facebook Ads Manager можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="edd9f-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="edd9f-155">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб Facebook Ads відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="edd9f-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="edd9f-156">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="edd9f-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="edd9f-157">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="edd9f-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
