---
title: З’єднувач Power BI
description: Дізнайтесь, як використовувати з’єднувач Dynamics 365 Customer Insights у Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407237"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="9e869-103">З’єднувач для Power BI (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="9e869-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="9e869-104">Створення графічних відображень для даних за допомогою програми Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="9e869-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="9e869-105">Створюйте додаткові аналітичні огляди та звіти з об’єднаними даними клієнтів.</span><span class="sxs-lookup"><span data-stu-id="9e869-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9e869-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="9e869-106">Prerequisites</span></span>

- <span data-ttu-id="9e869-107">Ви маєте уніфіковані профілів клієнта.</span><span class="sxs-lookup"><span data-stu-id="9e869-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="9e869-108">На комп'ютері інстальовано найновішу версію [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/).</span><span class="sxs-lookup"><span data-stu-id="9e869-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="9e869-109">[Дізнайтеся більше про Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="9e869-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="9e869-110">Настроювання з’єднувача для Power BI</span><span class="sxs-lookup"><span data-stu-id="9e869-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="9e869-111">У Power BI Desktop виберіть **Файл** > **Отримати дані**.</span><span class="sxs-lookup"><span data-stu-id="9e869-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="9e869-112">Клацніть **Більше** і виконайте пошук **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="9e869-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="9e869-113">Виберіть відповідний результат і натисніть кнопку **З’єднати**.</span><span class="sxs-lookup"><span data-stu-id="9e869-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="9e869-114">**Увійдіть** у систему за допомогою того самого облікового запису організації, що використовується для Customer Insights, і натисніть **З’єднати**.</span><span class="sxs-lookup"><span data-stu-id="9e869-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="9e869-115">Обліковий запис, вказаний на цьому кроці, використовується для вилучення даних із Customer Insights і не має бути таким же, що й обліковий запис, що використовується для входу в Power BI.</span><span class="sxs-lookup"><span data-stu-id="9e869-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="9e869-116">Для скидання облікового запису, який використовується для отримання даних, відкрийте Power BI і перейдіть до меню **Файл** > **Параметри** > **Налаштування** > **Настройки джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="9e869-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="9e869-117">У списку джерел даних виберіть **Dynamics 365 Customer Insights Логін** і виберіть **Очистити дозволи**.</span><span class="sxs-lookup"><span data-stu-id="9e869-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="9e869-118">У діалоговому вікні **Навігатор**.</span><span class="sxs-lookup"><span data-stu-id="9e869-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="9e869-119">ви бачите список усіх середовищ, до яких є доступ.</span><span class="sxs-lookup"><span data-stu-id="9e869-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="9e869-120">Розгорніть середовище та відкрийте будь-які папки (сутності, показники, сегменти, збагачення).</span><span class="sxs-lookup"><span data-stu-id="9e869-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="9e869-121">Наприклад, відкрийте папку **Сутності**, щоб переглянути всі сутності, які можна імпортувати.</span><span class="sxs-lookup"><span data-stu-id="9e869-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="9e869-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span><span class="sxs-lookup"><span data-stu-id="9e869-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="9e869-123">Установіть прапорці поруч із сутностями, які необхідно включити, і натисніть **Завантажити**.</span><span class="sxs-lookup"><span data-stu-id="9e869-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="9e869-124">Можна вибрати кілька сутностей з кількох середовищ.</span><span class="sxs-lookup"><span data-stu-id="9e869-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="9e869-125">Під час завантаження сутностей відобразиться діалогове вікно завантаження.</span><span class="sxs-lookup"><span data-stu-id="9e869-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="9e869-126">Коли всі вибрані сутності завантажено, можна скористатися можливостями Power BI для візуалізації даних.</span><span class="sxs-lookup"><span data-stu-id="9e869-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="9e869-127">Великі набори даних</span><span class="sxs-lookup"><span data-stu-id="9e869-127">Large data sets</span></span>

<span data-ttu-id="9e869-128">З'єднувач Customer Insights для Power BI призначений для роботи з наборами даних, що містять до 1 000 000 профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="9e869-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="9e869-129">Імпортування більших наборів, скоріш за все, працюватиме, але потребуватиме багато часу.</span><span class="sxs-lookup"><span data-stu-id="9e869-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="9e869-130">Крім того, процес може вичерпати час, відведений на виконання обмеженнями Power BI.</span><span class="sxs-lookup"><span data-stu-id="9e869-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="9e869-131">Для отримання додаткових відомостей див. розділ [Power BI: рекомендації щодо великих наборів даних](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="9e869-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="9e869-132">Робота з підмножиною даних</span><span class="sxs-lookup"><span data-stu-id="9e869-132">Work with a subset of data</span></span>

<span data-ttu-id="9e869-133">Розглянемо роботу з підмножиною даних.</span><span class="sxs-lookup"><span data-stu-id="9e869-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="9e869-134">Наприклад, можна створити [сегменти](segments.md) замість експортування всіх записів клієнтів до програми Power BI.</span><span class="sxs-lookup"><span data-stu-id="9e869-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
