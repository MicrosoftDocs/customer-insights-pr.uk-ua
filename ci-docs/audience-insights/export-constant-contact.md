---
title: Експортування даних Customer Insights до Constant Contact
description: Дізнайтеся, як налаштувати підключення та експорт до Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760661"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="50d96-103">Експорт списків сегментів до Constant Contact (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="50d96-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="50d96-104">Експортуйте сегменти, що складаються з уніфікованих профілів клієнтів, до Constant Contact і використовуйте їх для маркетингової діяльності.</span><span class="sxs-lookup"><span data-stu-id="50d96-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="50d96-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="50d96-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="50d96-106">У вас є [обліковий запис Constant Contact](https://www.constantcontact.com/account-home) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="50d96-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="50d96-107">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="50d96-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="50d96-108">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="50d96-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="50d96-109">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="50d96-109">Known limitations</span></span>

- <span data-ttu-id="50d96-110">У кожному експорті до Constant Contact можна експортувати до 1 мільйона профілів.</span><span class="sxs-lookup"><span data-stu-id="50d96-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="50d96-111">Експортувати в Constant Contact можна тільки сегменти.</span><span class="sxs-lookup"><span data-stu-id="50d96-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="50d96-112">Експортування до 1 мільйона профілів до Constant Contact може тривати до 1 години.</span><span class="sxs-lookup"><span data-stu-id="50d96-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="50d96-113">Кількість профілів, які можна експортувати до Constant Contact, визначається і обмежується сервісним договором з Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="50d96-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="50d96-114">Налаштуйте підключення до Constant Contact</span><span class="sxs-lookup"><span data-stu-id="50d96-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="50d96-115">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="50d96-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="50d96-116">Виберіть **Додати підключення**, потім виберіть **Constant Contact**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="50d96-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="50d96-117">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="50d96-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="50d96-118">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="50d96-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="50d96-119">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="50d96-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="50d96-120">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="50d96-120">Choose who can use this connection.</span></span> <span data-ttu-id="50d96-121">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="50d96-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="50d96-122">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="50d96-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="50d96-123">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="50d96-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="50d96-124">Виберіть **Підключити**, щоб ініціалізувати підключення до Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="50d96-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="50d96-125">Виберіть **Автентифікація за допомогою AdRoll** і введіть облікові дані адміністратора для Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="50d96-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="50d96-126">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="50d96-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="50d96-127">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="50d96-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="50d96-128">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="50d96-128">Configure an export</span></span>

<span data-ttu-id="50d96-129">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="50d96-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="50d96-130">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="50d96-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="50d96-131">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="50d96-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="50d96-132">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="50d96-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="50d96-133">У полі **Підключення для експорту** виберіть підключення з розділу «Constant Contact».</span><span class="sxs-lookup"><span data-stu-id="50d96-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="50d96-134">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="50d96-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="50d96-135">Введіть свій [**ідентифікатор списку Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="50d96-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="50d96-136">Відкрийте список у Constant Contact, щоб знайти ідентифікатор списку в URL-адресі.</span><span class="sxs-lookup"><span data-stu-id="50d96-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="50d96-137">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="50d96-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="50d96-138">Це необхідно для експорту сегментів до Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="50d96-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="50d96-139">Додатково можна експортувати Ім'я та Прізвище у вигляді додаткових полів для створення додаткових персоналізованих електронних листів.</span><span class="sxs-lookup"><span data-stu-id="50d96-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="50d96-140">Виберіть **Додати атрибут**, щоб зіставити ці поля.</span><span class="sxs-lookup"><span data-stu-id="50d96-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="50d96-141">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="50d96-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="50d96-142">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="50d96-142">Select **Save**.</span></span>

<span data-ttu-id="50d96-143">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="50d96-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="50d96-144">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="50d96-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="50d96-145">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="50d96-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="50d96-146">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="50d96-146">Data privacy and compliance</span></span>

<span data-ttu-id="50d96-147">Коли ви дозволяєте Dynamics 365 Customer Insights передавати дані до Constant Contact, ви дозволяєте передавати дані за межі нормативного регіону Dynamics 365 Customer Insights, зокрема й такі потенційно конфіденційні дані, як персональна інформація.</span><span class="sxs-lookup"><span data-stu-id="50d96-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="50d96-148">Майкрософт передаватиме такі дані за вашим розпорядженням, але ви несете відповідальність за забезпечення відповідності Constant Contact будь-яким вимогам щодо конфіденційності та безпеки, що можуть виникати.</span><span class="sxs-lookup"><span data-stu-id="50d96-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="50d96-149">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="50d96-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="50d96-150">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="50d96-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
