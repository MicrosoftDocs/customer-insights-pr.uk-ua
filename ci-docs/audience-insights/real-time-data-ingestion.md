---
title: Прийом даних і обмеження в режимі реального часу
description: Загальні відомості про можливості в режимі реального часу в розділі «Аналіз аудиторії».
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270305"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="7fe19-103">Обробка даних у режимі реального часу (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="7fe19-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="7fe19-104">Завдяки функціям, що працюють майже в режимі реального часу, за лічені секунди можна переглянути останні взаємодії клієнтів із продуктами або послугами.</span><span class="sxs-lookup"><span data-stu-id="7fe19-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="7fe19-105">[Заплановане оновлення ](system.md#schedule-tab)включає велику кількість записів і кілька комплексних операцій.</span><span class="sxs-lookup"><span data-stu-id="7fe19-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="7fe19-106">Спочатку дані витягаються з джерела даних.</span><span class="sxs-lookup"><span data-stu-id="7fe19-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="7fe19-107">Потім дані об’єднуються та збагачуються додатковою інформацією.</span><span class="sxs-lookup"><span data-stu-id="7fe19-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="7fe19-108">Кожне виконання цього процесу може тривати від кількох хвилин до кількох годин.</span><span class="sxs-lookup"><span data-stu-id="7fe19-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="7fe19-109">Функціональність у режимі реального часу забезпечує негайне використання даних, доки наступне заплановане оновлення не отримає ці дані з джерела даних.</span><span class="sxs-lookup"><span data-stu-id="7fe19-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="7fe19-110">Оновлення в режимі реального часу мають термін дії, після завершення якого вони більше не змінюють значення з джерела даних:</span><span class="sxs-lookup"><span data-stu-id="7fe19-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="7fe19-111">Оновлення профілю зберігатиметься протягом 4 годин</span><span class="sxs-lookup"><span data-stu-id="7fe19-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="7fe19-112">Справи зберігатимуться протягом 30 днів</span><span class="sxs-lookup"><span data-stu-id="7fe19-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="7fe19-113">Ці значення – це параметри виклику API, які можна змінити.</span><span class="sxs-lookup"><span data-stu-id="7fe19-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="7fe19-114">Вони мають забезпечити, щоб вихідні дані залишалися вашим достовірним джерелом.</span><span class="sxs-lookup"><span data-stu-id="7fe19-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="7fe19-115">Якщо потрібно, щоб оновлення в режимі реального часу були включені довше, потрібно додати їх до джерела даних, щоб вони витягнули під час наступного запланованого оновлення.</span><span class="sxs-lookup"><span data-stu-id="7fe19-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="7fe19-116">Оновлення полів уніфікованого профілю клієнта в режимі реального часу</span><span class="sxs-lookup"><span data-stu-id="7fe19-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="7fe19-117">Оновлені профілі відображатимуться в поданні картки клієнта або в будь-якому іншому поданні за лічені секунди.</span><span class="sxs-lookup"><span data-stu-id="7fe19-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="7fe19-118">Оскільки операції в режимі реального часу відбуваються після об’єднання даних, вони застосовуються лише до уніфікованих профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="7fe19-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="7fe19-119">Отже, зміни в профілі в режимі реального часу не стосуватимуться показників, складу сегментів і збагачень.</span><span class="sxs-lookup"><span data-stu-id="7fe19-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="7fe19-120">Обмеження</span><span class="sxs-lookup"><span data-stu-id="7fe19-120">Limitations</span></span>

- <span data-ttu-id="7fe19-121">Профілі клієнтів можна оновлювати, але не можна створювати й видаляти.</span><span class="sxs-lookup"><span data-stu-id="7fe19-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="7fe19-122">Експорт оновлень у режимі реального часу до зовнішніх систем, наприклад Power BI, наразі неможливий.</span><span class="sxs-lookup"><span data-stu-id="7fe19-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="7fe19-123">Створення справ у режимі реального часу</span><span class="sxs-lookup"><span data-stu-id="7fe19-123">Real-time creation of activities</span></span>

