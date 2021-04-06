---
title: Експортування даних Customer Insights до Adobe Campaign Standard
description: Дізнайтесь, як використовувати сегменти аналітичних оглядів аудиторії у Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596340"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="059d0-103">Використовуйте сегменти Customer Insights у Adobe Campaign Standard (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="059d0-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="059d0-104">Як користувач аналітики аудиторії для Dynamics 365 Customer Insights, ви могли створювати сегменти, щоб зробити свої маркетингові кампанії більш ефективними завдяки націлюванню на відповідні аудиторії.</span><span class="sxs-lookup"><span data-stu-id="059d0-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="059d0-105">Щоб використовувати сегмент з аналітики аудиторії на платформі Adobe Experience та в програмах, як-от Adobe Campaign Standard, потрібно виконати кілька кроків, наведених у цій статті.</span><span class="sxs-lookup"><span data-stu-id="059d0-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Схема процесів кроків, описаних у цій статті.":::

## <a name="prerequisites"></a><span data-ttu-id="059d0-107">Вимоги</span><span class="sxs-lookup"><span data-stu-id="059d0-107">Prerequisites</span></span>

-   <span data-ttu-id="059d0-108">Ліцензія Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="059d0-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="059d0-109">Ліцензія Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="059d0-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="059d0-110">Обліковий запис сховища Azure Blob</span><span class="sxs-lookup"><span data-stu-id="059d0-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="059d0-111">Огляд кампанії</span><span class="sxs-lookup"><span data-stu-id="059d0-111">Campaign Overview</span></span>

<span data-ttu-id="059d0-112">Щоб краще зрозуміти, як можна використовувати сегменти з аналітики аудиторії на платформі Adobe Experience, перегляньте вигадані приклади кампаній.</span><span class="sxs-lookup"><span data-stu-id="059d0-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="059d0-113">Припустімо, що ваша компанія пропонує клієнтам щомісячну передплату на послуги в Сполучених Штатах Америки.</span><span class="sxs-lookup"><span data-stu-id="059d0-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="059d0-114">Вам потрібно визначити клієнтів, передплати яких мають бути продовжені впродовж наступних 8 днів, але які ще не продовжили їх.</span><span class="sxs-lookup"><span data-stu-id="059d0-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="059d0-115">Щоб зберегти цих клієнтів, ви хочете надіслати їм акційну пропозицію електронною поштою за допомогою Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="059d0-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="059d0-116">У цьому прикладі ми хочемо запустити рекламну кампанію електронною поштою один раз.</span><span class="sxs-lookup"><span data-stu-id="059d0-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="059d0-117">У цій статті не розглядається варіант використання багатократного запуску кампанії.</span><span class="sxs-lookup"><span data-stu-id="059d0-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="059d0-118">Проте аналітичні огляди аудиторій і Adobe Campaign Standard можна настроювати також для роботи з повторюваним сценарієм кампанії.</span><span class="sxs-lookup"><span data-stu-id="059d0-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="059d0-119">Визначте цільову аудиторію</span><span class="sxs-lookup"><span data-stu-id="059d0-119">Identify your target audience</span></span>

<span data-ttu-id="059d0-120">У нашому сценарії ми припускаємо, що адреси електронної пошти клієнтів доступні в аналітичних оглядах аудиторії, в їхні рекламні уподобання були проаналізовані для ідентифікації учасників сегменту.</span><span class="sxs-lookup"><span data-stu-id="059d0-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="059d0-121">[Сегмент, визначений у аналітичних оглядах аудиторії](segments.md), називається **ChurnProneCustomers** і ви плануєте надіслати цим клієнтам рекламну пропозицію електронною поштою.</span><span class="sxs-lookup"><span data-stu-id="059d0-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Знімок екрана: сторінка сегментів зі створеним сегментом ChurnProneCustomers.":::

