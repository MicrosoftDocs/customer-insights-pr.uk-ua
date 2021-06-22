---
title: Експорт даних Customer Insights до SFTP hosts
description: Дізнайтеся, як налаштувати підключення та експорт до розташування SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124344"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a><span data-ttu-id="02580-103">Експорт сегментів та інших даних до SFTP (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="02580-103">Export segments and other data to SFTP (preview)</span></span>

<span data-ttu-id="02580-104">Використовуйте дані клієнтів у сторонніх програмах, експортуючи їх до розташування із підтримкою SFTP.</span><span class="sxs-lookup"><span data-stu-id="02580-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="02580-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="02580-105">Prerequisites for connection</span></span>

- <span data-ttu-id="02580-106">Доступність хосту SFTP і відповідні облікові дані.</span><span class="sxs-lookup"><span data-stu-id="02580-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="02580-107">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="02580-107">Known limitations</span></span>

- <span data-ttu-id="02580-108">Час виконання експорту залежатиме від швидкодії системи.</span><span class="sxs-lookup"><span data-stu-id="02580-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="02580-109">Рекомендуємо використовувати два ядра ЦП і 1 Гб пам'яті в якості мінімальної конфігурації сервера.</span><span class="sxs-lookup"><span data-stu-id="02580-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="02580-110">Експортування сутностей, що містять до 100 мільйонів профілів клієнтів, може тривати до 90 хвилин при використанні мінімальної конфігурації із двома ядрами ЦП та 1 Гб пам'яті.</span><span class="sxs-lookup"><span data-stu-id="02580-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="02580-111">Налаштування підключення до SFTP</span><span class="sxs-lookup"><span data-stu-id="02580-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="02580-112">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="02580-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="02580-113">Виберіть **Додати підключення** та оберіть **SFTP**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="02580-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="02580-114">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="02580-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="02580-115">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="02580-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="02580-116">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="02580-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="02580-117">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="02580-117">Choose who can use this connection.</span></span> <span data-ttu-id="02580-118">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="02580-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="02580-119">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="02580-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="02580-120">Укажіть **Ім'я користувача**, **Пароль**, **Ім'я хосту** та **Папку експорту** для вашого облікового запису SFTP.</span><span class="sxs-lookup"><span data-stu-id="02580-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="02580-121">Виберіть **Перевірити**, щоб перевірити підключення.</span><span class="sxs-lookup"><span data-stu-id="02580-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="02580-122">Виберіть, чи бажаєте ви експортувати дані **стиснутими за допомогою Gzip** або **без стискання**, а також вкажіть **роздільник полів** для експортованих файлів.</span><span class="sxs-lookup"><span data-stu-id="02580-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="02580-123">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="02580-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="02580-124">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="02580-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="02580-125">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="02580-125">Configure an export</span></span>

<span data-ttu-id="02580-126">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="02580-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="02580-127">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="02580-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="02580-128">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="02580-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="02580-129">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="02580-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="02580-130">У полі **Підключення для експорту** виберіть підключення з розділу SFTP.</span><span class="sxs-lookup"><span data-stu-id="02580-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="02580-131">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="02580-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="02580-132">Виберіть сутності, наприклад, сегменти, які необхідно експортувати.</span><span class="sxs-lookup"><span data-stu-id="02580-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="02580-133">Кожна вибрана сутність буде розділена на щонайбільше п'ять вихідних файлів під час експорту.</span><span class="sxs-lookup"><span data-stu-id="02580-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="02580-134">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="02580-134">Select **Save**.</span></span>

<span data-ttu-id="02580-135">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="02580-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="02580-136">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="02580-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="02580-137">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="02580-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="02580-138">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="02580-138">Data privacy and compliance</span></span>

<span data-ttu-id="02580-139">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до SFTP Technologies можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="02580-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="02580-140">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб напрям експорту відповідав будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="02580-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="02580-141">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="02580-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="02580-142">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="02580-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
