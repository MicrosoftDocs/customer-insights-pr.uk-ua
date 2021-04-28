---
title: Експорт даних Customer Insights до Marketo
description: Дізнайтеся, як налаштувати підключення та експорт до Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759846"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="34f22-103">Експорт сегментів до Marketo (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="34f22-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="34f22-104">Експортуйте сегменти уніфікованих профілів клієнтів, щоб формувати кампанії, здійснювати маркетингові розсилки електронною поштою та використовувати конкретні групи клієнтів за допомогою Marketo.</span><span class="sxs-lookup"><span data-stu-id="34f22-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="34f22-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="34f22-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="34f22-106">Ви маєте [обліковий запис Marketo](https://login.marketo.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="34f22-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="34f22-107">У Marketo наявні списки й відповідні ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="34f22-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="34f22-108">Для отримання додаткових відомостей див. розділ [Список Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="34f22-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="34f22-109">Ви маєте [налаштовані сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="34f22-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="34f22-110">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="34f22-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="34f22-111">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="34f22-111">Known limitations</span></span>

- <span data-ttu-id="34f22-112">До 1 000 000 профілів на експорт до Marketo.</span><span class="sxs-lookup"><span data-stu-id="34f22-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="34f22-113">Експорт до Marketo обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="34f22-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="34f22-114">Експортування сегментів загальною кількістю 1 000 000 профілів може тривати до 3 годин.</span><span class="sxs-lookup"><span data-stu-id="34f22-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="34f22-115">Кількість профілів, які можна експортувати до Marketo, залежить від сервісного договору з Marketo.</span><span class="sxs-lookup"><span data-stu-id="34f22-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="34f22-116">Налаштування підключення до Marketo</span><span class="sxs-lookup"><span data-stu-id="34f22-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="34f22-117">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="34f22-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="34f22-118">Виберіть **Додати підключення** та оберіть **Marketo**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="34f22-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="34f22-119">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="34f22-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="34f22-120">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="34f22-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="34f22-121">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="34f22-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="34f22-122">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="34f22-122">Choose who can use this connection.</span></span> <span data-ttu-id="34f22-123">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="34f22-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="34f22-124">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="34f22-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="34f22-125">Уведіть **[ідентифікатор клієнта Marketo, секретний ключ клієнта та Ім’я хоста кінцевої точки REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="34f22-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="34f22-126">Виберіть **Я погоджуюся**, щоб підтвердити **Конфіденційність даних і відповідність**, і натисніть **З'єднати**, щоб ініціалізувати підключення до Marketo.</span><span class="sxs-lookup"><span data-stu-id="34f22-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="34f22-127">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="34f22-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="34f22-128">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="34f22-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="34f22-129">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="34f22-129">Configure an export</span></span>

<span data-ttu-id="34f22-130">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="34f22-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="34f22-131">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="34f22-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="34f22-132">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="34f22-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="34f22-133">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="34f22-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="34f22-134">У полі **Підключення для експорту** виберіть підключення з розділу Marketo.</span><span class="sxs-lookup"><span data-stu-id="34f22-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="34f22-135">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="34f22-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="34f22-136">Введіть **[ідентифікатор списку Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="34f22-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="34f22-137">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="34f22-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="34f22-138">За бажанням ви можете експортувати **Ім'я**, **Прізвище**, **Місто**, **Штат** та **Країну/Регіон**, щоб створювати більш персоналізовані електронні листи.</span><span class="sxs-lookup"><span data-stu-id="34f22-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="34f22-139">Виберіть **Додати атрибут**, щоб зіставити ці поля.</span><span class="sxs-lookup"><span data-stu-id="34f22-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="34f22-140">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="34f22-140">Select the segments you want to export.</span></span> <span data-ttu-id="34f22-141">Загалом до Marketo можна експортувати до 1 000 000 профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="34f22-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="34f22-142">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="34f22-142">Select **Save**.</span></span>

<span data-ttu-id="34f22-143">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="34f22-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="34f22-144">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="34f22-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="34f22-145">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="34f22-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="34f22-146">Тепер в Marketo можна знайти сегменти у [списку Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="34f22-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="34f22-147">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="34f22-147">Data privacy and compliance</span></span>

<span data-ttu-id="34f22-148">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Marketo можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="34f22-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="34f22-149">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія Marketo відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="34f22-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="34f22-150">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="34f22-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="34f22-151">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="34f22-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]