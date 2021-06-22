---
title: Експорт даних Customer Insights до Microsoft Advertising
description: Дізнайтеся, як налаштувати підключення та експорт до Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124567"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="9edd8-103">Експорт сегментів до Microsoft Advertising (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="9edd8-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="9edd8-104">Експортуйте сегменти Customer Insights до Microsoft Advertising та створіть аудиторії Customer Match.</span><span class="sxs-lookup"><span data-stu-id="9edd8-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="9edd8-105">Використовуйте ці аудиторії для своїх рекламних кампаній.</span><span class="sxs-lookup"><span data-stu-id="9edd8-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9edd8-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="9edd8-106">Prerequisites</span></span>

-   <span data-ttu-id="9edd8-107">[Обліковий запис Microsoft Advertising](https://ads.microsoft.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="9edd8-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9edd8-108">Ви прийняли умови використання Customer Match.</span><span class="sxs-lookup"><span data-stu-id="9edd8-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="9edd8-109">[Налаштовані сегменти](segments.md) у аналізі аудиторій.</span><span class="sxs-lookup"><span data-stu-id="9edd8-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="9edd8-110">Уніфіковані профілі клієнтів в експортованих сегментах містять поле з адресою електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="9edd8-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9edd8-111">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="9edd8-111">Known limitations</span></span>

- <span data-ttu-id="9edd8-112">У кожному експорті до Microsoft Advertising можна експортувати до 500 000 профілів.</span><span class="sxs-lookup"><span data-stu-id="9edd8-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="9edd8-113">Експортувати в Microsoft Advertising можна тільки сегменти.</span><span class="sxs-lookup"><span data-stu-id="9edd8-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="9edd8-114">Експортування до 500 000 профілів до Microsoft Advertising може тривати до 10 хвилин.</span><span class="sxs-lookup"><span data-stu-id="9edd8-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="9edd8-115">Настройка підключення до Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="9edd8-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="9edd8-116">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="9edd8-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9edd8-117">Виберіть **Додати підключення**, потім виберіть **Microsoft Advertising**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="9edd8-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="9edd8-118">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="9edd8-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9edd8-119">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="9edd8-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9edd8-120">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="9edd8-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9edd8-121">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="9edd8-121">Choose who can use this connection.</span></span> <span data-ttu-id="9edd8-122">За замовчуванням це будуть адміністратори.</span><span class="sxs-lookup"><span data-stu-id="9edd8-122">The default is administrators.</span></span> <span data-ttu-id="9edd8-123">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9edd8-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9edd8-124">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="9edd8-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9edd8-125">Виберіть **Підключити**, щоб ініціалізувати підключення до Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="9edd8-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="9edd8-126">Виберіть **Автентифікація в Microsoft Advertising** і введіть облікові дані адміністратора Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="9edd8-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="9edd8-127">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9edd8-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9edd8-128">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="9edd8-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9edd8-129">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="9edd8-129">Configure an export</span></span>

<span data-ttu-id="9edd8-130">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="9edd8-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9edd8-131">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9edd8-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9edd8-132">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="9edd8-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9edd8-133">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="9edd8-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9edd8-134">У полі **Підключення для експорту** виберіть підключення з розділу «Microsoft Advertising».</span><span class="sxs-lookup"><span data-stu-id="9edd8-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="9edd8-135">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="9edd8-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9edd8-136">Виберіть сегменти для експорту.</span><span class="sxs-lookup"><span data-stu-id="9edd8-136">Select the segments to export.</span></span> <span data-ttu-id="9edd8-137">Аудиторії Customer Match у Microsoft Advertising створюються автоматично і отримують назви, що відповідають назвам вибраних для експорту сегментів.</span><span class="sxs-lookup"><span data-stu-id="9edd8-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="9edd8-138">В результаті для кожного сегмента буде створено окрему аудиторію Customer Match.</span><span class="sxs-lookup"><span data-stu-id="9edd8-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="9edd8-139">Уведіть **ідентифікатор клієнта та ідентифікатор облікового запису Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="9edd8-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="9edd8-140">Ви можете знайти ідентифікатор клієнта (`cid`) та ідентифікатор облікового запису (`aid`) у параметрах URL-адреси після виконання входу до Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="9edd8-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="9edd8-141">У розділі **Зіставлення даних** у полі **Електронна пошта** виберіть поле в уніфікованому профілі клієнта, що містить адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="9edd8-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="9edd8-142">Це необхідно для експорту сегментів до Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="9edd8-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="9edd8-143">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="9edd8-143">Select **Save**.</span></span>

<span data-ttu-id="9edd8-144">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="9edd8-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9edd8-145">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9edd8-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9edd8-146">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9edd8-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9edd8-147">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="9edd8-147">Data privacy and compliance</span></span>

<span data-ttu-id="9edd8-148">Коли ви дозволяєте Dynamics 365 Customer Insights передачу даних до Microsoft Advertising, ви дозволяєте передавати дані за межі нормативного регіону Dynamics 365 Customer Insights, зокрема й такі потенційно конфіденційні дані, як персональна інформація.</span><span class="sxs-lookup"><span data-stu-id="9edd8-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9edd8-149">Microsoft передаватиме такі дані за вашим розпорядженням, але ви несете відповідальність за забезпечення відповідності Microsoft Advertising будь-яким вимогам щодо конфіденційності та безпеки, що можуть виникати.</span><span class="sxs-lookup"><span data-stu-id="9edd8-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9edd8-150">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9edd8-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="9edd8-151">У будь-який час ваш адміністратор Dynamics 365 Customer Insights може видалити це призначення експорту, щоб припинити використання функції.</span><span class="sxs-lookup"><span data-stu-id="9edd8-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
