---
title: Експорт даних Customer Insights до Google Ads
description: Дізнайтесь, як настроїти підключення до Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568517"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="1e095-103">З'єднувач для Google Ads (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="1e095-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="1e095-104">Експорт сегментів уніфікованих профілів клієнтів до списків аудиторій Google Ads та використовуйте їх для рекламування у Google Search, Gmail, YouTube і Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="1e095-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="1e095-105">Вимоги</span><span class="sxs-lookup"><span data-stu-id="1e095-105">Prerequisites</span></span>

-   <span data-ttu-id="1e095-106">Ви маєте [обліковий запис Google Ads](https://ads.google.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="1e095-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1e095-107">У Google Ads наявні аудиторії й відповідні ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="1e095-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="1e095-108">Для отримання додаткових відомостей див. [Аудиторії Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="1e095-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="1e095-109">Ви маєте [налаштовані сегменти](segments.md)</span><span class="sxs-lookup"><span data-stu-id="1e095-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="1e095-110">Уніфіковані профілі клієнтів у експортованих сегментах містять поля, що представляють адресу електронної пошти, ім'я та прізвище</span><span class="sxs-lookup"><span data-stu-id="1e095-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="1e095-111">Підключення до Google Ads</span><span class="sxs-lookup"><span data-stu-id="1e095-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="1e095-112">Відкрийте **Адміністрування** > **Призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="1e095-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1e095-113">У розділі **Google Ads** виберіть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="1e095-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="1e095-114">Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="1e095-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1e095-115">Введіть свій **[ідентифікатор клієнта Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="1e095-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="1e095-116">Введіть свій **[маркер, схвалений розробником Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="1e095-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="1e095-117">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="1e095-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1e095-118">Введіть **[ідентифікатор аудиторії Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** і виберіть **З'єднати**, щоб ініціалізувати підключення до Google Ads.</span><span class="sxs-lookup"><span data-stu-id="1e095-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="1e095-119">Виберіть **Автентифікацію за допомогою Google Ads** і надайте облікові дані Google Ads.</span><span class="sxs-lookup"><span data-stu-id="1e095-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="1e095-120">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1e095-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Експорт скріншоту для підключення до Google Ads":::

1. <span data-ttu-id="1e095-122">Натисніть **Далі**, щоб налаштувати експорт.</span><span class="sxs-lookup"><span data-stu-id="1e095-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="1e095-123">Настроювання з’єднувача</span><span class="sxs-lookup"><span data-stu-id="1e095-123">Configure the connector</span></span>

1. <span data-ttu-id="1e095-124">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="1e095-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1e095-125">повторіть ці самі кроки для полів **Ім’я** і **Прізвище**.</span><span class="sxs-lookup"><span data-stu-id="1e095-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="1e095-126">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="1e095-126">Select the segments you want to export.</span></span> <span data-ttu-id="1e095-127">Загалом до Google Ads можна експортувати до 1 000 000 профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="1e095-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="1e095-128">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="1e095-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1e095-129">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="1e095-129">Export the data</span></span>

<span data-ttu-id="1e095-130">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1e095-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1e095-131">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1e095-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1e095-132">Тепер в Google Ads можна знайти сегменти в розділі [Аудиторія Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="1e095-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1e095-133">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="1e095-133">Known limitations</span></span>

- <span data-ttu-id="1e095-134">До 1 000 000 профілів на експорт до Google Ads.</span><span class="sxs-lookup"><span data-stu-id="1e095-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="1e095-135">Експорт до Google Ads обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="1e095-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="1e095-136">Експортування сегментів загальною кількістю 1 000 000 профілів може тривати до 5 хвилин через обмеження з боку постачальника.</span><span class="sxs-lookup"><span data-stu-id="1e095-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="1e095-137">Зіставлення в Google Ads може тривати до 48 годин.</span><span class="sxs-lookup"><span data-stu-id="1e095-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1e095-138">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="1e095-138">Data privacy and compliance</span></span>

<span data-ttu-id="1e095-139">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Google Ads можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="1e095-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1e095-140">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб Google Ads відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="1e095-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="1e095-141">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1e095-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1e095-142">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="1e095-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
