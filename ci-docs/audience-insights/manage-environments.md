---
title: Створення середовищ і керування ними
description: Дізнайтесь, як зареєструватися на послугу та як керувати середовищами.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644158"
---
# <a name="manage-environments"></a><span data-ttu-id="0347a-103">Керування середовищами</span><span class="sxs-lookup"><span data-stu-id="0347a-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0347a-104">У цій статті описується процедура створення нової організації та способи надання середовища.</span><span class="sxs-lookup"><span data-stu-id="0347a-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="0347a-105">Реєстрація та створення організації</span><span class="sxs-lookup"><span data-stu-id="0347a-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="0347a-106">Перейдіть на веб-сайт [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="0347a-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="0347a-107">Виберіть **Почати роботу**.</span><span class="sxs-lookup"><span data-stu-id="0347a-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="0347a-108">Виберіть бажаний сценарій реєстрації та виберіть відповідне посилання.</span><span class="sxs-lookup"><span data-stu-id="0347a-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="0347a-109">Прийміть умови та положення й натисніть **Продовжити**, щоб розпочати створення організації.</span><span class="sxs-lookup"><span data-stu-id="0347a-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="0347a-110">Після створення середовища вас буде переспрямовано на [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="0347a-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="0347a-111">Скористайтеся демонстраційним середовищем для ознайомлення з програмою або створіть нове середовище, виконавши кроки, описані в наступному розділі.</span><span class="sxs-lookup"><span data-stu-id="0347a-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="0347a-112">Визначивши настройки середовища, виберіть **Створити**.</span><span class="sxs-lookup"><span data-stu-id="0347a-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="0347a-113">Ви будете зареєстровані після успішного створення середовища.</span><span class="sxs-lookup"><span data-stu-id="0347a-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="0347a-114">Створення середовища в наявній організації</span><span class="sxs-lookup"><span data-stu-id="0347a-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="0347a-115">Існує два способи створити нове середовище.</span><span class="sxs-lookup"><span data-stu-id="0347a-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="0347a-116">Можна вказати цілком нову конфігурацію або ж скопіювати деякі параметри конфігурації з наявного середовища.</span><span class="sxs-lookup"><span data-stu-id="0347a-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="0347a-117">Щоб створити середовище, виконайте наведені нижче кроки.</span><span class="sxs-lookup"><span data-stu-id="0347a-117">To create an environment:</span></span>

