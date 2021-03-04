---
title: Створення середовищ і керування ними
description: Дізнайтесь, як зареєструватися на послугу та як керувати середовищами.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270137"
---
# <a name="manage-environments"></a><span data-ttu-id="a64cf-103">Керування середовищами</span><span class="sxs-lookup"><span data-stu-id="a64cf-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a64cf-104">У цій статті описується процедура створення нової організації та способи надання середовища.</span><span class="sxs-lookup"><span data-stu-id="a64cf-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="a64cf-105">Реєстрація та створення організації</span><span class="sxs-lookup"><span data-stu-id="a64cf-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="a64cf-106">Перейдіть на веб-сайт [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="a64cf-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="a64cf-107">Виберіть **Почати роботу**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="a64cf-108">Виберіть бажаний сценарій реєстрації та виберіть відповідне посилання.</span><span class="sxs-lookup"><span data-stu-id="a64cf-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="a64cf-109">Прийміть умови та положення й натисніть **Продовжити**, щоб розпочати створення організації.</span><span class="sxs-lookup"><span data-stu-id="a64cf-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="a64cf-110">Після створення середовища вас буде переспрямовано на [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="a64cf-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="a64cf-111">Скористайтеся демонстраційним середовищем для ознайомлення з програмою або створіть нове середовище, виконавши кроки, описані в наступному розділі.</span><span class="sxs-lookup"><span data-stu-id="a64cf-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="a64cf-112">Визначивши настройки середовища, виберіть **Створити**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="a64cf-113">Ви будете зареєстровані після успішного створення середовища.</span><span class="sxs-lookup"><span data-stu-id="a64cf-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="a64cf-114">Створення середовища в наявній організації</span><span class="sxs-lookup"><span data-stu-id="a64cf-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="a64cf-115">Існує два способи створити нове середовище.</span><span class="sxs-lookup"><span data-stu-id="a64cf-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="a64cf-116">Можна вказати цілком нову конфігурацію або ж скопіювати деякі параметри конфігурації з наявного середовища.</span><span class="sxs-lookup"><span data-stu-id="a64cf-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="a64cf-117">Щоб створити середовище, виконайте наведені нижче кроки.</span><span class="sxs-lookup"><span data-stu-id="a64cf-117">To create an environment:</span></span>

