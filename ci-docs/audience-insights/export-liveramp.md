---
title: З’єднувач LiveRamp
description: Дізнайтеся, як експортувати дані до LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270183"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="62f81-103">З’єднувач LiveRamp&reg; (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="62f81-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="62f81-104">Активуйте дані в LiveRamp, щоб з’єднатися з більш ніж 500 платформами в різноманітних цифрових, соціальних і телевізійних екосистемах.</span><span class="sxs-lookup"><span data-stu-id="62f81-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="62f81-105">Працюйте з даними в LiveRamp для націлювання, заборони та персоналізації рекламних кампаній.</span><span class="sxs-lookup"><span data-stu-id="62f81-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="62f81-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="62f81-106">Prerequisites</span></span>

- <span data-ttu-id="62f81-107">Для використання цього з’єднувача необхідна передплата на LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="62f81-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="62f81-108">Передплату можна отримати безпосередньо в [компанії LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="62f81-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="62f81-109">[Дізнайтеся більше про LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="62f81-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="62f81-110">Підключення до LiveRamp</span><span class="sxs-lookup"><span data-stu-id="62f81-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="62f81-111">У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.</span><span class="sxs-lookup"><span data-stu-id="62f81-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="62f81-112">У плитці **LiveRamp** натисніть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="62f81-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="62f81-113">Дайте своєму призначенню ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="62f81-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="62f81-114">Укажіть **Ім’я користувача** та **Пароль** для свого облікового запису LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="62f81-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="62f81-115">Ці облікові дані можуть відрізнятися від ваших облікових даних LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="62f81-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="62f81-116">Виберіть елемент **Перевірити** для перевірки підключення до LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="62f81-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="62f81-117">Після успішної перевірки необхідно прийняти умови **конфіденційності й відповідності даних**, установивши прапорець **Приймаю**.</span><span class="sxs-lookup"><span data-stu-id="62f81-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="62f81-118">Натисніть кнопку **Далі**, щоб перейти до настроювання з’єднувача LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="62f81-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="62f81-119">Настроювання з’єднувача</span><span class="sxs-lookup"><span data-stu-id="62f81-119">Configure the connector</span></span>

1. <span data-ttu-id="62f81-120">У полі **Виберіть ідентифікатор ключа** виберіть один із варіантів, як-от **Адреса електронної пошти**, **Ім’я та адреса** або **Номер телефону**, який буде відправлено до LiveRamp для ідентифікації особистості.</span><span class="sxs-lookup"><span data-stu-id="62f81-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="62f81-121">Зіставте відповідні атрибути з об’єднаної сутності клієнта для вибраного ідентифікатора ключа.</span><span class="sxs-lookup"><span data-stu-id="62f81-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="62f81-122">Виберіть елемент **Додати атрибут**, щоб зіставити додаткові атрибути, які буде відправлено до LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="62f81-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="62f81-123">Відправка більшої кількості атрибутів ідентифікатора ключа до LiveRamp може забезпечити більш високий відсоток збігу.</span><span class="sxs-lookup"><span data-stu-id="62f81-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="62f81-124">Виберіть сегменти, які потрібно експортувати до LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="62f81-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="62f81-125">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="62f81-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="62f81-126">![З’єднувач LiveRamp із зіставленням атрибутів](media/export-liveramp-segments.png "З’єднувач LiveRamp із зіставленням атрибутів")</span><span class="sxs-lookup"><span data-stu-id="62f81-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="62f81-127">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="62f81-127">Export the data</span></span>

<span data-ttu-id="62f81-128">Експорт розпочнеться найближчим часом, якщо будуть виконані всі передумови для експорту.</span><span class="sxs-lookup"><span data-stu-id="62f81-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="62f81-129">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="62f81-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="62f81-130">Після успішного завершення експорту можна увійти в LiveRamp Onboarding для активації та розповсюдження даних.</span><span class="sxs-lookup"><span data-stu-id="62f81-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="62f81-131">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="62f81-131">Data privacy and compliance</span></span>

<span data-ttu-id="62f81-132">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Liveramp можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="62f81-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="62f81-133">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія Liveramp відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="62f81-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="62f81-134">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="62f81-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="62f81-135">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="62f81-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]