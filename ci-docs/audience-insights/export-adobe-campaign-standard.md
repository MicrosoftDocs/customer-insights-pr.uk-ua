---
title: Експортування даних Customer Insights до Adobe Campaign Standard
description: Дізнайтесь, як використовувати сегменти аналітичних оглядів аудиторії у Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305411"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="e3565-103">Використовуйте сегменти Customer Insights у Adobe Campaign Standard (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="e3565-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="e3565-104">Як користувач аналітичних оглядів аудиторії в Dynamics 365 Customer Insights, ви могли створювати сегменти для підвищення ефективності своїх маркетингових кампаній способом націлювання рекламного матеріалу на доречні аудиторії.</span><span class="sxs-lookup"><span data-stu-id="e3565-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="e3565-105">Щоб використовувати сегмент з аналітики аудиторії на платформі Adobe Experience та в програмах, як-от Adobe Campaign Standard, потрібно виконати кілька кроків, наведених у цій статті.</span><span class="sxs-lookup"><span data-stu-id="e3565-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Схема процесів кроків, описаних у цій статті.":::

## <a name="prerequisites"></a><span data-ttu-id="e3565-107">Вимоги</span><span class="sxs-lookup"><span data-stu-id="e3565-107">Prerequisites</span></span>

-   <span data-ttu-id="e3565-108">Ліцензія Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e3565-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="e3565-109">Ліцензія Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e3565-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="e3565-110">Обліковий запис сховища Azure Blob</span><span class="sxs-lookup"><span data-stu-id="e3565-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="e3565-111">Огляд кампанії</span><span class="sxs-lookup"><span data-stu-id="e3565-111">Campaign overview</span></span>

<span data-ttu-id="e3565-112">Щоб краще зрозуміти, як можна використовувати сегменти з аналітики аудиторії на платформі Adobe Experience, перегляньте вигадані приклади кампаній.</span><span class="sxs-lookup"><span data-stu-id="e3565-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="e3565-113">Припустімо, що ваша компанія пропонує клієнтам щомісячну передплату на послуги в Сполучених Штатах Америки.</span><span class="sxs-lookup"><span data-stu-id="e3565-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="e3565-114">Вам потрібно визначити клієнтів, передплати яких мають бути продовжені впродовж наступних 8 днів, але які ще не продовжили їх.</span><span class="sxs-lookup"><span data-stu-id="e3565-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="e3565-115">Щоб зберегти цих клієнтів, ви хочете надіслати їм акційну пропозицію електронною поштою за допомогою Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e3565-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="e3565-116">У цьому прикладі ми хочемо запустити рекламну кампанію електронною поштою один раз.</span><span class="sxs-lookup"><span data-stu-id="e3565-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="e3565-117">У цій статті не розглядається варіант використання багатократного запуску кампанії.</span><span class="sxs-lookup"><span data-stu-id="e3565-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="e3565-118">Проте аналітичні огляди аудиторій і Adobe Campaign Standard можна настроювати також для роботи з повторюваним сценарієм кампанії.</span><span class="sxs-lookup"><span data-stu-id="e3565-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="e3565-119">Визначте цільову аудиторію</span><span class="sxs-lookup"><span data-stu-id="e3565-119">Identify your target audience</span></span>

<span data-ttu-id="e3565-120">У нашому сценарії ми припускаємо, що адреси електронної пошти клієнтів доступні в аналітичних оглядах аудиторії, в їхні рекламні уподобання були проаналізовані для ідентифікації учасників сегменту.</span><span class="sxs-lookup"><span data-stu-id="e3565-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="e3565-121">[Сегмент, визначений у аналітичних оглядах аудиторії](segments.md), називається **ChurnProneCustomers** і ви плануєте надіслати цим клієнтам рекламну пропозицію електронною поштою.</span><span class="sxs-lookup"><span data-stu-id="e3565-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Знімок екрана: сторінка сегментів зі створеним сегментом ChurnProneCustomers.":::

<span data-ttu-id="e3565-123">Повідомлення електронної пошти, яке необхідно надіслати, міститиме ім'я, прізвище та дату завершення передплати клієнта.</span><span class="sxs-lookup"><span data-stu-id="e3565-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="e3565-124">Він інформує клієнтів про знижку, яку вони отримають, якщо продовжать передплату до закінчення терміну її дії.</span><span class="sxs-lookup"><span data-stu-id="e3565-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="e3565-125">Експортуйте цільову аудиторію</span><span class="sxs-lookup"><span data-stu-id="e3565-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="e3565-126">Налаштуйте підключення</span><span class="sxs-lookup"><span data-stu-id="e3565-126">Configure a connection</span></span>

