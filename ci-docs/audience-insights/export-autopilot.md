---
title: Експорт даних Customer Insights до Autopilot
description: Дізнайтеся, як налаштувати підключення та експорт до Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760168"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="3b201-103">Експорт сегментів до Autopilot (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="3b201-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="3b201-104">Експортуйте сегменти уніфікованих профілів клієнтів до Autopilot і використовуйте їх для маркетингових електронних розсилок в Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3b201-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="3b201-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="3b201-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="3b201-106">Ви маєте [обліковий запис Autopilot](https://www.autopilothq.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="3b201-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3b201-107">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="3b201-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3b201-108">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="3b201-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3b201-109">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="3b201-109">Known limitations</span></span>

- <span data-ttu-id="3b201-110">Загалом до Autopilot можна експортувати до 100 000 профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="3b201-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="3b201-111">Експорт до Autopilot обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="3b201-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="3b201-112">Експортування до 100 000 профілів до Autopilot може тривати кілька годин.</span><span class="sxs-lookup"><span data-stu-id="3b201-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="3b201-113">Кількість профілів, які можна експортувати до Autopilot, залежить від сервісного договору з Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3b201-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="3b201-114">Налаштування підключення до Autopilot</span><span class="sxs-lookup"><span data-stu-id="3b201-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="3b201-115">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="3b201-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3b201-116">Виберіть **Додати підключення** та оберіть **Mailchimp**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="3b201-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="3b201-117">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="3b201-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3b201-118">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="3b201-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3b201-119">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="3b201-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3b201-120">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="3b201-120">Choose who can use this connection.</span></span> <span data-ttu-id="3b201-121">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="3b201-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3b201-122">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3b201-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="3b201-123">Введіть ключ [API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="3b201-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="3b201-124">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="3b201-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3b201-125">Виберіть **Підключити**, щоб ініціалізувати підключення до Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3b201-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="3b201-126">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3b201-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3b201-127">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="3b201-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3b201-128">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="3b201-128">Configure an export</span></span>

<span data-ttu-id="3b201-129">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="3b201-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3b201-130">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3b201-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3b201-131">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="3b201-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3b201-132">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="3b201-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3b201-133">У полі **Підключення для експорту** виберіть підключення з розділу Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3b201-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="3b201-134">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="3b201-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="3b201-135">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="3b201-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3b201-136">Повторіть ці самі кроки для інших необов'язкових полів, наприклад **Ім'я**, **Прізвище**.</span><span class="sxs-lookup"><span data-stu-id="3b201-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="3b201-137">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="3b201-137">Select the segments you want to export.</span></span> <span data-ttu-id="3b201-138">Ми настійно **рекомендуємо не експортувати більше 100 000 профілів клієнтів в цілому** до Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3b201-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="3b201-139">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="3b201-139">Select **Save**.</span></span>

<span data-ttu-id="3b201-140">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="3b201-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3b201-141">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3b201-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3b201-142">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3b201-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3b201-143">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="3b201-143">Data privacy and compliance</span></span>

<span data-ttu-id="3b201-144">Вмикаючи в Dynamics 365 Customer Insights передавання даних до Autopilot, ви дозволяєте передавати дані за межі нормативного регіону Dynamics 365 Customer Insights, зокрема потенційно конфіденційні дані (наприклад, особисті дані).</span><span class="sxs-lookup"><span data-stu-id="3b201-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3b201-145">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але на вас покладено усю відповідальність за забезпечення того, щоб компанія Autopilot відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки.</span><span class="sxs-lookup"><span data-stu-id="3b201-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="3b201-146">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3b201-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3b201-147">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="3b201-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
