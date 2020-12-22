---
title: Заповнення часткових даних за допомогою прогнозів
description: Використання прогнозів для заповнення неповних даних клієнтів.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 66f0b16b5d05741ab98ca5ce2157da8c46b6d9e0
ms.sourcegitcommit: 5379c2b77d613d071a177f509e6417ebf3c47516
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/26/2020
ms.locfileid: "4648736"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="3441d-103">Заповніть часткові дані за допомогою прогнозів</span><span class="sxs-lookup"><span data-stu-id="3441d-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3441d-104">Завдяки прогнозам ви можете легко створювати прогнозовані значення, щоб краще розуміти потреби своїх клієнтів.</span><span class="sxs-lookup"><span data-stu-id="3441d-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="3441d-105">На сторінці **Аналітика** > **Прогноз** можна вибрати параметр **Мої прогнози**, щоб переглянути прогнози, налаштовані в інших частинах аналізу аудиторії, і отримати дозвіл на подальше їх настроювання.</span><span class="sxs-lookup"><span data-stu-id="3441d-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="3441d-106">Ця функція недоступна, якщо в середовищі використовується сховище Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="3441d-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="3441d-107">Функція прогнозування за допомогою автоматизованих засобів оцінює дані та на їх основі створює прогнози, а отже може слугувати методом профілювання відповідно до визначення цього терміну в Генеральному регламенті із захисту персональних даних (GDPR).</span><span class="sxs-lookup"><span data-stu-id="3441d-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="3441d-108">Використання клієнтом цієї функції для обробки даних може регулюватися положеннями GDPR або інших законів чи постанов.</span><span class="sxs-lookup"><span data-stu-id="3441d-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="3441d-109">Ви несете відповідальність за те, що використання Dynamics 365 Customer Insights, включаючи прогнози, відповідає всім чинним законам і нормативним актам, зокрема законам, пов'язаним з конфіденційністю, персональними даними, біометричними даними, захистом даних і конфіденційністю комунікацій.</span><span class="sxs-lookup"><span data-stu-id="3441d-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3441d-110">Вимоги</span><span class="sxs-lookup"><span data-stu-id="3441d-110">Prerequisites</span></span>

