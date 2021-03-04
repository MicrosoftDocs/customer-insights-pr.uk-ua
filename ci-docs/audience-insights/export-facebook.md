---
title: Експорт даних Customer Insights до Facebook Ads Manager
description: Дізнайтесь, як настроїти підключення до Менеджера реклами Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269999"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="7a2ef-103">З'єднувач для Менеджера реклами Facebook (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="7a2ef-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="7a2ef-104">Експортуйте сегменти уніфікованих профілів клієнтів до Менеджера реклами Facebook, щоб створити кампанії у Facebook та Instagram.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7a2ef-105">Вимоги</span><span class="sxs-lookup"><span data-stu-id="7a2ef-105">Prerequisites</span></span>

- <span data-ttu-id="7a2ef-106">Ви повинні мати [Обліковий запис реклами у **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), що містить [корпоративний обліковий запис **Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="7a2ef-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="7a2ef-107">Потрібно бути адміністратором [Рекламного облікового запису **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)..</span><span class="sxs-lookup"><span data-stu-id="7a2ef-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="7a2ef-108">Підключення до Менеджера реклами Facebook</span><span class="sxs-lookup"><span data-stu-id="7a2ef-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="7a2ef-109">Відкрийте **Адміністрування** > **Призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7a2ef-110">В області **Менеджер реклам Facebook** виберіть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="7a2ef-111">Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7a2ef-112">Виберіть **Продовжити у Facebook**, щоб увійти до рекламного облікового запису Facebook.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="7a2ef-113">Надайте дозвіл **ads_management** після автентифікація за допомогою Facebook.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="7a2ef-114">Виберіть **Рекламний обліковий запис Facebook**, в якому потрібно працювати.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="7a2ef-115">Виберіть **Наявну настроювану аудиторію** з розкривного списку або створіть **Нову настроювану аудиторію**.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="7a2ef-116">Для отримання додаткових відомостей див. [**Аудиторія у Менеджері реклами Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="7a2ef-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="7a2ef-117">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7a2ef-118">Натисніть **Далі**, щоб налаштувати експорт.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="7a2ef-119">Настроювання з’єднувача</span><span class="sxs-lookup"><span data-stu-id="7a2ef-119">Configure the connector</span></span>

1. <span data-ttu-id="7a2ef-120">У полі **Вибір основного ідентифікатора**, виберіть **Повідомлення електронної пошти**, **Ім'я та адреса** або **Телефон**, щоб надсилати до Менеджера реклами Facebook.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="7a2ef-121">Зіставте відповідні атрибути з об’єднаної сутності клієнта для вибраного ідентифікатора ключа.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="7a2ef-122">Порада. Кращі шанси на відповідність будуть тоді, коли вибрати **електронну пошту** як основний ідентифікатор.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="7a2ef-123">Зіставлення може покращитися, якщо додавати додаткові ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="7a2ef-124">Виберіть **Додати атрибут**, щоб зіставити додаткові атрибути для розсилки до Менеджера реклами Facebook.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="7a2ef-125">Атрибути з Мереджера реклами Facebook зіставляються з такими зрозумілими іменами: **FN** = **Ім'я**, **LN** = **Прізвище**, **FI** = **Ініціали**, **PHONE** = **Телефон**, **GEN** = **Стать**, **DOB** = **Дата народження**, **ST** = **Область**, **CT** = **Місто**, **ZIP** = **Поштовий індекс**, **COUNTRY** = **Країна**</span><span class="sxs-lookup"><span data-stu-id="7a2ef-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="7a2ef-126">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="7a2ef-127">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7a2ef-128">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="7a2ef-128">Export the data</span></span>

<span data-ttu-id="7a2ef-129">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7a2ef-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7a2ef-130">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7a2ef-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7a2ef-131">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="7a2ef-131">Known limitations</span></span>

- <span data-ttu-id="7a2ef-132">До 10 мільйонів профілів клієнтів на один експорт до Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="7a2ef-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="7a2ef-133">Експорт до Facebook Ads Manager обмежено сегментами</span><span class="sxs-lookup"><span data-stu-id="7a2ef-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="7a2ef-134">Експортування сегментів загальною кількістю 10 мільйонів профілів може тривати до 90 хвилин.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7a2ef-135">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="7a2ef-135">Data privacy and compliance</span></span>

<span data-ttu-id="7a2ef-136">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Facebook Ads Manager можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7a2ef-137">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб Facebook Ads відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="7a2ef-138">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7a2ef-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7a2ef-139">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]