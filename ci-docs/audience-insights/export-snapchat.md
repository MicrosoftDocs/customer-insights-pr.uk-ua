---
title: Експортування даних Customer Insights до Snapchat
description: Дізнайтеся, як налаштувати підключення та експорт до Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760660"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="53f03-103">Експорт списків сегментів до Snapchat (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="53f03-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="53f03-104">Експортуйте сегменти, що складаються з уніфікованих профілів клієнтів, до Snapchat і використовуйте їх для реклами.</span><span class="sxs-lookup"><span data-stu-id="53f03-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="53f03-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="53f03-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="53f03-106">У вас є [корпоративний обліковий запис Snapchat](https://business.snapchat.com/), [обліковий запис рекламодавця Snapchat](https://ads.snapchat.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="53f03-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="53f03-107">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="53f03-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="53f03-108">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="53f03-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="53f03-109">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="53f03-109">Known limitations</span></span>

- <span data-ttu-id="53f03-110">Експортувати в Snapchat можна тільки сегменти.</span><span class="sxs-lookup"><span data-stu-id="53f03-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="53f03-111">Експортування до 1 мільйона профілів до Snapchat може тривати до 15 хвилин.</span><span class="sxs-lookup"><span data-stu-id="53f03-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="53f03-112">Налаштування підключення до Snapchat</span><span class="sxs-lookup"><span data-stu-id="53f03-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="53f03-113">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="53f03-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="53f03-114">Виберіть **Додати підключення** та оберіть **Snapchat**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="53f03-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="53f03-115">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="53f03-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="53f03-116">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="53f03-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="53f03-117">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="53f03-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="53f03-118">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="53f03-118">Choose who can use this connection.</span></span> <span data-ttu-id="53f03-119">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="53f03-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="53f03-120">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="53f03-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="53f03-121">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="53f03-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="53f03-122">Виберіть **Підключити**, щоб ініціалізувати підключення до Snapchat.</span><span class="sxs-lookup"><span data-stu-id="53f03-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="53f03-123">Виберіть **Автентифікація за допомогою Snapchat** і введіть облікові дані адміністратора для Snapchat.</span><span class="sxs-lookup"><span data-stu-id="53f03-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="53f03-124">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="53f03-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="53f03-125">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="53f03-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="53f03-126">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="53f03-126">Configure an export</span></span>

<span data-ttu-id="53f03-127">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="53f03-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="53f03-128">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="53f03-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="53f03-129">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="53f03-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="53f03-130">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="53f03-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="53f03-131">У полі **Підключення для експорту** виберіть підключення з розділу Snapchat.</span><span class="sxs-lookup"><span data-stu-id="53f03-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="53f03-132">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="53f03-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="53f03-133">Введіть [**ідентифікатор аудиторії Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="53f03-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="53f03-134">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="53f03-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="53f03-135">Це необхідно для експорту сегментів до Snapchat.</span><span class="sxs-lookup"><span data-stu-id="53f03-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="53f03-136">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="53f03-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="53f03-137">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="53f03-137">Select **Save**.</span></span>

<span data-ttu-id="53f03-138">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="53f03-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="53f03-139">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="53f03-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="53f03-140">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="53f03-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="53f03-141">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="53f03-141">Data privacy and compliance</span></span>

<span data-ttu-id="53f03-142">Коли ви дозволяєте Dynamics 365 Customer Insights передавати дані до Snapchat, ви дозволяєте передавати дані за межі нормативного регіону Dynamics 365 Customer Insights, зокрема й такі потенційно конфіденційні дані, як персональна інформація.</span><span class="sxs-lookup"><span data-stu-id="53f03-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="53f03-143">Корпорація Microsoft передаватиме такі дані за вашим розпорядженням, але ви несете відповідальність за забезпечення відповідності Snapchat будь-яким вимогам щодо конфіденційності та безпеки, що можуть виникати.</span><span class="sxs-lookup"><span data-stu-id="53f03-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="53f03-144">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="53f03-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="53f03-145">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="53f03-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
