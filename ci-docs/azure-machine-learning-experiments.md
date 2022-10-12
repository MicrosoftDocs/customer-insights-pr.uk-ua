---
title: Використання моделей на основі машинного навчання Azure
description: Використання моделей на основі машинного навчання Azure у Dynamics 365 Customer Insights.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609856"
---
# <a name="use-azure-machine-learning-based-models"></a>Використання моделей на основі машинного навчання Azure

Уніфіковані дані у програмі Dynamics 365 Customer Insights є джерелом для створення моделей машинного навчання, які можуть створювати додаткові аналітичні огляди бізнес-компаній. Customer Insights інтегровано зі службами машинного навчання Azure для можливості використання власних настроюваних моделей.

## <a name="prerequisites"></a>Вимоги

- Доступ до Customer Insights.
- Чинна передплата Azure Enterprise.
- [Уніфіковані профілі клієнтів](data-unification.md)
- [Експорт сутності до сховища BLOB-даних Azure](export-azure-blob-storage.md) налаштовано

## <a name="set-up-azure-machine-learning-workspace"></a>Налаштування робочої області машинного навчання Azure

1. Див. розділ [Створення робочої області «Машинне навчання Azure»](/azure/machine-learning/concept-workspace#-create-a-workspace) для різних параметрів створення робочої області. Для кращої продуктивності створіть робочу область в області Azure, яка географічно розташована в найближчому до вас середовищі Customer Insights.

1. Ввійдіть до робочої області через [Студію машинного навчання Azure](https://ml.azure.com/). Існує кілька [способів взаємодії](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) з робочою областю.

## <a name="work-with-azure-machine-learning-designer"></a>Робота з конструктором машинного навчання Azure

Azure машинне навчання Designer надає візуальне полотно, куди можна перетягувати набори даних і модулі. Пакетна воронка продажів, створена в конструкторі, може бути інтегрована у Customer Insights у разі відповідного налаштування. 

## <a name="working-with-azure-machine-learning-sdk"></a>Робота з SDK машинного навчання Azure

Спеціалісти з обробки даних і розробники штучного інтелекту використовують [SDK машинного навчання Azure](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py), щоб створити робочі цикли машинного навчання. Наразі моделі, що навчаються за допомогою SDK, не можна інтегрувати безпосередньо з Customer Insights. Для інтеграції з Customer Insights потрібен конвеєр пакетного виводу, що використовує цю модель.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Вимоги пакетної воронки продажів для інтеграції з Customer Insights

### <a name="dataset-configuration"></a>Конфігурація набору даних

Створіть набори даних, щоб використовувати дані сутності з Customer Insights для конвеєра пакетних висновків. Зареєструйте ці набори даних у робочій області. Наразі підтримуються лише [табличні набори даних](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) у форматі. csv. Параметризуйте набори даних, які відповідають даним сутності як параметру конвеєра.

- Параметри набору даних у конструкторі

  У конструкторі відкрийте параметр **Вибрати стовпці в наборі даних** і натисніть **Встановити як параметр воронки продажів** , де потрібно надати ім’я параметру.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Параметризація набору даних у конструкторі.":::

- Параметр набору даних у SDK (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Воронка продажів пакетного виведення
  
- У конструкторі використовуйте навчальний конвеєр для створення або оновлення трубопроводу умовиводу. Наразі підтримуються лише воронки продажів пакетного виведення.

- Використовуючи SDK, опублікуйте конвеєр до кінцевої точки. Наразі Customer Insights інтегрується з воронкою продажів за замовчуванням у кінцевій точці воронки продажів у робочій області машинного навчання.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Імпорт даних воронки продажів у Customer Insights

- Дизайнер надає [модуль даних експорту](/azure/machine-learning/algorithm-module-reference/export-data), що дає змогу експортувати воронку продажів до сховища даних Azure. Зараз модуль має використовувати тип сховища даних **Сховище BLOB-даних Azure** і парметризувати **Сховище даних** і пов’язаний **Перелік дій**. Customer Insights переписує обидва параметри під час виконання воронки продажів зі сховищем даних і переліком дій, доступних для продукту.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="Налаштування експортування модулю даних.":::

- Під час написання виводу умовиводу за допомогою коду завантажте вихід на шлях у зареєстрованому *сховищі* даних у робочій області. Якщо перелік даних і сховище даних параметризовані у воронці продажів, Customer insights зможе зчитати та імпортувати виведення. Наразі підтримується єдиний табличний вивід у форматі csv. Перелік дій має містити каталог і ім'я файлу.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]