<span data-ttu-id="7fe19-124">API в режимі реального часу дає змогу публікувати нову справу з вихідної системи (окремого вихідного запису) до уніфікованого профілю клієнта.</span><span class="sxs-lookup"><span data-stu-id="7fe19-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="7fe19-125">Нова справа буде доступна як уніфікована справа в цьому уніфікованому профілі клієнта за лічені секунди.</span><span class="sxs-lookup"><span data-stu-id="7fe19-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="7fe19-126">Шкалу часу можна переглянути в поданні картки клієнта або на будь-яку іншій інтеграції часової шкали, настроєну для цього.</span><span class="sxs-lookup"><span data-stu-id="7fe19-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7fe19-127">Справи є незмінними.</span><span class="sxs-lookup"><span data-stu-id="7fe19-127">Activities are immutable.</span></span> <span data-ttu-id="7fe19-128">Після створення вони не змінюються.</span><span class="sxs-lookup"><span data-stu-id="7fe19-128">They don't change once created.</span></span>
> - <span data-ttu-id="7fe19-129">Наразі сегменти та показники не оновлюються на основі нової справи.</span><span class="sxs-lookup"><span data-stu-id="7fe19-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="7fe19-130">Справи, додані лише за допомогою API в режимі реального часу, не є частиною експорту й не відображатимуться в PowerBI.</span><span class="sxs-lookup"><span data-stu-id="7fe19-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="7fe19-131">Існує два способи підключення до API в режимі реального часу.</span><span class="sxs-lookup"><span data-stu-id="7fe19-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="7fe19-132">[опосередковано](#connect-via-the-dynamics-365-customer-insights-connector) за допомогою [з’єднувача Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="7fe19-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="7fe19-133">[безпосередньо](#connect-directly-to-the-real-time-api) з кодом</span><span class="sxs-lookup"><span data-stu-id="7fe19-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="7fe19-134">Обидва способи мають наведені нижче передумови.</span><span class="sxs-lookup"><span data-stu-id="7fe19-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="7fe19-135">Середовище Customer Insights</span><span class="sxs-lookup"><span data-stu-id="7fe19-135">A Customer Insights environment</span></span>
- <span data-ttu-id="7fe19-136">Уніфіковані профілі клієнтів</span><span class="sxs-lookup"><span data-stu-id="7fe19-136">Unified customer profiles</span></span>
- <span data-ttu-id="7fe19-137">Настроєні справи та справи, які виконуються</span><span class="sxs-lookup"><span data-stu-id="7fe19-137">Activities configured and run</span></span>
- <span data-ttu-id="7fe19-138">Дозвіл співавтора або адміністратора на автентифікацію облікового запису</span><span class="sxs-lookup"><span data-stu-id="7fe19-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="7fe19-139">Підключення за допомогою з’єднувача Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="7fe19-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="7fe19-140">API в режимі реального часу може інтегрувати дані зі спеціалізованого з’єднувача Power Platform, [з’єднувач Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/), без необхідності писати та розгортати будь-який код.</span><span class="sxs-lookup"><span data-stu-id="7fe19-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="7fe19-141">З’єднувач може виконувати ті самі дії в режимі реального часу, що й API.</span><span class="sxs-lookup"><span data-stu-id="7fe19-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="7fe19-142">Для преміум-з’єднувачів потрібна дійсна ліцензія.</span><span class="sxs-lookup"><span data-stu-id="7fe19-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="7fe19-143">Щоб отримати додаткові відомості, див. [Поширені запитання про ліцензування Power Apps і Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="7fe19-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="7fe19-144">Power Platform [Power Apps та/або Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="7fe19-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="7fe19-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="7fe19-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="7fe19-146">Докладні відомості про створення потоків див. у [документації Power Automate](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="7fe19-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="7fe19-147">Підключення безпосередньо до API в режимі реального часу</span><span class="sxs-lookup"><span data-stu-id="7fe19-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="7fe19-148">Можна використовувати можливості реального часу, створивши власну воронку продажів і безпосередньо підключившись до API в режимі реального часу.</span><span class="sxs-lookup"><span data-stu-id="7fe19-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="7fe19-149">Опублікувати справу можна у форматі вихідної системи або у форматі UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="7fe19-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="7fe19-150">Створення формату шляхом виклику API до /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="7fe19-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="7fe19-151">Відомості про цей API, у тому числі параметри та відповіді, можна знайти в розділі **Дані сутності** у [довіднику API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="7fe19-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="7fe19-152">Для отримання додаткових відомостей див. розділ [Робота з Customer Insights API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="7fe19-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="7fe19-153">Ознайомтеся із навантаженням у режимі реального часу, використовуючи телеметрію.</span><span class="sxs-lookup"><span data-stu-id="7fe19-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="7fe19-154">Отримайте огляд обсягу запитів до API в режимі реального часу та інформацію про проблеми, які можуть виникнути в системі.</span><span class="sxs-lookup"><span data-stu-id="7fe19-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="7fe19-155">Ви можете [бачити дані телеметрії в режимі реального часу](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="7fe19-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]