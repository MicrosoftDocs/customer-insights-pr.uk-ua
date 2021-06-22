---
title: Експортування даних Customer Insights до Omnisend
description: Дізнайтеся, як налаштувати підключення та експорт до Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124568"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="ea15b-103">Експорт сегментів до Omnisend (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="ea15b-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="ea15b-104">Експортуйте сегменти, що складаються з уніфікованих профілів клієнтів, до Omnisend і використовуйте їх для маркетингової діяльності.</span><span class="sxs-lookup"><span data-stu-id="ea15b-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ea15b-105">Вимоги</span><span class="sxs-lookup"><span data-stu-id="ea15b-105">Prerequisites</span></span>

-   <span data-ttu-id="ea15b-106">У вас є [обліковий запис Omnisend](https://www.omnisend.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="ea15b-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ea15b-107">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="ea15b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ea15b-108">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="ea15b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ea15b-109">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="ea15b-109">Known limitations</span></span>

- <span data-ttu-id="ea15b-110">У кожному експорті до Omnisend можна експортувати до 1 мільйона профілів, і цей процес може тривати до 4 годин.</span><span class="sxs-lookup"><span data-stu-id="ea15b-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="ea15b-111">Експортувати в Omnisend можна тільки сегменти.</span><span class="sxs-lookup"><span data-stu-id="ea15b-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="ea15b-112">Кількість профілів, які можна експортувати в Omnisend, залежить від контракту, укладеного між вами та Omnisend.</span><span class="sxs-lookup"><span data-stu-id="ea15b-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="ea15b-113">Налаштування підключення до Omnisend</span><span class="sxs-lookup"><span data-stu-id="ea15b-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="ea15b-114">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="ea15b-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ea15b-115">Виберіть **Додати підключення** та оберіть **Omnisend**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="ea15b-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="ea15b-116">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="ea15b-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ea15b-117">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="ea15b-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ea15b-118">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="ea15b-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ea15b-119">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="ea15b-119">Choose who can use this connection.</span></span> <span data-ttu-id="ea15b-120">За замовчуванням це будуть лише адміністратори.</span><span class="sxs-lookup"><span data-stu-id="ea15b-120">By default it's only administrators.</span></span> <span data-ttu-id="ea15b-121">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ea15b-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ea15b-122">Введіть свій [ключ API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="ea15b-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="ea15b-123">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="ea15b-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ea15b-124">Виберіть **Підключити**, щоб ініціалізувати підключення до Omnisend.</span><span class="sxs-lookup"><span data-stu-id="ea15b-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="ea15b-125">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ea15b-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ea15b-126">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="ea15b-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ea15b-127">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="ea15b-127">Configure an export</span></span>

<span data-ttu-id="ea15b-128">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="ea15b-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ea15b-129">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ea15b-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ea15b-130">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="ea15b-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ea15b-131">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="ea15b-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ea15b-132">У полі **Підключення для експорту** виберіть підключення з розділу Omnisend.</span><span class="sxs-lookup"><span data-stu-id="ea15b-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="ea15b-133">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="ea15b-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ea15b-134">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="ea15b-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ea15b-135">Це необхідно для експорту сегментів до Omnisend.</span><span class="sxs-lookup"><span data-stu-id="ea15b-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="ea15b-136">За бажанням ви можете експортувати Ім'я, Прізвище, Адресу, Країну/Регіон, Штат, Місто та Поштовий індекс, щоб створювати більш персоналізовані електронні листи.</span><span class="sxs-lookup"><span data-stu-id="ea15b-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="ea15b-137">Виберіть **Додати атрибут**, щоб зіставити ці поля.</span><span class="sxs-lookup"><span data-stu-id="ea15b-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="ea15b-138">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="ea15b-138">Select **Save**.</span></span>

<span data-ttu-id="ea15b-139">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="ea15b-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ea15b-140">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ea15b-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ea15b-141">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ea15b-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ea15b-142">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="ea15b-142">Data privacy and compliance</span></span>

<span data-ttu-id="ea15b-143">Коли ви дозволяєте Dynamics 365 Customer Insights передавати дані до Omnisend, ви дозволяєте передавати дані за межі нормативного регіону Dynamics 365 Customer Insights, зокрема й такі потенційно конфіденційні дані, як персональна інформація.</span><span class="sxs-lookup"><span data-stu-id="ea15b-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ea15b-144">Корпорація Microsoft передаватиме такі дані за вашим розпорядженням, але ви несете відповідальність за забезпечення відповідності Omnisend будь-яким вимогам щодо конфіденційності та безпеки, що можуть виникати.</span><span class="sxs-lookup"><span data-stu-id="ea15b-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ea15b-145">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ea15b-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ea15b-146">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити це призначення експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="ea15b-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
