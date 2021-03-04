---
title: З’єднувач Power BI
description: Дізнайтесь, як використовувати з’єднувач Dynamics 365 Customer Insights у Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477113"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="2d5b4-103">З’єднувач для Power BI (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="2d5b4-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="2d5b4-104">Створення графічних відображень для даних за допомогою програми Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="2d5b4-105">Створюйте додаткові аналітичні огляди та звіти з об’єднаними даними клієнтів.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d5b4-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="2d5b4-106">Prerequisites</span></span>

- <span data-ttu-id="2d5b4-107">Ви маєте уніфіковані профілів клієнта.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="2d5b4-108">На комп'ютері інстальовано найновішу версію [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/).</span><span class="sxs-lookup"><span data-stu-id="2d5b4-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="2d5b4-109">[Дізнайтеся більше про Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="2d5b4-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="2d5b4-110">Настроювання з’єднувача для Power BI</span><span class="sxs-lookup"><span data-stu-id="2d5b4-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="2d5b4-111">У Power BI Desktop виберіть **Файл** > **Отримати дані**.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="2d5b4-112">Клацніть **Більше** і виконайте пошук **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="2d5b4-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="2d5b4-113">Виберіть **Підключити**.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-113">Select **Connect**.</span></span>

1. <span data-ttu-id="2d5b4-114">**Увійдіть** у систему за допомогою того самого облікового запису організації, що використовується для Customer Insights, і натисніть **З’єднати**.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="2d5b4-115">Обліковий запис, вказаний на цьому кроці, використовується для вилучення даних із Customer Insights і не має бути таким же, що й обліковий запис, що використовується для входу в Power BI.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="2d5b4-116">Для скидання облікового запису, який використовується для отримання даних, відкрийте Power BI і перейдіть до меню **Файл** > **Параметри** > **Налаштування** > **Настройки джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="2d5b4-117">У списку джерел даних виберіть **Dynamics 365 Customer Insights Логін** і виберіть **Очистити дозволи**.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="2d5b4-118">У діалоговому вікні **Навігатор**.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="2d5b4-119">ви бачите список усіх середовищ, до яких є доступ.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="2d5b4-120">Розгорніть середовище та відкрийте будь-які папки (сутності, показники, сегменти, збагачення).</span><span class="sxs-lookup"><span data-stu-id="2d5b4-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="2d5b4-121">Наприклад, відкрийте папку **Сутності**, щоб переглянути всі сутності, які можна імпортувати.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="2d5b4-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span><span class="sxs-lookup"><span data-stu-id="2d5b4-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="2d5b4-123">Установіть прапорці поруч із сутностями, які необхідно включити, і натисніть **Завантажити**.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="2d5b4-124">Можна вибрати кілька сутностей з кількох середовищ.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="2d5b4-125">Під час завантаження сутностей відобразиться діалогове вікно завантаження.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="2d5b4-126">Коли всі вибрані сутності завантажено, можна скористатися можливостями Power BI для візуалізації даних.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="2d5b4-127">Великі набори даних</span><span class="sxs-lookup"><span data-stu-id="2d5b4-127">Large data sets</span></span>

<span data-ttu-id="2d5b4-128">З'єднувач Customer Insights для Power BI призначений для роботи з наборами даних, що містять до 1 000 000 профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="2d5b4-129">Імпортування більших наборів, скоріш за все, працюватиме, але потребуватиме багато часу.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="2d5b4-130">Крім того, процес може вичерпати час, відведений на виконання обмеженнями Power BI.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="2d5b4-131">Для отримання додаткових відомостей див. розділ [Power BI: рекомендації щодо великих наборів даних](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="2d5b4-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="2d5b4-132">Робота з підмножиною даних</span><span class="sxs-lookup"><span data-stu-id="2d5b4-132">Work with a subset of data</span></span>

<span data-ttu-id="2d5b4-133">Розглянемо роботу з підмножиною даних.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="2d5b4-134">Наприклад, можна створити [сегменти](segments.md) замість експортування всіх записів клієнтів до програми Power BI.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2d5b4-135">Виправлення неполадок</span><span class="sxs-lookup"><span data-stu-id="2d5b4-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="2d5b4-136">Середовище Customer Insights не відображається в Power BI</span><span class="sxs-lookup"><span data-stu-id="2d5b4-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="2d5b4-137">Середовища, для яких визначено більше одного [зв’язка](relationships.md) між двома ідентичними сутностями в аналізі аудиторії, будуть недоступні в з’єднувачі Power BI.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="2d5b4-138">Можна визначити та видалити дублікати зв'язків.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="2d5b4-139">В аналізі аудиторії відкрийте **Дані** > **Зв’язки** у середовищі, що відсутнє у Power BI.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="2d5b4-140">Визначення дублікатів зв'язків:</span><span class="sxs-lookup"><span data-stu-id="2d5b4-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="2d5b4-141">Перевірте, чи існує більше одного визначеного зв’язку між однаковими сутностями.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="2d5b4-142">Перевірте, чи є зв'язки між двома сутностями, що обидва беруть участь в процесі уніфікації.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="2d5b4-143">Існує неявний зв'язок, визначений між усіма сутностями, включеними до процесу об'єднання.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="2d5b4-144">Видаліть усі виявлені дублікати зв'язків.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="2d5b4-145">Після видалення дублікатів зв'язків спробуйте знову налаштувати з’єднувач Power BI.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="2d5b4-146">Тепер середовище має бути доступним.</span><span class="sxs-lookup"><span data-stu-id="2d5b4-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

