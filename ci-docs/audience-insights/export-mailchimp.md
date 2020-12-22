---
title: Експорт даних Customer Insights до Mailchimp
description: Дізнайтесь, як настроїти підключення до Mailchimp
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407238"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="d8e56-103">З'єднувач для Mailchimp (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="d8e56-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="d8e56-104">Експорт сегментів уніфікованих профілів клієнтів до Mailchimp для створення інформаційних бюлетенів і кампаній електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="d8e56-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d8e56-105">Вимоги</span><span class="sxs-lookup"><span data-stu-id="d8e56-105">Prerequisites</span></span>

-   <span data-ttu-id="d8e56-106">Ви маєте [обліковий запис Mailchimp](https://mailchimp.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="d8e56-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d8e56-107">У Mailchimp наявні аудиторії й відповідні ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="d8e56-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="d8e56-108">Для отримання додаткових відомостей див. [Аудиторії Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="d8e56-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="d8e56-109">Ви маєте [налаштовані сегменти](segments.md)</span><span class="sxs-lookup"><span data-stu-id="d8e56-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="d8e56-110">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="d8e56-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="d8e56-111">Підключення до MailChimp</span><span class="sxs-lookup"><span data-stu-id="d8e56-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="d8e56-112">Відкрийте **Адміністрування** > **Призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="d8e56-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d8e56-113">У розділі **Mailchimp** натисніть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="d8e56-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="d8e56-114">Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="d8e56-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d8e56-115">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="d8e56-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d8e56-116">Введіть **[ідентифікатор аудиторії Mailchimp](https://mailchimp.com/help/find-audience-id/)** і виберіть **З'єднати**, щоб ініціалізувати підключення до Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="d8e56-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="d8e56-117">Виберіть **Автентифікацію за допомогою Mailchimp** і надайте облікові дані Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="d8e56-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="d8e56-118">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d8e56-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Експорт скріншоту для підключення до Mailchimp":::

1. <span data-ttu-id="d8e56-120">Натисніть **Далі**, щоб налаштувати експорт.</span><span class="sxs-lookup"><span data-stu-id="d8e56-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="d8e56-121">Настроювання з’єднувача</span><span class="sxs-lookup"><span data-stu-id="d8e56-121">Configure the connector</span></span>

1. <span data-ttu-id="d8e56-122">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="d8e56-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="d8e56-123">Додатково можна експортувати **Ім'я** та **Прізвище** у вигляді додаткових полів для створення додаткових персоналізованих електронних листів.</span><span class="sxs-lookup"><span data-stu-id="d8e56-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="d8e56-124">Виберіть **Додати атрибут**, щоб зіставити ці поля.</span><span class="sxs-lookup"><span data-stu-id="d8e56-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d8e56-125">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="d8e56-125">Select the segments you want to export.</span></span> <span data-ttu-id="d8e56-126">Загалом до Mailchimp можна експортувати до 1 000 000 профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="d8e56-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Вибір полів і сегментів для експорту в Mailchimp":::

1. <span data-ttu-id="d8e56-128">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="d8e56-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d8e56-129">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="d8e56-129">Export the data</span></span>

<span data-ttu-id="d8e56-130">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d8e56-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d8e56-131">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d8e56-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d8e56-132">Тепер в Mailchimp можна знайти сегменти в розділі [Аудиторія Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="d8e56-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d8e56-133">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="d8e56-133">Known limitations</span></span>

- <span data-ttu-id="d8e56-134">До 1 000 000 профілів на експорт до Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="d8e56-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="d8e56-135">Експорт до Mailchimp обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="d8e56-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="d8e56-136">Експортування сегментів загальною кількістю 1 000 000 профілів може тривати до трьох годин через обмеження з боку постачальника.</span><span class="sxs-lookup"><span data-stu-id="d8e56-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="d8e56-137">Кількість профілів, які можна експортувати до Mailchimp, залежить від сервісного договору з Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="d8e56-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d8e56-138">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="d8e56-138">Data privacy and compliance</span></span>

<span data-ttu-id="d8e56-139">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Mailchimp можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="d8e56-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d8e56-140">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія Mailchimp відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="d8e56-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d8e56-141">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d8e56-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d8e56-142">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="d8e56-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
