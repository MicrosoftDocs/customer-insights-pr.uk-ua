---
title: Покрокове оновлення для джерел даних на основі Power Query
description: Оновлюйте нові й оновлені дані для великих джерел даних на основі Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 03f76bcfc7336d8430146e8a26ffa649c6a17db0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596846"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="8bc73-103">Інкрементне оновлення для джерел даних на основі Power Query</span><span class="sxs-lookup"><span data-stu-id="8bc73-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="8bc73-104">Інкрементне оновлення для джерел даних забезпечує зазначені нижче переваги.</span><span class="sxs-lookup"><span data-stu-id="8bc73-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="8bc73-105">**Швидке оновлення** – оновлюються лише дані, які було змінено.</span><span class="sxs-lookup"><span data-stu-id="8bc73-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="8bc73-106">Наприклад, можна оновити лише останні п’ять днів історичного набору даних.</span><span class="sxs-lookup"><span data-stu-id="8bc73-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="8bc73-107">**Підвищена надійність** – з меншим обсягом оновлення не потрібно підтримувати підключення до нестабільних вихідних систем довго, що зменшує ризик виникнення проблем із підключенням.</span><span class="sxs-lookup"><span data-stu-id="8bc73-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="8bc73-108">**Зменшене споживання ресурсів** – оновлення лише підмножини загальної кількості даних допомагає ефективніше використовувати ресурси обчислення та зменшує екологічні наслідки.</span><span class="sxs-lookup"><span data-stu-id="8bc73-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="8bc73-109">Налаштування інкрементного оновлення</span><span class="sxs-lookup"><span data-stu-id="8bc73-109">Configure incremental refresh</span></span>

<span data-ttu-id="8bc73-110">Аналіз аудиторії дає змогу покроково оновити джерела даних, імпортовані за допомогою Power Query, які підтримують покрокове передавання.</span><span class="sxs-lookup"><span data-stu-id="8bc73-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="8bc73-111">Наприклад, бази даних Azure SQL з полями дати та часу, які вказують, коли записи даних було оновлено останній раз.</span><span class="sxs-lookup"><span data-stu-id="8bc73-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="8bc73-112">[Створення нового джерела даних на основі Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="8bc73-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="8bc73-113">Уведіть ім’я джерела даних.</span><span class="sxs-lookup"><span data-stu-id="8bc73-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="8bc73-114">Виберіть джерело даних, що підтримує інкрементне оновлення, наприклад базу даних SQL Azure.</span><span class="sxs-lookup"><span data-stu-id="8bc73-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="8bc73-115">Виберіть сутності або таблиці для обробки.</span><span class="sxs-lookup"><span data-stu-id="8bc73-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="8bc73-116">Завершіть перетворення та натисніть кнопку **Далі**.</span><span class="sxs-lookup"><span data-stu-id="8bc73-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="8bc73-117">У діалоговому вікні **Налаштування інкрементного оновлення** виберіть елемент **Налаштування**, щоб відкрити **Параметри інкрементного оновлення**.</span><span class="sxs-lookup"><span data-stu-id="8bc73-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="8bc73-118">Якщо натиснути кнопку **Пропустити**, джерело даних оновить весь набір даних.</span><span class="sxs-lookup"><span data-stu-id="8bc73-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="8bc73-119">Крім того, можна застосувати інкрементне оновлення пізніше, змінивши наявне джерело даних.</span><span class="sxs-lookup"><span data-stu-id="8bc73-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="8bc73-120">У **Параметрах інкрементного оновлення** можна налаштувати інкрементне оновлення для всіх сутностей, вибраних під час створення джерела даних.</span><span class="sxs-lookup"><span data-stu-id="8bc73-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8bc73-121">![Налаштування сутностей у джерелі даних для інкрементного оновлення](media/incremental-refresh-settings.png "Налаштування сутностей у джерелі даних для інкрементного оновлення")</span><span class="sxs-lookup"><span data-stu-id="8bc73-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="8bc73-122">Виберіть сутність, а потім укажіть зазначені нижче дані.</span><span class="sxs-lookup"><span data-stu-id="8bc73-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="8bc73-123">**Виберіть первинний ключ**: вибір первинного ключа для сутності або таблиці.</span><span class="sxs-lookup"><span data-stu-id="8bc73-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="8bc73-124">**Визначте поле «Останнє оновлення»**: у цьому полі відображатимуться лише атрибути типу дата й час.</span><span class="sxs-lookup"><span data-stu-id="8bc73-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="8bc73-125">Виберіть атрибут, який вказує на час останнього оновлення записів.</span><span class="sxs-lookup"><span data-stu-id="8bc73-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="8bc73-126">Його буде використано для визначення записів у межах часових рамок інкрементного оновлення.</span><span class="sxs-lookup"><span data-stu-id="8bc73-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="8bc73-127">**Перевіряти наявність оновлень кожні**: укажіть часові рамки для інкрементного оновлення.</span><span class="sxs-lookup"><span data-stu-id="8bc73-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="8bc73-128">Натисніть кнопку **Зберегти**, щоб завершити створення джерела даних.</span><span class="sxs-lookup"><span data-stu-id="8bc73-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="8bc73-129">Початкове оновлення даних буде повним оновленням.</span><span class="sxs-lookup"><span data-stu-id="8bc73-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="8bc73-130">Після цього інткрементне оновлення даних виконується відповідно до налаштувань на попередньому кроці.</span><span class="sxs-lookup"><span data-stu-id="8bc73-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]