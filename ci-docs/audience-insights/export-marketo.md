---
title: Експорт даних Customer Insights до Marketo
description: Дізнайтесь, як настроїти підключення до Marketo
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597996"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="f9c01-103">З'єднувач для Marketo (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="f9c01-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="f9c01-104">Експортуйте сегменти уніфікованих профілів клієнтів, щоб формувати кампанії, здійснювати маркетингові розсилки електронною поштою та використовувати конкретні групи клієнтів за допомогою Marketo.</span><span class="sxs-lookup"><span data-stu-id="f9c01-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f9c01-105">Вимоги</span><span class="sxs-lookup"><span data-stu-id="f9c01-105">Prerequisites</span></span>

-   <span data-ttu-id="f9c01-106">Ви маєте [обліковий запис Marketo](https://login.marketo.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="f9c01-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f9c01-107">У Marketo наявні списки й відповідні ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="f9c01-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="f9c01-108">Для отримання додаткових відомостей див. розділ [Список Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="f9c01-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="f9c01-109">Ви маєте [налаштовані сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f9c01-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="f9c01-110">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="f9c01-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="f9c01-111">Підключення до Marketo</span><span class="sxs-lookup"><span data-stu-id="f9c01-111">Connect to Marketo</span></span>

1. <span data-ttu-id="f9c01-112">Відкрийте **Адміністрування** > **Призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="f9c01-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f9c01-113">У розділі **Marketo** натисніть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="f9c01-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="f9c01-114">Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="f9c01-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f9c01-115">Введіть **[ідентифікатор клієнта Marketo, секретний ключ клієнта та Ім’я хоста кінцевої точки REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="f9c01-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="f9c01-116">Введіть **[ідентифікатор списку Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="f9c01-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="f9c01-117">Виберіть **Я погоджуюся**, щоб підтвердити **Конфіденційність даних і відповідність**, і натисніть **З'єднати**, щоб ініціалізувати підключення до Marketo.</span><span class="sxs-lookup"><span data-stu-id="f9c01-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="f9c01-118">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f9c01-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Експорт скріншоту для підключення до Marketo":::

1. <span data-ttu-id="f9c01-120">Натисніть **Далі**, щоб налаштувати експорт.</span><span class="sxs-lookup"><span data-stu-id="f9c01-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f9c01-121">Настроювання з’єднувача</span><span class="sxs-lookup"><span data-stu-id="f9c01-121">Configure the connector</span></span>

1. <span data-ttu-id="f9c01-122">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="f9c01-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="f9c01-123">Додатково можна експортувати **Ім’я**, **Прізвище**, **Місто**, **Штат** і **Країну/регіон** у вигляді додаткових полів для створення додаткових персоналізованих електронних листів.</span><span class="sxs-lookup"><span data-stu-id="f9c01-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="f9c01-124">Виберіть **Додати атрибут**, щоб зіставити ці поля.</span><span class="sxs-lookup"><span data-stu-id="f9c01-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="f9c01-125">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="f9c01-125">Select the segments you want to export.</span></span> <span data-ttu-id="f9c01-126">Загалом до Marketo можна експортувати до 1 000 000 профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="f9c01-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Вибір полів і сегментів для експорту в Marketo":::

1. <span data-ttu-id="f9c01-128">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="f9c01-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f9c01-129">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="f9c01-129">Export the data</span></span>

<span data-ttu-id="f9c01-130">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f9c01-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f9c01-131">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f9c01-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f9c01-132">Тепер в Marketo можна знайти сегменти у [списку Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="f9c01-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f9c01-133">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="f9c01-133">Known limitations</span></span>

- <span data-ttu-id="f9c01-134">До 1 000 000 профілів на експорт до Marketo.</span><span class="sxs-lookup"><span data-stu-id="f9c01-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="f9c01-135">Експорт до Marketo обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="f9c01-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="f9c01-136">Експортування сегментів загальною кількістю 1 000 000 профілів може тривати до 3 годин.</span><span class="sxs-lookup"><span data-stu-id="f9c01-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="f9c01-137">Кількість профілів, які можна експортувати до Marketo, залежить від сервісного договору з Marketo.</span><span class="sxs-lookup"><span data-stu-id="f9c01-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f9c01-138">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="f9c01-138">Data privacy and compliance</span></span>

<span data-ttu-id="f9c01-139">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Marketo можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="f9c01-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f9c01-140">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія Marketo відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="f9c01-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f9c01-141">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f9c01-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f9c01-142">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="f9c01-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]