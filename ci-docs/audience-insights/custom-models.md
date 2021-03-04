---
title: Спеціальні моделі машинного навчання | Microsoft Docs
description: Робота з настроюваними моделями з машинного навчання Azure у Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267259"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="2744b-103">Спеціальні моделі машинного навчання</span><span class="sxs-lookup"><span data-stu-id="2744b-103">Custom machine learning models</span></span>

<span data-ttu-id="2744b-104">**Аналітика** > **Спеціальні моделі** дає вам змогу керувати робочими циклами на основі моделей Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="2744b-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="2744b-105">Робочі цикли допомагають вибрати дані, для яких потрібно створити аналітичні огляди та зіставити результати з уніфікованими даними про клієнта.</span><span class="sxs-lookup"><span data-stu-id="2744b-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="2744b-106">Для отримання додаткових відомостей про створення настроюваних моделей ML див. розділ [Використання моделей на основі машинного навчання Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="2744b-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="2744b-107">Відповідальний ШІ</span><span class="sxs-lookup"><span data-stu-id="2744b-107">Responsible AI</span></span>

<span data-ttu-id="2744b-108">Прогнози надають можливості для створення кращого досвіду клієнтів, поліпшення бізнес-ресурсів та потоків доходів.</span><span class="sxs-lookup"><span data-stu-id="2744b-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="2744b-109">Ми настійно рекомендуємо збалансувати цінність вашого прогнозу з його впливом та упередженнями, які можуть бути введені в етичному порядку.</span><span class="sxs-lookup"><span data-stu-id="2744b-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="2744b-110">Дізнайтеся більше про те, як корпорація Microsoft [звертається до відповідального ШІ](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="2744b-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="2744b-111">Також можна дізнатися про [техніки та процеси для відповідального машинного навчання](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml), що стосуються машинного навчання Azure.</span><span class="sxs-lookup"><span data-stu-id="2744b-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2744b-112">Вимоги</span><span class="sxs-lookup"><span data-stu-id="2744b-112">Prerequisites</span></span>

- <span data-ttu-id="2744b-113">Наразі ця функція підтримує веб-служби, опубліковані за допомогою [студії машинного навчання (класична версія)](https://studio.azureml.net) і [пакетної воронки продажів машинного навчання Azure](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="2744b-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="2744b-114">Щоб скористатися цією функцією, потрібно мати обліковий запис сховища Azure Data Lake Gen2, пов’язаний із інсталяцією студії Azure.</span><span class="sxs-lookup"><span data-stu-id="2744b-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="2744b-115">Докладніше див. у розділі [Створення облікового запису сховища Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="2744b-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="2744b-116">Додати новий робочий цикл</span><span class="sxs-lookup"><span data-stu-id="2744b-116">Add a new workflow</span></span>

1. <span data-ttu-id="2744b-117">Перейдіть до розділу **Аналітика** > **Спеціальні моделі** та виберіть елемент **Новий робочий цикл**.</span><span class="sxs-lookup"><span data-stu-id="2744b-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="2744b-118">Задайте для своєї настроюваної моделі ім’я, яке легко впізнати, в полі **Ім’я**.</span><span class="sxs-lookup"><span data-stu-id="2744b-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2744b-119">![Знімок екрана області «Новий робочий цикл»](media/new-workflowv2.png "Знімок екрана області «Новий робочий цикл»")</span><span class="sxs-lookup"><span data-stu-id="2744b-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="2744b-120">Виберіть організацію, яка містить веб-службу в розділі **Клієнт, що містить веб-службу**.</span><span class="sxs-lookup"><span data-stu-id="2744b-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="2744b-121">Якщо передплата на Azure Machine Learning знаходиться в іншому клієнті, ніж Customer Insights, виберіть **Вхід** зі своїми обліковими даними для вибраної організації.</span><span class="sxs-lookup"><span data-stu-id="2744b-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="2744b-122">Виберіть **Робочі області**, зв'язані з веб-службою.</span><span class="sxs-lookup"><span data-stu-id="2744b-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="2744b-123">У списку є два розділи, один для машинного навчання Azure v1 (Студія машинного навчання (класична версія)) і машинного навчання Azure v2 (Машинне навчання Azure).</span><span class="sxs-lookup"><span data-stu-id="2744b-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="2744b-124">Якщо ви не впевнені, яка робоча область правильна для вашої веб-служби студії машинного навчання (класична версія), натисніть **Будь-яка**.</span><span class="sxs-lookup"><span data-stu-id="2744b-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="2744b-125">Виберіть веб-службу студії машинного навчання або воронку продажів машинного навчання Azure у розкривному меню **Веб-служби, що містять вашу модель**.</span><span class="sxs-lookup"><span data-stu-id="2744b-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="2744b-126">Потім виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="2744b-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="2744b-127">Докладніше про [публікацію веб-служби в студії машинного навчання (класична версія)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="2744b-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="2744b-128">Докладніше про [публікацію воронки продажів у машинному навчанні Azure за допомогою конструктора](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) або [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="2744b-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="2744b-129">Ваша воронка продажів має бути опублікована в [кінцевій точці воронки продажів](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="2744b-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="2744b-130">Для кожного **Введення веб-служби** виберіть відповідну **Сутність** з аналізу аудиторії і натисніть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="2744b-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="2744b-131">Робочий цикл настроюваної моделі застосовуватиме евристику для зіставлення полів вводу веб-служби із атрибутами сутності на основі імені та типу даних поля.</span><span class="sxs-lookup"><span data-stu-id="2744b-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="2744b-132">З'явиться повідомлення про помилку, якщо поле веб-служби не вдасться зіставити із сутністю.</span><span class="sxs-lookup"><span data-stu-id="2744b-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2744b-133">![Налаштуйте робочий цикл](media/intelligence-screen2-updated.png "Налаштуйте робочий цикл")</span><span class="sxs-lookup"><span data-stu-id="2744b-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="2744b-134">В етапі **Параметри виводу моделі** встановіть такі властивості:</span><span class="sxs-lookup"><span data-stu-id="2744b-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="2744b-135">Студія машинного навчання (класична версія)</span><span class="sxs-lookup"><span data-stu-id="2744b-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="2744b-136">Введіть вивід **Ім'я сутності**, до якого потрібно додати результати виводу веб-служби.</span><span class="sxs-lookup"><span data-stu-id="2744b-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="2744b-137">Машинне навчання Azure</span><span class="sxs-lookup"><span data-stu-id="2744b-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="2744b-138">Введіть вивід **Ім'я сутності**, до якого потрібно додати результати виводу воронки продажів.</span><span class="sxs-lookup"><span data-stu-id="2744b-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="2744b-139">Виберіть у розкривному меню **Назву параметру сховища вихідних даних**.</span><span class="sxs-lookup"><span data-stu-id="2744b-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="2744b-140">Виберіть у розкривному меню **Назву параметру шляху вихідних даних** вашої воронки пакетних продажів.</span><span class="sxs-lookup"><span data-stu-id="2744b-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="2744b-141">![Область параметрів виводу моделі](media/intelligence-screen3-outputparameters.png "Область параметрів виводу моделі")</span><span class="sxs-lookup"><span data-stu-id="2744b-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="2744b-142">Виберіть відповідний атрибут із розкривного списку **Ідентифікатор клієнта в результатах**, що ідентифікує клієнтів і натисніть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="2744b-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2744b-143">![Пов’язати результати з областю даних клієнта](media/intelligence-screen4-relatetocustomer.png "Пов’язати результати з областю даних клієнта")</span><span class="sxs-lookup"><span data-stu-id="2744b-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="2744b-144">Ви побачите екран **Робочий цикл збережено** з докладною інформацією про цей робочий цикл.</span><span class="sxs-lookup"><span data-stu-id="2744b-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="2744b-145">Якщо було настроєно робочий цикл для воронки продажів машинного навчання Azure, аналіз аудиторії буде додано до робочої області, що містить воронку продажів.</span><span class="sxs-lookup"><span data-stu-id="2744b-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="2744b-146">Аналізи аудиторій отримають роль **Співавтор** в робочій області Azure.</span><span class="sxs-lookup"><span data-stu-id="2744b-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="2744b-147">Виберіть **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2744b-147">Select **Done**.</span></span>

1. <span data-ttu-id="2744b-148">Тепер робочий цикл можна виконати на сторінці **Настроювані моделі**.</span><span class="sxs-lookup"><span data-stu-id="2744b-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="2744b-149">Редагуйте робочий цикл</span><span class="sxs-lookup"><span data-stu-id="2744b-149">Edit a workflow</span></span>

1. <span data-ttu-id="2744b-150">На сторінці **Спеціальні моделі** виберіть вертикальні три крапки в стовпці **Дії** поруч із попередньо створеним робочим циклом, а тоді виберіть **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="2744b-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="2744b-151">Впізнаване ім'я робочого циклу можна оновити в полі **Коротке ім'я**, але не можна змінити настроєну веб-службу або воронку продажів.</span><span class="sxs-lookup"><span data-stu-id="2744b-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="2744b-152">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="2744b-152">Select **Next**.</span></span>

1. <span data-ttu-id="2744b-153">Для кожного **Введення веб-служби** можна оновити відповідну **Сутність** з аналізу аудиторії.</span><span class="sxs-lookup"><span data-stu-id="2744b-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="2744b-154">Потім виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="2744b-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="2744b-155">В етапі **Параметри виводу моделі** встановіть такі властивості:</span><span class="sxs-lookup"><span data-stu-id="2744b-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="2744b-156">Студія машинного навчання (класична версія)</span><span class="sxs-lookup"><span data-stu-id="2744b-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="2744b-157">Введіть вивід **Ім'я сутності**, до якого потрібно додати результати виводу веб-служби.</span><span class="sxs-lookup"><span data-stu-id="2744b-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="2744b-158">Машинне навчання Azure</span><span class="sxs-lookup"><span data-stu-id="2744b-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="2744b-159">Введіть вивід **Ім'я сутності**, до якого потрібно додати результати виводу воронки продажів.</span><span class="sxs-lookup"><span data-stu-id="2744b-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="2744b-160">Виберіть **Ім’я параметру сховища вихідних даних** для вашої тестової воронки продажів.</span><span class="sxs-lookup"><span data-stu-id="2744b-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="2744b-161">Виберіть значення **Ім'я параметру шляху виводу** для вашої тестової воронки продажів.</span><span class="sxs-lookup"><span data-stu-id="2744b-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="2744b-162">Виберіть відповідний атрибут із розкривного списку **Ідентифікатор клієнта в результатах**, що ідентифікує клієнтів і натисніть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="2744b-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="2744b-163">Необхідно вибрати атрибут у виводі зі значеннями, подібними до стовпця «Ідентифікатор клієнта» сутності клієнта.</span><span class="sxs-lookup"><span data-stu-id="2744b-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="2744b-164">Якщо у наборі даних відсутній такий стовпець, виберіть атрибут, який дає змогу однозначно ідентифікувати рядок.</span><span class="sxs-lookup"><span data-stu-id="2744b-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="2744b-165">Виконання робочого циклу</span><span class="sxs-lookup"><span data-stu-id="2744b-165">Run a workflow</span></span>

1. <span data-ttu-id="2744b-166">На сторінці **Спеціальні моделі** виберіть вертикальні три крапки в стовпці **Дії** поруч із попередньо створеним робочим циклом.</span><span class="sxs-lookup"><span data-stu-id="2744b-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="2744b-167">Виберіть **Запустити**.</span><span class="sxs-lookup"><span data-stu-id="2744b-167">Select **Run**.</span></span>

<span data-ttu-id="2744b-168">Цей робочий цикл також запускається автоматично з кожним запланованим оновленням.</span><span class="sxs-lookup"><span data-stu-id="2744b-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="2744b-169">Дізнайтеся докладніше про [настроювання запланованих оновлень](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2744b-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="2744b-170">Видаліть робочий цикл</span><span class="sxs-lookup"><span data-stu-id="2744b-170">Delete a workflow</span></span>

1. <span data-ttu-id="2744b-171">На сторінці **Спеціальні моделі** виберіть вертикальні три крапки в стовпці **Дії** поруч із попередньо створеним робочим циклом.</span><span class="sxs-lookup"><span data-stu-id="2744b-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="2744b-172">Натисніть кнопку **Видалити** та підтвердьте видалення.</span><span class="sxs-lookup"><span data-stu-id="2744b-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="2744b-173">Робочий цикл буде видалено.</span><span class="sxs-lookup"><span data-stu-id="2744b-173">Your workflow will be deleted.</span></span> <span data-ttu-id="2744b-174">[Сутність](entities.md), створена під час створення робочого циклу, залишається, її можна переглянути на сторінці **Сутності**.</span><span class="sxs-lookup"><span data-stu-id="2744b-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]