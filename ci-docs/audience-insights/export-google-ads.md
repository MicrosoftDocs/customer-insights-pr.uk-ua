---
title: Експорт даних Customer Insights до Google Ads
description: Дізнайтеся, як налаштувати підключення та експорт до Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759800"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="901cb-103">Експорт сегментів до Google Ads (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="901cb-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="901cb-104">Експорт сегментів уніфікованих профілів клієнтів до списків аудиторій Google Ads та використовуйте їх для рекламування у Google Search, Gmail, YouTube і Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="901cb-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="901cb-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="901cb-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="901cb-106">Ви маєте [обліковий запис Google Ads](https://ads.google.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="901cb-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="901cb-107">У вас є [затверджений маркер розробника Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="901cb-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="901cb-108">Ви відповідаєте вимогам [Політики заставлення клієнтів](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="901cb-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="901cb-109">Ви відповідаєте вимогам щодо [розмірів списку ремаркетингу](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="901cb-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="901cb-110">У Google Ads наявні аудиторії й відповідні ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="901cb-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="901cb-111">Для отримання додаткових відомостей див. [Аудиторії Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="901cb-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="901cb-112">Ви маєте [налаштовані сегменти](segments.md)</span><span class="sxs-lookup"><span data-stu-id="901cb-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="901cb-113">Уніфіковані профілі клієнтів у експортованих сегментах містять поля, що представляють адресу електронної пошти, ім'я та прізвище</span><span class="sxs-lookup"><span data-stu-id="901cb-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="901cb-114">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="901cb-114">Known limitations</span></span>

- <span data-ttu-id="901cb-115">До 1 000 000 профілів на експорт до Google Ads.</span><span class="sxs-lookup"><span data-stu-id="901cb-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="901cb-116">Експорт до Google Ads обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="901cb-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="901cb-117">Експортування сегментів загальною кількістю 1 000 000 профілів може тривати до 5 хвилин через обмеження з боку постачальника.</span><span class="sxs-lookup"><span data-stu-id="901cb-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="901cb-118">Зіставлення в Google Ads може тривати до 48 годин.</span><span class="sxs-lookup"><span data-stu-id="901cb-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="901cb-119">Налаштування підключення до Google Ads</span><span class="sxs-lookup"><span data-stu-id="901cb-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="901cb-120">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="901cb-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="901cb-121">Виберіть **Додати підключення** та оберіть **Google Ads**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="901cb-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="901cb-122">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="901cb-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="901cb-123">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="901cb-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="901cb-124">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="901cb-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="901cb-125">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="901cb-125">Choose who can use this connection.</span></span> <span data-ttu-id="901cb-126">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="901cb-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="901cb-127">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="901cb-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="901cb-128">Введіть свій **[ідентифікатор клієнта Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="901cb-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="901cb-129">Введіть свій **[маркер, схвалений розробником Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="901cb-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="901cb-130">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="901cb-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="901cb-131">Виберіть **Автентифікацію за допомогою Google Ads** і надайте облікові дані Google Ads.</span><span class="sxs-lookup"><span data-stu-id="901cb-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="901cb-132">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="901cb-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="901cb-133">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="901cb-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="901cb-134">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="901cb-134">Configure an export</span></span>

<span data-ttu-id="901cb-135">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="901cb-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="901cb-136">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="901cb-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="901cb-137">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="901cb-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="901cb-138">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="901cb-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="901cb-139">У полі **Підключення для експорту** виберіть підключення з розділу Google Ads.</span><span class="sxs-lookup"><span data-stu-id="901cb-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="901cb-140">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="901cb-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="901cb-141">Введіть **[ідентифікатор аудиторії Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** і виберіть **З'єднати**, щоб ініціалізувати підключення до Google Ads.</span><span class="sxs-lookup"><span data-stu-id="901cb-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="901cb-142">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="901cb-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="901cb-143">повторіть ці самі кроки для полів **Ім’я** і **Прізвище**.</span><span class="sxs-lookup"><span data-stu-id="901cb-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="901cb-144">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="901cb-144">Select the segments you want to export.</span></span> <span data-ttu-id="901cb-145">Загалом до Google Ads можна експортувати до 1 000 000 профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="901cb-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="901cb-146">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="901cb-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="901cb-147">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="901cb-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="901cb-148">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="901cb-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="901cb-149">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="901cb-149">Data privacy and compliance</span></span>

<span data-ttu-id="901cb-150">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Google Ads можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="901cb-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="901cb-151">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб Google Ads відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="901cb-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="901cb-152">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="901cb-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="901cb-153">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="901cb-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
