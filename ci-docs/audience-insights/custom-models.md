---
title: Спеціальні моделі машинного навчання | Microsoft Docs
description: Робота з настроюваними моделями з машинного навчання Azure у Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668928"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="34741-103">Спеціальні моделі машинного навчання</span><span class="sxs-lookup"><span data-stu-id="34741-103">Custom machine learning models</span></span>

<span data-ttu-id="34741-104">**Аналітика** > **Спеціальні моделі** дає вам змогу керувати робочими циклами на основі моделей Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="34741-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="34741-105">Робочі цикли допомагають вибрати дані, для яких потрібно створити аналітичні огляди та зіставити результати з уніфікованими даними про клієнта.</span><span class="sxs-lookup"><span data-stu-id="34741-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="34741-106">Для отримання додаткових відомостей про створення настроюваних моделей ML див. розділ [Використання моделей на основі машинного навчання Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="34741-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="34741-107">Відповідальний ШІ</span><span class="sxs-lookup"><span data-stu-id="34741-107">Responsible AI</span></span>

<span data-ttu-id="34741-108">Прогнози надають можливості для створення кращого досвіду клієнтів, поліпшення бізнес-ресурсів та потоків доходів.</span><span class="sxs-lookup"><span data-stu-id="34741-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="34741-109">Ми настійно рекомендуємо збалансувати цінність вашого прогнозу з його впливом та упередженнями, які можуть бути введені в етичному порядку.</span><span class="sxs-lookup"><span data-stu-id="34741-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="34741-110">Дізнайтеся більше про те, як корпорація Microsoft [звертається до відповідального ШІ](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="34741-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="34741-111">Також можна дізнатися про [техніки та процеси для відповідального машинного навчання](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml), що стосуються машинного навчання Azure.</span><span class="sxs-lookup"><span data-stu-id="34741-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="34741-112">Вимоги</span><span class="sxs-lookup"><span data-stu-id="34741-112">Prerequisites</span></span>

- <span data-ttu-id="34741-113">Наразі ця функція підтримує веб-служби, опубліковані за допомогою [студії машинного навчання (класична версія)](https://studio.azureml.net) і [пакетної воронки продажів машинного навчання Azure](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="34741-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="34741-114">Щоб скористатися цією функцією, потрібно мати обліковий запис сховища Azure Data Lake Gen2, пов’язаний із інсталяцією студії Azure.</span><span class="sxs-lookup"><span data-stu-id="34741-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="34741-115">Докладніше див. у розділі [Створення облікового запису сховища Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="34741-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="34741-116">Додати новий робочий цикл</span><span class="sxs-lookup"><span data-stu-id="34741-116">Add a new workflow</span></span>

1. <span data-ttu-id="34741-117">Перейдіть до розділу **Аналітика** > **Спеціальні моделі** та виберіть елемент **Новий робочий цикл**.</span><span class="sxs-lookup"><span data-stu-id="34741-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="34741-118">Задайте для своєї настроюваної моделі ім’я, яке легко впізнати, в полі **Ім’я**.</span><span class="sxs-lookup"><span data-stu-id="34741-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="34741-119">![Знімок екрана області «Новий робочий цикл»](media/new-workflowv2.png "Знімок екрана області «Новий робочий цикл»")</span><span class="sxs-lookup"><span data-stu-id="34741-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="34741-120">Виберіть організацію, яка містить веб-службу в розділі **Клієнт, що містить веб-службу**.</span><span class="sxs-lookup"><span data-stu-id="34741-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="34741-121">Якщо передплата на Azure Machine Learning знаходиться в іншому клієнті, ніж Customer Insights, виберіть **Вхід** зі своїми обліковими даними для вибраної організації.</span><span class="sxs-lookup"><span data-stu-id="34741-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="34741-122">Виберіть **Робочі області**, зв'язані з веб-службою.</span><span class="sxs-lookup"><span data-stu-id="34741-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="34741-123">У списку є два розділи, один для машинного навчання Azure v1 (Студія машинного навчання (класична версія)) і машинного навчання Azure v2 (Машинне навчання Azure).</span><span class="sxs-lookup"><span data-stu-id="34741-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="34741-124">Якщо ви не впевнені, яка робоча область правильна для вашої веб-служби студії машинного навчання (класична версія), натисніть **Будь-яка**.</span><span class="sxs-lookup"><span data-stu-id="34741-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="34741-125">Виберіть веб-службу студії машинного навчання або воронку продажів машинного навчання Azure у розкривному меню **Веб-служби, що містять вашу модель**.</span><span class="sxs-lookup"><span data-stu-id="34741-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="34741-126">Потім виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="34741-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="34741-127">Докладніше про [публікацію веб-служби в студії машинного навчання (класична версія)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="34741-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="34741-128">Докладніше про [публікацію воронки продажів у машинному навчанні Azure за допомогою конструктора](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) або [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="34741-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="34741-129">Ваша воронка продажів має бути опублікована в [кінцевій точці воронки продажів](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="34741-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="34741-130">Для кожного **Введення веб-служби** виберіть відповідну **Сутність** з аналізу аудиторії і натисніть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="34741-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="34741-131">![Налаштуйте робочий цикл](media/intelligence-screen2-updated.png "Налаштуйте робочий цикл")</span><span class="sxs-lookup"><span data-stu-id="34741-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="34741-132">В етапі **Параметри виводу моделі** встановіть такі властивості:</span><span class="sxs-lookup"><span data-stu-id="34741-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="34741-133">Студія машинного навчання (класична версія)</span><span class="sxs-lookup"><span data-stu-id="34741-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="34741-134">Введіть вивід **Ім'я сутності**, до якого потрібно додати результати виводу веб-служби.</span><span class="sxs-lookup"><span data-stu-id="34741-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="34741-135">Машинне навчання Azure</span><span class="sxs-lookup"><span data-stu-id="34741-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="34741-136">Введіть вивід **Ім'я сутності**, до якого потрібно додати результати виводу воронки продажів.</span><span class="sxs-lookup"><span data-stu-id="34741-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="34741-137">Виберіть у розкривному меню **Назву параметру сховища вихідних даних**.</span><span class="sxs-lookup"><span data-stu-id="34741-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="34741-138">Виберіть у розкривному меню **Назву параметру шляху вихідних даних** вашої воронки пакетних продажів.</span><span class="sxs-lookup"><span data-stu-id="34741-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="34741-139">![Область параметрів виводу моделі](media/intelligence-screen3-outputparameters.png "Область параметрів виводу моделі")</span><span class="sxs-lookup"><span data-stu-id="34741-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="34741-140">Виберіть відповідний атрибут із розкривного списку **Ідентифікатор клієнта в результатах**, що ідентифікує клієнтів і натисніть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="34741-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="34741-141">![Пов’язати результати з областю даних клієнта](media/intelligence-screen4-relatetocustomer.png "Пов’язати результати з областю даних клієнта")</span><span class="sxs-lookup"><span data-stu-id="34741-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="34741-142">Ви побачите екран **Робочий цикл збережено** з докладною інформацією про цей робочий цикл.</span><span class="sxs-lookup"><span data-stu-id="34741-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="34741-143">Якщо було настроєно робочий цикл для воронки продажів машинного навчання Azure, аналіз аудиторії буде додано до робочої області, що містить воронку продажів.</span><span class="sxs-lookup"><span data-stu-id="34741-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="34741-144">Аналізи аудиторій отримають роль **Співавтор** в робочій області Azure.</span><span class="sxs-lookup"><span data-stu-id="34741-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="34741-145">Виберіть **Готово**.</span><span class="sxs-lookup"><span data-stu-id="34741-145">Select **Done**.</span></span>

1. <span data-ttu-id="34741-146">Тепер робочий цикл можна виконати на сторінці **Настроювані моделі**.</span><span class="sxs-lookup"><span data-stu-id="34741-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="34741-147">Редагуйте робочий цикл</span><span class="sxs-lookup"><span data-stu-id="34741-147">Edit a workflow</span></span>

1. <span data-ttu-id="34741-148">На сторінці **Спеціальні моделі** виберіть вертикальні три крапки в стовпці **Дії** поруч із попередньо створеним робочим циклом, а тоді виберіть **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="34741-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="34741-149">Впізнаване ім'я робочого циклу можна оновити в полі **Коротке ім'я**, але не можна змінити настроєну веб-службу або воронку продажів.</span><span class="sxs-lookup"><span data-stu-id="34741-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="34741-150">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="34741-150">Select **Next**.</span></span>

1. <span data-ttu-id="34741-151">Для кожного **Введення веб-служби** можна оновити відповідну **Сутність** з аналізу аудиторії.</span><span class="sxs-lookup"><span data-stu-id="34741-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="34741-152">Потім виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="34741-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="34741-153">В етапі **Параметри виводу моделі** встановіть такі властивості:</span><span class="sxs-lookup"><span data-stu-id="34741-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="34741-154">Студія машинного навчання (класична версія)</span><span class="sxs-lookup"><span data-stu-id="34741-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="34741-155">Введіть вивід **Ім'я сутності**, до якого потрібно додати результати виводу веб-служби.</span><span class="sxs-lookup"><span data-stu-id="34741-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="34741-156">Машинне навчання Azure</span><span class="sxs-lookup"><span data-stu-id="34741-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="34741-157">Введіть вивід **Ім'я сутності**, до якого потрібно додати результати виводу воронки продажів.</span><span class="sxs-lookup"><span data-stu-id="34741-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="34741-158">Виберіть **Ім’я параметру сховища вихідних даних** для вашої тестової воронки продажів.</span><span class="sxs-lookup"><span data-stu-id="34741-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="34741-159">Виберіть значення **Ім'я параметру шляху виводу** для вашої тестової воронки продажів.</span><span class="sxs-lookup"><span data-stu-id="34741-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="34741-160">Виберіть відповідний атрибут із розкривного списку **Ідентифікатор клієнта в результатах**, що ідентифікує клієнтів і натисніть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="34741-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="34741-161">Необхідно вибрати атрибут у виводі зі значеннями, подібними до стовпця «Ідентифікатор клієнта» сутності клієнта.</span><span class="sxs-lookup"><span data-stu-id="34741-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="34741-162">Якщо у наборі даних відсутній такий стовпець, виберіть атрибут, який дає змогу однозначно ідентифікувати рядок.</span><span class="sxs-lookup"><span data-stu-id="34741-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="34741-163">Виконання робочого циклу</span><span class="sxs-lookup"><span data-stu-id="34741-163">Run a workflow</span></span>

1. <span data-ttu-id="34741-164">На сторінці **Спеціальні моделі** виберіть вертикальні три крапки в стовпці **Дії** поруч із попередньо створеним робочим циклом.</span><span class="sxs-lookup"><span data-stu-id="34741-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="34741-165">Виберіть **Запустити**.</span><span class="sxs-lookup"><span data-stu-id="34741-165">Select **Run**.</span></span>

<span data-ttu-id="34741-166">Цей робочий цикл також запускається автоматично з кожним запланованим оновленням.</span><span class="sxs-lookup"><span data-stu-id="34741-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="34741-167">Дізнайтеся докладніше про [настроювання запланованих оновлень](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="34741-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="34741-168">Видаліть робочий цикл</span><span class="sxs-lookup"><span data-stu-id="34741-168">Delete a workflow</span></span>

1. <span data-ttu-id="34741-169">На сторінці **Спеціальні моделі** виберіть вертикальні три крапки в стовпці **Дії** поруч із попередньо створеним робочим циклом.</span><span class="sxs-lookup"><span data-stu-id="34741-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="34741-170">Натисніть кнопку **Видалити** та підтвердьте видалення.</span><span class="sxs-lookup"><span data-stu-id="34741-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="34741-171">Робочий цикл буде видалено.</span><span class="sxs-lookup"><span data-stu-id="34741-171">Your workflow will be deleted.</span></span> <span data-ttu-id="34741-172">[Сутність](entities.md), створена під час створення робочого циклу, залишається, її можна переглянути на сторінці **Сутності**.</span><span class="sxs-lookup"><span data-stu-id="34741-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
