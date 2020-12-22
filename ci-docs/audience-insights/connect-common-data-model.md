---
title: Підключення даних Common Data Model до облікового запису Azure Data Lake
description: Робота з даними Common Data Model за допомогою Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643483"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="3cb54-103">Підключіться до папки Common Data Model, використовуючи обліковий запис Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="3cb54-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="3cb54-104">У цій статті наведено відомості про інтеграцію даних з папки Common Data Model даних за допомогою облікового запису Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="3cb54-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="3cb54-105">Важливі міркування</span><span class="sxs-lookup"><span data-stu-id="3cb54-105">Important considerations</span></span>

- <span data-ttu-id="3cb54-106">Дані у вашому Azure Data Lake мають відповідати стандарту Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="3cb54-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="3cb54-107">На цей час інші формати не підтримуються.</span><span class="sxs-lookup"><span data-stu-id="3cb54-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="3cb54-108">Приймання даних підтримує винятково облікові записи сховища Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="3cb54-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="3cb54-109">Облікові записи сховища Azure Data Lake Gen1 не можна використовувати для прийому даних.</span><span class="sxs-lookup"><span data-stu-id="3cb54-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="3cb54-110">Щоб пройти автентифікацію з допомогою принципалу служби Azure, переконайтеся, що вона налаштована у вашому клієнті.</span><span class="sxs-lookup"><span data-stu-id="3cb54-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="3cb54-111">Для отримання додаткових відомостей див. розділ [Підключення аналізу аудиторії до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="3cb54-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="3cb54-112">Azure Data Lake, до якого вам потрібно підключитися і з якого потрібно прийняти дані, має бути в тій самій області Azure, що й середовище Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3cb54-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="3cb54-113">Підключення до спільної папки Common Data Model з озера даних в іншій області Azure не підтримується.</span><span class="sxs-lookup"><span data-stu-id="3cb54-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="3cb54-114">Щоб дізнатися область Azure середовища, перейдіть до меню **Адміністратор** > **Система** > **Відомості** у аналізі аудиторії.</span><span class="sxs-lookup"><span data-stu-id="3cb54-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="3cb54-115">Дані, що зберігаються в онлайнових службах, можуть зберігатися в іншому розташуванні, ніж у тому, де дані обробляються або зберігаються у Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3cb54-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="3cb54-116">Імпортуючи дані, що зберігаються в онлайнових службах, або встановлюючи підключення до таких даних, ви надаєте згоду, що дані можуть передаватися до Dynamics 365 Customer Insights і зберігатися в цій службі.  [Дізнайтесь більше в Центрі безпеки та конфіденційності Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="3cb54-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="3cb54-117">Підключитися до папки Common Data Model</span><span class="sxs-lookup"><span data-stu-id="3cb54-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="3cb54-118">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="3cb54-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="3cb54-119">Виберіть **Додати джерело даних**.</span><span class="sxs-lookup"><span data-stu-id="3cb54-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="3cb54-120">Виберіть **Підключення до папки Common Data Model**, введіть **Ім’я** для джерела даних і натисніть кнопку **Далі**.</span><span class="sxs-lookup"><span data-stu-id="3cb54-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="3cb54-121">Для автентифікації можна вибрати між використанням параметра на основі ресурсів або на основі передплати.</span><span class="sxs-lookup"><span data-stu-id="3cb54-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="3cb54-122">Для отримання додаткових відомостей див. розділ [Підключення аналізу аудиторії до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="3cb54-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="3cb54-123">Введіть дані про **Контейнер** і натисніть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="3cb54-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3cb54-124">![Діалогове вікно для введення даних для з’єднання для Azure Data Lake](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="3cb54-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="3cb54-125">У діалозі **Вибір папки Common Data Model** виберіть файл model.json, з якого потрібно імпортувати дані, і натисніть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="3cb54-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="3cb54-126">Будь-який файл model.json, пов’язаний із іншим джерелом даних у середовищі, не буде відображатися в списку.</span><span class="sxs-lookup"><span data-stu-id="3cb54-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="3cb54-127">Ви отримаєте список доступних сутностей у вибраному файлі model.json.</span><span class="sxs-lookup"><span data-stu-id="3cb54-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="3cb54-128">Ви можете переглянути список та вибрати з нього доступні сутності, а потім натиснути кнопку **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="3cb54-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="3cb54-129">Всі вибрані сутності прийматимуться з нового джерела даних.</span><span class="sxs-lookup"><span data-stu-id="3cb54-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3cb54-130">![Діалогове вікно, в якому відображається список сутностей з файлу model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="3cb54-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="3cb54-131">Укажіть, які сутності даних мають увімкнути профілювання даних і натисніть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="3cb54-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="3cb54-132">Профілювання даних дає змогу використовувати засоби аналітики та інші можливості.</span><span class="sxs-lookup"><span data-stu-id="3cb54-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="3cb54-133">Можна вибрати всю сутність, яка вибере всі атрибути сутності, або вибрати певні атрибути для цього вибору.</span><span class="sxs-lookup"><span data-stu-id="3cb54-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="3cb54-134">За замовчуванням для профілювання даних не ввімкнуто жодної сутності.</span><span class="sxs-lookup"><span data-stu-id="3cb54-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3cb54-135">![Діалогове вікно з відповідним профілюванням даних](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="3cb54-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="3cb54-136">Після збереження вашого вибору відкриється сторінка **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="3cb54-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="3cb54-137">Тепер ви маєте побачити підключення до папки Common Data Model у вигляді джерела даних.</span><span class="sxs-lookup"><span data-stu-id="3cb54-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="3cb54-138">Файл model.json може зв'язуватися лише з одним джерелом даних в тому самому середовищі.</span><span class="sxs-lookup"><span data-stu-id="3cb54-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="3cb54-139">Проте такий самий файл model.json може використовуватися для джерел даних у різних середовищах.</span><span class="sxs-lookup"><span data-stu-id="3cb54-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="3cb54-140">Редагування джерела даних папки Common Data Model</span><span class="sxs-lookup"><span data-stu-id="3cb54-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="3cb54-141">Можна оновити ключ доступу для облікового запису сховища, який містить папку Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="3cb54-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="3cb54-142">Крім того, можна змінити файл model.json.</span><span class="sxs-lookup"><span data-stu-id="3cb54-142">You may also change the model.json file.</span></span> <span data-ttu-id="3cb54-143">Щоб підключитися до іншого контейнера зі свого облікового запису сховища або змінити ім’я облікового запису, [створіть нове підключення до джерела даних](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="3cb54-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="3cb54-144">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="3cb54-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="3cb54-145">Виберіть три крапки поряд із джерелом даних, яке ви бажаєте оновити.</span><span class="sxs-lookup"><span data-stu-id="3cb54-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="3cb54-146">Виберіть зі списку параметр **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="3cb54-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="3cb54-147">Додатково оновіть **Ключ доступу** й виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="3cb54-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Діалогове вікно для редагування й оновлення ключа доступу для існуючого джерела даних](media/edit-access-key.png)

5. <span data-ttu-id="3cb54-149">Крім того, можна змінити підключення ключа облікового запису на підключення на основі ресурсу або передплати.</span><span class="sxs-lookup"><span data-stu-id="3cb54-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="3cb54-150">Для отримання додаткових відомостей див. розділ [Підключення аналізу аудиторії до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="3cb54-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="3cb54-151">Під час оновлення з'єднання інформацію про **Контейнер** змінити не можна.</span><span class="sxs-lookup"><span data-stu-id="3cb54-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3cb54-152">![Діалогове вікно для введення даних для з’єднання для Azure Data Lake](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="3cb54-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="3cb54-153">Додатково виберіть інший файл model.json із іншого набору сутностей у контейнері.</span><span class="sxs-lookup"><span data-stu-id="3cb54-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="3cb54-154">Крім того, можна вибрати додаткові сутності для прийому.</span><span class="sxs-lookup"><span data-stu-id="3cb54-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="3cb54-155">Також можна в разі відсутності залежностей видалити будь-які вже вибрані сутності.</span><span class="sxs-lookup"><span data-stu-id="3cb54-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="3cb54-156">Якщо в існуючому файлі model.json і наборі сутностей є залежності, ви побачите повідомлення про помилку. При цьому вибрати інший файл model.json неможливо.</span><span class="sxs-lookup"><span data-stu-id="3cb54-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="3cb54-157">Видаліть ці залежності до змінення файлу model.json або створіть нове джерело даних за допомогою файлу model.json, яке ви бажаєте використовувати, щоб уникнути видалення залежностей.</span><span class="sxs-lookup"><span data-stu-id="3cb54-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="3cb54-158">Крім того, можна вибрати додаткові атрибути або сутності, які дають змогу виконувати профілювання даних або вимикати вже вибрані.</span><span class="sxs-lookup"><span data-stu-id="3cb54-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
