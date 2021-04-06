---
title: Експорт даних Customer Insights до AdRoll
description: Дізнайтесь, як настроїти підключення до AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697099"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="f403c-103">З'єднувач для AdRoll (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="f403c-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="f403c-104">Експортуйте до AdRoll сегменти уніфікованих профілів клієнтів і використовуйте їх для реклами.</span><span class="sxs-lookup"><span data-stu-id="f403c-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f403c-105">Вимоги</span><span class="sxs-lookup"><span data-stu-id="f403c-105">Prerequisites</span></span>

-   <span data-ttu-id="f403c-106">Ви маєте [обліковий запис AdRoll](https://www.adroll.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="f403c-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f403c-107">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="f403c-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f403c-108">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="f403c-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="f403c-109">Підключитися до AdRoll</span><span class="sxs-lookup"><span data-stu-id="f403c-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="f403c-110">Відкрийте **Адміністрування** > **Призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="f403c-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f403c-111">У розділі **AdRoll** натисніть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="f403c-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="f403c-112">Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="f403c-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Область налаштування для підключення AdRoll.":::

1. <span data-ttu-id="f403c-114">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="f403c-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f403c-115">Виберіть **Підключити**, щоб ініціалізувати підключення до AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f403c-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="f403c-116">Виберіть **Автентифікацію за допомогою AdRoll** і надайте облікові дані AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f403c-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="f403c-117">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f403c-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f403c-118">Введіть свій **Ідентифікатор рекламодавця AdRoll** [Рекламодавець AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="f403c-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="f403c-119">Натисніть **Далі**, щоб налаштувати експорт.</span><span class="sxs-lookup"><span data-stu-id="f403c-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f403c-120">Настроювання з’єднувача</span><span class="sxs-lookup"><span data-stu-id="f403c-120">Configure the connector</span></span>

1. <span data-ttu-id="f403c-121">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="f403c-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f403c-122">Необхідно експортувати сегменти в AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f403c-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="f403c-123">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="f403c-123">Select the segments you want to export.</span></span> <span data-ttu-id="f403c-124">Виберіть сегмент, який має щонайменше 100 учасників.</span><span class="sxs-lookup"><span data-stu-id="f403c-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="f403c-125">Сегменти меншого розміру експортувати не можна.</span><span class="sxs-lookup"><span data-stu-id="f403c-125">You can't export smaller segments.</span></span> <span data-ttu-id="f403c-126">Крім того, максимальний розмір сегмента для експорту до 250 000 учасників на один експорт.</span><span class="sxs-lookup"><span data-stu-id="f403c-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="f403c-127">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="f403c-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f403c-128">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="f403c-128">Export the data</span></span>

<span data-ttu-id="f403c-129">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f403c-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f403c-130">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f403c-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f403c-131">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="f403c-131">Known limitations</span></span>

- <span data-ttu-id="f403c-132">Загалом до AdRoll можна експортувати до 250 000 профілів за один експорт.</span><span class="sxs-lookup"><span data-stu-id="f403c-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="f403c-133">В AdRoll не можна експортувати сегменти, які містять менше, ніж 100 профілів.</span><span class="sxs-lookup"><span data-stu-id="f403c-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="f403c-134">Експорт до AdRoll обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="f403c-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="f403c-135">Експортування до 250 000 профілів в AdRoll може тривати до 10 хвилин.</span><span class="sxs-lookup"><span data-stu-id="f403c-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="f403c-136">Кількість профілів, які можна експортувати до AdRoll, залежить від сервісного договору з AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f403c-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f403c-137">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="f403c-137">Data privacy and compliance</span></span>

<span data-ttu-id="f403c-138">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до AdRoll можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="f403c-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f403c-139">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія AdRoll відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="f403c-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f403c-140">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f403c-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="f403c-141">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="f403c-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