1. <span data-ttu-id="0347a-118">Виберіть символ **Настройки** в заголовку програми.</span><span class="sxs-lookup"><span data-stu-id="0347a-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="0347a-119">Виберіть **Створити середовище**.</span><span class="sxs-lookup"><span data-stu-id="0347a-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0347a-120">![Параметри середовища](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="0347a-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="0347a-121">У діалоговому вікні **Створення нового середовища** виберіть **Створити середовище**.</span><span class="sxs-lookup"><span data-stu-id="0347a-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="0347a-122">Якщо потрібно [скопіювати дані з поточного середовища](#additional-considerations-for-copy-configuration-preview), виберіть **Копіювати з наявного середовища**.</span><span class="sxs-lookup"><span data-stu-id="0347a-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="0347a-123">Відобразиться список усіх наявних середовищ в організації, з яких можна скопіювати дані.</span><span class="sxs-lookup"><span data-stu-id="0347a-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="0347a-124">Вкажіть нижчезазначені відомості.</span><span class="sxs-lookup"><span data-stu-id="0347a-124">Provide the following details:</span></span>
   - <span data-ttu-id="0347a-125">**Ім'я**: ім'я цього середовища.</span><span class="sxs-lookup"><span data-stu-id="0347a-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="0347a-126">Це поле буде вже заповнено, якщо ви копіювали з наявного середовища, але ці значення можна змінити.</span><span class="sxs-lookup"><span data-stu-id="0347a-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="0347a-127">**Регіон**: розташування, в якому розгорнуто та розміщено службу.</span><span class="sxs-lookup"><span data-stu-id="0347a-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="0347a-128">**Тип**: виберіть тип середовища, яке потрібно створити: виробниче або ізольоване.</span><span class="sxs-lookup"><span data-stu-id="0347a-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="0347a-129">Також можна вибрати **Додаткові параметри**.</span><span class="sxs-lookup"><span data-stu-id="0347a-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="0347a-130">**Зберегти всі дані до**: указує місце, в якому потрібно зберігати вихідні дані, створені з Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0347a-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="0347a-131">Доступні два варіанти: **Сховище Customer Insights** (Azure Data Lake, яким керує робоча команда Customer Insights) і **Azure Data Lake Storage Gen2** (ваше власне сховище Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="0347a-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="0347a-132">За замовчуванням вибрано сховище Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0347a-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0347a-133">При збереженні даних у Azure Data Lake Storage ви погоджуєтеся з тим, що дані будуть передаватися до відповідного географічного розташування для облікового запису сховища Azure та зберігатися в ньому. Це географічне розташування може відрізнятися від розташування, в якому зберігаються дані, передані до Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0347a-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="0347a-134">Дізнайтеся докладніше в центрі безпеки та конфіденційності Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0347a-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="0347a-135">Наразі оброблені сутності завжди зберігаються у керованому озері даних Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0347a-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="0347a-136">Ми підтримуємо тільки облікові записи сховища Azure Data Lake Gen2 для того самого регіону Azure, який ви вибрали під час створення середовища.</span><span class="sxs-lookup"><span data-stu-id="0347a-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="0347a-137">Ми підтримуємо лише облікові записи сховища, в яких ввімкнена функція ієрархічного простору імен (HNS) Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="0347a-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="0347a-138">Для параметру Azure Data Lake Storage Gen2 можна вибрати між використанням параметра на основі ресурсів або на основі підписки.</span><span class="sxs-lookup"><span data-stu-id="0347a-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="0347a-139">Для отримання додаткових відомостей див. розділ [Підключення аналізу аудиторії до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="0347a-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="0347a-140">**Ім'я контейнера** не можна змінити, воно матиме значення «customerinsights».</span><span class="sxs-lookup"><span data-stu-id="0347a-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="0347a-141">Якщо потрібно використати [прогнози](predictions.md), введіть URL-адресу інсталяції Common Data Service у полі **Адреса сервера** в меню **Використання прогнозів**.</span><span class="sxs-lookup"><span data-stu-id="0347a-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="0347a-142">Під час запуску процесів, наприклад, приймання даних або створення сегмента, в обліковому записі сховища, яке було зазначено вище, буде створено відповідні папки.</span><span class="sxs-lookup"><span data-stu-id="0347a-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="0347a-143">В залежності від того, який процес ви запускаєте, у відповідних вкладених папках буде створено файли даних і файли model.json.</span><span class="sxs-lookup"><span data-stu-id="0347a-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="0347a-144">У разі створення кількох середовищ Customer Insights і вибору збереження вихідних сутностей з цих середовищ у вашому обліковому записі сховища, окремі папки створюватимуться для кожного середовища з ci_ <environmentid> в контейнері.</span><span class="sxs-lookup"><span data-stu-id="0347a-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="0347a-145">Додаткові відомості про копіювання конфігурації (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="0347a-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="0347a-146">Буде скопійовано параметри конфігурації, перелічені нижче.</span><span class="sxs-lookup"><span data-stu-id="0347a-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="0347a-147">Конфігурація функцій</span><span class="sxs-lookup"><span data-stu-id="0347a-147">Feature configurations</span></span>
- <span data-ttu-id="0347a-148">Інтегровані/імпортовані джерела даних</span><span class="sxs-lookup"><span data-stu-id="0347a-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="0347a-149">Конфігурація уніфікації даних (зіставлення, відповідність, злиття)</span><span class="sxs-lookup"><span data-stu-id="0347a-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="0347a-150">Сегменти</span><span class="sxs-lookup"><span data-stu-id="0347a-150">Segments</span></span>
- <span data-ttu-id="0347a-151">Вимірювання</span><span class="sxs-lookup"><span data-stu-id="0347a-151">Measures</span></span>
- <span data-ttu-id="0347a-152">Зв'язки</span><span class="sxs-lookup"><span data-stu-id="0347a-152">Relationships</span></span>
- <span data-ttu-id="0347a-153">Справи</span><span class="sxs-lookup"><span data-stu-id="0347a-153">Activities</span></span>
- <span data-ttu-id="0347a-154">Покажчик «Пошук і фільтрація»</span><span class="sxs-lookup"><span data-stu-id="0347a-154">Search & filter Index</span></span>
- <span data-ttu-id="0347a-155">Експортні напрямки</span><span class="sxs-lookup"><span data-stu-id="0347a-155">Export destinations</span></span>
- <span data-ttu-id="0347a-156">Заплановане оновлення</span><span class="sxs-lookup"><span data-stu-id="0347a-156">Scheduled refresh</span></span>
- <span data-ttu-id="0347a-157">Збагачення</span><span class="sxs-lookup"><span data-stu-id="0347a-157">Enrichments</span></span>
- <span data-ttu-id="0347a-158">Керування моделлю</span><span class="sxs-lookup"><span data-stu-id="0347a-158">Model management</span></span>
- <span data-ttu-id="0347a-159">Призначення ролей</span><span class="sxs-lookup"><span data-stu-id="0347a-159">Role assignments</span></span>

<span data-ttu-id="0347a-160">Перелічені нижче параметри скопійовано *не* буде.</span><span class="sxs-lookup"><span data-stu-id="0347a-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="0347a-161">Профілі клієнтів.</span><span class="sxs-lookup"><span data-stu-id="0347a-161">Customer profiles.</span></span>
- <span data-ttu-id="0347a-162">Облікові дані джерела даних.</span><span class="sxs-lookup"><span data-stu-id="0347a-162">Data source credentials.</span></span> <span data-ttu-id="0347a-163">Доведеться надати облікові дані для кожного джерела даних та оновити джерела даних вручну.</span><span class="sxs-lookup"><span data-stu-id="0347a-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="0347a-164">Джерела даних з папки Common Data Model та озера, керованого Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0347a-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="0347a-165">Ви повинні створити ці джерела даних вручну під іменами, ідентичними іменам у вихідному середовищі.</span><span class="sxs-lookup"><span data-stu-id="0347a-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="0347a-166">Після копіювання середовища відобразиться підтвердження стосовно того, що було створено нове середовище.</span><span class="sxs-lookup"><span data-stu-id="0347a-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="0347a-167">Виберіть **Перейти до джерел даних**, щоб переглянути список джерел даних.</span><span class="sxs-lookup"><span data-stu-id="0347a-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="0347a-168">Усі джерела даних відображатимуться зі станом **Відсутні облікові дані**.</span><span class="sxs-lookup"><span data-stu-id="0347a-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="0347a-169">Відредагуйте джерела даних і укажіть облікові дані, щоб оновити їх.</span><span class="sxs-lookup"><span data-stu-id="0347a-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0347a-170">![Джерела даних скопійовано](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="0347a-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="0347a-171">Після оновлення джерел даних перейдіть до розділу **Дані** > **Уніфікувати**.</span><span class="sxs-lookup"><span data-stu-id="0347a-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="0347a-172">Тут ви знайдете настройки з вихідного середовища.</span><span class="sxs-lookup"><span data-stu-id="0347a-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="0347a-173">Відредагуйте їх відповідно до потреб або виберіть **Виконати**, щоб почати процес уніфікації даних і створити єдину сутність клієнта.</span><span class="sxs-lookup"><span data-stu-id="0347a-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="0347a-174">Після завершення уніфікації даних виберіть **Показники** та **Сегменти**, щоб оновити їх також.</span><span class="sxs-lookup"><span data-stu-id="0347a-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="0347a-175">Редагувати наявне середовище</span><span class="sxs-lookup"><span data-stu-id="0347a-175">Edit an existing environment</span></span>

<span data-ttu-id="0347a-176">Ви можете редагувати деякі відомості наявних середовищ.</span><span class="sxs-lookup"><span data-stu-id="0347a-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="0347a-177">Перейдіть до **Адміністрування** > **Система** > **Інформація**.</span><span class="sxs-lookup"><span data-stu-id="0347a-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="0347a-178">Виберіть **Редагування**.</span><span class="sxs-lookup"><span data-stu-id="0347a-178">Select **Edit**.</span></span>

3. <span data-ttu-id="0347a-179">Можна оновити **Коротке ім’я** середовища, але не можна змінити **Регіон** або **Тип**.</span><span class="sxs-lookup"><span data-stu-id="0347a-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="0347a-180">Якщо середовище настроєно для збереження даних у Azure Data Lake Storage Gen2, ви можете оновити **Ключ бізнес-партнера**.</span><span class="sxs-lookup"><span data-stu-id="0347a-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="0347a-181">Проте не можна змінити **Ім’я облікового запису** або **Контейнера**.</span><span class="sxs-lookup"><span data-stu-id="0347a-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="0347a-182">Крім того, можна змінити підключення ключа облікового запису на підключення на основі ресурсу або підписки.</span><span class="sxs-lookup"><span data-stu-id="0347a-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="0347a-183">Після оновлення не можна повернутися до ключа облікового запису.</span><span class="sxs-lookup"><span data-stu-id="0347a-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="0347a-184">Для отримання додаткових відомостей див. розділ [Підключення аналізу аудиторії до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="0347a-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="0347a-185">Під час оновлення з'єднання інформацію про **Контейнер** змінити не можна.</span><span class="sxs-lookup"><span data-stu-id="0347a-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="0347a-186">Скидання існуючого середовища</span><span class="sxs-lookup"><span data-stu-id="0347a-186">Reset an existing environment</span></span>

<span data-ttu-id="0347a-187">Якщо потрібно видалити всі конфігурації та видалити прийняті дані, можна скинути середовище в пустий стан.</span><span class="sxs-lookup"><span data-stu-id="0347a-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="0347a-188">Перейдіть до **Адміністрування** > **Система** > **Інформація**.</span><span class="sxs-lookup"><span data-stu-id="0347a-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="0347a-189">Вибір елемента **Скинути**.</span><span class="sxs-lookup"><span data-stu-id="0347a-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="0347a-190">Щоб підтвердити видалення, введіть ім'я середовища та натисніть кнопку **Скинути**.</span><span class="sxs-lookup"><span data-stu-id="0347a-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="0347a-191">Видалення наявного середовища</span><span class="sxs-lookup"><span data-stu-id="0347a-191">Delete an existing environment</span></span>

1. <span data-ttu-id="0347a-192">Перейдіть до **Адміністрування** > **Система** > **Інформація**.</span><span class="sxs-lookup"><span data-stu-id="0347a-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="0347a-193">Виберіть **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="0347a-193">Select **Delete**.</span></span>

1. <span data-ttu-id="0347a-194">Щоб підтвердити видалення, введіть ім'я середовища, потім виберіть **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="0347a-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