<span data-ttu-id="3441d-111">До використання організацією функції прогнозів необхідно задовольнити наведеним далі передумовам.</span><span class="sxs-lookup"><span data-stu-id="3441d-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="3441d-112">В організації є інсталяція, [настроєна в програмі Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites), і в тій самій організації, що й Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3441d-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="3441d-113">Ваше середовище вкладено до вашої інсталяції Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3441d-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="3441d-114">Якщо ви [створюєте перше середовище](manage-environments.md), налаштуйте його в діалоговому вікні **Створення середовища** та виберіть **Додатково**.</span><span class="sxs-lookup"><span data-stu-id="3441d-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="3441d-115">Якщо ви вже створили середовище, перейдіть до його настройок і виберіть **Додатково**.</span><span class="sxs-lookup"><span data-stu-id="3441d-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="3441d-116">У будь-якому разі в розділі **Використання прогнозів** введіть URL-адресу інсталяції Common Data Service, потрібно вкласти середовище.</span><span class="sxs-lookup"><span data-stu-id="3441d-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="3441d-117">Створення прогнозу в сутності «Клієнт»</span><span class="sxs-lookup"><span data-stu-id="3441d-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="3441d-118">У розділі «Аналіз аудиторії» виберіть пункт **Дані** > **Сутності**.</span><span class="sxs-lookup"><span data-stu-id="3441d-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="3441d-119">Виберіть сутність **Клієнт**.</span><span class="sxs-lookup"><span data-stu-id="3441d-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="3441d-120">У сутності **"Клієнт: CustomerInsights** перейдіть на вкладку **Поля**.</span><span class="sxs-lookup"><span data-stu-id="3441d-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="3441d-121">Знайдіть ім’я атрибута, для якого потрібно спрогнозувати значення, а потім клацніть піктограму **Огляд** у стовпці **Зведення**.</span><span class="sxs-lookup"><span data-stu-id="3441d-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3441d-122">![Піктограма "Огляд"](media/intelligence-overviewicon.png "Піктограма "Огляд"")</span><span class="sxs-lookup"><span data-stu-id="3441d-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="3441d-123">Якщо для атрибута бракує багато значень, виберіть **Прогнозувати відсутні значення**, щоб продовжити створення прогнозу.</span><span class="sxs-lookup"><span data-stu-id="3441d-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3441d-124">![Стан огляду з кнопками прогнозування відсутніх значень](media/intelligence-overviewpredictmissingvalues.png "Стан огляду з кнопками прогнозування відсутніх значень")</span><span class="sxs-lookup"><span data-stu-id="3441d-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="3441d-125">Укажіть значення полів **Коротке ім’я** та **Ім’я вихідної сутності** для результатів прогнозування.</span><span class="sxs-lookup"><span data-stu-id="3441d-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="3441d-126">Зі списку параметрів, який заповниться автоматично, ви дізнаєтеся, чи можна зіставити значення з прогнозованою категорією.</span><span class="sxs-lookup"><span data-stu-id="3441d-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="3441d-127">У цьому разі єдиними доступними для вас параметрами категорії є 0 або 1, оскільки вони зіставляються зі значеннями «істинно» й «хибно» або двійковим характером прогнозу.</span><span class="sxs-lookup"><span data-stu-id="3441d-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="3441d-128">У стовпці «Категорія» зіставте значення полів, які потрібно класифікувати як «0» в остаточному прогнозі, зі значенням «0» у стовпці «Категорія», а елементи, які потрібно віднести до категорії «1» в остаточному прогнозі, – зі значенням «1».</span><span class="sxs-lookup"><span data-stu-id="3441d-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3441d-129">![Зразок зіставлення значень полів із категоріями](media/intelligence-categorymapping.png "Зразок зіставлення значень полів із категоріями")</span><span class="sxs-lookup"><span data-stu-id="3441d-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="3441d-130">Виберіть **Готово**, щоб обробити прогноз.</span><span class="sxs-lookup"><span data-stu-id="3441d-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="3441d-131">Оброблення триватиме деякий час залежно від розміру та складності даних.</span><span class="sxs-lookup"><span data-stu-id="3441d-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="3441d-132">Результати будуть доступні в новій сутності зі значенням поля **Ім’я вихідної сутності**, заданим для створеного вами прогнозу.</span><span class="sxs-lookup"><span data-stu-id="3441d-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="3441d-133">Створення прогнозу під час створення сегмента</span><span class="sxs-lookup"><span data-stu-id="3441d-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="3441d-134">Передбачати відсутні значення певних вибраних атрибутів можна також під час створення сегмента.</span><span class="sxs-lookup"><span data-stu-id="3441d-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="3441d-135">Зокрема, у разі швидкого створення сегмента на основі вашої єдиної сутності "Клієнт" або "Міра клієнта".</span><span class="sxs-lookup"><span data-stu-id="3441d-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="3441d-136">У межах цього циклу ви можете вибрати певний атрибут, на основі якого потрібно створити сегмент, наприклад, «Задоволення клієнта» або «Сума покупки».</span><span class="sxs-lookup"><span data-stu-id="3441d-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="3441d-137">Після створення сегмента система запропонує метод прогнозування будь-яких відсутніх значень для цього атрибута.</span><span class="sxs-lookup"><span data-stu-id="3441d-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="3441d-138">У аналізі аудиторій відкрийте параметр **Сегменти** та виберіть плитку **Профілі**.</span><span class="sxs-lookup"><span data-stu-id="3441d-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="3441d-139">Виберіть **Поле**, на основі якого потрібно створити сегмент, і клацніть **Оператор**, а потім – **Огляд.**</span><span class="sxs-lookup"><span data-stu-id="3441d-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="3441d-140">Укажіть значення полів **Ім’я** та **Коротке ім’я** для сегмента.</span><span class="sxs-lookup"><span data-stu-id="3441d-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="3441d-141">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="3441d-141">Select **Save**.</span></span>

