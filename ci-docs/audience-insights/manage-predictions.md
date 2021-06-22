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
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095762"
---
# <a name="manage-predictions"></a><span data-ttu-id="25da2-103">Керування прогнозами</span><span class="sxs-lookup"><span data-stu-id="25da2-103">Manage predictions</span></span>

<span data-ttu-id="25da2-104">У цій статті розглядаються деякі завдання, спільні для більшості сценаріїв прогнозування.</span><span class="sxs-lookup"><span data-stu-id="25da2-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="25da2-105">Усунення проблем з помилкою прогнозів</span><span class="sxs-lookup"><span data-stu-id="25da2-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="25da2-106">Перейдіть до розділу **Аналітика** > **Прогнози** і виберіть вкладку **Мої прогнози**.</span><span class="sxs-lookup"><span data-stu-id="25da2-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="25da2-107">Виберіть вертикальні три крапки поруч із прогнозом, для яких потрібно переглянути журнал помилок.</span><span class="sxs-lookup"><span data-stu-id="25da2-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="25da2-108">Натисніть **Журнали**.</span><span class="sxs-lookup"><span data-stu-id="25da2-108">Select **Logs**.</span></span>

1. <span data-ttu-id="25da2-109">Перегляньте усі помилки.</span><span class="sxs-lookup"><span data-stu-id="25da2-109">Review all the errors.</span></span> <span data-ttu-id="25da2-110">Може виникати кілька типів помилок, і у них описуються умови, що призвели до помилки.</span><span class="sxs-lookup"><span data-stu-id="25da2-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="25da2-111">Наприклад, помилка, яка сповіщає, що недостатньо даних для точного прогнозування зазвичай вирішується, якщо завантажити додаткові дані до Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="25da2-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="25da2-112">Звіт про зручність використання вхідних даних</span><span class="sxs-lookup"><span data-stu-id="25da2-112">Input data usability report</span></span>

<span data-ttu-id="25da2-113">У звіті про зручність використання вхідних даних надається узагальнене подання помилок і попереджень, які можуть виникати при роботі готових прогнозів.</span><span class="sxs-lookup"><span data-stu-id="25da2-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="25da2-114">Він також дає рекомендації щодо поліпшення продуктивності моделі.</span><span class="sxs-lookup"><span data-stu-id="25da2-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="25da2-115">Звіт стає доступним після того, як модель завершить процес навчання.</span><span class="sxs-lookup"><span data-stu-id="25da2-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="25da2-116">Він створюється окремо для кожної моделі, незалежно від того, чи була робота моделі успішною, чи ні.</span><span class="sxs-lookup"><span data-stu-id="25da2-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="25da2-117">Наразі ця функція працює лише для моделі відтоку транзакцій.</span><span class="sxs-lookup"><span data-stu-id="25da2-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="25da2-118">Перегляд звіту про зручність використання вхідних даних</span><span class="sxs-lookup"><span data-stu-id="25da2-118">View the input data usability report</span></span>

<span data-ttu-id="25da2-119">Після завершення кроку навчання готової моделі перегляньте звіт:</span><span class="sxs-lookup"><span data-stu-id="25da2-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="25da2-120">Виберіть три крапки поруч із назвою моделі та виберіть **Звіт про зручність використання вхідних даних**.</span><span class="sxs-lookup"><span data-stu-id="25da2-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="25da2-121">Виберіть стан моделі, виберіть **Відобразити звіт про зручність використання вхідних даних** на бічній панелі.</span><span class="sxs-lookup"><span data-stu-id="25da2-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="25da2-122">Виберіть одну з моделей у списку, а тоді виберіть **Звіт про зручність використання вхідних даних** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="25da2-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="25da2-123">Відкрийте сторінку із результатами моделі, а тоді виберіть **Звіт про зручність використання вхідних даних** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="25da2-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="25da2-124">Відомості, що містяться у звіті про зручність використання даних</span><span class="sxs-lookup"><span data-stu-id="25da2-124">Information in the input data usability report</span></span>

<span data-ttu-id="25da2-125">Зазначені нижче стовпці у звіті містять відомості, що є корисними для покращення даних для моделі.</span><span class="sxs-lookup"><span data-stu-id="25da2-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Приклад звіту про зручність використання вхідних даних, де показано таблицю із помилками, попередженнями та рекомендаціями.":::

- <span data-ttu-id="25da2-127">Ім'я: змістовне ім'я помилки, попередження або рекомендації.</span><span class="sxs-lookup"><span data-stu-id="25da2-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="25da2-128">Крок: фаза роботи моделі, навчання або оцінювання, до якої відносяться відомості.</span><span class="sxs-lookup"><span data-stu-id="25da2-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="25da2-129">Стан: серйозність відомостей (помилка, попередження, рекомендація).</span><span class="sxs-lookup"><span data-stu-id="25da2-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="25da2-130">Ім'я стовпця: стовпець у сутності, який потрібно змінити для підвищення продуктивності моделі.</span><span class="sxs-lookup"><span data-stu-id="25da2-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="25da2-131">Ім'я сутності: ім’я сутності, яку потрібно змінити для підвищення продуктивності моделі.</span><span class="sxs-lookup"><span data-stu-id="25da2-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="25da2-132">Подробиці: докладні відомості про помилку, попередження або рекомендацію.</span><span class="sxs-lookup"><span data-stu-id="25da2-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="25da2-133">Оновлення прогнозу</span><span class="sxs-lookup"><span data-stu-id="25da2-133">Refresh a prediction</span></span>

<span data-ttu-id="25da2-134">Прогнози автоматично оновлюватимуться за тим самим [розкладом, за яким оновлюються дані](system.md#schedule-tab), що налаштовується в параметрах.</span><span class="sxs-lookup"><span data-stu-id="25da2-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="25da2-135">Їх можна також оновити вручну.</span><span class="sxs-lookup"><span data-stu-id="25da2-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="25da2-136">Перейдіть до розділу **Аналітика** > **Прогнози** і виберіть вкладку **Мої прогнози**.</span><span class="sxs-lookup"><span data-stu-id="25da2-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="25da2-137">Виберіть вертикальні три крапки поруч із прогнозом, який потрібно оновити.</span><span class="sxs-lookup"><span data-stu-id="25da2-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="25da2-138">Виберіть **Оновити**.</span><span class="sxs-lookup"><span data-stu-id="25da2-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="25da2-139">Видалення прогнозу</span><span class="sxs-lookup"><span data-stu-id="25da2-139">Delete a prediction</span></span>

<span data-ttu-id="25da2-140">Видалення прогнозу також видаляє його вихідну сутність.</span><span class="sxs-lookup"><span data-stu-id="25da2-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="25da2-141">Перейдіть до розділу **Аналітика** > **Прогнози** і виберіть вкладку **Мої прогнози**.</span><span class="sxs-lookup"><span data-stu-id="25da2-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="25da2-142">Виберіть вертикальні три крапки поруч із прогнозом, який потрібно видалити.</span><span class="sxs-lookup"><span data-stu-id="25da2-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="25da2-143">Виберіть **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="25da2-143">Select **Delete**.</span></span>
