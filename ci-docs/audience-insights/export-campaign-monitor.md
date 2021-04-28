---
title: Експортування даних Customer Insights до Campaign Monitor
description: Дізнайтеся, як налаштувати підключення та експорт до Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760662"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="37dd4-103">Експорт списків сегментів до Campaign Monitor (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="37dd4-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="37dd4-104">Експортуйте сегменти, що складаються з уніфікованих профілів клієнтів, до Campaign Monitor і використовуйте їх для маркетингової діяльності.</span><span class="sxs-lookup"><span data-stu-id="37dd4-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="37dd4-105">Вимоги</span><span class="sxs-lookup"><span data-stu-id="37dd4-105">Prerequisites</span></span>

-   <span data-ttu-id="37dd4-106">У вас є [обліковий запис Campaign Monitor](https://www.campaignmonitor.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="37dd4-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="37dd4-107">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="37dd4-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="37dd4-108">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="37dd4-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="37dd4-109">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="37dd4-109">Known limitations</span></span>

- <span data-ttu-id="37dd4-110">У кожному експорті до Campaign Monitor можна експортувати до 1 мільйона профілів.</span><span class="sxs-lookup"><span data-stu-id="37dd4-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="37dd4-111">Експортувати до Campaign Monitor можна тільки сегменти.</span><span class="sxs-lookup"><span data-stu-id="37dd4-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="37dd4-112">Експортування до 1 мільйона профілів до Campaign Monitor може тривати до 20 хвилин.</span><span class="sxs-lookup"><span data-stu-id="37dd4-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="37dd4-113">Кількість профілів, які можна експортувати до Campaign Monitor, визначається і обмежується сервісним договором з Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="37dd4-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="37dd4-114">Налаштуйте підключення до Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="37dd4-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="37dd4-115">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="37dd4-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="37dd4-116">Виберіть **Додати підключення** та оберіть **Campaign Monitor**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="37dd4-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="37dd4-117">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="37dd4-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="37dd4-118">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="37dd4-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="37dd4-119">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="37dd4-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="37dd4-120">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="37dd4-120">Choose who can use this connection.</span></span> <span data-ttu-id="37dd4-121">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="37dd4-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="37dd4-122">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="37dd4-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="37dd4-123">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="37dd4-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="37dd4-124">Виберіть **Підключити**, щоб ініціалізувати підключення до Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="37dd4-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="37dd4-125">Виберіть **Автентифікація за допомогою Campaign Monitor** і введіть облікові дані адміністратора Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="37dd4-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="37dd4-126">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="37dd4-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="37dd4-127">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="37dd4-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="37dd4-128">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="37dd4-128">Configure an export</span></span>

<span data-ttu-id="37dd4-129">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="37dd4-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="37dd4-130">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="37dd4-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="37dd4-131">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="37dd4-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="37dd4-132">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="37dd4-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="37dd4-133">У полі **Підключення для експорту** виберіть підключення з розділу «Campaign Monitor».</span><span class="sxs-lookup"><span data-stu-id="37dd4-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="37dd4-134">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="37dd4-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="37dd4-135">Введіть свій ідентифікатор списку [**Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="37dd4-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="37dd4-136">Спочатку [створіть ключ API](https://www.campaignmonitor.com/api/getting-started/) в розділі **Параметри облікового запису** у програмі Campaign Monitor, щоб переглянути ідентифікатор списку API.</span><span class="sxs-lookup"><span data-stu-id="37dd4-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="37dd4-137">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="37dd4-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="37dd4-138">Це необхідно для експорту сегментів до Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="37dd4-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="37dd4-139">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="37dd4-139">Select **Save**.</span></span>

<span data-ttu-id="37dd4-140">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="37dd4-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="37dd4-141">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="37dd4-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="37dd4-142">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="37dd4-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="37dd4-143">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="37dd4-143">Data privacy and compliance</span></span>

<span data-ttu-id="37dd4-144">Коли ви дозволяєте Dynamics 365 Customer Insights передавати дані до Campaign Monitor, ви дозволяєте передавати дані за межі нормативного регіону Dynamics 365 Customer Insights, зокрема й такі потенційно конфіденційні дані, як персональна інформація.</span><span class="sxs-lookup"><span data-stu-id="37dd4-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="37dd4-145">Майкрософт передаватиме такі дані за вашим розпорядженням, але ви несете відповідальність за забезпечення відповідності Campaign Monitor будь-яким вимогам щодо конфіденційності та безпеки, що можуть виникати.</span><span class="sxs-lookup"><span data-stu-id="37dd4-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="37dd4-146">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="37dd4-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="37dd4-147">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="37dd4-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
