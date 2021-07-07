---
title: Експорт даних Customer Insights до AdRoll
description: Дізнайтеся, як налаштувати підключення та експорт до AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304859"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="ecedc-103">Експорт сегментів до AdRoll (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="ecedc-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="ecedc-104">Експортуйте до AdRoll сегменти уніфікованих профілів клієнтів і використовуйте їх для реклами.</span><span class="sxs-lookup"><span data-stu-id="ecedc-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ecedc-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="ecedc-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ecedc-106">Ви маєте [обліковий запис AdRoll](https://www.adroll.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="ecedc-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ecedc-107">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="ecedc-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ecedc-108">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="ecedc-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ecedc-109">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="ecedc-109">Known limitations</span></span>

- <span data-ttu-id="ecedc-110">За один раз до AdRoll можна експортувати до 250 000 профілів.</span><span class="sxs-lookup"><span data-stu-id="ecedc-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="ecedc-111">В AdRoll не можна експортувати сегменти, які містять менше, ніж 100 профілів.</span><span class="sxs-lookup"><span data-stu-id="ecedc-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="ecedc-112">Експорт до AdRoll обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="ecedc-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="ecedc-113">Експортування до 250 000 профілів в AdRoll може тривати до 10 хвилин.</span><span class="sxs-lookup"><span data-stu-id="ecedc-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="ecedc-114">Кількість профілів, які ви можете експортувати до AdRoll залежить від сервісного договору з AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ecedc-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="ecedc-115">Налаштування підключення до AdRoll</span><span class="sxs-lookup"><span data-stu-id="ecedc-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="ecedc-116">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="ecedc-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ecedc-117">Виберіть **Додати підключення** та оберіть **AdRoll**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="ecedc-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="ecedc-118">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="ecedc-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ecedc-119">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="ecedc-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ecedc-120">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="ecedc-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ecedc-121">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="ecedc-121">Choose who can use this connection.</span></span> <span data-ttu-id="ecedc-122">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="ecedc-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ecedc-123">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ecedc-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ecedc-124">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="ecedc-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ecedc-125">Виберіть **Підключити**, щоб ініціалізувати підключення до AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ecedc-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="ecedc-126">Виберіть **Автентифікацію за допомогою AdRoll** і надайте облікові дані AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ecedc-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="ecedc-127">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ecedc-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ecedc-128">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="ecedc-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ecedc-129">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="ecedc-129">Configure an export</span></span>

<span data-ttu-id="ecedc-130">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="ecedc-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ecedc-131">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ecedc-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ecedc-132">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="ecedc-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ecedc-133">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="ecedc-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ecedc-134">У полі **Підключення для експорту** виберіть підключення з розділу AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ecedc-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="ecedc-135">Якщо ви не бачите імені цього розділу, це означає, що для вас не доступні будь-які підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="ecedc-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="ecedc-136">Введіть свій **Ідентифікатор рекламодавця AdRoll**.</span><span class="sxs-lookup"><span data-stu-id="ecedc-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="ecedc-137">Див. [профілі рекламодавців AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles), щоб отримати докладніші відомості.</span><span class="sxs-lookup"><span data-stu-id="ecedc-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="ecedc-138">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="ecedc-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ecedc-139">Необхідно експортувати сегменти в AdRoll.</span><span class="sxs-lookup"><span data-stu-id="ecedc-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="ecedc-140">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="ecedc-140">Select the segments you want to export.</span></span> <span data-ttu-id="ecedc-141">Виберіть сегмент, який має щонайменше 100 учасників.</span><span class="sxs-lookup"><span data-stu-id="ecedc-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="ecedc-142">Сегменти меншого розміру експортувати не можна.</span><span class="sxs-lookup"><span data-stu-id="ecedc-142">You can't export smaller segments.</span></span> <span data-ttu-id="ecedc-143">Крім того, максимальний розмір сегмента для експорту становить до 250 000 учасників за одну операцію експорту.</span><span class="sxs-lookup"><span data-stu-id="ecedc-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="ecedc-144">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="ecedc-144">Select **Save**.</span></span>

<span data-ttu-id="ecedc-145">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="ecedc-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ecedc-146">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ecedc-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="ecedc-147">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ecedc-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ecedc-148">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="ecedc-148">Data privacy and compliance</span></span>

<span data-ttu-id="ecedc-149">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до AdRoll можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="ecedc-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ecedc-150">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія AdRoll відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="ecedc-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ecedc-151">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ecedc-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ecedc-152">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити це призначення експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="ecedc-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
