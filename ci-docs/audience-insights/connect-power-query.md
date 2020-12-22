---
title: Передавання даних за допомогою з'єднувача Power Query
description: З’єднувачі для джерел даних, що основані на Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407256"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="f85a3-103">Підключення до джерела даних Power Query</span><span class="sxs-lookup"><span data-stu-id="f85a3-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="f85a3-104">Power Query пропонує широкий набір з’єднувачів для отримання даних.</span><span class="sxs-lookup"><span data-stu-id="f85a3-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="f85a3-105">Dynamics 365 Customer Insights підтримує більшість із цих з’єднувачів.</span><span class="sxs-lookup"><span data-stu-id="f85a3-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="f85a3-106">Додавання джерел даних на основі з’єднувачів Power Query в цілому виконується за кроками, окресленими у наступному розділі.</span><span class="sxs-lookup"><span data-stu-id="f85a3-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="f85a3-107">Однак можуть знадобитися різні відомості, залежно від використовуваного з'єднувача.</span><span class="sxs-lookup"><span data-stu-id="f85a3-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="f85a3-108">Для отримання додаткових відомостей див. документацію для окремих з’єднувачів у [Довіднику зі з’єднувачів Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="f85a3-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="f85a3-109">Створення нового джерела даних</span><span class="sxs-lookup"><span data-stu-id="f85a3-109">Create a new data source</span></span>

1. <span data-ttu-id="f85a3-110">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="f85a3-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="f85a3-111">Виберіть **Додати джерело даних**.</span><span class="sxs-lookup"><span data-stu-id="f85a3-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="f85a3-112">Виберіть метод **Імпорт даних**, а тоді виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="f85a3-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="f85a3-113">Укажіть **Ім'я** для джерела даних, а тоді виберіть **Далі**, щоб створити джерело даних.</span><span class="sxs-lookup"><span data-stu-id="f85a3-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="f85a3-114">Виберіть один із [доступних з’єднувачів](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="f85a3-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="f85a3-115">У цьому прикладі ми вибираємо з’єднувач **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="f85a3-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f85a3-116">Уведіть необхідні відомості в **Параметрах підключення** для вибраного з’єднувача та виберіть **Далі**, щоб побачити попередній перегляд даних.</span><span class="sxs-lookup"><span data-stu-id="f85a3-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="f85a3-117">Виберіть **Перетворити дані**.</span><span class="sxs-lookup"><span data-stu-id="f85a3-117">Select **Transform data**.</span></span> <span data-ttu-id="f85a3-118">На цьому кроці додаються сутності до джерела даних.</span><span class="sxs-lookup"><span data-stu-id="f85a3-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="f85a3-119">Сутності — це набори даних.</span><span class="sxs-lookup"><span data-stu-id="f85a3-119">Entities are datasets.</span></span> <span data-ttu-id="f85a3-120">Якщо у вас є база даних, яка містить кілька наборів даних, кожен набір даних є власною сутністю.</span><span class="sxs-lookup"><span data-stu-id="f85a3-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="f85a3-121">Діалогове вікно **Power Query — редагування запитів** дає змогу переглянути та уточнити дані.</span><span class="sxs-lookup"><span data-stu-id="f85a3-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="f85a3-122">Сутності, які системи визначать в вибраному джерелі даних, відобразяться в області ліворуч.</span><span class="sxs-lookup"><span data-stu-id="f85a3-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f85a3-123">![Діалогове вікно редагування запитів](media/data-manager-configure-edit-queries.png "Діалогове вікно редагування запитів")</span><span class="sxs-lookup"><span data-stu-id="f85a3-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="f85a3-124">Дані можна також перетворювати.</span><span class="sxs-lookup"><span data-stu-id="f85a3-124">You can also transform your data.</span></span> <span data-ttu-id="f85a3-125">Виберіть сутність для редагування або перетворення.</span><span class="sxs-lookup"><span data-stu-id="f85a3-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="f85a3-126">Скористайтеся параметрами у вікні Power Query, щоб застосувати перетворення.</span><span class="sxs-lookup"><span data-stu-id="f85a3-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="f85a3-127">Кожне перетворення буде додано до списку попід **Застосовані кроки**.</span><span class="sxs-lookup"><span data-stu-id="f85a3-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="f85a3-128">Power Query надає численні заздалегідь задані параметри перетворення.</span><span class="sxs-lookup"><span data-stu-id="f85a3-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="f85a3-129">Для отримання додаткових відомостей див. розділ [Перетворення Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="f85a3-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="f85a3-130">Ви можете додати додаткові сутності до джерела даних. Для цього виберіть **Отримати дані** в діалоговому вікні **Редагування запитів**.</span><span class="sxs-lookup"><span data-stu-id="f85a3-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="f85a3-131">Ці перетворення рекомендовано виконувати в наведених нижче випадках.</span><span class="sxs-lookup"><span data-stu-id="f85a3-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="f85a3-132">Якщо ви отримуєте дані з CSV-файлу, перший рядок часто містить заголовки.</span><span class="sxs-lookup"><span data-stu-id="f85a3-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="f85a3-133">Відкрийте **Трансформування таблиці** та виберіть **Використовувати заголовки як перший рядок**.</span><span class="sxs-lookup"><span data-stu-id="f85a3-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="f85a3-134">Перевірте, що тип даних задано належним чином.</span><span class="sxs-lookup"><span data-stu-id="f85a3-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="f85a3-135">Виберіть **Зберегти** в нижній частині вікна Power Query, щоб зберегти перетворення.</span><span class="sxs-lookup"><span data-stu-id="f85a3-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="f85a3-136">Після збереження ви побачите своє джерело даних в списку **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="f85a3-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="f85a3-137">На сторінці **Джерела даних** можна помітити, що нове джерело даних має стан **Оновлюється**.</span><span class="sxs-lookup"><span data-stu-id="f85a3-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="f85a3-138">Доступні джерела даних Power Query</span><span class="sxs-lookup"><span data-stu-id="f85a3-138">Available Power Query data sources</span></span>

<span data-ttu-id="f85a3-139">Див. [Довідник зі з’єднувачів Power Query](https://docs.microsoft.com/power-query/connectors/), щоб знайти актуальний список з’єднувачів, що можна вибрати для імпортування даних у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f85a3-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="f85a3-140">З’єднувачі із галочкою у стовпці **Customer Insights (Потоки даних)** можуть використовуватись для створення нових джерел даних на основі Power Query.</span><span class="sxs-lookup"><span data-stu-id="f85a3-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="f85a3-141">Перегляньте документацію для певного з'єднувача, щоб дізнатися більше про його попередні умови, обмеження та інші відомості.</span><span class="sxs-lookup"><span data-stu-id="f85a3-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="f85a3-142">Редагування джерел даних Power Query</span><span class="sxs-lookup"><span data-stu-id="f85a3-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="f85a3-143">Можливо, не вдасться внести зміни до джерел даних, які зараз використовуються в одному з процесів програми (наприклад, *сегментації*, *зіставленні* або *злитті*).</span><span class="sxs-lookup"><span data-stu-id="f85a3-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="f85a3-144">За допомогою сторінки **Настройки** можна відстежувати перебіг виконання кожного з активних процесів.</span><span class="sxs-lookup"><span data-stu-id="f85a3-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="f85a3-145">Після завершення процесу можна повернутися на сторінку **Джерела даних** і внести зміни.</span><span class="sxs-lookup"><span data-stu-id="f85a3-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="f85a3-146">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="f85a3-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="f85a3-147">Виберіть вертикальні три крапки поруч із джерелом даних, яке потрібно змінити, а потім натисніть **Змінити** в розкривному меню.</span><span class="sxs-lookup"><span data-stu-id="f85a3-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f85a3-148">![Параметр редагування](media/edit-option-data-sources.png "Параметр редагування")</span><span class="sxs-lookup"><span data-stu-id="f85a3-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="f85a3-149">Застосуйте зміни та перетворення в діалоговому вікні **Power Query — редагування запитів**, як описано в розділі [Створення нового джерела даних](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="f85a3-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="f85a3-150">Виберіть **Зберегти** в Power Query після завершення редагування, щоб зберегти зміни.</span><span class="sxs-lookup"><span data-stu-id="f85a3-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
