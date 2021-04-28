---
title: Експорт даних Customer Insights до Mailchimp
description: Дізнайтеся, як налаштувати підключення та експорт до Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759903"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="0caf1-103">Експорт списків сегментів до Mailchimp (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="0caf1-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="0caf1-104">Експорт сегментів уніфікованих профілів клієнтів до Mailchimp для створення інформаційних бюлетенів і кампаній електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="0caf1-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0caf1-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="0caf1-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="0caf1-106">Ви маєте [обліковий запис Mailchimp](https://mailchimp.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="0caf1-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0caf1-107">У Mailchimp наявні аудиторії й відповідні ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="0caf1-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="0caf1-108">Для отримання додаткових відомостей див. [Аудиторії Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="0caf1-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="0caf1-109">Ви маєте [налаштовані сегменти](segments.md)</span><span class="sxs-lookup"><span data-stu-id="0caf1-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="0caf1-110">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="0caf1-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0caf1-111">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="0caf1-111">Known limitations</span></span>

- <span data-ttu-id="0caf1-112">До 1 000 000 профілів на експорт до Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0caf1-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="0caf1-113">Експорт до Mailchimp обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="0caf1-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="0caf1-114">Експорт сегментів з 1 мільйоном профілів може тривати до трьох годин.</span><span class="sxs-lookup"><span data-stu-id="0caf1-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="0caf1-115">Кількість профілів, які можна експортувати до Mailchimp, залежить від сервісного договору з Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0caf1-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="0caf1-116">Налаштування підключення до Mailchimp</span><span class="sxs-lookup"><span data-stu-id="0caf1-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="0caf1-117">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="0caf1-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0caf1-118">Виберіть **Додати підключення** та оберіть **Mailchimp**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="0caf1-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="0caf1-119">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="0caf1-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0caf1-120">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="0caf1-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0caf1-121">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="0caf1-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0caf1-122">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="0caf1-122">Choose who can use this connection.</span></span> <span data-ttu-id="0caf1-123">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="0caf1-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0caf1-124">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0caf1-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0caf1-125">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="0caf1-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0caf1-126">Виберіть **Підключити**, щоб ініціалізувати підключення до Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0caf1-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="0caf1-127">Виберіть **Автентифікацію за допомогою Mailchimp** і надайте облікові дані Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0caf1-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="0caf1-128">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0caf1-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0caf1-129">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="0caf1-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="0caf1-130">Настроювання з’єднувача</span><span class="sxs-lookup"><span data-stu-id="0caf1-130">Configure the connector</span></span>

<span data-ttu-id="0caf1-131">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="0caf1-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0caf1-132">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0caf1-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0caf1-133">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="0caf1-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="0caf1-134">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="0caf1-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0caf1-135">У полі **Підключення для експорту** виберіть підключення з розділу Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0caf1-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="0caf1-136">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="0caf1-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0caf1-137">Уведіть свій **[Ідентифікатор аудиторії Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="0caf1-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="0caf1-138">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="0caf1-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0caf1-139">За бажанням ви можете експортувати **Ім'я** та **Прізвище**, щоб створювати більш персоналізовані електронні листи.</span><span class="sxs-lookup"><span data-stu-id="0caf1-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="0caf1-140">Виберіть **Додати атрибут**, щоб зіставити ці поля.</span><span class="sxs-lookup"><span data-stu-id="0caf1-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0caf1-141">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="0caf1-141">Select the segments you want to export.</span></span> <span data-ttu-id="0caf1-142">Загалом до Mailchimp можна експортувати до 1 000 000 профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="0caf1-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="0caf1-143">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="0caf1-143">Select **Save**.</span></span>

<span data-ttu-id="0caf1-144">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="0caf1-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0caf1-145">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0caf1-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0caf1-146">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0caf1-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0caf1-147">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="0caf1-147">Data privacy and compliance</span></span>

<span data-ttu-id="0caf1-148">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Mailchimp можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="0caf1-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0caf1-149">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія Mailchimp відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="0caf1-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0caf1-150">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0caf1-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0caf1-151">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="0caf1-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
