---
title: Експорт даних Customer Insights до SFTP hosts
description: Дізнайтесь, як настроїти підключення до хоста SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598410"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="5a259-103">З’єднувач для SFTP (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="5a259-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="5a259-104">Використовуйте дані клієнтів у програмах сторонніх виробників, експортувавши їх до хосту протоколу SFTP.</span><span class="sxs-lookup"><span data-stu-id="5a259-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a259-105">Вимоги</span><span class="sxs-lookup"><span data-stu-id="5a259-105">Prerequisites</span></span>

- <span data-ttu-id="5a259-106">Доступність хосту SFTP і відповідні облікові дані.</span><span class="sxs-lookup"><span data-stu-id="5a259-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="5a259-107">Підключитися до SFTP</span><span class="sxs-lookup"><span data-stu-id="5a259-107">Connect to SFTP</span></span>

1. <span data-ttu-id="5a259-108">Відкрийте **Адміністрування** > **Призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="5a259-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5a259-109">У розділі **SFTP** виберіть **Настроювання**.</span><span class="sxs-lookup"><span data-stu-id="5a259-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="5a259-110">Дайте своєму призначенню ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="5a259-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="5a259-111">Укажіть **Ім'я користувача**, **Пароль**, **Ім'я хосту** та **Папку експорту** для вашого облікового запису SFTP.</span><span class="sxs-lookup"><span data-stu-id="5a259-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="5a259-112">Виберіть **Перевірити**, щоб перевірити підключення.</span><span class="sxs-lookup"><span data-stu-id="5a259-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="5a259-113">Після успішної перевірки виберіть, чи потрібно експортувати дані **стиснутими gzip** або **без стискання**, і виберіть **роздільник полів** для експортованих файлів.</span><span class="sxs-lookup"><span data-stu-id="5a259-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="5a259-114">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="5a259-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5a259-115">Натисніть **Далі**, щоб почати настроювання експорту.</span><span class="sxs-lookup"><span data-stu-id="5a259-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="5a259-116">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="5a259-116">Configure the export</span></span>

1. <span data-ttu-id="5a259-117">Виберіть сутності, наприклад, сегменти, які необхідно експортувати.</span><span class="sxs-lookup"><span data-stu-id="5a259-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5a259-118">Кожна вибрана сутність при експортуванні створюватиме до п’яти файлів із результатами.</span><span class="sxs-lookup"><span data-stu-id="5a259-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="5a259-119">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="5a259-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5a259-120">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="5a259-120">Export the data</span></span>

<span data-ttu-id="5a259-121">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5a259-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="5a259-122">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5a259-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5a259-123">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="5a259-123">Known limitations</span></span>

- <span data-ttu-id="5a259-124">Час виконання експорту залежатиме від швидкодії системи.</span><span class="sxs-lookup"><span data-stu-id="5a259-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="5a259-125">Рекомендуємо використовувати два ядра ЦП і 1 Гб пам'яті в якості мінімальної конфігурації сервера.</span><span class="sxs-lookup"><span data-stu-id="5a259-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="5a259-126">Експортування сутностей, що містять до 100 мільйонів профілів клієнтів, може тривати до 90 хвилин при використанні мінімальної конфігурації із двома ядрами ЦП та 1 Гб пам'яті.</span><span class="sxs-lookup"><span data-stu-id="5a259-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5a259-127">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="5a259-127">Data privacy and compliance</span></span>

<span data-ttu-id="5a259-128">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до SFTP Technologies можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="5a259-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5a259-129">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб напрям експорту відповідав будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="5a259-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5a259-130">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5a259-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5a259-131">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="5a259-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]