---
title: Покрокове оновлення для джерел даних на основі Power Query
description: Оновлюйте нові й оновлені дані для великих джерел даних на основі Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268573"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="284cb-103">Інкрементне оновлення для джерел даних на основі Power Query</span><span class="sxs-lookup"><span data-stu-id="284cb-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="284cb-104">Інкрементне оновлення для джерел даних забезпечує зазначені нижче переваги.</span><span class="sxs-lookup"><span data-stu-id="284cb-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="284cb-105">**Швидке оновлення** – оновлюються лише дані, які було змінено.</span><span class="sxs-lookup"><span data-stu-id="284cb-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="284cb-106">Наприклад, можна оновити лише останні п’ять днів історичного набору даних.</span><span class="sxs-lookup"><span data-stu-id="284cb-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="284cb-107">**Підвищена надійність** – з меншим обсягом оновлення не потрібно підтримувати підключення до нестабільних вихідних систем довго, що зменшує ризик виникнення проблем із підключенням.</span><span class="sxs-lookup"><span data-stu-id="284cb-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="284cb-108">**Зменшене споживання ресурсів** – оновлення лише підмножини загальної кількості даних допомагає ефективніше використовувати ресурси обчислення та зменшує екологічні наслідки.</span><span class="sxs-lookup"><span data-stu-id="284cb-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="284cb-109">Налаштування інкрементного оновлення</span><span class="sxs-lookup"><span data-stu-id="284cb-109">Configure incremental refresh</span></span>

<span data-ttu-id="284cb-110">Аналіз аудиторії дає змогу покроково оновити джерела даних, імпортовані за допомогою Power Query, які підтримують покрокове передавання.</span><span class="sxs-lookup"><span data-stu-id="284cb-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="284cb-111">Наприклад, бази даних Azure SQL з полями дати та часу, які вказують, коли записи даних було оновлено останній раз.</span><span class="sxs-lookup"><span data-stu-id="284cb-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="284cb-112">[Створення нового джерела даних на основі Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="284cb-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="284cb-113">Уведіть ім’я джерела даних.</span><span class="sxs-lookup"><span data-stu-id="284cb-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="284cb-114">Виберіть джерело даних, що підтримує інкрементне оновлення, наприклад базу даних SQL Azure.</span><span class="sxs-lookup"><span data-stu-id="284cb-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="284cb-115">Виберіть сутності або таблиці для обробки.</span><span class="sxs-lookup"><span data-stu-id="284cb-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="284cb-116">Завершіть перетворення та натисніть кнопку **Далі**.</span><span class="sxs-lookup"><span data-stu-id="284cb-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="284cb-117">У діалоговому вікні **Налаштування інкрементного оновлення** виберіть елемент **Налаштування**, щоб відкрити **Параметри інкрементного оновлення**.</span><span class="sxs-lookup"><span data-stu-id="284cb-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="284cb-118">Якщо натиснути кнопку **Пропустити**, джерело даних оновить весь набір даних.</span><span class="sxs-lookup"><span data-stu-id="284cb-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="284cb-119">Крім того, можна застосувати інкрементне оновлення пізніше, змінивши наявне джерело даних.</span><span class="sxs-lookup"><span data-stu-id="284cb-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="284cb-120">У **Параметрах інкрементного оновлення** можна налаштувати інкрементне оновлення для всіх сутностей, вибраних під час створення джерела даних.</span><span class="sxs-lookup"><span data-stu-id="284cb-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="284cb-121">![Налаштування сутностей у джерелі даних для інкрементного оновлення](media/incremental-refresh-settings.png "Налаштування сутностей у джерелі даних для інкрементного оновлення")</span><span class="sxs-lookup"><span data-stu-id="284cb-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="284cb-122">Виберіть сутність, а потім укажіть зазначені нижче дані.</span><span class="sxs-lookup"><span data-stu-id="284cb-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="284cb-123">**Виберіть первинний ключ**: вибір первинного ключа для сутності або таблиці.</span><span class="sxs-lookup"><span data-stu-id="284cb-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="284cb-124">**Визначте поле «Останнє оновлення»**: у цьому полі відображатимуться лише атрибути типу дата й час.</span><span class="sxs-lookup"><span data-stu-id="284cb-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="284cb-125">Виберіть атрибут, який вказує на час останнього оновлення записів.</span><span class="sxs-lookup"><span data-stu-id="284cb-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="284cb-126">Його буде використано для визначення записів у межах часових рамок інкрементного оновлення.</span><span class="sxs-lookup"><span data-stu-id="284cb-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="284cb-127">**Перевіряти наявність оновлень кожні**: укажіть часові рамки для інкрементного оновлення.</span><span class="sxs-lookup"><span data-stu-id="284cb-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="284cb-128">Натисніть кнопку **Зберегти**, щоб завершити створення джерела даних.</span><span class="sxs-lookup"><span data-stu-id="284cb-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="284cb-129">Початкове оновлення даних буде повним оновленням.</span><span class="sxs-lookup"><span data-stu-id="284cb-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="284cb-130">Після цього інткрементне оновлення даних виконується відповідно до налаштувань на попередньому кроці.</span><span class="sxs-lookup"><span data-stu-id="284cb-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]