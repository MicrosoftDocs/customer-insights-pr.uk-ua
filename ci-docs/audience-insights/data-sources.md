---
title: Використання джерел даних для прийому даних
description: Дізнайтесь, як імпортувати дані з різних джерел.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643978"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="70702-103">Знайомство із джерелами даних</span><span class="sxs-lookup"><span data-stu-id="70702-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="70702-104">Можливість аналізу аудиторій у Dynamics 365 Customer Insights підключається до даних з широкого набору джерел.</span><span class="sxs-lookup"><span data-stu-id="70702-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="70702-105">Підключення до джерела даних часто називається процесом *отримання даних*.</span><span class="sxs-lookup"><span data-stu-id="70702-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="70702-106">Після того як дані буде отримано, ви можете [уніфікувати](data-unification.md) їх та виконувати із ними дії.</span><span class="sxs-lookup"><span data-stu-id="70702-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="70702-107">Додати джерело даних</span><span class="sxs-lookup"><span data-stu-id="70702-107">Add a data source</span></span>

<span data-ttu-id="70702-108">Ознайомтеся з докладними статтями про додавання джерел даних, залежно від вибраного вами варіанту.</span><span class="sxs-lookup"><span data-stu-id="70702-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="70702-109">Ви можете додати джерело даних трьома основними способами:</span><span class="sxs-lookup"><span data-stu-id="70702-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="70702-110">Використовуючи десятки з’єднувачів Power Query</span><span class="sxs-lookup"><span data-stu-id="70702-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="70702-111">З папки Common Data Model</span><span class="sxs-lookup"><span data-stu-id="70702-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="70702-112">З власного озера Common Data Service</span><span class="sxs-lookup"><span data-stu-id="70702-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="70702-113">Поки що не можна додавати дані з локальний джерел даних.</span><span class="sxs-lookup"><span data-stu-id="70702-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="70702-114">Перегляд отриманих даних</span><span class="sxs-lookup"><span data-stu-id="70702-114">Review ingested data</span></span>

<span data-ttu-id="70702-115">Ви побачите ім'я кожного отриманого джерела даних, його стан та час останнього оновлення даних для цього джерела.</span><span class="sxs-lookup"><span data-stu-id="70702-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="70702-116">Список джерел даних можна сортувати за кожним стовпцем.</span><span class="sxs-lookup"><span data-stu-id="70702-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="70702-117">![Додане джерело даних](media/configure-data-datasource-added.png "Додане джерело даних")</span><span class="sxs-lookup"><span data-stu-id="70702-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="70702-118">Статус</span><span class="sxs-lookup"><span data-stu-id="70702-118">Status</span></span>  |<span data-ttu-id="70702-119">Опис</span><span class="sxs-lookup"><span data-stu-id="70702-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="70702-120">Успішно</span><span class="sxs-lookup"><span data-stu-id="70702-120">Successful</span></span>   |<span data-ttu-id="70702-121">Якщо в стовпці **Оновлено** вказано час, джерело даних було успішно прийнято.</span><span class="sxs-lookup"><span data-stu-id="70702-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="70702-122">Не розпочато</span><span class="sxs-lookup"><span data-stu-id="70702-122">Not started</span></span>   |<span data-ttu-id="70702-123">Джерело даних ще не має прийнятих даних або все ще працює в режимі чернетки.</span><span class="sxs-lookup"><span data-stu-id="70702-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="70702-124">Оновлення</span><span class="sxs-lookup"><span data-stu-id="70702-124">Refreshing</span></span>    |<span data-ttu-id="70702-125">Триває обробка даних.</span><span class="sxs-lookup"><span data-stu-id="70702-125">Data ingestion is in progress.</span></span> <span data-ttu-id="70702-126">Цю операцію можна скасувати, вибравши команду **Зупинити оновлення** в стовпці **Дії**.</span><span class="sxs-lookup"><span data-stu-id="70702-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="70702-127">Якщо зупинити оновлення джерела даних, його буде повернуто до останнього стану оновлення.</span><span class="sxs-lookup"><span data-stu-id="70702-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="70702-128">Не пройдено</span><span class="sxs-lookup"><span data-stu-id="70702-128">Failed</span></span>     |<span data-ttu-id="70702-129">Виникли помилки під час додавання даних.</span><span class="sxs-lookup"><span data-stu-id="70702-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="70702-130">Виберіть параметр **Оновити стан**, щоб переглянути додаткові відомості про стан оновлення, зокрема відомості про помилку та оновлення низхідного процесу.</span><span class="sxs-lookup"><span data-stu-id="70702-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="70702-131">Завантаження даних може тривати певний час.</span><span class="sxs-lookup"><span data-stu-id="70702-131">Loading data can take some time.</span></span> <span data-ttu-id="70702-132">Після успішного оновлення, додані дані можна переглянути на сторінці **Сутності**.</span><span class="sxs-lookup"><span data-stu-id="70702-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="70702-133">Додаткові відомості див. в розділі [Сутності](entities.md).</span><span class="sxs-lookup"><span data-stu-id="70702-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="70702-134">Оновлення джерела даних</span><span class="sxs-lookup"><span data-stu-id="70702-134">Refresh a data source</span></span>

<span data-ttu-id="70702-135">Джерела даних можна оновити за автоматичним розкладом або оновити вручну за запитом.</span><span class="sxs-lookup"><span data-stu-id="70702-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="70702-136">Перейдіть до меню **Адміністратор** > **Система** > [**Розклад**](system.md#schedule-tab), щоб налаштувати заплановані оновлення всіх ваших прийнятих джерел даних.</span><span class="sxs-lookup"><span data-stu-id="70702-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="70702-137">Щоб оновити джерело даних на вимогу, виконайте такі дії.</span><span class="sxs-lookup"><span data-stu-id="70702-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="70702-138">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="70702-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="70702-139">Натисніть вертикальні три крапки поряд із джерелом даних, яке потрібно оновити, і натисніть **Оновити** в розкривному списку.</span><span class="sxs-lookup"><span data-stu-id="70702-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="70702-140">Тепер джерело даних запускається для оновлення вручну.</span><span class="sxs-lookup"><span data-stu-id="70702-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="70702-141">Оновлення джерела даних призведе до оновлення схеми сутності і даних для всіх сутностей, визначених у джерела даних.</span><span class="sxs-lookup"><span data-stu-id="70702-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="70702-142">Виберіть **Зупинити оновлення**, якщо потрібно скасувати наявне оновлення, і джерело даних повернеться до останнього стану оновлення.</span><span class="sxs-lookup"><span data-stu-id="70702-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="70702-143">Видалення джерела даних</span><span class="sxs-lookup"><span data-stu-id="70702-143">Delete a data source</span></span>

1. <span data-ttu-id="70702-144">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="70702-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="70702-145">Виберіть вертикальні три крапки поруч із джерелом даних, яке потрібно видалити, а потім натисніть **Видалити** в розкривному меню.</span><span class="sxs-lookup"><span data-stu-id="70702-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="70702-146">Підтвердьте видалення.</span><span class="sxs-lookup"><span data-stu-id="70702-146">Confirm your deletion.</span></span>
