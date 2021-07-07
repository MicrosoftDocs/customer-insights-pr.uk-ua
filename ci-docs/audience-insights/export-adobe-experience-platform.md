---
title: Експортування даних Customer Insights до платформи Adobe Experience
description: Дізнайтеся про те, як використовувати сегменти аналітичних оглядів аудиторії на платформі Adobe Experience.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305549"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="fbbc8-103">Використовуйте сегменти Customer Insights на платформі Adobe Experience (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="fbbc8-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="fbbc8-104">Як користувач аналітичних оглядів аудиторії в Dynamics 365 Customer Insights, ви могли створювати сегменти для підвищення ефективності своїх маркетингових кампаній способом націлювання рекламного матеріалу на доречні аудиторії.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="fbbc8-105">Щоб використовувати сегмент з аналітики аудиторії на платформі Adobe Experience та в програмах, як-от Adobe Campaign Standard, потрібно виконати кілька кроків, наведених у цій статті.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Схема процесів кроків, описаних у цій статті.":::

## <a name="prerequisites"></a><span data-ttu-id="fbbc8-107">Вимоги</span><span class="sxs-lookup"><span data-stu-id="fbbc8-107">Prerequisites</span></span>

-   <span data-ttu-id="fbbc8-108">Ліцензія Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="fbbc8-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="fbbc8-109">Ліцензія платформи Adobe Experience</span><span class="sxs-lookup"><span data-stu-id="fbbc8-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="fbbc8-110">Ліцензія Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fbbc8-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="fbbc8-111">Обліковий запис сховища Azure Blob</span><span class="sxs-lookup"><span data-stu-id="fbbc8-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="fbbc8-112">Огляд кампанії</span><span class="sxs-lookup"><span data-stu-id="fbbc8-112">Campaign Overview</span></span>

<span data-ttu-id="fbbc8-113">Щоб краще зрозуміти, як можна використовувати сегменти з аналітики аудиторії на платформі Adobe Experience, перегляньте вигадані приклади кампаній.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="fbbc8-114">Припустімо, що ваша компанія пропонує клієнтам щомісячну передплату на послуги в Сполучених Штатах Америки.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="fbbc8-115">Вам потрібно визначити клієнтів, передплати яких мають бути продовжені впродовж наступних 8 днів, але які ще не продовжили їх.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="fbbc8-116">Щоб зберегти цих клієнтів, ви хочете надіслати їм акційну пропозицію електронною поштою за допомогою платформи Adobe Experience.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="fbbc8-117">У цьому прикладі ми хочемо запустити рекламну кампанію електронною поштою один раз.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="fbbc8-118">У цій статті не розглядається варіант використання багатократного запуску кампанії.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="fbbc8-119">Визначте цільову аудиторію</span><span class="sxs-lookup"><span data-stu-id="fbbc8-119">Identify your target audience</span></span>

<span data-ttu-id="fbbc8-120">У нашому сценарії ми припускаємо, що адреси електронної пошти клієнтів доступні в аналітичних оглядах аудиторії, в їхні рекламні уподобання були проаналізовані для ідентифікації учасників сегменту.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="fbbc8-121">[Сегмент, визначений у аналітичних оглядах аудиторії](segments.md), називається **ChurnProneCustomers** і ви плануєте надіслати цим клієнтам рекламну пропозицію електронною поштою.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Знімок екрана: сторінка сегментів зі створеним сегментом ChurnProneCustomers.":::

<span data-ttu-id="fbbc8-123">Повідомлення електронної пошти, яке необхідно надіслати, міститиме ім'я, прізвище та дату завершення передплати клієнта.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="fbbc8-124">Він інформує клієнтів про знижку, яку вони отримають, якщо продовжать передплату до закінчення терміну її дії.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="fbbc8-125">Експортуйте цільову аудиторію</span><span class="sxs-lookup"><span data-stu-id="fbbc8-125">Export your target audience</span></span>

<span data-ttu-id="fbbc8-126">Визначивши нашу цільову аудиторію, можна налаштувати експорту з аналітичних оглядів аудиторії до облікового запису сховища BLOB-об'єктів Azure.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="fbbc8-127">Налаштуйте підключення</span><span class="sxs-lookup"><span data-stu-id="fbbc8-127">Configure a connection</span></span>

1. <span data-ttu-id="fbbc8-128">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="fbbc8-129">Виберіть розділ **Додати підключення**, потім виберіть **Сховище BLOB-об’єктів Azure** або виберіть **Налаштувати** на плитці **Сховище BLOB-об’єктів Azure**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Плитка конфігурації для сховища BLOB-об'єктів Azure."::: 

