---
title: Експерименти машинного навчання Azure
description: Використання моделей на основі машинного навчання Azure у Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668805"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="d49cd-103">Використання моделей на основі машинного навчання Azure</span><span class="sxs-lookup"><span data-stu-id="d49cd-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="d49cd-104">Уніфіковані дані у програмі Dynamics 365 Customer Insights є джерелом для створення моделей машинного навчання, які можуть створювати додаткові аналітичні огляди бізнес-компаній.</span><span class="sxs-lookup"><span data-stu-id="d49cd-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="d49cd-105">Customer Insights інтегрується з Machine Learning Studio (classic) і машинним навчанням Azure для використання власних користувацьких моделей.</span><span class="sxs-lookup"><span data-stu-id="d49cd-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="d49cd-106">Ознайомтеся з [експериментами студії машинного навчання (класична версія)](machine-learning-studio-experiments.md), де наведено експерименти, створені у студії машинного навчання (класичний варіант).</span><span class="sxs-lookup"><span data-stu-id="d49cd-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d49cd-107">Вимоги</span><span class="sxs-lookup"><span data-stu-id="d49cd-107">Prerequisites</span></span>

- <span data-ttu-id="d49cd-108">Доступ до Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d49cd-108">Access to Customer Insights</span></span>
- <span data-ttu-id="d49cd-109">Чинна передплата Azure Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d49cd-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="d49cd-110">Уніфіковані профілі клієнтів</span><span class="sxs-lookup"><span data-stu-id="d49cd-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="d49cd-111">[Експорт сутності до сховища BLOB-даних Azure](export-azure-blob-storage.md) налаштовано</span><span class="sxs-lookup"><span data-stu-id="d49cd-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="d49cd-112">Налаштування робочої області машинного навчання Azure</span><span class="sxs-lookup"><span data-stu-id="d49cd-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="d49cd-113">Див. розділ [Створення робочої області «Машинне навчання Azure»](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) для різних параметрів створення робочої області.</span><span class="sxs-lookup"><span data-stu-id="d49cd-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="d49cd-114">Для кращої продуктивності створіть робочу область в області Azure, яка географічно розташована в найближчому до вас середовищі Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d49cd-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="d49cd-115">Ввійдіть до робочої області через [Студію машинного навчання Azure](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="d49cd-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="d49cd-116">Існує кілька [способів взаємодії](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) з робочою областю.</span><span class="sxs-lookup"><span data-stu-id="d49cd-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="d49cd-117">Робота з конструктором машинного навчання Azure</span><span class="sxs-lookup"><span data-stu-id="d49cd-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="d49cd-118">Конструктор машинного навчання надає наочне полотно, в якому можна перетягувати набори даних і модулі, так само як у студії машинного навчання Azure (класична версія).</span><span class="sxs-lookup"><span data-stu-id="d49cd-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="d49cd-119">Пакетна воронка продажів, створена в конструкторі, може бути інтегрована у Customer Insights у разі відповідного налаштування.</span><span class="sxs-lookup"><span data-stu-id="d49cd-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="d49cd-120">Робота з SDK машинного навчання Azure</span><span class="sxs-lookup"><span data-stu-id="d49cd-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="d49cd-121">Спеціалісти з обробки даних і розробники штучного інтелекту використовують [SDK машинного навчання Azure](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true), щоб створити робочі цикли машинного навчання.</span><span class="sxs-lookup"><span data-stu-id="d49cd-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="d49cd-122">Наразі моделі, що навчаються за допомогою SDK, не можна інтегрувати безпосередньо з Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d49cd-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="d49cd-123">Для інтеграції з Customer Insights потрібен конвеєр пакетного виводу, що використовує цю модель.</span><span class="sxs-lookup"><span data-stu-id="d49cd-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="d49cd-124">Вимоги пакетної воронки продажів для інтеграції з Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d49cd-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="d49cd-125">Конфігурація набору даних</span><span class="sxs-lookup"><span data-stu-id="d49cd-125">Dataset Configuration</span></span>

<span data-ttu-id="d49cd-126">Необхідно створити набори даних для використання даних сутності з Customer Insights до конвеєра пакетного виводу.</span><span class="sxs-lookup"><span data-stu-id="d49cd-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="d49cd-127">Ці набори даних потрібно зареєструвати в робочій області.</span><span class="sxs-lookup"><span data-stu-id="d49cd-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="d49cd-128">Наразі підтримуються лише [табличні набори даних](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) у форматі. csv.</span><span class="sxs-lookup"><span data-stu-id="d49cd-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="d49cd-129">Набори даних, які відповідають даним сутності, потрібно парметризувати як параметр воронки продажів.</span><span class="sxs-lookup"><span data-stu-id="d49cd-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="d49cd-130">Параметри набору даних у конструкторі</span><span class="sxs-lookup"><span data-stu-id="d49cd-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="d49cd-131">У конструкторі відкрийте параметр **Вибрати стовпці в наборі даних** і натисніть **Встановити як параметр воронки продажів** , де потрібно надати ім’я параметру.</span><span class="sxs-lookup"><span data-stu-id="d49cd-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="d49cd-132">![Параметризація набору даних у конструкторі](media/intelligence-designer-dataset-parameters.png "Параметризація набору даних у конструкторі")</span><span class="sxs-lookup"><span data-stu-id="d49cd-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="d49cd-133">Параметр набору даних у SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="d49cd-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="d49cd-134">Воронка продажів пакетного виведення</span><span class="sxs-lookup"><span data-stu-id="d49cd-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="d49cd-135">У конструкторі для створення або оновлення воронки продажів виведення можна використовувати тренувальну воронку продажів.</span><span class="sxs-lookup"><span data-stu-id="d49cd-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="d49cd-136">Наразі підтримуються лише воронки продажів пакетного виведення.</span><span class="sxs-lookup"><span data-stu-id="d49cd-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="d49cd-137">За допомогою SDK можна опублікувати воронки продажів до кінцевої точки.</span><span class="sxs-lookup"><span data-stu-id="d49cd-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="d49cd-138">Наразі Customer Insights інтегрується з воронкою продажів за замовчуванням у кінцевій точці воронки продажів у робочій області машинного навчання.</span><span class="sxs-lookup"><span data-stu-id="d49cd-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="d49cd-139">Імпорт даних воронки продажів у Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d49cd-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="d49cd-140">Дизайнер надає [модуль даних експорту](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data), що дає змогу експортувати воронку продажів до сховища даних Azure.</span><span class="sxs-lookup"><span data-stu-id="d49cd-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="d49cd-141">Зараз модуль має використовувати тип сховища даних **Сховище BLOB-даних Azure** і парметризувати **Сховище даних** і пов’язаний **Перелік дій**.</span><span class="sxs-lookup"><span data-stu-id="d49cd-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="d49cd-142">Customer Insights переписує обидва параметри під час виконання воронки продажів зі сховищем даних і переліком дій, доступних для продукту.</span><span class="sxs-lookup"><span data-stu-id="d49cd-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d49cd-143">![Налаштування експортування модулю даних](media/intelligence-designer-importdata.png "Налаштування експортування модулю даних")</span><span class="sxs-lookup"><span data-stu-id="d49cd-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="d49cd-144">Під час написання виведення з використанням коду ви можете завантажити виведення до переліку дій у *зареєстрованому сховищі даних* робочої області.</span><span class="sxs-lookup"><span data-stu-id="d49cd-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="d49cd-145">Якщо перелік даних і сховище даних параметризовані у воронці продажів, Customer insights зможе зчитати та імпортувати виведення.</span><span class="sxs-lookup"><span data-stu-id="d49cd-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="d49cd-146">Наразі підтримується єдиний табличний вивід у форматі csv.</span><span class="sxs-lookup"><span data-stu-id="d49cd-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="d49cd-147">Перелік дій має містити каталог і ім'я файлу.</span><span class="sxs-lookup"><span data-stu-id="d49cd-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```