1. <span data-ttu-id="a64cf-118">Виберіть засіб вибору **Середовище** в заголовку програми.</span><span class="sxs-lookup"><span data-stu-id="a64cf-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="a64cf-119">Виберіть **Створити**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a64cf-120">![Параметри середовища](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="a64cf-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="a64cf-121">У діалоговому вікні **Створення нового середовища** виберіть **Створити середовище**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="a64cf-122">Якщо потрібно [скопіювати дані з поточного середовища](#additional-considerations-for-copy-configuration-preview), виберіть **Копіювати з наявного середовища**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="a64cf-123">Відобразиться список усіх наявних середовищ в організації, з яких можна скопіювати дані.</span><span class="sxs-lookup"><span data-stu-id="a64cf-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="a64cf-124">Вкажіть нижчезазначені відомості.</span><span class="sxs-lookup"><span data-stu-id="a64cf-124">Provide the following details:</span></span>
   - <span data-ttu-id="a64cf-125">**Ім'я**: ім'я цього середовища.</span><span class="sxs-lookup"><span data-stu-id="a64cf-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="a64cf-126">Це поле буде вже заповнено, якщо ви копіювали з наявного середовища, але ці значення можна змінити.</span><span class="sxs-lookup"><span data-stu-id="a64cf-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="a64cf-127">**Регіон**: розташування, в якому розгорнуто та розміщено службу.</span><span class="sxs-lookup"><span data-stu-id="a64cf-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="a64cf-128">**Тип**: виберіть тип середовища, яке потрібно створити: виробниче або ізольоване.</span><span class="sxs-lookup"><span data-stu-id="a64cf-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="a64cf-129">Також можна вибрати **Додаткові параметри**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="a64cf-130">**Зберегти всі дані до**: указує місце, в якому потрібно зберігати вихідні дані, створені з Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a64cf-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="a64cf-131">Доступні два варіанти: **Сховище Customer Insights** (Azure Data Lake, яким керує робоча команда Customer Insights) і **Azure Data Lake Storage Gen2** (ваше власне сховище Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="a64cf-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="a64cf-132">За замовчуванням вибрано сховище Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a64cf-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a64cf-133">При збереженні даних у Azure Data Lake Storage ви погоджуєтеся з тим, що дані будуть передаватися до відповідного географічного розташування для облікового запису сховища Azure та зберігатися в ньому. Це географічне розташування може відрізнятися від розташування, в якому зберігаються дані, передані до Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a64cf-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="a64cf-134">Дізнайтеся докладніше в центрі безпеки та конфіденційності Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a64cf-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="a64cf-135">Наразі оброблені сутності завжди зберігаються у керованому озері даних Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a64cf-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="a64cf-136">Ми підтримуємо тільки облікові записи сховища Azure Data Lake Gen2 для того самого регіону Azure, який ви вибрали під час створення середовища.</span><span class="sxs-lookup"><span data-stu-id="a64cf-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="a64cf-137">Ми підтримуємо лише облікові записи сховища, в яких ввімкнена функція ієрархічного простору імен (HNS) Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="a64cf-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="a64cf-138">Для параметру Azure Data Lake Storage Gen2 можна вибрати між використанням параметра на основі ресурсів або на основі підписки.</span><span class="sxs-lookup"><span data-stu-id="a64cf-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="a64cf-139">Для отримання додаткових відомостей див. розділ [Підключення аналізу аудиторії до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a64cf-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="a64cf-140">**Ім'я контейнера** не можна змінити, воно матиме значення «customerinsights».</span><span class="sxs-lookup"><span data-stu-id="a64cf-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="a64cf-141">Якщо потрібно використовувати [прогнози](predictions.md) або налаштувати спільний доступ до даних для програм та рішень на основі Microsoft Dataverse, укажіть URL-адресу середовища Microsoft Dataverse в розділі **Налаштування спільного доступу до даних для Microsoft Dataverse та ввімкнення додаткових можливостей**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="a64cf-142">Виберіть **Увімкнути спільний доступ до даних**, щоб надати спільний доступ до вихідних даних Customer Insights, використовуючи службу керованого Data Lake Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a64cf-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="a64cf-143">Спільний доступ до даних за допомогою служби керованого Data Lake Microsoft Dataverse наразі не підтримується, якщо ви зберігаєте усі дані у власному Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="a64cf-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="a64cf-144">[Прогнозування відсутнього значення в сутності](predictions.md) наразі не підтримується, якщо увімкнуто спільний доступ до даних за допомогою служби керованого Data Lake Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a64cf-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="a64cf-145">![Параметри конфігурації для ввімкнення спільного доступу до даних за допомогою Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="a64cf-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="a64cf-146">Під час запуску процесів, наприклад, приймання даних або створення сегмента, в обліковому записі сховища, яке було зазначено вище, буде створено відповідні папки.</span><span class="sxs-lookup"><span data-stu-id="a64cf-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="a64cf-147">В залежності від того, який процес ви запускаєте, у відповідних вкладених папках буде створено файли даних і файли model.json.</span><span class="sxs-lookup"><span data-stu-id="a64cf-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="a64cf-148">У разі створення кількох середовищ Customer Insights і вибору збереження вихідних сутностей з цих середовищ у вашому обліковому записі сховища, окремі папки створюватимуться для кожного середовища з ci_ <environmentid> в контейнері.</span><span class="sxs-lookup"><span data-stu-id="a64cf-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="a64cf-149">Додаткові відомості про копіювання конфігурації (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="a64cf-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="a64cf-150">Буде скопійовано параметри конфігурації, перелічені нижче.</span><span class="sxs-lookup"><span data-stu-id="a64cf-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="a64cf-151">Конфігурація функцій</span><span class="sxs-lookup"><span data-stu-id="a64cf-151">Feature configurations</span></span>
- <span data-ttu-id="a64cf-152">Прийняті/імпортовані джерела даних</span><span class="sxs-lookup"><span data-stu-id="a64cf-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="a64cf-153">Конфігурація уніфікації даних (зіставлення, відповідність, злиття)</span><span class="sxs-lookup"><span data-stu-id="a64cf-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="a64cf-154">Сегменти</span><span class="sxs-lookup"><span data-stu-id="a64cf-154">Segments</span></span>
- <span data-ttu-id="a64cf-155">Вимірювання</span><span class="sxs-lookup"><span data-stu-id="a64cf-155">Measures</span></span>
- <span data-ttu-id="a64cf-156">Зв'язки</span><span class="sxs-lookup"><span data-stu-id="a64cf-156">Relationships</span></span>
- <span data-ttu-id="a64cf-157">Справи</span><span class="sxs-lookup"><span data-stu-id="a64cf-157">Activities</span></span>
- <span data-ttu-id="a64cf-158">Покажчик «Пошук і фільтрація»</span><span class="sxs-lookup"><span data-stu-id="a64cf-158">Search & filter Index</span></span>
- <span data-ttu-id="a64cf-159">Експортні напрямки</span><span class="sxs-lookup"><span data-stu-id="a64cf-159">Export destinations</span></span>
- <span data-ttu-id="a64cf-160">Заплановане оновлення</span><span class="sxs-lookup"><span data-stu-id="a64cf-160">Scheduled refresh</span></span>
- <span data-ttu-id="a64cf-161">Збагачення</span><span class="sxs-lookup"><span data-stu-id="a64cf-161">Enrichments</span></span>
- <span data-ttu-id="a64cf-162">Керування моделлю</span><span class="sxs-lookup"><span data-stu-id="a64cf-162">Model management</span></span>
- <span data-ttu-id="a64cf-163">Призначення ролей</span><span class="sxs-lookup"><span data-stu-id="a64cf-163">Role assignments</span></span>

<span data-ttu-id="a64cf-164">Перелічені нижче параметри скопійовано *не* буде.</span><span class="sxs-lookup"><span data-stu-id="a64cf-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="a64cf-165">Профілі клієнтів.</span><span class="sxs-lookup"><span data-stu-id="a64cf-165">Customer profiles.</span></span>
- <span data-ttu-id="a64cf-166">Облікові дані джерела даних.</span><span class="sxs-lookup"><span data-stu-id="a64cf-166">Data source credentials.</span></span> <span data-ttu-id="a64cf-167">Доведеться надати облікові дані для кожного джерела даних та оновити джерела даних вручну.</span><span class="sxs-lookup"><span data-stu-id="a64cf-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="a64cf-168">Джерела даних з папки Common Data Model та озера, керованого Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a64cf-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="a64cf-169">Ви повинні створити ці джерела даних вручну під іменами, ідентичними іменам у вихідному середовищі.</span><span class="sxs-lookup"><span data-stu-id="a64cf-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="a64cf-170">Після копіювання середовища відобразиться підтвердження стосовно того, що було створено нове середовище.</span><span class="sxs-lookup"><span data-stu-id="a64cf-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="a64cf-171">Виберіть **Перейти до джерел даних**, щоб переглянути список джерел даних.</span><span class="sxs-lookup"><span data-stu-id="a64cf-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="a64cf-172">Усі джерела даних відображатимуться зі станом **Відсутні облікові дані**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="a64cf-173">Відредагуйте джерела даних і укажіть облікові дані, щоб оновити їх.</span><span class="sxs-lookup"><span data-stu-id="a64cf-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a64cf-174">![Джерела даних скопійовано](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="a64cf-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="a64cf-175">Після оновлення джерел даних перейдіть до розділу **Дані** > **Уніфікувати**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="a64cf-176">Тут ви знайдете настройки з вихідного середовища.</span><span class="sxs-lookup"><span data-stu-id="a64cf-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="a64cf-177">Відредагуйте їх відповідно до потреб або виберіть **Виконати**, щоб почати процес уніфікації даних і створити єдину сутність клієнта.</span><span class="sxs-lookup"><span data-stu-id="a64cf-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="a64cf-178">Після завершення уніфікації даних виберіть **Показники** та **Сегменти**, щоб оновити їх також.</span><span class="sxs-lookup"><span data-stu-id="a64cf-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="a64cf-179">Редагувати наявне середовище</span><span class="sxs-lookup"><span data-stu-id="a64cf-179">Edit an existing environment</span></span>

<span data-ttu-id="a64cf-180">Ви можете редагувати деякі відомості наявних середовищ.</span><span class="sxs-lookup"><span data-stu-id="a64cf-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="a64cf-181">Виберіть засіб вибору **Середовище** в заголовку програми.</span><span class="sxs-lookup"><span data-stu-id="a64cf-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="a64cf-182">Виберіть піктограму **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="a64cf-183">У полі **Редагування середовища** можна вказати нове **Коротке ім'я** середовища, але не можна змінити **Регіон** або **Тип**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="a64cf-184">Якщо середовище настроєно для збереження даних у Azure Data Lake Storage Gen2, ви можете оновити **Ключ бізнес-партнера**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="a64cf-185">Проте не можна змінити **Ім’я облікового запису** або **Контейнера**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="a64cf-186">Крім того, можна змінити підключення ключа облікового запису на підключення на основі ресурсу або підписки.</span><span class="sxs-lookup"><span data-stu-id="a64cf-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="a64cf-187">Після оновлення не можна повернутися до ключа облікового запису.</span><span class="sxs-lookup"><span data-stu-id="a64cf-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="a64cf-188">Для отримання додаткових відомостей див. розділ [Підключення аналізу аудиторії до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a64cf-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="a64cf-189">Під час оновлення з'єднання інформацію про **Контейнер** змінити не можна.</span><span class="sxs-lookup"><span data-stu-id="a64cf-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="a64cf-190">Скидання існуючого середовища</span><span class="sxs-lookup"><span data-stu-id="a64cf-190">Reset an existing environment</span></span>

<span data-ttu-id="a64cf-191">Якщо ви адміністратор, можна скинути середовище в пустий стан, щоб видалити всі конфігурації та прийняті дані.</span><span class="sxs-lookup"><span data-stu-id="a64cf-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="a64cf-192">Виберіть засіб вибору **Середовище** в заголовку програми.</span><span class="sxs-lookup"><span data-stu-id="a64cf-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="a64cf-193">Виберіть середовище, яке потрібно скинути, і виберіть три крапки **...**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="a64cf-194">Виберіть пункт **Скинути**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="a64cf-195">Щоб підтвердити видалення, введіть ім'я середовища та натисніть кнопку **Скинути**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="a64cf-196">Видалення наявного середовища (доступне лише для адміністраторів)</span><span class="sxs-lookup"><span data-stu-id="a64cf-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="a64cf-197">Якщо ви адміністратор, ви можете видалити середовище, яке адмініструєте.</span><span class="sxs-lookup"><span data-stu-id="a64cf-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="a64cf-198">Виберіть засіб вибору **Середовище** в заголовку програми.</span><span class="sxs-lookup"><span data-stu-id="a64cf-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="a64cf-199">Виберіть середовище, яке потрібно скинути, і виберіть три крапки **...**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="a64cf-200">Виберіть пункт **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="a64cf-201">Щоб підтвердити видалення, введіть ім'я середовища, потім виберіть **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="a64cf-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]