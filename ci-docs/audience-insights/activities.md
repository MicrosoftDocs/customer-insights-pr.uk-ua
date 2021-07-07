---
title: Дії клієнта
description: Визначення дій клієнтів і перегляд їх у часовій шкалі клієнта.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304951"
---
# <a name="customer-activities"></a><span data-ttu-id="d23d4-103">Дії клієнта</span><span class="sxs-lookup"><span data-stu-id="d23d4-103">Customer activities</span></span>

<span data-ttu-id="d23d4-104">Об'єднайте справи клієнтів [із різних джерел даних](data-sources.md) у Dynamics 365 Customer Insights, щоб створити часову шкалу, яка має список справ у хронологічному порядку.</span><span class="sxs-lookup"><span data-stu-id="d23d4-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="d23d4-105">Додайте часову шкалу до програм Dynamics 365 за [допомогою рішення надбудови Customer Card ](customer-card-add-in.md) або в приладній дошці Power BI.</span><span class="sxs-lookup"><span data-stu-id="d23d4-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="d23d4-106">Визначення справи</span><span class="sxs-lookup"><span data-stu-id="d23d4-106">Define an activity</span></span>

<span data-ttu-id="d23d4-107">Ваші джерела даних можуть сутності з даними про транзакції та справи з кількох джерел даних.</span><span class="sxs-lookup"><span data-stu-id="d23d4-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="d23d4-108">Визначте ці сутності та виберіть справи, які потрібно переглянути на часовій шкалі клієнта.</span><span class="sxs-lookup"><span data-stu-id="d23d4-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="d23d4-109">Виберіть сутність, яка містить цільову справу або справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="d23d4-110">У сутності має бути принаймні один атрибут типу **Дата**, який слід включити до часової шкали. Ви не можете додавати сутності без полів **Дата**.</span><span class="sxs-lookup"><span data-stu-id="d23d4-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="d23d4-111">Елемент керування **Додати справу** буде вимкнуто, якщо не буде знайдено жодної такої сутності.</span><span class="sxs-lookup"><span data-stu-id="d23d4-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="d23d4-112">У розділі «Аналіз аудиторії» виберіть **Дані** > **Дії**.</span><span class="sxs-lookup"><span data-stu-id="d23d4-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="d23d4-113">Виберіть пункт **Додати справу**, щоб почати екскурсію процедурою налаштування справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="d23d4-114">На кроці **Дані справи** задайте значення для наведених далі полів.</span><span class="sxs-lookup"><span data-stu-id="d23d4-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="d23d4-115">**Ім’я справи**: виберіть найменування для своєї справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="d23d4-116">**Сутність**: виберіть сутність, яка містить дані про транзакції та справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="d23d4-117">**Первинний ключ**: виберіть поле, яке однозначно ідентифікує запис.</span><span class="sxs-lookup"><span data-stu-id="d23d4-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="d23d4-118">Він не має містити повторюваних значень, пустих або відсутніх значень.</span><span class="sxs-lookup"><span data-stu-id="d23d4-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Налаштуйте дані справи з іменем, сутністю й основним ключем.":::

1. <span data-ttu-id="d23d4-120">Виберіть **Далі**, щоб перейти до наступного кроку.</span><span class="sxs-lookup"><span data-stu-id="d23d4-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="d23d4-121">На кроці **Зв’язок** налаштуйте докладні відомості для підключення даних своєї справи до відповідного клієнта.</span><span class="sxs-lookup"><span data-stu-id="d23d4-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="d23d4-122">На цьому кроці здійснюється візуалізація зв’язку між сутностями.</span><span class="sxs-lookup"><span data-stu-id="d23d4-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="d23d4-123">**Перше**: чужорідне поле в сутності вашої справи, яке використовуватиметься для створення зв’язку з іншою сутністю.</span><span class="sxs-lookup"><span data-stu-id="d23d4-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="d23d4-124">**Друге**: відповідне поле вихідного клієнта, з яким сутність справи матиме зв’язок.</span><span class="sxs-lookup"><span data-stu-id="d23d4-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="d23d4-125">Зв’язок можна встановлювати лише з сутностями вихідного клієнта, які використовуються в процесі уніфікації даних.</span><span class="sxs-lookup"><span data-stu-id="d23d4-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="d23d4-126">**Третє** : якщо зв'язок між цією сутністю справи та вибраною сутністю вихідного клієнта вже існує, ім'я зв'язку буде в режимі «лише для читання».</span><span class="sxs-lookup"><span data-stu-id="d23d4-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="d23d4-127">Якщо такі зв'язки відсутні, буде створено новий зв'язок з іменем, яке ви ввели в цьому полі.</span><span class="sxs-lookup"><span data-stu-id="d23d4-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Визначення зв’язку сутностей.":::