5. <span data-ttu-id="3441d-142">Якщо в створеного сегмента відсутні деякі дані вихідного поля, ви можете прогнозувати відсутні значення.</span><span class="sxs-lookup"><span data-stu-id="3441d-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3441d-143">![Кнопка "Прогноз"](media/segments-predictoption.png "Кнопка "Прогноз"")</span><span class="sxs-lookup"><span data-stu-id="3441d-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="3441d-144">Укажіть значення полів **Коротке ім’я** та **Ім’я вихідної сутності** для результатів прогнозування.</span><span class="sxs-lookup"><span data-stu-id="3441d-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="3441d-145">Виберіть **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3441d-145">Select **Done**.</span></span> <span data-ttu-id="3441d-146">Ваш прогноз невдовзі буде створено в новій сутності з іменем, заданим для поля **Ім’я вихідної сутності**.</span><span class="sxs-lookup"><span data-stu-id="3441d-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="3441d-147">Перегляд прогнозу</span><span class="sxs-lookup"><span data-stu-id="3441d-147">View a prediction</span></span>

1. <span data-ttu-id="3441d-148">У розділі «Аналіз аудиторії» виберіть пункт **Аналітика** > **Прогнози** > **Мої прогнози**.</span><span class="sxs-lookup"><span data-stu-id="3441d-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3441d-149">Виберіть прогноз, який потрібно переглянути.</span><span class="sxs-lookup"><span data-stu-id="3441d-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="3441d-150">Клацніть три крапки в стовпці **Дії** та виберіть **Переглянути**</span><span class="sxs-lookup"><span data-stu-id="3441d-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="3441d-151">Відобразиться кількість точок даних у поданні прогнозу.</span><span class="sxs-lookup"><span data-stu-id="3441d-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3441d-152">![Сторінка "Прогнози"](media/intelligence-predictionsviewpage.png "Сторінка "Прогнози"")</span><span class="sxs-lookup"><span data-stu-id="3441d-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="3441d-153">У розділі **Прогнозовані значення** наведено зіставлення, створені на етапі зіставлення значення поля з категорією.</span><span class="sxs-lookup"><span data-stu-id="3441d-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="3441d-154">Це значення в наборі даних, зіставлені з певною категорією.</span><span class="sxs-lookup"><span data-stu-id="3441d-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="3441d-155">У розділі -**Основні авторитети** наведено фактори вашого набору даних, які, найімовірніше, вплинули на достовірність прогнозу зіставлення значення поля з певною категорією.</span><span class="sxs-lookup"><span data-stu-id="3441d-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="3441d-156">У розділі **Швидкодія** можна дізнатися про ефективність функції прогнозування.</span><span class="sxs-lookup"><span data-stu-id="3441d-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="3441d-157">Клацніть посилання, щоб дізнатися більше.</span><span class="sxs-lookup"><span data-stu-id="3441d-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="3441d-158">У розділі **Попередній перегляд** наведено зразки вихідних наборів даних із прогнозу та ймовірність, або достовірність, прогнозованого значення, де 0 – недостовірне, а 1 – достовірне.</span><span class="sxs-lookup"><span data-stu-id="3441d-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="3441d-159">Оновлення прогнозу</span><span class="sxs-lookup"><span data-stu-id="3441d-159">Update a prediction</span></span>

1. <span data-ttu-id="3441d-160">У розділі «Аналіз аудиторії» виберіть пункт **Аналітика** > **Прогнози** > **Мої прогнози**.</span><span class="sxs-lookup"><span data-stu-id="3441d-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3441d-161">Виберіть прогноз, який потрібно оновити, і клацніть піктограму **Оновити**.</span><span class="sxs-lookup"><span data-stu-id="3441d-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="3441d-162">Прогноз буде призначено для оброблення.</span><span class="sxs-lookup"><span data-stu-id="3441d-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="3441d-163">Переглянути час останнього оновлення можна в стовпці **Оновлено** на сторінці **Прогнози**.</span><span class="sxs-lookup"><span data-stu-id="3441d-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="3441d-164">Редагування прогнозу</span><span class="sxs-lookup"><span data-stu-id="3441d-164">Edit a prediction</span></span>