<span data-ttu-id="e3565-127">Визначивши нашу цільову аудиторію, можна налаштувати експорту з аналітичних оглядів аудиторії до облікового запису сховища BLOB-об'єктів Azure.</span><span class="sxs-lookup"><span data-stu-id="e3565-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="e3565-128">У аналітиці аудиторії перейдіть до розділу **Адміністратор** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="e3565-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e3565-129">Виберіть розділ **Додати підключення**, потім виберіть **Кампанія Adobe**, щоб налаштувати підключення, або виберіть пункт **Налаштувати** на плитці **Кампанія Adobe**.</span><span class="sxs-lookup"><span data-stu-id="e3565-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Плитка «Конфігурація» для Adobe Campaign Standard.":::

1. <span data-ttu-id="e3565-131">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="e3565-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e3565-132">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="e3565-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e3565-133">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="e3565-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e3565-134">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="e3565-134">Choose who can use this connection.</span></span> <span data-ttu-id="e3565-135">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="e3565-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e3565-136">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e3565-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e3565-137">Введіть **Ім’я бізнес-партнера**, **Ключ бізнес-партнера** і **Контейнер** у сховищі BLOB-об’єктів Azure, до якого ви бажаєте експортувати сегмент.</span><span class="sxs-lookup"><span data-stu-id="e3565-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Знімок екрана із конфігураціями облікового запису сховища."::: 

   - <span data-ttu-id="e3565-139">Докладніше про те, як знайти обліковий запис сховища BLOB-об’єктів Azure і ключ облікового запису, див. у розділі [Керування настройками облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="e3565-139">To learn more about how to find the Azure Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="e3565-140">Щоб дізнатися, як створити контейнер, див. розділ [Створення контейнера ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="e3565-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="e3565-141">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="e3565-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="e3565-142">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="e3565-142">Configure an export</span></span>

<span data-ttu-id="e3565-143">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="e3565-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e3565-144">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e3565-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e3565-145">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="e3565-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e3565-146">Щоб створити новий експорт, виберіть **Додати експорт**.</span><span class="sxs-lookup"><span data-stu-id="e3565-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="e3565-147">У полі **Підключення для експорту** виберіть підключення з розділу «Кампанія Adobe».</span><span class="sxs-lookup"><span data-stu-id="e3565-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="e3565-148">Якщо ви не бачите імені цього розділу, це означає, що для вас не доступні будь-які підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="e3565-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="e3565-149">Виберіть сегмент, який потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="e3565-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="e3565-150">У цьому прикладі це **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="e3565-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Знімок екрана: інтерфейс користувача вибору сегмента з вибраним сегментом ChurnProneCustomers.":::

1. <span data-ttu-id="e3565-152">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="e3565-152">Select **Next**.</span></span>

1. <span data-ttu-id="e3565-153">Тепер ми зіставляємо поля **Джерело** з сегменту аналітичних оглядів аудиторії з іменами поля **Ціль** у схемі профілю Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e3565-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Зіставлення полів для стандартного з'єднувача Adobe Campaign Standard.":::

   <span data-ttu-id="e3565-155">Щоб додати більше атрибутів, виберіть **Додати атрибут**.</span><span class="sxs-lookup"><span data-stu-id="e3565-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="e3565-156">Кінцеве ім'я може відрізнятися від вихідного імені поля, м=тому ви все одно можете зіставити вивід сегмента х аналітичних оглядів аудиторії з Adobe Campaign Standard, якщо поля не мають однакового імені в двох системах.</span><span class="sxs-lookup"><span data-stu-id="e3565-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e3565-157">Адреса електронної пошти використовується як поле посвідчення, але можна використовувати будь-який інший ідентифікатор з профілю клієнта аналітичних оглядів аудиторії, щоб зіставити дані в Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e3565-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="e3565-158">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="e3565-158">Select **Save**.</span></span>

<span data-ttu-id="e3565-159">Після того, як ви зберегли пункт призначення експорту, ви зможете знайти його в розділі **Дані** > **Експорт**.</span><span class="sxs-lookup"><span data-stu-id="e3565-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="e3565-160">Тепер сегмент [можна експортувати неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e3565-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="e3565-161">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md).</span><span class="sxs-lookup"><span data-stu-id="e3565-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e3565-162">Переконайтеся, що кількість записів у експортованому сегменті перебуває в межах дозволеного ліміту вашої ліцензії Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e3565-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="e3565-163">Експортовані дані зберігаються в контейнері сховища BLOB-об'єктів Azure, який було налаштовано вище.</span><span class="sxs-lookup"><span data-stu-id="e3565-163">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="e3565-164">У контейнері автоматично створюється такий перелік дій:</span><span class="sxs-lookup"><span data-stu-id="e3565-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="e3565-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="e3565-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="e3565-166">Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="e3565-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="e3565-167">Налаштування Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e3565-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="e3565-168">У разі експортування сегмента аналітичного огляду аудиторії він містить стовпці, вибрані під час визначення призначення експорту в попередньому кроці.</span><span class="sxs-lookup"><span data-stu-id="e3565-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="e3565-169">Ці дані можна використовувати для [створення профілів у Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="e3565-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="e3565-170">Для використання сегменту в Adobe Campaign Standard, потрібно розширити схему профілю в Adobe Campaign Standard , щоб додати два додаткові поля.</span><span class="sxs-lookup"><span data-stu-id="e3565-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="e3565-171">Навчіться [розширювати ресурс профілю](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) за допомогою нових полів у Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e3565-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="e3565-172">У цьому прикладі такими полями є: *«Назва сегмента» та «Дата сегмента» (необов'язково)*.</span><span class="sxs-lookup"><span data-stu-id="e3565-172">In our example, these fields are *Segment Name and Segment Date (optional)*.</span></span>

<span data-ttu-id="e3565-173">Ці поля використовуватимуться для визначення профілів у Adobe Campaign Standard, визначених для цієї кампанії.</span><span class="sxs-lookup"><span data-stu-id="e3565-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="e3565-174">Якщо в Adobe Campaign Standard немає інших записів, що відрізняються від тих, які ви хочете імпортувати, ви можете пропустити цей крок.</span><span class="sxs-lookup"><span data-stu-id="e3565-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="e3565-175">Імпортування даних до Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e3565-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="e3565-176">Тепер, коли все готово, необхідно імпортувати підготовлені дані про аудиторію аналітичних оглядів аудиторії до Adobe Campaign Standard, щоб створити профілі.</span><span class="sxs-lookup"><span data-stu-id="e3565-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="e3565-177">Дізнайтеся [як імпортувати профілі в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) за допомогою робочого циклу.</span><span class="sxs-lookup"><span data-stu-id="e3565-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="e3565-178">Робочий цикл імпорту на наведеному нижче зображенні налаштовано для запуску кожні вісім годин, коли цей цикл виконуватиме пошук експортованих сегментів аналітичних оглядів аудиторії (файлу .csv у Сховищі BLOB-об’єктів Azure).</span><span class="sxs-lookup"><span data-stu-id="e3565-178">The import workflow in the image below has been configured to run every eight hours and look for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="e3565-179">Робочий цикл отримує вміст .csv-файлу у вказаному порядку стовпців.</span><span class="sxs-lookup"><span data-stu-id="e3565-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="e3565-180">Цей робочий цикл створено для виконання базової обробки помилок і забезпечення того, щоб кожен запис мав адресу електронної пошти перед зливом даних у Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e3565-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="e3565-181">Цей робочий цикл також видобуває ім’я сегмента з імені файлу до його вставляння в дані стандартного профілю кампанії Adobe.</span><span class="sxs-lookup"><span data-stu-id="e3565-181">The workflow also extracts the segment name from the filename before upserting into Adobe Campaign Standard profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Знімок екрана: робочий цикл імпорту в інтерфейсі користувача Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="e3565-183">Отримання аудиторії у Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e3565-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="e3565-184">Після імпорту даних у Adobe Campaign Standard [можна створити робочий цикл](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) і [запит](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) клієнтів на основі *Імені сегмента* і *Дати сегменту* для вибору профілів, визначених для нашого прикладу кампанії.</span><span class="sxs-lookup"><span data-stu-id="e3565-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="e3565-185">Створення та надсилання електронної пошти за допомогою Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e3565-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="e3565-186">Створіть вміст електронної пошти, а потім [перевірте та надішліть](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) повідомлення електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="e3565-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Зразок повідомлення електронної пошти із пропозицією оновлення за допомогою Adobe Campaign Standard.":::