1. <span data-ttu-id="d23d4-129">Виберіть **Далі**, щоб перейти до наступного кроку.</span><span class="sxs-lookup"><span data-stu-id="d23d4-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="d23d4-130">На кроці **Уніфікація справи** виберіть подію справи та почніть час своєї справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="d23d4-131">**Обов’язкові поля**</span><span class="sxs-lookup"><span data-stu-id="d23d4-131">**Required fields**</span></span>
      - <span data-ttu-id="d23d4-132">**Подія справи**: це поле є подією для цієї справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="d23d4-133">**Позначка часу**: це поле представляє собою час початку справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="d23d4-134">**Необов’язкові поля**</span><span class="sxs-lookup"><span data-stu-id="d23d4-134">**Optional fields**</span></span>
      - <span data-ttu-id="d23d4-135">**Додаткові відомості**: це поле має доречну інформацію для цієї справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="d23d4-136">**Піктограма**: це зображення, яке найкращим чином представляє тип справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="d23d4-137">**Веб-адреса**: це поле, яке містить URL-адресу з інформацією про цю справу.</span><span class="sxs-lookup"><span data-stu-id="d23d4-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="d23d4-138">Наприклад, транзакційна система, з якої походить ця справа.</span><span class="sxs-lookup"><span data-stu-id="d23d4-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="d23d4-139">Ця URL-адреса може бути будь-яким полем у джерелі даних, або для неї може створюватись нове поле із використанням засобів перетворення Power Query.</span><span class="sxs-lookup"><span data-stu-id="d23d4-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="d23d4-140">Дані URL-адреси зберігаються в сутності *Єдина справа*, яку можна використовувати в рамках нисхідних процесів за допомогою [API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="d23d4-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="У сутності «Єдина справа» зазначте дані справи клієнта.":::

1. <span data-ttu-id="d23d4-142">Виберіть **Далі**, щоб перейти до наступного кроку.</span><span class="sxs-lookup"><span data-stu-id="d23d4-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="d23d4-143">Ви можете вибрати пункт **Закінчити й переглянути**, щоб зберегти справу зараз із заданим типом справи **Інше**.</span><span class="sxs-lookup"><span data-stu-id="d23d4-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="d23d4-144">На кроці **Тип справи** виберіть тип справи, а також додатково виберіть, чи ви бажаєте семантично зіставляти деякі типи справ для використання в інших областях програми Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d23d4-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="d23d4-145">Наразі типи справ *Передплата* й *SalesOrderLine* можуть семантично зіставлятися після погодження зіставити ці поля.</span><span class="sxs-lookup"><span data-stu-id="d23d4-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="d23d4-146">Якщо даний тип справи не є доречним до нової справи, ви можете вибрати пункт *Інше* або *Створити новий* для настроюваного типу справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="d23d4-147">Виберіть **Далі**, щоб перейти до наступного кроку.</span><span class="sxs-lookup"><span data-stu-id="d23d4-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="d23d4-148">На кроці **Перегляд** перевірте свої варіанти вибору.</span><span class="sxs-lookup"><span data-stu-id="d23d4-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="d23d4-149">Поверніться до будь-якого із попередніх кроків і за необхідності оновіть інформацію.</span><span class="sxs-lookup"><span data-stu-id="d23d4-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Перегляньте зазначені поля справи.":::
   
1. <span data-ttu-id="d23d4-151">Виберіть пункт **Зберегти справу**, щоб застосувати свої зміни, потім виберіть **Готово**, щоб повернутися до розділу **Дані** > **Справи**.</span><span class="sxs-lookup"><span data-stu-id="d23d4-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="d23d4-152">Тут ви побачите, які справи налаштовано для відображення на часовій шкалі.</span><span class="sxs-lookup"><span data-stu-id="d23d4-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="d23d4-153">На сторінці **Справи** виберіть **Запустити**, щоб виконати обробку справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="d23d4-154">Існує [шість типів станів](system.md#status-types) для завдань/процесів.</span><span class="sxs-lookup"><span data-stu-id="d23d4-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d23d4-155">Крім того, більшість процесів [залежать від інших низхідних процесів](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d23d4-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d23d4-156">Можна вибрати стан процесу, щоб переглянути докладні відомості про перебіг виконання всієї роботи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d23d4-157">Після вибору **Переглянути відомості** для однієї з робіт завдання ви побачите додаткові відомості: час обробки, дата останньої обробки, а також усі помилки та попередження, пов'язані з завданням.</span><span class="sxs-lookup"><span data-stu-id="d23d4-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="d23d4-158">Керування наявними справами</span><span class="sxs-lookup"><span data-stu-id="d23d4-158">Manage existing activities</span></span>

<span data-ttu-id="d23d4-159">У розділі **Дані** > **Справи** ви можете переглянути свої збережені справи й керувати ними.</span><span class="sxs-lookup"><span data-stu-id="d23d4-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="d23d4-160">Кожна справа представлена рядком, який також містить відомості про джерело, сутність і тип справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="d23d4-161">При виборі справи доступними будуть наведені нижче справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="d23d4-162">**Редагувати**: відкривається сторінка налаштування справи на кроці перегляду.</span><span class="sxs-lookup"><span data-stu-id="d23d4-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="d23d4-163">На цьому кроці ви можете змінити будь-які або всі поточні налаштування.</span><span class="sxs-lookup"><span data-stu-id="d23d4-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="d23d4-164">Після зміни налаштувань виберіть **Зберегти справу**, потім виберіть **Запустити**, щоб виконати обробку змін.</span><span class="sxs-lookup"><span data-stu-id="d23d4-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="d23d4-165">**Перейменувати**: відкривається діалогове вікно, в якому ви можете ввести інше ім’я для вибраної справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="d23d4-166">Натисніть кнопку **Зберегти**, щоб застосувати зміни.</span><span class="sxs-lookup"><span data-stu-id="d23d4-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="d23d4-167">**Видалити**: відкриває діалогове вікно, в якому можна підтвердити видалення вибраної справи.</span><span class="sxs-lookup"><span data-stu-id="d23d4-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="d23d4-168">Ви також можете видалити більше однієї справи за один раз способом вибору справ, а потім – вибору піктограми видалення.</span><span class="sxs-lookup"><span data-stu-id="d23d4-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="d23d4-169">Виберіть **Видалити**, щоб підтвердити видалення.</span><span class="sxs-lookup"><span data-stu-id="d23d4-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
