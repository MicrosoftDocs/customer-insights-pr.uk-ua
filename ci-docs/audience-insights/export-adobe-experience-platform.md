---
title: Експортування даних Customer Insights до платформи Adobe Experience
description: Дізнайтесь, як використовувати сегменти аналітичних оглядів аудиторії на платформі Adobe Experience.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596294"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="fabed-103">Використовуйте сегменти Customer Insights на платформі Adobe Experience (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="fabed-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="fabed-104">Як користувач аналітики аудиторії для Dynamics 365 Customer Insights, ви могли створювати сегменти, щоб зробити свої маркетингові кампанії більш ефективними завдяки націлюванню на відповідні аудиторії.</span><span class="sxs-lookup"><span data-stu-id="fabed-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="fabed-105">Щоб використовувати сегмент з аналітики аудиторії на платформі Adobe Experience та в програмах, як-от Adobe Campaign Standard, потрібно виконати кілька кроків, наведених у цій статті.</span><span class="sxs-lookup"><span data-stu-id="fabed-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Схема процесів кроків, описаних у цій статті.":::

## <a name="prerequisites"></a><span data-ttu-id="fabed-107">Вимоги</span><span class="sxs-lookup"><span data-stu-id="fabed-107">Prerequisites</span></span>

-   <span data-ttu-id="fabed-108">Ліцензія Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="fabed-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="fabed-109">Ліцензія платформи Adobe Experience</span><span class="sxs-lookup"><span data-stu-id="fabed-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="fabed-110">Ліцензія Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fabed-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="fabed-111">Обліковий запис сховища Azure Blob</span><span class="sxs-lookup"><span data-stu-id="fabed-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="fabed-112">Огляд кампанії</span><span class="sxs-lookup"><span data-stu-id="fabed-112">Campaign Overview</span></span>

<span data-ttu-id="fabed-113">Щоб краще зрозуміти, як можна використовувати сегменти з аналітики аудиторії на платформі Adobe Experience, перегляньте вигадані приклади кампаній.</span><span class="sxs-lookup"><span data-stu-id="fabed-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="fabed-114">Припустімо, що ваша компанія пропонує клієнтам щомісячну передплату на послуги в Сполучених Штатах Америки.</span><span class="sxs-lookup"><span data-stu-id="fabed-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="fabed-115">Вам потрібно визначити клієнтів, передплати яких мають бути продовжені впродовж наступних 8 днів, але які ще не продовжили їх.</span><span class="sxs-lookup"><span data-stu-id="fabed-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="fabed-116">Щоб зберегти цих клієнтів, ви хочете надіслати їм акційну пропозицію електронною поштою за допомогою платформи Adobe Experience.</span><span class="sxs-lookup"><span data-stu-id="fabed-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="fabed-117">У цьому прикладі ми хочемо запустити рекламну кампанію електронною поштою один раз.</span><span class="sxs-lookup"><span data-stu-id="fabed-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="fabed-118">У цій статті не розглядається варіант використання багатократного запуску кампанії.</span><span class="sxs-lookup"><span data-stu-id="fabed-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="fabed-119">Визначте цільову аудиторію</span><span class="sxs-lookup"><span data-stu-id="fabed-119">Identify your target audience</span></span>

<span data-ttu-id="fabed-120">У нашому сценарії ми припускаємо, що адреси електронної пошти клієнтів доступні в аналітичних оглядах аудиторії, в їхні рекламні уподобання були проаналізовані для ідентифікації учасників сегменту.</span><span class="sxs-lookup"><span data-stu-id="fabed-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="fabed-121">[Сегмент, визначений у аналітичних оглядах аудиторії](segments.md), називається **ChurnProneCustomers** і ви плануєте надіслати цим клієнтам рекламну пропозицію електронною поштою.</span><span class="sxs-lookup"><span data-stu-id="fabed-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Знімок екрана: сторінка сегментів зі створеним сегментом ChurnProneCustomers.":::

<span data-ttu-id="fabed-123">Повідомлення електронної пошти, яке необхідно надіслати, міститиме ім'я, прізвище та дату завершення передплати клієнта.</span><span class="sxs-lookup"><span data-stu-id="fabed-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="fabed-124">Він інформує клієнтів про знижку, яку вони отримають, якщо продовжать передплату до закінчення терміну її дії.</span><span class="sxs-lookup"><span data-stu-id="fabed-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="fabed-125">Експортуйте цільову аудиторію</span><span class="sxs-lookup"><span data-stu-id="fabed-125">Export your target audience</span></span>

<span data-ttu-id="fabed-126">Визначивши нашу цільову аудиторію, можна налаштувати експорту з аналітичних оглядів аудиторії до облікового запису сховища BLOB-об'єктів Azure.</span><span class="sxs-lookup"><span data-stu-id="fabed-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="fabed-127">У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.</span><span class="sxs-lookup"><span data-stu-id="fabed-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fabed-128">У плитці **Сховище BLOB-об'єктів Azure**" натисніть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="fabed-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Плитка конфігурації для сховища BLOB-об'єктів Azure.":::

