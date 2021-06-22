---
title: Експортування даних Customer Insights до LinkedIn Ads
description: Дізнайтеся, як налаштувати підключення та експорт до LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124569"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="fbc1b-103">Експорт сегментів до LinkedIn Ads (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="fbc1b-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="fbc1b-104">Експортуйте сегменти уніфікованих профілів клієнтів до LinkedIn Ads, щоб створити зіставлені аудиторії.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="fbc1b-105">Використовуйте зіставлені аудиторії для націлювання на компанії та націлювання на контактних осіб.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fbc1b-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="fbc1b-106">Prerequisites</span></span>

-   <span data-ttu-id="fbc1b-107">У вас є [обліковий запис LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fbc1b-108">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="fbc1b-109">Профілі клієнтів в експортованих сегментах містять поле з адресою електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fbc1b-110">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="fbc1b-110">Known limitations</span></span>

- <span data-ttu-id="fbc1b-111">У кожному експорті до LinkedIn Ads можна експортувати до 100 000 профілів.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="fbc1b-112">Експортувати в LinkedIn Ads можна тільки сегменти.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="fbc1b-113">Експортування до 100 000 профілів до LinkedIn Ads може тривати до 10 хвилин.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="fbc1b-114">Налаштування підключення до LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="fbc1b-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="fbc1b-115">У аналітиці аудиторії перейдіть до розділу **Адміністратор** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="fbc1b-116">Виберіть **Додати підключення** та оберіть **LinkedIn Ads**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="fbc1b-117">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="fbc1b-118">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="fbc1b-119">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="fbc1b-120">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-120">Choose who can use this connection.</span></span> <span data-ttu-id="fbc1b-121">Якщо не вжити жодних дій, за замовчуванням це будуть адміністратори.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="fbc1b-122">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="fbc1b-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="fbc1b-123">Укажіть [ідентифікатор облікового запису LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="fbc1b-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="fbc1b-124">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fbc1b-125">Виберіть **Підключити**, щоб ініціалізувати підключення до Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="fbc1b-126">Виберіть **Автентифікація в LinkedIn** і введіть облікові дані адміністратора для LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="fbc1b-127">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="fbc1b-128">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="fbc1b-129">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="fbc1b-129">Configure an export</span></span>

<span data-ttu-id="fbc1b-130">Ви можете налаштувати експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="fbc1b-131">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="fbc1b-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fbc1b-132">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="fbc1b-133">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="fbc1b-134">У полі **Підключення для експорту** виберіть підключення з розділу LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="fbc1b-135">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="fbc1b-136">Виберіть, чи хочете ви експортувати дані для здійснення [націлювання на контактну особу](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) або для [націлювання на компанію](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) на LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="fbc1b-137">У розділі **Зіставлення даних** виберіть в уніфікованому профілі клієнта поле, що відповідає адресі електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="fbc1b-138">Це необхідно для експорту сегментів до LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="fbc1b-139">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-139">Select the segments you want to export.</span></span> <span data-ttu-id="fbc1b-140">Зіставлені аудиторії у LinkedIn Campaign Manager будуть створені автоматично і отримають назви, що відповідають назвам сегментів, вибраних для експорту.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="fbc1b-141">В результаті для кожного сегмента буде створено окрему зіставлену аудиторію.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="fbc1b-142">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-142">Select **Save**.</span></span>

<span data-ttu-id="fbc1b-143">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="fbc1b-144">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fbc1b-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fbc1b-145">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fbc1b-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fbc1b-146">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="fbc1b-146">Data privacy and compliance</span></span>

<span data-ttu-id="fbc1b-147">Коли ви дозволяєте Dynamics 365 Customer Insights передавати дані до LinkedIn Ads, ви дозволяєте передавати дані за межі нормативного регіону Dynamics 365 Customer Insights, зокрема й такі потенційно конфіденційні дані, як персональна інформація.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fbc1b-148">Корпорація Microsoft передаватиме такі дані за вашим розпорядженням, але ви несете відповідальність за забезпечення відповідності LinkedIn Ads будь-яким вимогам щодо конфіденційності та безпеки, що можуть виникати.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="fbc1b-149">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fbc1b-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="fbc1b-150">У будь-який час ваш адміністратор Dynamics 365 Customer Insights може видалити це призначення експорту, щоб припинити використання функції.</span><span class="sxs-lookup"><span data-stu-id="fbc1b-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
