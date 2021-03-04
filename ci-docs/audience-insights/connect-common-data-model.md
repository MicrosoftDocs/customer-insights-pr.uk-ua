---
title: Підключення даних Common Data Model до облікового запису Azure Data Lake
description: Робота з даними Common Data Model за допомогою Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267885"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="6043b-103">Підключіться до папки Common Data Model, використовуючи обліковий запис Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="6043b-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="6043b-104">У цій статті наведено відомості про інтеграцію даних з папки Common Data Model даних за допомогою облікового запису Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="6043b-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="6043b-105">Важливі міркування</span><span class="sxs-lookup"><span data-stu-id="6043b-105">Important considerations</span></span>

- <span data-ttu-id="6043b-106">Дані у вашому Azure Data Lake мають відповідати стандарту Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="6043b-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="6043b-107">На цей час інші формати не підтримуються.</span><span class="sxs-lookup"><span data-stu-id="6043b-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="6043b-108">Приймання даних підтримує винятково облікові записи сховища Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="6043b-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="6043b-109">Облікові записи сховища Azure Data Lake Gen1 не можна використовувати для прийому даних.</span><span class="sxs-lookup"><span data-stu-id="6043b-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="6043b-110">Щоб пройти автентифікацію з допомогою принципалу служби Azure, переконайтеся, що вона налаштована у вашому клієнті.</span><span class="sxs-lookup"><span data-stu-id="6043b-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="6043b-111">Для отримання додаткових відомостей див. розділ [Підключення аналізу аудиторії до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="6043b-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="6043b-112">Azure Data Lake, до якого вам потрібно підключитися і з якого потрібно прийняти дані, має бути в тій самій області Azure, що й середовище Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6043b-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="6043b-113">Підключення до спільної папки Common Data Model з озера даних в іншій області Azure не підтримується.</span><span class="sxs-lookup"><span data-stu-id="6043b-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="6043b-114">Щоб дізнатися область Azure середовища, перейдіть до меню **Адміністратор** > **Система** > **Відомості** у аналізі аудиторії.</span><span class="sxs-lookup"><span data-stu-id="6043b-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="6043b-115">Дані, що зберігаються в онлайнових службах, можуть зберігатися в іншому розташуванні, ніж у тому, де дані обробляються або зберігаються у Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6043b-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="6043b-116">Імпортуючи дані, що зберігаються в онлайнових службах, або встановлюючи підключення до таких даних, ви надаєте згоду, що дані можуть передаватися до Dynamics 365 Customer Insights і зберігатися в цій службі.  [Дізнайтесь більше в Центрі безпеки та конфіденційності Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="6043b-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="6043b-117">Підключитися до папки Common Data Model</span><span class="sxs-lookup"><span data-stu-id="6043b-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="6043b-118">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="6043b-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="6043b-119">Виберіть **Додати джерело даних**.</span><span class="sxs-lookup"><span data-stu-id="6043b-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="6043b-120">Виберіть **Підключення до папки Common Data Model**, введіть **Ім’я** для джерела даних і натисніть кнопку **Далі**.</span><span class="sxs-lookup"><span data-stu-id="6043b-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="6043b-121">Рекомендації щодо імен:</span><span class="sxs-lookup"><span data-stu-id="6043b-121">Name guidelines:</span></span> 
   - <span data-ttu-id="6043b-122">Починайте з букви.</span><span class="sxs-lookup"><span data-stu-id="6043b-122">Start with a letter.</span></span>
   - <span data-ttu-id="6043b-123">Використовуйте лише букви та цифри.</span><span class="sxs-lookup"><span data-stu-id="6043b-123">Use letters and numbers only.</span></span> <span data-ttu-id="6043b-124">Не можна використовувати спеціальні символи та пробіли.</span><span class="sxs-lookup"><span data-stu-id="6043b-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="6043b-125">Використовуйте від 3 до 64 символів.</span><span class="sxs-lookup"><span data-stu-id="6043b-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="6043b-126">Для автентифікації можна вибрати між використанням параметра на основі ресурсів або на основі передплати.</span><span class="sxs-lookup"><span data-stu-id="6043b-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="6043b-127">Для отримання додаткових відомостей див. розділ [Підключення аналізу аудиторії до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="6043b-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="6043b-128">Введіть дані про **Контейнер** і натисніть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="6043b-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6043b-129">![Діалогове вікно для введення нових відомостей про підключення для Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="6043b-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="6043b-130">Щоб підключитися та створити джерело даних, ви повинні мати одну із зазначених нижче ролей для контейнера або облікового запису сховища, згаданого вище.</span><span class="sxs-lookup"><span data-stu-id="6043b-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="6043b-131">Зчитувач даних BLOB-об'єктів сховища</span><span class="sxs-lookup"><span data-stu-id="6043b-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="6043b-132">Відповідальний для BLOB-об'єктів сховища</span><span class="sxs-lookup"><span data-stu-id="6043b-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="6043b-133">Постачальник даних BLOB-об’єктів сховища</span><span class="sxs-lookup"><span data-stu-id="6043b-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="6043b-134">У діалозі **Вибір папки Common Data Model** виберіть файл model.json або manifest.json, з якого потрібно імпортувати дані, і натисніть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="6043b-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="6043b-135">Будь-який файл model.json або manifest.json, пов’язаний із іншим джерелом даних у середовищі, не відображатиметься в списку.</span><span class="sxs-lookup"><span data-stu-id="6043b-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="6043b-136">Ви отримаєте список доступних сутностей у вибраному файлі model.json або manifest.json.</span><span class="sxs-lookup"><span data-stu-id="6043b-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="6043b-137">Ви можете переглянути список та вибрати з нього доступні сутності, а потім натиснути кнопку **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="6043b-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="6043b-138">Всі вибрані сутності прийматимуться з нового джерела даних.</span><span class="sxs-lookup"><span data-stu-id="6043b-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6043b-139">![Діалогове вікно, в якому відображається список сутностей з файлу model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="6043b-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="6043b-140">Укажіть, які сутності даних мають увімкнути профілювання даних і натисніть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="6043b-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="6043b-141">Профілювання даних дає змогу використовувати засоби аналітики та інші можливості.</span><span class="sxs-lookup"><span data-stu-id="6043b-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="6043b-142">Можна вибрати всю сутність, яка вибере всі атрибути сутності, або вибрати певні атрибути для цього вибору.</span><span class="sxs-lookup"><span data-stu-id="6043b-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="6043b-143">За замовчуванням для профілювання даних не ввімкнуто жодної сутності.</span><span class="sxs-lookup"><span data-stu-id="6043b-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6043b-144">![Діалогове вікно з відповідним профілюванням даних](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="6043b-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="6043b-145">Після збереження вашого вибору відкриється сторінка **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="6043b-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="6043b-146">Тепер ви маєте побачити підключення до папки Common Data Model у вигляді джерела даних.</span><span class="sxs-lookup"><span data-stu-id="6043b-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="6043b-147">Файл model.json або manifest.json може зв'язуватися лише з одним джерелом даних в тому самому середовищі.</span><span class="sxs-lookup"><span data-stu-id="6043b-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="6043b-148">Проте такий самий файл model.json або manifest.json може використовуватися для джерел даних у різних середовищах.</span><span class="sxs-lookup"><span data-stu-id="6043b-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="6043b-149">Редагування джерела даних папки Common Data Model</span><span class="sxs-lookup"><span data-stu-id="6043b-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="6043b-150">Можна оновити ключ доступу для облікового запису сховища, який містить папку Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="6043b-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="6043b-151">Ви також можете змінити файл model.json або manifest.json.</span><span class="sxs-lookup"><span data-stu-id="6043b-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="6043b-152">Щоб підключитися до іншого контейнера зі свого облікового запису сховища або змінити ім’я облікового запису, [створіть нове підключення до джерела даних](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="6043b-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="6043b-153">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="6043b-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6043b-154">Виберіть три крапки поряд із джерелом даних, яке ви бажаєте оновити.</span><span class="sxs-lookup"><span data-stu-id="6043b-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="6043b-155">Виберіть зі списку параметр **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="6043b-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="6043b-156">Додатково оновіть **Ключ доступу** й виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="6043b-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Діалогове вікно для редагування й оновлення ключа доступу для існуючого джерела даних](media/edit-access-key.png)

5. <span data-ttu-id="6043b-158">Крім того, можна змінити підключення ключа облікового запису на підключення на основі ресурсу або передплати.</span><span class="sxs-lookup"><span data-stu-id="6043b-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="6043b-159">Для отримання додаткових відомостей див. розділ [Підключення аналізу аудиторії до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="6043b-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="6043b-160">Під час оновлення з'єднання інформацію про **Контейнер** змінити не можна.</span><span class="sxs-lookup"><span data-stu-id="6043b-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Діалогове вікно для введення відомостей про підключення для Azure Data Lake до наявного облікового запису сховища](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="6043b-162">Щоб підключитися та створити джерело даних, ви повинні мати одну із зазначених нижче ролей для контейнера або облікового запису сховища, згаданого вище.</span><span class="sxs-lookup"><span data-stu-id="6043b-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="6043b-163">Зчитувач даних BLOB-об'єктів сховища</span><span class="sxs-lookup"><span data-stu-id="6043b-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="6043b-164">Відповідальний для BLOB-об'єктів сховища</span><span class="sxs-lookup"><span data-stu-id="6043b-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="6043b-165">Постачальник даних BLOB-об’єктів сховища</span><span class="sxs-lookup"><span data-stu-id="6043b-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="6043b-166">За бажанням виберіть інший файл model.json або manifest.json із іншим набором сутностей з контейнера.</span><span class="sxs-lookup"><span data-stu-id="6043b-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="6043b-167">Крім того, можна вибрати додаткові сутності для прийому.</span><span class="sxs-lookup"><span data-stu-id="6043b-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="6043b-168">Також можна в разі відсутності залежностей видалити будь-які вже вибрані сутності.</span><span class="sxs-lookup"><span data-stu-id="6043b-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6043b-169">Якщо існують залежності від наявного файлу model.json або manifest.json і набору сутностей, ви побачите повідомлення про помилку та не зможете вибрати інший файл model.json або manifest.json.</span><span class="sxs-lookup"><span data-stu-id="6043b-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="6043b-170">Усуньте ці залежності перед тим, як змінювати файл model.json або manifest.json, або ж створіть нове джерело даних з файлом model.json або manifest.json, який потрібно використовувати, щоб уникнути усунення залежностей.</span><span class="sxs-lookup"><span data-stu-id="6043b-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="6043b-171">Крім того, можна вибрати додаткові атрибути або сутності, які дають змогу виконувати профілювання даних або вимикати вже вибрані.</span><span class="sxs-lookup"><span data-stu-id="6043b-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]