1. <span data-ttu-id="fabed-130">Вкажіть **Коротке ім'я** для нового призначення експорту і введіть **Ім'я облікового запису**, **Ключ облікового запису** і **Контейнер** облікового запису сховища Blob-об'єктів Azure, до якого потрібно експортувати сегмент.</span><span class="sxs-lookup"><span data-stu-id="fabed-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Знімок екрана із конфігураціями облікового запису сховища."::: 

   - <span data-ttu-id="fabed-132">Докладніше про те, як знайти обліковий запис сховища BLOB-об’єктів Azure і ключ облікового запису, див. у розділі [Керування настройками облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="fabed-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="fabed-133">Щоб дізнатися, як створити контейнер, див. розділ [Створення контейнера ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="fabed-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="fabed-134">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="fabed-134">Select **Next**.</span></span>

1. <span data-ttu-id="fabed-135">Виберіть сегмент, який потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="fabed-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="fabed-136">У цьому прикладі це **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="fabed-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Знімок екрана: інтерфейс користувача вибору сегмента з вибраним сегментом ChurnProneCustomers.":::

1. <span data-ttu-id="fabed-138">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="fabed-138">Select **Save**.</span></span>

<span data-ttu-id="fabed-139">Після збереження призначення експорту його можна знайти в меню **Адміністратор** > **Експортування** > **Мої призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="fabed-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Знімок екрана зі списком експортів і виділеним прикладом сегменту.":::

<span data-ttu-id="fabed-141">Тепер сегмент [можна експортувати неавтоматично](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fabed-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="fabed-142">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md).</span><span class="sxs-lookup"><span data-stu-id="fabed-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fabed-143">Переконайтеся, що кількість записів у експортованому сегменті перебуває в межах дозволеного ліміту вашої ліцензії Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="fabed-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="fabed-144">Експортовані дані зберігаються в контейнері сховища BLOB-об'єктів Azure, який було настроєно вище.</span><span class="sxs-lookup"><span data-stu-id="fabed-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="fabed-145">У контейнері автоматично створюється такий перелік дій:</span><span class="sxs-lookup"><span data-stu-id="fabed-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="fabed-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="fabed-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="fabed-147">Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="fabed-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="fabed-148">*model.json* для експортованих сутностей розташовується на рівні *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="fabed-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="fabed-149">Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="fabed-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="fabed-150">Визначення моделі даних досвіду (XDM) на платформі Adobe Experience</span><span class="sxs-lookup"><span data-stu-id="fabed-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="fabed-151">Перед тим, як експортовані дані з аналітичних оглядів аудиторії можна буде використовувати в межах платформи Adobe Experience, потрібно визначити схему моделі даних досвіду та [налаштувати дані для профілю користувача в реальному часі](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="fabed-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="fabed-152">Дізнайтеся, [що таке XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) і зрозумійте [основи створення схем](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="fabed-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="fabed-153">Імпортування даних до платформи Adobe Experience</span><span class="sxs-lookup"><span data-stu-id="fabed-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="fabed-154">Тепер, коли все готово, необхідно імпортувати підготовлені дані про аудиторію аналітичних оглядів аудиторії до платформи Adobe Experience.</span><span class="sxs-lookup"><span data-stu-id="fabed-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="fabed-155">Спочатку [створіть підключення до джерела сховища Blob-об'єктів Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="fabed-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="fabed-156">Після визначення підключення до джерела [налаштуйте потік даних](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) для підключення до хмарного сховища для імпорту виводу сегменту з аналітичних оглядів до платформи Adobe Experience.</span><span class="sxs-lookup"><span data-stu-id="fabed-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="fabed-157">Створення аудиторії у Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fabed-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="fabed-158">Ми використовуватимемо Adobe Campaign Standard, щоб надіслати електронний лист до цієї кампанії.</span><span class="sxs-lookup"><span data-stu-id="fabed-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="fabed-159">Після імпорту даних до платформи Adobe Experience потрібно [створити аудиторію](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) в Adobe Campaign Standard за допомогою даних на платформі Adobe Experience.</span><span class="sxs-lookup"><span data-stu-id="fabed-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="fabed-160">Інформація про [використання конструктора сегменту](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) в Adobe Campaign Standard для визначення аудиторії на основі даних на платформі Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="fabed-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="fabed-161">Створення та надсилання електронної пошти за допомогою Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="fabed-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="fabed-162">Створіть вміст електронної пошти, а потім [перевірте та надішліть](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) повідомлення електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="fabed-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Зразок повідомлення електронної пошти із пропозицією оновлення за допомогою Adobe Campaign Standard.":::