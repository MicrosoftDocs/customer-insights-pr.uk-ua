---
title: Експортуйте дані Customer Insights до Sendinblue
description: Дізнайтеся про те, як налаштувати підключення та експортувати дані до Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314691"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="2675b-103">Експортуйте сегменти до Sendinblue (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="2675b-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="2675b-104">Експортуйте сегменти єдиних профілів клієнтів, щоб створювати кампанії, здійснювати маркетинг електронною поштою, а також використовуйте за допомогою Sendinblue спеціальні групи клієнтів.</span><span class="sxs-lookup"><span data-stu-id="2675b-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="2675b-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="2675b-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="2675b-106">У вас є [обліковий запис Sendinblue](https://www.sendinblue.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="2675b-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2675b-107">У Sendinblue вже є наявні списки та відповідні ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="2675b-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="2675b-108">Ви маєте [налаштовані сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="2675b-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="2675b-109">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="2675b-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2675b-110">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="2675b-110">Known limitations</span></span>

- <span data-ttu-id="2675b-111">До Sendinblue можна експортувати до одного мільйона профілів.</span><span class="sxs-lookup"><span data-stu-id="2675b-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="2675b-112">Експорт до Sendinblue обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="2675b-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="2675b-113">Процедура експортування сегментів із одним мільйоном профілів може займати до 90 хвилин часу.</span><span class="sxs-lookup"><span data-stu-id="2675b-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="2675b-114">Кількість профілів, які ви можете експортувати до Sendinblue, визначається й обмежується сервісним договором із Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="2675b-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="2675b-115">Налаштуйте підключення до Sendinblue</span><span class="sxs-lookup"><span data-stu-id="2675b-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="2675b-116">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="2675b-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2675b-117">Виберіть розділ **Додати підключення**, потім виберіть **Sendinblue**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="2675b-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="2675b-118">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="2675b-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2675b-119">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="2675b-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2675b-120">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="2675b-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2675b-121">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="2675b-121">Choose who can use this connection.</span></span> <span data-ttu-id="2675b-122">За замовчуванням це будуть лише адміністратори.</span><span class="sxs-lookup"><span data-stu-id="2675b-122">By default it's only administrators.</span></span> <span data-ttu-id="2675b-123">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2675b-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2675b-124">Введіть **[ключ API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="2675b-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="2675b-125">Виберіть пункт **Погоджуюся**, щоб підтвердити обов’язковість розділу **Конфіденційність і відповідність даних**, потім виберіть **Підключитися** для ініціалізації підключення до Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="2675b-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="2675b-126">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2675b-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2675b-127">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="2675b-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2675b-128">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="2675b-128">Configure an export</span></span>

<span data-ttu-id="2675b-129">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="2675b-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2675b-130">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2675b-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2675b-131">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="2675b-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2675b-132">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="2675b-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2675b-133">У полі **Підключення для експорту** виберіть підключення з розділу Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="2675b-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="2675b-134">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="2675b-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2675b-135">Введіть **Ідентифікатор списку Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="2675b-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="2675b-136">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="2675b-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="2675b-137">Додатково ви можете експортувати **Ім’я**, **Прізвище** й **Телефон**, щоб створювати персоналізовані повідомлення електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="2675b-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="2675b-138">Виберіть **Додати атрибут**, щоб зіставити ці поля.</span><span class="sxs-lookup"><span data-stu-id="2675b-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="2675b-139">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="2675b-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="2675b-140">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="2675b-140">Select **Save**.</span></span>

<span data-ttu-id="2675b-141">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="2675b-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2675b-142">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2675b-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2675b-143">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2675b-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2675b-144">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="2675b-144">Data privacy and compliance</span></span>

<span data-ttu-id="2675b-145">При увімкненні Dynamics 365 Customer Insights для передавання даних до Sendinblue ви також надаєте дозвіл на передавання даних поза межі нормативно-правової відповідності для Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, такими як особисті дані.</span><span class="sxs-lookup"><span data-stu-id="2675b-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2675b-146">Майкрософт виконає передавання таких даних за вашою вказівкою, але ви несете відповідальність за забезпечення того, щоб Sendinblue відповідала зобов’язанням щодо конфіденційності або безпеки, які можуть у вас бути.</span><span class="sxs-lookup"><span data-stu-id="2675b-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2675b-147">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2675b-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2675b-148">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити це призначення експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="2675b-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
