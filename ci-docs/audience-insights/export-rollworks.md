---
title: Експортування даних Customer Insights до RollWorks
description: Дізнайтеся, як налаштувати підключення та експорт до RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760663"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="3b1b1-103">Експорт списків сегментів до RollWorks (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="3b1b1-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="3b1b1-104">Експортуйте сегменти, що складаються з уніфікованих профілів клієнтів, до RollWorks і використовуйте їх для реклами.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="3b1b1-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="3b1b1-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="3b1b1-106">У вас є [обліковий запис RollWorks](https://www.rollworks.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3b1b1-107">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3b1b1-108">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3b1b1-109">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="3b1b1-109">Known limitations</span></span>

- <span data-ttu-id="3b1b1-110">У кожному експорті до RollWorks можна експортувати до 250 000 профілів.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="3b1b1-111">Не можна експортувати до RollWorks сегменти, що містять менше 100 профілів.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="3b1b1-112">Експортувати в RollWorks можна тільки сегменти.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="3b1b1-113">Експортування до 250 000 профілів до RollWorks може тривати до 10 хвилин.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="3b1b1-114">Кількість профілів, які можна експортувати до RollWorks, визначається і обмежується сервісним договором з RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="3b1b1-115">Налаштування підключення до RollWorks</span><span class="sxs-lookup"><span data-stu-id="3b1b1-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="3b1b1-116">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3b1b1-117">Виберіть **Додати підключення** та оберіть **RollWorks**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="3b1b1-118">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3b1b1-119">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3b1b1-120">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3b1b1-121">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-121">Choose who can use this connection.</span></span> <span data-ttu-id="3b1b1-122">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3b1b1-123">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3b1b1-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3b1b1-124">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3b1b1-125">Виберіть **Підключити**, щоб ініціалізувати підключення до RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="3b1b1-126">Виберіть **Автентифікація за допомогою RollWorks** і введіть облікові дані адміністратора для RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="3b1b1-127">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3b1b1-128">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3b1b1-129">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="3b1b1-129">Configure an export</span></span>

<span data-ttu-id="3b1b1-130">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3b1b1-131">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3b1b1-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3b1b1-132">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3b1b1-133">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3b1b1-134">У полі **Підключення для експорту** виберіть підключення з розділу RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="3b1b1-135">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3b1b1-136">Уведіть свій **Ідентифікатор рекламодавця RollWorks** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="3b1b1-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="3b1b1-137">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3b1b1-138">Це необхідно для експорту сегментів до RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="3b1b1-139">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-139">Select the segments you want to export.</span></span> <span data-ttu-id="3b1b1-140">Виберіть сегмент, який має щонайменше 100 учасників.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="3b1b1-141">Сегменти меншого розміру експортувати не можна.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-141">You can't export smaller segments.</span></span> <span data-ttu-id="3b1b1-142">Крім того, максимальний розмір сегмента для експорту до 250 000 учасників на один експорт.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="3b1b1-143">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-143">Select **Save**.</span></span>

<span data-ttu-id="3b1b1-144">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3b1b1-145">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3b1b1-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3b1b1-146">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3b1b1-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3b1b1-147">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="3b1b1-147">Data privacy and compliance</span></span>

<span data-ttu-id="3b1b1-148">Коли ви дозволяєте Dynamics 365 Customer Insights передавати дані до RollWorks, ви дозволяєте передавати дані за межі нормативного регіону Dynamics 365 Customer Insights, зокрема й такі потенційно конфіденційні дані, як персональна інформація.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3b1b1-149">Корпорація Microsoft передаватиме такі дані за вашим розпорядженням, але ви несете відповідальність за забезпечення відповідності RollWorks будь-яким вимогам щодо конфіденційності та безпеки, що можуть виникати.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3b1b1-150">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3b1b1-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="3b1b1-151">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
