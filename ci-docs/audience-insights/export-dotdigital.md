---
title: Експорт даних Customer Insights до DotDigital
description: Дізнайтесь, як настроїти підключення до DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269125"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="0a1b1-103">З'єднувач для DotDigital (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="0a1b1-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="0a1b1-104">Експорт сегментів уніфікованих профілів клієнтів до адресних книг DotDigital і використання їх для кампаній, маркетингових повідомлень і створення сегментів клієнтів за допомогою DotDigital.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0a1b1-105">Вимоги</span><span class="sxs-lookup"><span data-stu-id="0a1b1-105">Prerequisites</span></span>

-   <span data-ttu-id="0a1b1-106">Ви маєте [обліковий запис DotDigital](https://dotdigital.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0a1b1-107">Наявні адресні книги в DotDigital і відповідні ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="0a1b1-108">ІДЕНТИФІКАТОР можна знайти в URL-адресі, якщо вибрати та відкрити адресну книгу.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="0a1b1-109">Для отримання додаткових відомостей див. [адресні книги DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="0a1b1-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="0a1b1-110">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0a1b1-111">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="0a1b1-112">Підключення до DotDigital</span><span class="sxs-lookup"><span data-stu-id="0a1b1-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="0a1b1-113">Відкрийте **Адміністрування** > **Призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0a1b1-114">У розділі **DotDigital** натисніть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="0a1b1-115">Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Область конфігурації для експорту DotDigital.":::

1. <span data-ttu-id="0a1b1-117">Введіть ваше **ім’я користувача DotDigital та пароль**.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="0a1b1-118">Введіть **[ідентифікатор адресної книги DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="0a1b1-119">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0a1b1-120">Виберіть **З'єднати**, щоб ініціалізувати підключення до DotDigital.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="0a1b1-121">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0a1b1-122">Натисніть **Далі**, щоб налаштувати експорт.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0a1b1-123">Настроювання з’єднувача</span><span class="sxs-lookup"><span data-stu-id="0a1b1-123">Configure the connector</span></span>

1. <span data-ttu-id="0a1b1-124">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0a1b1-125">Повторіть ці самі кроки для інших необов'язкових полів, наприклад **Ім'я**, **Прізвище**, **Повне ім'я**, **Стать** і **Поштовий індекс**.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="0a1b1-126">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-126">Select the segments you want to export.</span></span> <span data-ttu-id="0a1b1-127">Загалом до DotDigital можна експортувати до 1 000 000 профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="0a1b1-128">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0a1b1-129">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="0a1b1-129">Export the data</span></span>

<span data-ttu-id="0a1b1-130">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0a1b1-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0a1b1-131">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0a1b1-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0a1b1-132">Тепер у DotDigital можна знайти сегменти в [адресних книгах DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="0a1b1-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0a1b1-133">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="0a1b1-133">Known limitations</span></span>

- <span data-ttu-id="0a1b1-134">До 1 000 000 профілів на експорт до DotDigital.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="0a1b1-135">Експорт до DotDigital обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="0a1b1-136">Експортування сегментів загальною кількістю 1 000 000 профілів може тривати до 3 годин через обмеження з боку постачальника.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="0a1b1-137">Кількість профілів, які можна експортувати до DotDigital, залежить від сервісного договору з DotDigital.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0a1b1-138">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="0a1b1-138">Data privacy and compliance</span></span>

<span data-ttu-id="0a1b1-139">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до DotDigital можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0a1b1-140">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія DotDigital відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0a1b1-141">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0a1b1-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0a1b1-142">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="0a1b1-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]