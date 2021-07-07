---
title: Спільні завдання для сценаріїв прогнозування
description: Дізнайтеся, як керувати прогнозами, уточнювати їх та виправляти неполадки.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315903"
---
# <a name="manage-predictions"></a><span data-ttu-id="de2fb-103">Керування прогнозами</span><span class="sxs-lookup"><span data-stu-id="de2fb-103">Manage predictions</span></span>

<span data-ttu-id="de2fb-104">У цій статті розглядаються деякі завдання, спільні для більшості сценаріїв прогнозування.</span><span class="sxs-lookup"><span data-stu-id="de2fb-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="de2fb-105">Усунення проблем з помилкою прогнозів</span><span class="sxs-lookup"><span data-stu-id="de2fb-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="de2fb-106">Перейдіть до розділу **Аналітика** > **Прогнози** і виберіть вкладку **Мої прогнози**.</span><span class="sxs-lookup"><span data-stu-id="de2fb-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="de2fb-107">Виберіть вертикальні три крапки поруч із прогнозом, для яких потрібно переглянути журнал помилок.</span><span class="sxs-lookup"><span data-stu-id="de2fb-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="de2fb-108">Натисніть **Журнали**.</span><span class="sxs-lookup"><span data-stu-id="de2fb-108">Select **Logs**.</span></span>

1. <span data-ttu-id="de2fb-109">Перегляньте усі помилки.</span><span class="sxs-lookup"><span data-stu-id="de2fb-109">Review all the errors.</span></span> <span data-ttu-id="de2fb-110">Може виникати кілька типів помилок, і у них описуються умови, що призвели до помилки.</span><span class="sxs-lookup"><span data-stu-id="de2fb-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="de2fb-111">Наприклад, помилка, яка сповіщає, що недостатньо даних для точного прогнозування зазвичай вирішується, якщо завантажити додаткові дані до Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="de2fb-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="de2fb-112">Звіт про зручність використання вхідних даних</span><span class="sxs-lookup"><span data-stu-id="de2fb-112">Input data usability report</span></span>

<span data-ttu-id="de2fb-113">У звіті про зручність використання вхідних даних надається узагальнене подання помилок і попереджень, які можуть виникати при роботі готових прогнозів.</span><span class="sxs-lookup"><span data-stu-id="de2fb-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="de2fb-114">Він також дає рекомендації щодо поліпшення продуктивності моделі.</span><span class="sxs-lookup"><span data-stu-id="de2fb-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="de2fb-115">Звіт стає доступним після того, як модель завершить процес навчання.</span><span class="sxs-lookup"><span data-stu-id="de2fb-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="de2fb-116">Він створюється окремо для кожної моделі, незалежно від того, чи була робота моделі успішною, чи ні.</span><span class="sxs-lookup"><span data-stu-id="de2fb-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="de2fb-117">Перегляд звіту про зручність використання вхідних даних</span><span class="sxs-lookup"><span data-stu-id="de2fb-117">View the input data usability report</span></span>

<span data-ttu-id="de2fb-118">Після завершення кроку навчання готової моделі перегляньте звіт:</span><span class="sxs-lookup"><span data-stu-id="de2fb-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="de2fb-119">Виберіть три крапки поруч із назвою моделі та виберіть **Звіт про зручність використання вхідних даних**.</span><span class="sxs-lookup"><span data-stu-id="de2fb-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="de2fb-120">Виберіть стан моделі, виберіть **Відобразити звіт про зручність використання вхідних даних** на бічній панелі.</span><span class="sxs-lookup"><span data-stu-id="de2fb-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="de2fb-121">Виберіть одну з моделей у списку, а тоді виберіть **Звіт про зручність використання вхідних даних** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="de2fb-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="de2fb-122">Відкрийте сторінку із результатами моделі, а тоді виберіть **Звіт про зручність використання вхідних даних** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="de2fb-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="de2fb-123">Відомості, що містяться у звіті про зручність використання даних</span><span class="sxs-lookup"><span data-stu-id="de2fb-123">Information in the input data usability report</span></span>

<span data-ttu-id="de2fb-124">Зазначені нижче стовпці у звіті містять відомості, що є корисними для покращення даних для моделі.</span><span class="sxs-lookup"><span data-stu-id="de2fb-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Приклад звіту про зручність використання вхідних даних, де показано таблицю із помилками, попередженнями та рекомендаціями.":::

- <span data-ttu-id="de2fb-126">Ім'я: змістовне ім'я помилки, попередження або рекомендації.</span><span class="sxs-lookup"><span data-stu-id="de2fb-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="de2fb-127">Крок: фаза роботи моделі, навчання або оцінювання, до якої відносяться відомості.</span><span class="sxs-lookup"><span data-stu-id="de2fb-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="de2fb-128">Стан: серйозність відомостей (помилка, попередження, рекомендація).</span><span class="sxs-lookup"><span data-stu-id="de2fb-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="de2fb-129">Ім'я стовпця: стовпець у сутності, який потрібно змінити для підвищення продуктивності моделі.</span><span class="sxs-lookup"><span data-stu-id="de2fb-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="de2fb-130">Ім'я сутності: ім’я сутності, яку потрібно змінити для підвищення продуктивності моделі.</span><span class="sxs-lookup"><span data-stu-id="de2fb-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="de2fb-131">Подробиці: докладні відомості про помилку, попередження або рекомендацію.</span><span class="sxs-lookup"><span data-stu-id="de2fb-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="de2fb-132">Оновлення прогнозу</span><span class="sxs-lookup"><span data-stu-id="de2fb-132">Refresh a prediction</span></span>

<span data-ttu-id="de2fb-133">Прогнози автоматично оновлюватимуться за тим самим [розкладом, за яким оновлюються дані](system.md#schedule-tab), що налаштовується в параметрах.</span><span class="sxs-lookup"><span data-stu-id="de2fb-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="de2fb-134">Їх можна також оновити вручну.</span><span class="sxs-lookup"><span data-stu-id="de2fb-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="de2fb-135">Перейдіть до розділу **Аналітика** > **Прогнози** і виберіть вкладку **Мої прогнози**.</span><span class="sxs-lookup"><span data-stu-id="de2fb-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="de2fb-136">Виберіть вертикальні три крапки поруч із прогнозом, який потрібно оновити.</span><span class="sxs-lookup"><span data-stu-id="de2fb-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="de2fb-137">Виберіть **Оновити**.</span><span class="sxs-lookup"><span data-stu-id="de2fb-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="de2fb-138">Видалення прогнозу</span><span class="sxs-lookup"><span data-stu-id="de2fb-138">Delete a prediction</span></span>

<span data-ttu-id="de2fb-139">Видалення прогнозу також видаляє його вихідну сутність.</span><span class="sxs-lookup"><span data-stu-id="de2fb-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="de2fb-140">Перейдіть до розділу **Аналітика** > **Прогнози** і виберіть вкладку **Мої прогнози**.</span><span class="sxs-lookup"><span data-stu-id="de2fb-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="de2fb-141">Виберіть вертикальні три крапки поруч із прогнозом, який потрібно видалити.</span><span class="sxs-lookup"><span data-stu-id="de2fb-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="de2fb-142">Виберіть **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="de2fb-142">Select **Delete**.</span></span>