<span data-ttu-id="059d0-123">Повідомлення електронної пошти, яке необхідно надіслати, міститиме ім'я, прізвище та дату завершення передплати клієнта.</span><span class="sxs-lookup"><span data-stu-id="059d0-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="059d0-124">Він інформує клієнтів про знижку, яку вони отримають, якщо продовжать передплату до закінчення терміну її дії.</span><span class="sxs-lookup"><span data-stu-id="059d0-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="059d0-125">Експортуйте цільову аудиторію</span><span class="sxs-lookup"><span data-stu-id="059d0-125">Export your target audience</span></span>

<span data-ttu-id="059d0-126">Визначивши нашу цільову аудиторію, можна налаштувати експорту з аналітичних оглядів аудиторії до облікового запису сховища BLOB-об'єктів Azure.</span><span class="sxs-lookup"><span data-stu-id="059d0-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="059d0-127">У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.</span><span class="sxs-lookup"><span data-stu-id="059d0-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="059d0-128">У плитці **Adobe Campaign** натисніть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="059d0-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Плитка «Конфігурація» для Adobe Campaign Standard.":::

1. <span data-ttu-id="059d0-130">Вкажіть **Коротке ім'я** для нового призначення експорту і введіть **Ім'я облікового запису**, **Ключ облікового запису** і **Контейнер** облікового запису сховища Blob-об'єктів Azure, до якого потрібно експортувати сегмент.</span><span class="sxs-lookup"><span data-stu-id="059d0-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Знімок екрана із конфігураціями облікового запису сховища."::: 

   - <span data-ttu-id="059d0-132">Докладніше про те, як знайти обліковий запис сховища BLOB-об’єктів Azure і ключ облікового запису, див. у розділі [Керування настройками облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="059d0-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="059d0-133">Щоб дізнатися, як створити контейнер, див. розділ [Створення контейнера ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="059d0-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="059d0-134">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="059d0-134">Select **Next**.</span></span>

1. <span data-ttu-id="059d0-135">Виберіть сегмент, який потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="059d0-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="059d0-136">У цьому прикладі це **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="059d0-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Знімок екрана: інтерфейс користувача вибору сегмента з вибраним сегментом ChurnProneCustomers.":::

1. <span data-ttu-id="059d0-138">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="059d0-138">Select **Next**.</span></span>

1. <span data-ttu-id="059d0-139">Тепер ми зіставляємо поля **Джерело** з сегменту аналітичних оглядів аудиторії з іменами поля **Ціль** у схемі профілю Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="059d0-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Зіставлення полів для стандартного з'єднувача Adobe Campaign Standard.":::

   <span data-ttu-id="059d0-141">Щоб додати більше атрибутів, виберіть **Додати атрибут**.</span><span class="sxs-lookup"><span data-stu-id="059d0-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="059d0-142">Кінцеве ім'я може відрізнятися від вихідного імені поля, м=тому ви все одно можете зіставити вивід сегмента х аналітичних оглядів аудиторії з Adobe Campaign Standard, якщо поля не мають однакового імені в двох системах.</span><span class="sxs-lookup"><span data-stu-id="059d0-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="059d0-143">Адреса електронної пошти використовується як поле посвідчення, але можна використовувати будь-який інший ідентифікатор з профілю клієнта аналітичних оглядів аудиторії, щоб зіставити дані в Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="059d0-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="059d0-144">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="059d0-144">Select **Save**.</span></span>

<span data-ttu-id="059d0-145">Після збереження призначення експорту його можна знайти в меню **Адміністратор** > **Експортування** > **Мої призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="059d0-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Знімок екрана зі списком експортів і виділеним прикладом сегменту.":::

<span data-ttu-id="059d0-147">Тепер сегмент [можна експортувати неавтоматично](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="059d0-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="059d0-148">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md).</span><span class="sxs-lookup"><span data-stu-id="059d0-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="059d0-149">Переконайтеся, що кількість записів у експортованому сегменті перебуває в межах дозволеного ліміту вашої ліцензії Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="059d0-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="059d0-150">Експортовані дані зберігаються в контейнері сховища BLOB-об'єктів Azure, який було настроєно вище.</span><span class="sxs-lookup"><span data-stu-id="059d0-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="059d0-151">У контейнері автоматично створюється такий перелік дій:</span><span class="sxs-lookup"><span data-stu-id="059d0-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="059d0-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="059d0-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="059d0-153">Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="059d0-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="059d0-154">Налаштування Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="059d0-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="059d0-155">У разі експортування сегмента аналітичного огляду аудиторії він містить стовпці, вибрані під час визначення призначення експорту в попередньому кроці.</span><span class="sxs-lookup"><span data-stu-id="059d0-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="059d0-156">Ці дані можна використовувати для [створення профілів у Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="059d0-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="059d0-157">Для використання сегменту в Adobe Campaign Standard, потрібно розширити схему профілю в Adobe Campaign Standard , щоб додати два додаткові поля.</span><span class="sxs-lookup"><span data-stu-id="059d0-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="059d0-158">Навчіться [розширювати ресурс профілю](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) за допомогою нових полів у Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="059d0-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="059d0-159">У нашому прикладі це поля *«Назва сегмента» та «Дата сегмента» (необов'язково).*</span><span class="sxs-lookup"><span data-stu-id="059d0-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="059d0-160">Ці поля використовуватимуться для визначення профілів у Adobe Campaign Standard, визначених для цієї кампанії.</span><span class="sxs-lookup"><span data-stu-id="059d0-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="059d0-161">Якщо в Adobe Campaign Standard немає інших записів, що відрізняються від тих, які ви хочете імпортувати, ви можете пропустити цей крок.</span><span class="sxs-lookup"><span data-stu-id="059d0-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="059d0-162">Імпортування даних до Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="059d0-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="059d0-163">Тепер, коли все готово, необхідно імпортувати підготовлені дані про аудиторію аналітичних оглядів аудиторії до Adobe Campaign Standard, щоб створити профілі.</span><span class="sxs-lookup"><span data-stu-id="059d0-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="059d0-164">Дізнайтеся [як імпортувати профілі в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) за допомогою робочого циклу.</span><span class="sxs-lookup"><span data-stu-id="059d0-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="059d0-165">Робочий цикл імпорту на зображенні нижче настроєний для запуску кожні 8 годин і шукає експортовані сегменти аналітичних оглядів аудиторії (.csv-файл у сховищі BLOB-об'єктів Azure).</span><span class="sxs-lookup"><span data-stu-id="059d0-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="059d0-166">Робочий цикл отримує вміст .csv-файлу у вказаному порядку стовпців.</span><span class="sxs-lookup"><span data-stu-id="059d0-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="059d0-167">Цей робочий цикл створено для виконання базової обробки помилок і забезпечення того, щоб кожен запис мав адресу електронної пошти перед зливом даних у Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="059d0-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="059d0-168">Робочий цикл також отримує ім'я сегмента з імені файлу перед вставлянням у дані профілю ACS.</span><span class="sxs-lookup"><span data-stu-id="059d0-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Знімок екрана: робочий цикл імпорту в інтерфейсі користувача Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="059d0-170">Отримання аудиторії у Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="059d0-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="059d0-171">Після імпорту даних у Adobe Campaign Standard [можна створити робочий цикл](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) і [запит](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) клієнтів на основі *Імені сегмента* і *Дати сегменту* для вибору профілів, визначених для нашого прикладу кампанії.</span><span class="sxs-lookup"><span data-stu-id="059d0-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="059d0-172">Створення та надсилання електронної пошти за допомогою Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="059d0-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="059d0-173">Створіть вміст електронної пошти, а потім [перевірте та надішліть](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) повідомлення електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="059d0-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Зразок повідомлення електронної пошти із пропозицією оновлення за допомогою Adobe Campaign Standard.":::