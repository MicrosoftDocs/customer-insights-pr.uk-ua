---
title: Експорт даних Customer Insights до Marketo
description: Дізнайтеся, як налаштувати підключення та експорт до Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059341"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="720b3-103">Експорт сегментів до Marketo (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="720b3-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="720b3-104">Експортуйте сегменти уніфікованих профілів клієнтів, щоб формувати кампанії, здійснювати маркетингові розсилки електронною поштою та використовувати конкретні групи клієнтів за допомогою Marketo.</span><span class="sxs-lookup"><span data-stu-id="720b3-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="720b3-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="720b3-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="720b3-106">Ви маєте [обліковий запис Marketo](https://login.marketo.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="720b3-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="720b3-107">У Marketo наявні списки й відповідні ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="720b3-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="720b3-108">Для отримання додаткових відомостей див. розділ [Список Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="720b3-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="720b3-109">Ви маєте [налаштовані сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="720b3-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="720b3-110">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="720b3-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="720b3-111">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="720b3-111">Known limitations</span></span>

- <span data-ttu-id="720b3-112">До 1 000 000 профілів на експорт до Marketo.</span><span class="sxs-lookup"><span data-stu-id="720b3-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="720b3-113">Експорт до Marketo обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="720b3-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="720b3-114">Експортування сегментів загальною кількістю 1 000 000 профілів може тривати до 3 годин.</span><span class="sxs-lookup"><span data-stu-id="720b3-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="720b3-115">Кількість профілів, які можна експортувати до Marketo, залежить від сервісного договору з Marketo.</span><span class="sxs-lookup"><span data-stu-id="720b3-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="720b3-116">Налаштування підключення до Marketo</span><span class="sxs-lookup"><span data-stu-id="720b3-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="720b3-117">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="720b3-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="720b3-118">Виберіть **Додати підключення** та оберіть **Marketo**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="720b3-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="720b3-119">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="720b3-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="720b3-120">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="720b3-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="720b3-121">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="720b3-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="720b3-122">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="720b3-122">Choose who can use this connection.</span></span> <span data-ttu-id="720b3-123">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="720b3-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="720b3-124">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="720b3-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="720b3-125">Уведіть **[ідентифікатор клієнта Marketo, секретний ключ клієнта та Ім’я хоста кінцевої точки REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="720b3-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="720b3-126">Ім'я хоста кінцевої точки REST — це лише ім’я хоста, без `https://`.</span><span class="sxs-lookup"><span data-stu-id="720b3-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="720b3-127">Приклад:`xyz-abc-123.mktorest.com`</span><span class="sxs-lookup"><span data-stu-id="720b3-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="720b3-128">Виберіть **Я погоджуюся**, щоб підтвердити **Конфіденційність даних і відповідність**, і натисніть **З'єднати**, щоб ініціалізувати підключення до Marketo.</span><span class="sxs-lookup"><span data-stu-id="720b3-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="720b3-129">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="720b3-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="720b3-130">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="720b3-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="720b3-131">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="720b3-131">Configure an export</span></span>

<span data-ttu-id="720b3-132">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="720b3-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="720b3-133">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="720b3-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="720b3-134">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="720b3-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="720b3-135">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="720b3-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="720b3-136">У полі **Підключення для експорту** виберіть підключення з розділу Marketo.</span><span class="sxs-lookup"><span data-stu-id="720b3-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="720b3-137">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="720b3-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="720b3-138">Введіть **[ідентифікатор списку Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="720b3-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="720b3-139">Ідентифікатор списку — це тільки числове значення.</span><span class="sxs-lookup"><span data-stu-id="720b3-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="720b3-140">Наприклад, якщо ваш ідентифікатор списку Marketo ST12345A7, видаліть символи до та після цифр і введіть `12345`.</span><span class="sxs-lookup"><span data-stu-id="720b3-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="720b3-141">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="720b3-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="720b3-142">За бажанням ви можете експортувати **Ім'я**, **Прізвище**, **Місто**, **Штат** та **Країну/Регіон**, щоб створювати більш персоналізовані електронні листи.</span><span class="sxs-lookup"><span data-stu-id="720b3-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="720b3-143">Виберіть **Додати атрибут**, щоб зіставити ці поля.</span><span class="sxs-lookup"><span data-stu-id="720b3-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="720b3-144">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="720b3-144">Select the segments you want to export.</span></span> <span data-ttu-id="720b3-145">Загалом до Marketo можна експортувати до 1 000 000 профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="720b3-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="720b3-146">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="720b3-146">Select **Save**.</span></span>

<span data-ttu-id="720b3-147">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="720b3-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="720b3-148">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="720b3-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="720b3-149">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="720b3-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="720b3-150">Тепер в Marketo можна знайти сегменти у [списку Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="720b3-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="720b3-151">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="720b3-151">Data privacy and compliance</span></span>

<span data-ttu-id="720b3-152">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Marketo можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="720b3-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="720b3-153">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія Marketo відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="720b3-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="720b3-154">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="720b3-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="720b3-155">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="720b3-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
