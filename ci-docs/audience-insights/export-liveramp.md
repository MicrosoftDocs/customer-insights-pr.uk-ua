---
title: З’єднувач LiveRamp
description: Дізнайтеся, як налаштувати підключення та експорт до LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760352"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="9ed31-103">Експорт сегментів до LiveRamp&reg; (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="9ed31-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="9ed31-104">Активуйте дані в LiveRamp, щоб підключатися до понад 500 платформ за допомогою цифрових, соціальних і телевізійних каналів.</span><span class="sxs-lookup"><span data-stu-id="9ed31-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="9ed31-105">Працюйте з даними в LiveRamp для націлювання, заборони та персоналізації рекламних кампаній.</span><span class="sxs-lookup"><span data-stu-id="9ed31-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="9ed31-106">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="9ed31-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="9ed31-107">Для використання цього з’єднувача необхідна передплата на LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="9ed31-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="9ed31-108">Передплату можна отримати безпосередньо в [компанії LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="9ed31-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="9ed31-109">[Дізнайтеся більше про LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="9ed31-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="9ed31-110">Налаштування підключення до LiveRamp</span><span class="sxs-lookup"><span data-stu-id="9ed31-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="9ed31-111">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="9ed31-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9ed31-112">Виберіть **Додати підключення** та оберіть **LiveRamp**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="9ed31-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="9ed31-113">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="9ed31-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9ed31-114">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="9ed31-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9ed31-115">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="9ed31-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9ed31-116">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="9ed31-116">Choose who can use this connection.</span></span> <span data-ttu-id="9ed31-117">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="9ed31-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9ed31-118">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9ed31-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9ed31-119">Укажіть **Ім’я користувача** та **Пароль** для свого облікового запису LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="9ed31-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="9ed31-120">Ці облікові дані можуть відрізнятися від ваших облікових даних LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="9ed31-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="9ed31-121">Виберіть елемент **Перевірити** для перевірки підключення до LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="9ed31-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="9ed31-122">Після успішної перевірки необхідно прийняти умови **конфіденційності й відповідності даних**, установивши прапорець **Приймаю**.</span><span class="sxs-lookup"><span data-stu-id="9ed31-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="9ed31-123">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="9ed31-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9ed31-124">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="9ed31-124">Configure an export</span></span>

<span data-ttu-id="9ed31-125">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="9ed31-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9ed31-126">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9ed31-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9ed31-127">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="9ed31-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9ed31-128">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="9ed31-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9ed31-129">У полі **Підключення для експорту** виберіть підключення з розділу LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="9ed31-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="9ed31-130">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="9ed31-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9ed31-131">У полі **Виберіть ідентифікатор ключа** виберіть один із варіантів, як-от **Адреса електронної пошти**, **Ім’я та адреса** або **Номер телефону**, який буде відправлено до LiveRamp для ідентифікації особистості.</span><span class="sxs-lookup"><span data-stu-id="9ed31-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9ed31-132">![З’єднувач LiveRamp із зіставленням атрибутів](media/export-liveramp-segments.png "З’єднувач LiveRamp із зіставленням атрибутів")</span><span class="sxs-lookup"><span data-stu-id="9ed31-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="9ed31-133">Зіставте відповідні атрибути з об’єднаної сутності клієнта для вибраного ідентифікатора ключа.</span><span class="sxs-lookup"><span data-stu-id="9ed31-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="9ed31-134">Виберіть **Додати атрибут**, щоб зіставити інші атрибути, що надсилатимуться до LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="9ed31-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="9ed31-135">Відправка більшої кількості атрибутів ідентифікатора ключа до LiveRamp може забезпечити більш високий відсоток збігу.</span><span class="sxs-lookup"><span data-stu-id="9ed31-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="9ed31-136">Виберіть сегменти, які потрібно експортувати до LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="9ed31-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="9ed31-137">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="9ed31-137">Select **Save**.</span></span>

<span data-ttu-id="9ed31-138">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="9ed31-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9ed31-139">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9ed31-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9ed31-140">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9ed31-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9ed31-141">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="9ed31-141">Data privacy and compliance</span></span>

<span data-ttu-id="9ed31-142">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Liveramp можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="9ed31-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9ed31-143">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія Liveramp відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="9ed31-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9ed31-144">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9ed31-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9ed31-145">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="9ed31-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
