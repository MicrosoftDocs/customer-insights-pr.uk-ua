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
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124390"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="1a495-103">Експорт сегментів до AdRoll (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="1a495-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="1a495-104">Експортуйте до AdRoll сегменти уніфікованих профілів клієнтів і використовуйте їх для реклами.</span><span class="sxs-lookup"><span data-stu-id="1a495-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="1a495-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="1a495-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="1a495-106">Ви маєте [обліковий запис AdRoll](https://www.adroll.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="1a495-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1a495-107">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="1a495-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1a495-108">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="1a495-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1a495-109">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="1a495-109">Known limitations</span></span>

- <span data-ttu-id="1a495-110">Загалом до AdRoll можна експортувати до 250 000 профілів за один експорт.</span><span class="sxs-lookup"><span data-stu-id="1a495-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="1a495-111">В AdRoll не можна експортувати сегменти, які містять менше, ніж 100 профілів.</span><span class="sxs-lookup"><span data-stu-id="1a495-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="1a495-112">Експорт до AdRoll обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="1a495-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="1a495-113">Експортування до 250 000 профілів в AdRoll може тривати до 10 хвилин.</span><span class="sxs-lookup"><span data-stu-id="1a495-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="1a495-114">Кількість профілів, які можна експортувати до AdRoll, залежить від сервісного договору з AdRoll.</span><span class="sxs-lookup"><span data-stu-id="1a495-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="1a495-115">Налаштування підключення до AdRoll</span><span class="sxs-lookup"><span data-stu-id="1a495-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="1a495-116">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="1a495-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1a495-117">Виберіть **Додати підключення** та оберіть **AdRoll**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="1a495-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="1a495-118">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="1a495-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1a495-119">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="1a495-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1a495-120">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="1a495-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1a495-121">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="1a495-121">Choose who can use this connection.</span></span> <span data-ttu-id="1a495-122">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="1a495-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1a495-123">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1a495-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1a495-124">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="1a495-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1a495-125">Виберіть **Підключити**, щоб ініціалізувати підключення до AdRoll.</span><span class="sxs-lookup"><span data-stu-id="1a495-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="1a495-126">Виберіть **Автентифікацію за допомогою AdRoll** і надайте облікові дані AdRoll.</span><span class="sxs-lookup"><span data-stu-id="1a495-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="1a495-127">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1a495-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1a495-128">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="1a495-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1a495-129">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="1a495-129">Configure an export</span></span>

<span data-ttu-id="1a495-130">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="1a495-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1a495-131">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1a495-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1a495-132">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="1a495-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1a495-133">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="1a495-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1a495-134">У полі **Підключення для експорту** виберіть підключення з розділу AdRoll.</span><span class="sxs-lookup"><span data-stu-id="1a495-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="1a495-135">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="1a495-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1a495-136">Введіть свій **Ідентифікатор рекламодавця AdRoll**. Докладніші відомості див. у розділі [Профілі рекламодавців AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="1a495-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="1a495-137">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="1a495-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1a495-138">Необхідно експортувати сегменти в AdRoll.</span><span class="sxs-lookup"><span data-stu-id="1a495-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="1a495-139">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="1a495-139">Select the segments you want to export.</span></span> <span data-ttu-id="1a495-140">Виберіть сегмент, який має щонайменше 100 учасників.</span><span class="sxs-lookup"><span data-stu-id="1a495-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="1a495-141">Сегменти меншого розміру експортувати не можна.</span><span class="sxs-lookup"><span data-stu-id="1a495-141">You can't export smaller segments.</span></span> <span data-ttu-id="1a495-142">Крім того, максимальний розмір сегмента для експорту до 250 000 учасників на один експорт.</span><span class="sxs-lookup"><span data-stu-id="1a495-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="1a495-143">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="1a495-143">Select **Save**.</span></span>

<span data-ttu-id="1a495-144">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="1a495-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1a495-145">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1a495-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1a495-146">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1a495-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1a495-147">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="1a495-147">Data privacy and compliance</span></span>

<span data-ttu-id="1a495-148">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до AdRoll можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="1a495-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1a495-149">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія AdRoll відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="1a495-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1a495-150">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1a495-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="1a495-151">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="1a495-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
