---
title: Передавання даних за допомогою з'єднувача Power Query
description: З’єднувачі для джерел даних, що основані на Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305916"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="49081-103">Підключення до джерела даних Power Query</span><span class="sxs-lookup"><span data-stu-id="49081-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="49081-104">Power Query пропонує широкий набір з’єднувачів для отримання даних.</span><span class="sxs-lookup"><span data-stu-id="49081-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="49081-105">Dynamics 365 Customer Insights підтримує більшість із цих з’єднувачів.</span><span class="sxs-lookup"><span data-stu-id="49081-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="49081-106">Додавання джерел даних на основі з’єднувачів Power Query в цілому виконується за кроками, окресленими у наступному розділі.</span><span class="sxs-lookup"><span data-stu-id="49081-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="49081-107">Однак можуть знадобитися різні відомості, залежно від використовуваного з'єднувача.</span><span class="sxs-lookup"><span data-stu-id="49081-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="49081-108">Для отримання додаткових відомостей див. документацію для окремих з’єднувачів у [Довіднику зі з’єднувачів Power Query](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="49081-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="49081-109">Створення нового джерела даних</span><span class="sxs-lookup"><span data-stu-id="49081-109">Create a new data source</span></span>

1. <span data-ttu-id="49081-110">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="49081-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="49081-111">Виберіть **Додати джерело даних**.</span><span class="sxs-lookup"><span data-stu-id="49081-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="49081-112">Виберіть метод **Імпорт даних**, а тоді виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="49081-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="49081-113">Укажіть **Ім'я** для джерела даних, а тоді виберіть **Далі**, щоб створити джерело даних.</span><span class="sxs-lookup"><span data-stu-id="49081-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="49081-114">Рекомендації щодо імен:</span><span class="sxs-lookup"><span data-stu-id="49081-114">Name guidelines:</span></span> 
   - <span data-ttu-id="49081-115">Починайте з букви.</span><span class="sxs-lookup"><span data-stu-id="49081-115">Start with a letter.</span></span>
   - <span data-ttu-id="49081-116">Використовуйте лише букви та цифри.</span><span class="sxs-lookup"><span data-stu-id="49081-116">Use letters and numbers only.</span></span> <span data-ttu-id="49081-117">Не можна використовувати спеціальні символи та пробіли.</span><span class="sxs-lookup"><span data-stu-id="49081-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="49081-118">Використовуйте від 3 до 64 символів.</span><span class="sxs-lookup"><span data-stu-id="49081-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="49081-119">Виберіть один із [доступних з’єднувачів](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="49081-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="49081-120">У цьому прикладі ми вибираємо з’єднувач **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="49081-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="49081-121">Уведіть необхідні відомості в **Параметрах підключення** для вибраного з’єднувача та виберіть **Далі**, щоб побачити попередній перегляд даних.</span><span class="sxs-lookup"><span data-stu-id="49081-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="49081-122">Виберіть **Перетворити дані**.</span><span class="sxs-lookup"><span data-stu-id="49081-122">Select **Transform data**.</span></span> <span data-ttu-id="49081-123">На цьому кроці додаються сутності до джерела даних.</span><span class="sxs-lookup"><span data-stu-id="49081-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="49081-124">Сутності — це набори даних.</span><span class="sxs-lookup"><span data-stu-id="49081-124">Entities are datasets.</span></span> <span data-ttu-id="49081-125">Якщо у вас є база даних, яка містить кілька наборів даних, кожен набір даних є власною сутністю.</span><span class="sxs-lookup"><span data-stu-id="49081-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="49081-126">Діалогове вікно **Power Query — редагування запитів** дає змогу переглянути та уточнити дані.</span><span class="sxs-lookup"><span data-stu-id="49081-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="49081-127">Сутності, які системи визначать в вибраному джерелі даних, відобразяться в області ліворуч.</span><span class="sxs-lookup"><span data-stu-id="49081-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="49081-128">![Діалогове вікно редагування запитів](media/data-manager-configure-edit-queries.png "Діалогове вікно редагування запитів")</span><span class="sxs-lookup"><span data-stu-id="49081-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="49081-129">Дані можна також перетворювати.</span><span class="sxs-lookup"><span data-stu-id="49081-129">You can also transform your data.</span></span> <span data-ttu-id="49081-130">Виберіть сутність для редагування або перетворення.</span><span class="sxs-lookup"><span data-stu-id="49081-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="49081-131">Скористайтеся параметрами у вікні Power Query, щоб застосувати перетворення.</span><span class="sxs-lookup"><span data-stu-id="49081-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="49081-132">Кожне перетворення буде додано до списку попід **Застосовані кроки**.</span><span class="sxs-lookup"><span data-stu-id="49081-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="49081-133">Power Query надає численні заздалегідь задані параметри перетворення.</span><span class="sxs-lookup"><span data-stu-id="49081-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="49081-134">Для отримання додаткових відомостей див. розділ [Перетворення Power Query](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="49081-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="49081-135">Ви можете додати додаткові сутності до джерела даних. Для цього виберіть **Отримати дані** в діалоговому вікні **Редагування запитів**.</span><span class="sxs-lookup"><span data-stu-id="49081-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="49081-136">Ці перетворення рекомендовано виконувати в наведених нижче випадках.</span><span class="sxs-lookup"><span data-stu-id="49081-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="49081-137">Якщо ви отримуєте дані з CSV-файлу, перший рядок часто містить заголовки.</span><span class="sxs-lookup"><span data-stu-id="49081-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="49081-138">Відкрийте **Трансформування таблиці** та виберіть **Використовувати заголовки як перший рядок**.</span><span class="sxs-lookup"><span data-stu-id="49081-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="49081-139">Перевірте, що тип даних задано належним чином.</span><span class="sxs-lookup"><span data-stu-id="49081-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="49081-140">Виберіть **Зберегти** в нижній частині вікна Power Query, щоб зберегти перетворення.</span><span class="sxs-lookup"><span data-stu-id="49081-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="49081-141">Після збереження ви побачите своє джерело даних в списку **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="49081-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="49081-142">На сторінці **Джерела даних** можна помітити, що нове джерело даних має стан **Оновлюється**.</span><span class="sxs-lookup"><span data-stu-id="49081-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="49081-143">Доступні джерела даних Power Query</span><span class="sxs-lookup"><span data-stu-id="49081-143">Available Power Query data sources</span></span>

<span data-ttu-id="49081-144">Див. [Довідник зі з’єднувачів Power Query](/power-query/connectors/), щоб знайти актуальний список з’єднувачів, що можна вибрати для імпортування даних у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="49081-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="49081-145">З’єднувачі із галочкою у стовпці **Customer Insights (Потоки даних)** можуть використовуватись для створення нових джерел даних на основі Power Query.</span><span class="sxs-lookup"><span data-stu-id="49081-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="49081-146">Перегляньте документацію для певного з'єднувача, щоб дізнатися більше про його попередні умови, обмеження та інші відомості.</span><span class="sxs-lookup"><span data-stu-id="49081-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="49081-147">Редагування джерел даних Power Query</span><span class="sxs-lookup"><span data-stu-id="49081-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="49081-148">Можливо, не вдасться внести зміни до джерел даних, які зараз використовуються в одному з процесів програми (наприклад, *сегментації*, *зіставленні* або *злитті*).</span><span class="sxs-lookup"><span data-stu-id="49081-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="49081-149">За допомогою сторінки **Настройки** можна відстежувати перебіг виконання кожного з активних процесів.</span><span class="sxs-lookup"><span data-stu-id="49081-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="49081-150">Після завершення процесу можна повернутися на сторінку **Джерела даних** і внести зміни.</span><span class="sxs-lookup"><span data-stu-id="49081-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="49081-151">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="49081-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="49081-152">Виберіть вертикальні три крапки поряд із джерелом даних, які ви бажаєте змінити, потім виберіть **Редагувати** з розкривного меню.</span><span class="sxs-lookup"><span data-stu-id="49081-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the dropdown menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="49081-153">![Параметр редагування](media/edit-option-data-sources.png "Параметр редагування")</span><span class="sxs-lookup"><span data-stu-id="49081-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="49081-154">Застосуйте зміни та перетворення в діалоговому вікні **Power Query — редагування запитів**, як описано в розділі [Створення нового джерела даних](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="49081-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="49081-155">Виберіть **Зберегти** в Power Query після завершення редагування, щоб зберегти зміни.</span><span class="sxs-lookup"><span data-stu-id="49081-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]