---
title: Експортуйте дані Customer Insights до ActiveCampaign
description: Дізнайтеся про те, як налаштувати підключення та експортувати дані до ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314692"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="a1887-103">Експортуйте сегменти до ActiveCampaign (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="a1887-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="a1887-104">Експортуйте сегменти єдиних профілів клієнтів до ActiveCampaign і використовуйте їх для маркетингової діяльності.</span><span class="sxs-lookup"><span data-stu-id="a1887-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a1887-105">Вимоги</span><span class="sxs-lookup"><span data-stu-id="a1887-105">Prerequisites</span></span>

-   <span data-ttu-id="a1887-106">У вас є [обліковий запис ActiveCampaign](https://www.activecampaign.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="a1887-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a1887-107">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="a1887-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a1887-108">Уніфіковані профілі клієнтів в експортованих сегментах містять поле з адресою електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="a1887-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a1887-109">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="a1887-109">Known limitations</span></span>

- <span data-ttu-id="a1887-110">Ви можете експортувати до ActiveCampaign до 1 мільйона профілів у межах однієї операції експорту. Для завершення операції може знадобитися до 90 хвилин.</span><span class="sxs-lookup"><span data-stu-id="a1887-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="a1887-111">Експорт до ActiveCampaign обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="a1887-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="a1887-112">Кількість профілів, які ви можете експортувати до ActiveCampaign залежить від сервісного договору з ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a1887-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="a1887-113">Налаштуйте підключення до ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="a1887-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="a1887-114">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="a1887-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a1887-115">Виберіть розділ **Додати підключення**, потім виберіть **ActiveCampaign**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="a1887-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="a1887-116">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="a1887-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a1887-117">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="a1887-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a1887-118">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="a1887-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a1887-119">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="a1887-119">Choose who can use this connection.</span></span> <span data-ttu-id="a1887-120">За промовчанням це можуть робити лише адміністратори.</span><span class="sxs-lookup"><span data-stu-id="a1887-120">By default, it's only administrators.</span></span> <span data-ttu-id="a1887-121">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a1887-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a1887-122">Введіть [ключ API ActiveCampaign API та ім’я хоста кінцевої точки REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="a1887-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="a1887-123">Ім'я хоста кінцевої точки REST — це лише ім’я хоста, без https://.</span><span class="sxs-lookup"><span data-stu-id="a1887-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="a1887-124">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="a1887-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a1887-125">Виберіть **Підключити** для ініціалізації підключення до ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a1887-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="a1887-126">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a1887-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a1887-127">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="a1887-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a1887-128">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="a1887-128">Configure an export</span></span>

<span data-ttu-id="a1887-129">Ви можете налаштувати експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="a1887-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="a1887-130">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a1887-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a1887-131">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="a1887-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a1887-132">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="a1887-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a1887-133">У полі **Підключення для експорту** виберіть підключення з розділу ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a1887-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="a1887-134">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="a1887-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a1887-135">Введіть [**ідентифікатор списку ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="a1887-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="a1887-136">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="a1887-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a1887-137">Він вимагається для того, щоб експортувати сегменти до ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a1887-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="a1887-138">Це не обов’язково, але ви також можете експортувати ім’я, прізвище та телефон, щоб додатково персоналізувати повідомлення електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="a1887-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="a1887-139">Виберіть Додати атрибут, щоб зіставити ці поля.</span><span class="sxs-lookup"><span data-stu-id="a1887-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="a1887-140">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="a1887-140">Select **Save**.</span></span>

<span data-ttu-id="a1887-141">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="a1887-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a1887-142">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a1887-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a1887-143">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a1887-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a1887-144">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="a1887-144">Data privacy and compliance</span></span>

<span data-ttu-id="a1887-145">При увімкненні Dynamics 365 Customer Insights для передавання даних до ActiveCampaign ви також надаєте дозвіл на передавання даних поза межі нормативно-правової відповідності для Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, такими як особисті дані.</span><span class="sxs-lookup"><span data-stu-id="a1887-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a1887-146">Майкрософт виконає передавання таких даних за вашою вказівкою, але ви несете відповідальність за забезпечення того, щоб ActiveCampaign відповідала зобов’язанням щодо конфіденційності або безпеки, які можуть у вас бути.</span><span class="sxs-lookup"><span data-stu-id="a1887-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a1887-147">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a1887-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a1887-148">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити це призначення експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="a1887-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
