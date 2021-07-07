---
title: Використання джерел даних для прийому даних
description: Дізнайтесь, як імпортувати дані з різних джерел.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304721"
---
# <a name="data-sources-overview"></a><span data-ttu-id="e9a8b-103">Огляд джерел даних</span><span class="sxs-lookup"><span data-stu-id="e9a8b-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e9a8b-104">Можливість аналізу аудиторій у Dynamics 365 Customer Insights підключається до даних з широкого набору джерел.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="e9a8b-105">Підключення до джерела даних часто називається процесом *отримання даних*.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="e9a8b-106">Після того як дані буде отримано, ви можете [уніфікувати](data-unification.md) їх та виконувати із ними дії.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="e9a8b-107">Додати джерело даних</span><span class="sxs-lookup"><span data-stu-id="e9a8b-107">Add a data source</span></span>

<span data-ttu-id="e9a8b-108">Ознайомтеся з докладними статтями про додавання джерел даних, залежно від вибраного вами варіанту.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="e9a8b-109">Ви можете додати джерело даних трьома основними способами:</span><span class="sxs-lookup"><span data-stu-id="e9a8b-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="e9a8b-110">Використовуючи десятки з’єднувачів Power Query</span><span class="sxs-lookup"><span data-stu-id="e9a8b-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="e9a8b-111">З папки Common Data Model</span><span class="sxs-lookup"><span data-stu-id="e9a8b-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="e9a8b-112">З власного озера Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="e9a8b-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="e9a8b-113">Додавайте дані з локальних джерел даних</span><span class="sxs-lookup"><span data-stu-id="e9a8b-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="e9a8b-114">Використання даних із локальних джерел даних у Audience Insights підтримується на основі потоків даних Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="e9a8b-115">Потоки даних можна увімкнути в Customer Insights способом [зазначення URL-адреси середовища Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) при налаштуванні цього середовища.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="e9a8b-116">Джерела даних, створені після прив’язування середовища Dataverse до Customer Insights, використовуватимуть [потоки даних Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) за промовчанням.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="e9a8b-117">Потоки даних підтримують локальне підключення за допомогою шлюзу даних.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="e9a8b-118">Видаліть і відтворіть джерела даних, які існували до прив’язування середовища Dataverse для [використання локальних шлюзів даних](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="e9a8b-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="e9a8b-119">Шлюзи даних із наявного середовища Power BI або Power Apps будуть видимі, й ви можете повторно користуватися Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="e9a8b-120">На сторінці джерел даних відображено посилання для переходу до середовища Microsoft Power Platform, де ви можете переглянути та налаштувати локальні шлюзи даних.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="e9a8b-121">Перегляд отриманих даних</span><span class="sxs-lookup"><span data-stu-id="e9a8b-121">Review ingested data</span></span>

<span data-ttu-id="e9a8b-122">Ви побачите ім'я кожного отриманого джерела даних, його стан та час останнього оновлення даних для цього джерела.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="e9a8b-123">Список джерел даних можна сортувати за кожним стовпцем.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e9a8b-124">![Додане джерело даних](media/configure-data-datasource-added.png "Додане джерело даних")</span><span class="sxs-lookup"><span data-stu-id="e9a8b-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="e9a8b-125">Статус</span><span class="sxs-lookup"><span data-stu-id="e9a8b-125">Status</span></span>  |<span data-ttu-id="e9a8b-126">Опис</span><span class="sxs-lookup"><span data-stu-id="e9a8b-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="e9a8b-127">Успішно</span><span class="sxs-lookup"><span data-stu-id="e9a8b-127">Successful</span></span>   |<span data-ttu-id="e9a8b-128">Якщо в стовпці **Оновлено** вказано час, джерело даних було успішно прийнято.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="e9a8b-129">Не розпочато</span><span class="sxs-lookup"><span data-stu-id="e9a8b-129">Not started</span></span>   |<span data-ttu-id="e9a8b-130">Джерело даних ще не має прийнятих даних або все ще працює в режимі чернетки.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="e9a8b-131">Оновлення</span><span class="sxs-lookup"><span data-stu-id="e9a8b-131">Refreshing</span></span>    |<span data-ttu-id="e9a8b-132">Триває обробка даних.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-132">Data ingestion is in progress.</span></span> <span data-ttu-id="e9a8b-133">Цю операцію можна скасувати, вибравши команду **Зупинити оновлення** в стовпці **Дії**.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="e9a8b-134">Якщо зупинити оновлення джерела даних, його буде повернуто до останнього стану оновлення.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="e9a8b-135">Не пройдено</span><span class="sxs-lookup"><span data-stu-id="e9a8b-135">Failed</span></span>     |<span data-ttu-id="e9a8b-136">Виникли помилки під час додавання даних.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="e9a8b-137">Щоб переглянути додаткові відомості, виберіть значення у стовпці **Стан** для будь-якого джерела даних.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="e9a8b-138">В області **Відомості про перебіг виконання** розгорніть елемент **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="e9a8b-139">Виберіть **Переглянути відомості**, щоб отримати більше відомостей про стан оновлення, зокрема відомості про помилку та оновлення низхідного процесу.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="e9a8b-140">Завантаження даних може тривати значний час.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-140">Loading data can take time.</span></span> <span data-ttu-id="e9a8b-141">Після успішного оновлення, додані дані можна переглянути на сторінці **Сутності**.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="e9a8b-142">Додаткові відомості див. в розділі [Сутності](entities.md).</span><span class="sxs-lookup"><span data-stu-id="e9a8b-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="e9a8b-143">Оновлення джерела даних</span><span class="sxs-lookup"><span data-stu-id="e9a8b-143">Refresh a data source</span></span>

<span data-ttu-id="e9a8b-144">Джерела даних можна оновити за автоматичним розкладом або оновити вручну за запитом.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="e9a8b-145">Перейдіть до меню **Адміністратор** > **Система** > [**Розклад**](system.md#schedule-tab), щоб налаштувати заплановані оновлення всіх ваших прийнятих джерел даних.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="e9a8b-146">Щоб оновити джерело даних на вимогу, виконайте такі дії.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="e9a8b-147">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="e9a8b-148">Виберіть вертикальні три крапки поряд із джерелом даних, які ви бажаєте оновити, потім виберіть **Оновити** з розкривного списку.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="e9a8b-149">Тепер джерело даних запускається для оновлення вручну.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="e9a8b-150">При оновленні джерела даних виконається оновлення як схеми сутності, так і даних для всіх сутностей, зазначених у джерелі даних.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="e9a8b-151">Виберіть **Зупинити оновлення**, якщо потрібно скасувати наявне оновлення, і джерело даних повернеться до останнього стану оновлення.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="e9a8b-152">Видалення джерела даних</span><span class="sxs-lookup"><span data-stu-id="e9a8b-152">Delete a data source</span></span>

1. <span data-ttu-id="e9a8b-153">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="e9a8b-154">Виберіть вертикальні три крапки поряд із джерелом даних, які ви бажаєте видалити, потім виберіть **Видалити** з розкривного меню.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="e9a8b-155">Підтвердьте видалення.</span><span class="sxs-lookup"><span data-stu-id="e9a8b-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
