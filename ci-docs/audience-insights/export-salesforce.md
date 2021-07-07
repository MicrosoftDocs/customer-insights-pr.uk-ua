---
title: Експортуйте дані Customer Insights до хмари Salesforce Marketing
description: Дізнайтеся про те, як налаштувати підключення та експортувати дані до хмари Salesforce Marketing.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314690"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="2f1d8-103">Експортуйте сегменти та інші дані до хмари Salesforce Marketing (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="2f1d8-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="2f1d8-104">Використовуйте дані клієнтів у хмарі Salesforce Marketing способом експорту через розташування Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="2f1d8-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="2f1d8-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="2f1d8-105">Prerequisites for connection</span></span>

- <span data-ttu-id="2f1d8-106">Доступність хост-комп’ютера SFTP і відповідних облікових даних адміністратора.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="2f1d8-107">Як налаштувати розташування SFTP для хмари Salesforce Marketing</span><span class="sxs-lookup"><span data-stu-id="2f1d8-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="2f1d8-108">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="2f1d8-108">Known limitations</span></span>

- <span data-ttu-id="2f1d8-109">Час виконання експорту залежатиме від швидкодії системи.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="2f1d8-110">Рекомендуємо використовувати два ядра ЦП і 1 Гб пам'яті в якості мінімальної конфігурації сервера.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="2f1d8-111">Для експорту сутностей із максимумом 100 мільйонів профілів клієнтів може знадобитися 90 хвилин при використанні рекомендованої мінімальної конфігурації.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="2f1d8-112">Налаштуйте підключення до хмари Salesforce Marketing</span><span class="sxs-lookup"><span data-stu-id="2f1d8-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="2f1d8-113">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2f1d8-114">Виберіть пункт **Додати підключення**, потім виберіть розділ **Хмара Salesforce Marketing**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="2f1d8-115">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2f1d8-116">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2f1d8-117">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2f1d8-118">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-118">Choose who can use this connection.</span></span> <span data-ttu-id="2f1d8-119">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2f1d8-120">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2f1d8-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2f1d8-121">Укажіть **Ім'я користувача**, **Пароль**, **Ім'я хосту** та **Папку експорту** для вашого облікового запису SFTP.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="2f1d8-122">Виберіть **Перевірити**, щоб перевірити підключення.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="2f1d8-123">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2f1d8-124">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2f1d8-125">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="2f1d8-125">Configure an export</span></span>

<span data-ttu-id="2f1d8-126">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2f1d8-127">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2f1d8-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2f1d8-128">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2f1d8-129">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2f1d8-130">У полі **Підключення для експорту** виберіть підключення з розділу SFTP.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="2f1d8-131">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2f1d8-132">Виберіть, чи бажаєте ви експортувати дані **стиснутими за допомогою Gzip** або **без стискання**, а також вкажіть **роздільник полів** для експортованих файлів.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="2f1d8-133">Виберіть сутності, наприклад, сегменти, які необхідно експортувати.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2f1d8-134">Кожна вибрана сутність буде розділена на щонайбільше п'ять вихідних файлів під час експорту.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="2f1d8-135">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-135">Select **Save**.</span></span>

<span data-ttu-id="2f1d8-136">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2f1d8-137">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2f1d8-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2f1d8-138">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2f1d8-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="2f1d8-139">Імпортуйте дані Customer Insights із розташування SFTP до хмари Salesforce Marketing</span><span class="sxs-lookup"><span data-stu-id="2f1d8-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="2f1d8-140">Створіть [розширення даних у хмарі Salesforce Marketing](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), щоб імпортувати файл даних Customer Insights із розташування SFTP.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="2f1d8-141">[Імпортуйте дані з розташування SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) до розширення даних хмари Salesforce Marketing.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="2f1d8-142">Налаштуйте автоматизацію, щоб імпортувати дані до розширень даних.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="2f1d8-143">Дізнайтеся докладніше про [автоматизацію перенесення файлів і заплановану автоматизацію](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="2f1d8-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="2f1d8-144">Визначте [автоматизацію перенесення файлів](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) або [заплановану автоматизацію](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="2f1d8-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="2f1d8-145">Далі наведено приклад [автоматизації за допомогою SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="2f1d8-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2f1d8-146">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="2f1d8-146">Data privacy and compliance</span></span>

<span data-ttu-id="2f1d8-147">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до SFTP Technologies можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2f1d8-148">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб напрям експорту відповідав будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2f1d8-149">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2f1d8-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2f1d8-150">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити це призначення експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="2f1d8-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