1. <span data-ttu-id="fbbc8-131">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="fbbc8-132">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="fbbc8-133">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="fbbc8-134">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-134">Choose who can use this connection.</span></span> <span data-ttu-id="fbbc8-135">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="fbbc8-136">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="fbbc8-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="fbbc8-137">Введіть **Ім’я бізнес-партнера**, **Ключ бізнес-партнера** та **Контейнер** для облікового запису сховища BLOB-об’єктів, до якого ви бажаєте експортувати сегмент.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Знімок екрана із конфігураціями облікового запису сховища."::: 
   
    - <span data-ttu-id="fbbc8-139">Щоб отримати докладніші відомості про те, як знайти ім’я облікового запису сховища BLOB-об’єктів, див. розділ [Керуйте налаштуваннями облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="fbbc8-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="fbbc8-140">Щоб дізнатися, як створити контейнер, див. розділ [Створення контейнера ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="fbbc8-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="fbbc8-141">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="fbbc8-142">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="fbbc8-142">Configure an export</span></span>

<span data-ttu-id="fbbc8-143">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="fbbc8-144">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="fbbc8-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fbbc8-145">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="fbbc8-146">Щоб створити новий експорт, виберіть **Додати експорт**.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="fbbc8-147">У полі **Підключення для експорту** виберіть підключення з розділу «Сховище BLOB-об’єктів Azure».</span><span class="sxs-lookup"><span data-stu-id="fbbc8-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="fbbc8-148">Якщо ви не бачите імені цього розділу, це означає, що для вас не доступні будь-які підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="fbbc8-149">Виберіть сегмент, який потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="fbbc8-150">У цьому прикладі це **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Знімок екрана: інтерфейс користувача вибору сегмента з вибраним сегментом ChurnProneCustomers.":::

1. <span data-ttu-id="fbbc8-152">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-152">Select **Save**.</span></span>

<span data-ttu-id="fbbc8-153">Після того, як ви зберегли пункт призначення експорту, ви зможете знайти його в розділі **Дані** > **Експорт**.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="fbbc8-154">Тепер сегмент [можна експортувати неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fbbc8-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="fbbc8-155">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md).</span><span class="sxs-lookup"><span data-stu-id="fbbc8-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fbbc8-156">Переконайтеся, що кількість записів у експортованому сегменті перебуває в межах дозволеного ліміту вашої ліцензії Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="fbbc8-157">Експортовані дані зберігаються в контейнері сховища BLOB-об'єктів Azure, який було налаштовано вище.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="fbbc8-158">У контейнері автоматично створюється такий перелік дій:</span><span class="sxs-lookup"><span data-stu-id="fbbc8-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="fbbc8-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="fbbc8-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="fbbc8-160">Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="fbbc8-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="fbbc8-161">*model.json* для експортованих сутностей розташовується на рівні *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="fbbc8-162">Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="fbbc8-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="fbbc8-163">Визначення моделі даних досвіду (XDM) на платформі Adobe Experience</span><span class="sxs-lookup"><span data-stu-id="fbbc8-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="fbbc8-164">Перед тим, як експортовані дані з аналітичних оглядів аудиторії можна буде використовувати в межах платформи Adobe Experience, потрібно визначити схему моделі даних досвіду та [налаштувати дані для профілю користувача в реальному часі](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="fbbc8-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="fbbc8-165">Дізнайтеся, [що таке XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) і зрозумійте [основи створення схем](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="fbbc8-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="fbbc8-166">Імпортування даних до платформи Adobe Experience</span><span class="sxs-lookup"><span data-stu-id="fbbc8-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="fbbc8-167">Тепер, коли все готово, необхідно імпортувати підготовлені дані про аудиторію аналітичних оглядів аудиторії до платформи Adobe Experience.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="fbbc8-168">Спочатку [створіть підключення до джерела сховища Blob-об'єктів Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="fbbc8-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="fbbc8-169">Після визначення підключення до джерела [налаштуйте потік даних](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) для підключення до хмарного сховища для імпорту виводу сегменту з аналітичних оглядів до платформи Adobe Experience.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="fbbc8-170">Створення аудиторії у Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fbbc8-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="fbbc8-171">Для надсилання повідомлення електронної пошти для цієї кампанії мі скористаємося засобом Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="fbbc8-172">Після імпорту даних до платформи Adobe Experience потрібно [створити аудиторію](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) в Adobe Campaign Standard за допомогою даних на платформі Adobe Experience.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="fbbc8-173">Інформація про [використання конструктора сегменту](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) в Adobe Campaign Standard для визначення аудиторії на основі даних на платформі Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="fbbc8-174">Створення та надсилання електронної пошти за допомогою Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fbbc8-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="fbbc8-175">Створіть вміст електронної пошти, а потім [перевірте та надішліть](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) повідомлення електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="fbbc8-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Зразок повідомлення електронної пошти із пропозицією оновлення за допомогою Adobe Campaign Standard.":::
