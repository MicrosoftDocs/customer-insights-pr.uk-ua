---
title: Експорт даних Customer Insights до SendGrid
description: Дізнайтесь, як налаштувати підключення до SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268757"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="2f44f-103">З'єднувач для SendGrid (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="2f44f-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="2f44f-104">Експортуйте сегменти уніфікованих профілів клієнтів до списків контактних осіб SendGrid і використовуйте їх для кампаній та маркетингових електронних розсилок в SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2f44f-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="2f44f-105">Вимоги</span><span class="sxs-lookup"><span data-stu-id="2f44f-105">Prerequisites</span></span>

-   <span data-ttu-id="2f44f-106">Ви маєте [обліковий запис SendGrid](https://sendgrid.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="2f44f-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2f44f-107">У SendGrid наявні списки контактних осіб й відповідні ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="2f44f-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="2f44f-108">Для отримання додаткових відомостей див. [SendGrid — Керування контактними особами](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="2f44f-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="2f44f-109">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="2f44f-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2f44f-110">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="2f44f-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="2f44f-111">Підключення до SendGrid</span><span class="sxs-lookup"><span data-stu-id="2f44f-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="2f44f-112">Відкрийте **Адміністрування** > **Призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="2f44f-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2f44f-113">У розділі **SendGrid** натисніть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="2f44f-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="2f44f-114">Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="2f44f-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Область налаштування експорту SendGrid.":::

1. <span data-ttu-id="2f44f-116">Введіть **ключ API SendGrid** [ключ API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="2f44f-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="2f44f-117">Введіть **[ідентифікатор списку SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="2f44f-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="2f44f-118">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="2f44f-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2f44f-119">Виберіть **Підключити**, щоб ініціалізувати підключення до SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2f44f-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="2f44f-120">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2f44f-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2f44f-121">Натисніть **Далі**, щоб налаштувати експорт.</span><span class="sxs-lookup"><span data-stu-id="2f44f-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="2f44f-122">Настроювання з’єднувача</span><span class="sxs-lookup"><span data-stu-id="2f44f-122">Configure the connector</span></span>

1. <span data-ttu-id="2f44f-123">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="2f44f-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2f44f-124">Повторіть ці самі кроки для інших необов'язкових полів, таких як **Ім'я**, **Прізвище**, **Країна або регіон**, **Штат**, **Місто** і **Поштовий індекс**.</span><span class="sxs-lookup"><span data-stu-id="2f44f-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="2f44f-125">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="2f44f-125">Select the segments you want to export.</span></span> <span data-ttu-id="2f44f-126">Ми настійно **рекомендуємо не експортувати більше 100 000 профілів клієнтів в цілому** до SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2f44f-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="2f44f-127">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="2f44f-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2f44f-128">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="2f44f-128">Export the data</span></span>

<span data-ttu-id="2f44f-129">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2f44f-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2f44f-130">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2f44f-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2f44f-131">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="2f44f-131">Known limitations</span></span>

- <span data-ttu-id="2f44f-132">До 100 000 профілів в цілому до SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2f44f-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="2f44f-133">Експорт до SendGrid обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="2f44f-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="2f44f-134">Експортування до 100 000 профілів до SendGrid може тривати кілька годин.</span><span class="sxs-lookup"><span data-stu-id="2f44f-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="2f44f-135">Кількість профілів, які можна експортувати до SendGrid, залежить від сервісного договору з SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2f44f-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2f44f-136">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="2f44f-136">Data privacy and compliance</span></span>

<span data-ttu-id="2f44f-137">Коли ви вмикаєте передавання даних до SendGrid у Dynamics 365 Customer Insights, ви дозволяєте перенесення даних за межі нормативного регіону для Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="2f44f-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2f44f-138">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але на вас покладено усю відповідальність за забезпечення того, щоб компанія SendGrid відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки.</span><span class="sxs-lookup"><span data-stu-id="2f44f-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="2f44f-139">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2f44f-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2f44f-140">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="2f44f-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]