---
title: Експорт даних Customer Insights до Autopilot
description: Дізнайтесь, як настроїти підключення до Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596156"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="e6a4d-103">З'єднувач для Autopilot (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="e6a4d-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="e6a4d-104">Експортуйте сегменти уніфікованих профілів клієнтів до Autopilot і використовуйте їх для маркетингових електронних розсилок в Autopilot.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e6a4d-105">Вимоги</span><span class="sxs-lookup"><span data-stu-id="e6a4d-105">Prerequisites</span></span>

-   <span data-ttu-id="e6a4d-106">Ви маєте [обліковий запис Autopilot](https://www.autopilothq.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e6a4d-107">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e6a4d-108">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="e6a4d-109">Підключення до Autopilot</span><span class="sxs-lookup"><span data-stu-id="e6a4d-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="e6a4d-110">Відкрийте **Адміністрування** > **Призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e6a4d-111">У розділі **Autopilot** натисніть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="e6a4d-112">Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Область налаштування для підключення Autopilot.":::

1. <span data-ttu-id="e6a4d-114">Уведіть **ключ API Autopilot** [ключ API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="e6a4d-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="e6a4d-115">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e6a4d-116">Виберіть **Підключити**, щоб ініціалізувати підключення до Autopilot.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="e6a4d-117">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e6a4d-118">Натисніть **Далі**, щоб налаштувати експорт.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e6a4d-119">Настроювання з’єднувача</span><span class="sxs-lookup"><span data-stu-id="e6a4d-119">Configure the connector</span></span>

1. <span data-ttu-id="e6a4d-120">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e6a4d-121">Повторіть ці самі кроки для інших необов'язкових полів, наприклад **Ім'я**, **Прізвище**.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="e6a4d-122">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-122">Select the segments you want to export.</span></span> <span data-ttu-id="e6a4d-123">Ми настійно **рекомендуємо не експортувати більше 100 000 профілів клієнтів в цілому** до Autopilot.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="e6a4d-124">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e6a4d-125">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="e6a4d-125">Export the data</span></span>

<span data-ttu-id="e6a4d-126">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e6a4d-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e6a4d-127">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e6a4d-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e6a4d-128">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="e6a4d-128">Known limitations</span></span>

- <span data-ttu-id="e6a4d-129">Загалом до Autopilot можна експортувати до 100 000 профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="e6a4d-130">Експорт до Autopilot обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="e6a4d-131">Експортування до 100 000 профілів до Autopilot може тривати кілька годин.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="e6a4d-132">Кількість профілів, які можна експортувати до Autopilot, залежить від сервісного договору з Autopilot.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e6a4d-133">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="e6a4d-133">Data privacy and compliance</span></span>

<span data-ttu-id="e6a4d-134">Вмикаючи в Dynamics 365 Customer Insights передавання даних до Autopilot, ви дозволяєте передавати дані за межі нормативного регіону Dynamics 365 Customer Insights, зокрема потенційно конфіденційні дані (наприклад, особисті дані).</span><span class="sxs-lookup"><span data-stu-id="e6a4d-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e6a4d-135">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але на вас покладено усю відповідальність за забезпечення того, щоб компанія Autopilot відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e6a4d-136">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e6a4d-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e6a4d-137">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="e6a4d-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]