<span data-ttu-id="3441d-165">Після створення прогнозу ви можете настроїти модель у AI Builder, щоб збільшити ефективність своєї моделі.</span><span class="sxs-lookup"><span data-stu-id="3441d-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="3441d-166">У розділі «Аналіз аудиторії» виберіть пункт **Аналітика** > **Прогнози** > **Мої прогнози**.</span><span class="sxs-lookup"><span data-stu-id="3441d-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3441d-167">Виберіть прогноз, який потрібно змінити.</span><span class="sxs-lookup"><span data-stu-id="3441d-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="3441d-168">Клацніть три крапки в стовпці **Дії** та виберіть **Переглянути**</span><span class="sxs-lookup"><span data-stu-id="3441d-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="3441d-169">Виберіть **Налаштувати в AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="3441d-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="3441d-170">Оновіть свою модель в AI Builder.</span><span class="sxs-lookup"><span data-stu-id="3441d-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="3441d-171">[Докладніше про керування моделями в AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="3441d-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="3441d-172">Під час наступного запуску прогнозу використовуватиметься оновлена модель.</span><span class="sxs-lookup"><span data-stu-id="3441d-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="3441d-173">Нові моделі, створені в AI Builder, не відображатимуться в аналізі аудиторії, якщо модель не була створена з наведеного вище завдання.</span><span class="sxs-lookup"><span data-stu-id="3441d-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="3441d-174">Вилучення прогнозу</span><span class="sxs-lookup"><span data-stu-id="3441d-174">Remove a prediction</span></span>

1. <span data-ttu-id="3441d-175">У розділі «Аналіз аудиторії» виберіть пункт **Аналітика** > **Прогнози** > **Мої прогнози**.</span><span class="sxs-lookup"><span data-stu-id="3441d-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3441d-176">Виберіть прогноз, який потрібно видалити.</span><span class="sxs-lookup"><span data-stu-id="3441d-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="3441d-177">Клацніть три крапки в стовпці **Дії** та виберіть **Видалити**</span><span class="sxs-lookup"><span data-stu-id="3441d-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="3441d-178">Підтвердьте видалення.</span><span class="sxs-lookup"><span data-stu-id="3441d-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="3441d-179">Виправлення неполадок</span><span class="sxs-lookup"><span data-stu-id="3441d-179">Troubleshooting</span></span>

<span data-ttu-id="3441d-180">Якщо процес вкладення Common Data Service не вдається виконати через помилку, можна спробувати виконати процес вручну.</span><span class="sxs-lookup"><span data-stu-id="3441d-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="3441d-181">Існує дві відомі проблеми, які можуть виникнути в процесі вкладення.</span><span class="sxs-lookup"><span data-stu-id="3441d-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="3441d-182">Рішення надбудови картки клієнта не інстальовано.</span><span class="sxs-lookup"><span data-stu-id="3441d-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="3441d-183">Дотримуйтеся вказівок, щоб [інсталювати й настроїти рішення](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="3441d-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="3441d-184">Дозволи програми не надаються.</span><span class="sxs-lookup"><span data-stu-id="3441d-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="3441d-185">Перейти до [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3441d-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="3441d-186">Виберіть **Середовища**.</span><span class="sxs-lookup"><span data-stu-id="3441d-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="3441d-187">Виберіть три крапки поруч із середовищем, до якого потрібно додати дозвіл, і натисніть **Настройки**.</span><span class="sxs-lookup"><span data-stu-id="3441d-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="3441d-188">Розгорніть **Користувачі + дозволи** й виберіть **Користувачі**.</span><span class="sxs-lookup"><span data-stu-id="3441d-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="3441d-189">Виберіть **+ Новий**, а потім – **Користувач**.</span><span class="sxs-lookup"><span data-stu-id="3441d-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="3441d-190">Виберіть параметр **Користувач програми**, якщо його ще не вибрано, і введіть таку інформацію:</span><span class="sxs-lookup"><span data-stu-id="3441d-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="3441d-191">**Ім’я користувача:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3441d-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="3441d-192">**Ідентифікатор програми:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="3441d-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="3441d-193">**Ім’я:** клієнт</span><span class="sxs-lookup"><span data-stu-id="3441d-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="3441d-194">**Прізвище:** Insights</span><span class="sxs-lookup"><span data-stu-id="3441d-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="3441d-195">**Основна адреса електронної пошти:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3441d-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="3441d-196">Виберіть елемент **Зберегти й закрити**.</span><span class="sxs-lookup"><span data-stu-id="3441d-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="3441d-197">Виберіть щойно створеного користувача.</span><span class="sxs-lookup"><span data-stu-id="3441d-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="3441d-198">Виберіть **Керування ролями** на панелі меню згори.</span><span class="sxs-lookup"><span data-stu-id="3441d-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="3441d-199">Виберіть **Системний адміністратор**, а потім натисніть кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3441d-199">Select **System Administrator**, then select **OK**.</span></span>
