---
title: Зв'язки між сутностями і шляхами до сутностей
description: Створення та керування зв'язками між сутностями з різних джерел даних.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171189"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="b44f6-103">Зв’язки між сутностями</span><span class="sxs-lookup"><span data-stu-id="b44f6-103">Relationships between entities</span></span>

<span data-ttu-id="b44f6-104">Зв'язки з'єднують сутності та визначають граф даних, коли сутності мають однаковий спільний ідентифікатор – зовнішній ключ.</span><span class="sxs-lookup"><span data-stu-id="b44f6-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="b44f6-105">На цей зовнішній ключ в одній сутності можна посилатися з іншої.</span><span class="sxs-lookup"><span data-stu-id="b44f6-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="b44f6-106">З’єднані сутності дають змогу визначати сегменти та показники на основі кількох джерел даних.</span><span class="sxs-lookup"><span data-stu-id="b44f6-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="b44f6-107">Нижче перелічено три доступні типи зв'язків.</span><span class="sxs-lookup"><span data-stu-id="b44f6-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="b44f6-108">Системні зв’язки без можливості редагування, що створюються системою в рамках процесу уніфікації даних</span><span class="sxs-lookup"><span data-stu-id="b44f6-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="b44f6-109">Успадковані зв'язки без можливості редагування, які автоматично створюються при отриманні даних з джерел даних</span><span class="sxs-lookup"><span data-stu-id="b44f6-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="b44f6-110">Настроювані зв'язки, які можна редагувати, що створюються та налаштовуються користувачами</span><span class="sxs-lookup"><span data-stu-id="b44f6-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="b44f6-111">Системні зв'язки без можливості редагування</span><span class="sxs-lookup"><span data-stu-id="b44f6-111">Non-editable system relationships</span></span>

<span data-ttu-id="b44f6-112">Системні зв'язки створюються автоматично під час уніфікації даних, і для цього використовується інтелектуальне зіставлення.</span><span class="sxs-lookup"><span data-stu-id="b44f6-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="b44f6-113">Такі зв’язки допомагають пов’язувати записи профілів клієнтів з іншими відповідними записами.</span><span class="sxs-lookup"><span data-stu-id="b44f6-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="b44f6-114">На діаграмі нижче продемонстровано створення трьох системних зв'язків.</span><span class="sxs-lookup"><span data-stu-id="b44f6-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="b44f6-115">Сутність клієнта зіставляється з іншими сутностями, і в результаті створюється уніфікована сутність *Клієнт*.</span><span class="sxs-lookup"><span data-stu-id="b44f6-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Діаграма, на якій показано шляхи зв’язків для сутності клієнта із трьома зв'язками «один до багатьох».":::

- <span data-ttu-id="b44f6-117">**Зв’язок *CustomerToContact*** створено між сутністю *Клієнт* та сутністю *Контактна особа*.</span><span class="sxs-lookup"><span data-stu-id="b44f6-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="b44f6-118">У сутності *Клієнт* поле ключа **Contact_contactID** пов’язується із полем ключа **contactID** сутності *Контактна особа*.</span><span class="sxs-lookup"><span data-stu-id="b44f6-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="b44f6-119">**Зв’язок *CustomerToAccount*** створено між сутністю *Клієнт* та сутністю *Бізнес-партнер*.</span><span class="sxs-lookup"><span data-stu-id="b44f6-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="b44f6-120">У сутності *Клієнт* поле ключа **Account_accountID** пов’язується із полем ключа **accountID** сутності *Бізнес-партнер*.</span><span class="sxs-lookup"><span data-stu-id="b44f6-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="b44f6-121">**Зв’язок *CustomerToWebAccount*** створено між сутністю *Клієнт* та сутністю *Веб-бізнес-партнер*.</span><span class="sxs-lookup"><span data-stu-id="b44f6-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="b44f6-122">У сутності *Клієнта* поле ключа **WebAccount_webaccountID** пов’язується із полем ключа **webaccountID** сутності *Веб-бізнес-партнер*.</span><span class="sxs-lookup"><span data-stu-id="b44f6-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="b44f6-123">Успадковані зв'язки без можливості редагування</span><span class="sxs-lookup"><span data-stu-id="b44f6-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="b44f6-124">Під час процесу отримання даних система шукає в джерелах даних наявні зв’язки.</span><span class="sxs-lookup"><span data-stu-id="b44f6-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="b44f6-125">Якщо зв'язків не існує, система автоматично створює їх.</span><span class="sxs-lookup"><span data-stu-id="b44f6-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="b44f6-126">Ці зв'язки використовуються також в низхідних процесах.</span><span class="sxs-lookup"><span data-stu-id="b44f6-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="b44f6-127">Створення настроюваних зв’язків</span><span class="sxs-lookup"><span data-stu-id="b44f6-127">Create a custom relationship</span></span>

<span data-ttu-id="b44f6-128">Зв'язок складається з *вихідної сутності*, яка містить зовнішній ключ, і *цільової сутності*, на яку вказує зовнішній ключ вихідної сутності.</span><span class="sxs-lookup"><span data-stu-id="b44f6-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="b44f6-129">У розділі «Аналіз аудиторії» виберіть **Дані** > **Зв'язки**.</span><span class="sxs-lookup"><span data-stu-id="b44f6-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="b44f6-130">Виберіть елемент **Створити зв’язок**.</span><span class="sxs-lookup"><span data-stu-id="b44f6-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="b44f6-131">В області **Новий зв’язок** введіть зазначені нижче відомості.</span><span class="sxs-lookup"><span data-stu-id="b44f6-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Бічна панель «Новий зв’язок» з пустими полями для введення.":::

   - <span data-ttu-id="b44f6-133">**Ім'я зв’язку**: ім'я, з якого стає ясним призначення цього зв'язку.</span><span class="sxs-lookup"><span data-stu-id="b44f6-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="b44f6-134">Наприклад, CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="b44f6-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="b44f6-135">**Опис**: опис зв’язку.</span><span class="sxs-lookup"><span data-stu-id="b44f6-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="b44f6-136">**Вихідна сутність**: сутність, яка використовується у зв’язку в якості джерела.</span><span class="sxs-lookup"><span data-stu-id="b44f6-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="b44f6-137">Наприклад, SupportCase.</span><span class="sxs-lookup"><span data-stu-id="b44f6-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="b44f6-138">**Цільова сутність**: сутність, яка використовується у зв’язку в якості цілі.</span><span class="sxs-lookup"><span data-stu-id="b44f6-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="b44f6-139">Наприклад, Клієнт.</span><span class="sxs-lookup"><span data-stu-id="b44f6-139">Example: Customer.</span></span>
   - <span data-ttu-id="b44f6-140">**Кратність джерела**: укажіть кратність вихідної сутності.</span><span class="sxs-lookup"><span data-stu-id="b44f6-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="b44f6-141">Кратність описує можливу кількість елементів у наборі.</span><span class="sxs-lookup"><span data-stu-id="b44f6-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="b44f6-142">Вона завжди співвідноситься із кратністю цілі.</span><span class="sxs-lookup"><span data-stu-id="b44f6-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="b44f6-143">Ви можете вибрати **Один** або **Багато**.</span><span class="sxs-lookup"><span data-stu-id="b44f6-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="b44f6-144">Підтримуються лише зв’язки «багато-до-одного» та «один-до-одного».</span><span class="sxs-lookup"><span data-stu-id="b44f6-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="b44f6-145">Багато-до-одного: кілька вихідних записів можуть зв'язуватися з одним цільовим записом.</span><span class="sxs-lookup"><span data-stu-id="b44f6-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="b44f6-146">Наприклад, кілька інцидентів підтримки, створені одним клієнтом.</span><span class="sxs-lookup"><span data-stu-id="b44f6-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="b44f6-147">Один-до-одного: один вихідний запис зв’язується із одним цільовим записом.</span><span class="sxs-lookup"><span data-stu-id="b44f6-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="b44f6-148">Наприклад, один ідентифікатор лояльності для одного клієнта.</span><span class="sxs-lookup"><span data-stu-id="b44f6-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="b44f6-149">Зв’язки «Багато до багатьох» можна створити, якщо створити два зв’язки «Багато-до-одного» та зв’язати сутність, що пов’язує вихідну та цільову сутність.</span><span class="sxs-lookup"><span data-stu-id="b44f6-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="b44f6-150">**Кратність цільового об’єкта**: виберіть кратність записів цільової сутності.</span><span class="sxs-lookup"><span data-stu-id="b44f6-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="b44f6-151">**Вихідне поле ключа**: поле зовнішнього ключа у вихідній сутності.</span><span class="sxs-lookup"><span data-stu-id="b44f6-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="b44f6-152">Наприклад, SupportCase може використовувати в якості поля зовнішнього ключа CaseID.</span><span class="sxs-lookup"><span data-stu-id="b44f6-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="b44f6-153">**Цільове поле ключа**: поле ключа цільової сутності.</span><span class="sxs-lookup"><span data-stu-id="b44f6-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="b44f6-154">Наприклад, сутність «Клієнт» може використовувати поле ключа **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="b44f6-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="b44f6-155">Щоб створити настроюваний зв’язок, виберіть **Створити**.</span><span class="sxs-lookup"><span data-stu-id="b44f6-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="b44f6-156">Перегляд зв’язків</span><span class="sxs-lookup"><span data-stu-id="b44f6-156">View relationships</span></span>

<span data-ttu-id="b44f6-157">На сторінці «Зв'язки» перелічено всі створені зв'язки.</span><span class="sxs-lookup"><span data-stu-id="b44f6-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="b44f6-158">Кожен рядок відповідає зв’язку і містить відомості про вихідну сутність, цільову сутність та кратність.</span><span class="sxs-lookup"><span data-stu-id="b44f6-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Список зв'язків і можливості на панелі дій сторінки «Зв'язки».":::

<span data-ttu-id="b44f6-160">На цій сторінці для наявних та нових зв’язків доступний набір можливостей.</span><span class="sxs-lookup"><span data-stu-id="b44f6-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="b44f6-161">**Створити зв’язок**: [Створення настроюваного зв’язку](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="b44f6-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="b44f6-162">**Графічне відображення**: [відкрийте засіб графічного відображення зв'язків](#explore-the-relationship-visualizer), щоб побачити схематичне зображення мережі наявних зв’язків та їхню кратність.</span><span class="sxs-lookup"><span data-stu-id="b44f6-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="b44f6-163">**Фільтрувати за**: виберіть тип зв'язків, що відображатиметься у списку.</span><span class="sxs-lookup"><span data-stu-id="b44f6-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="b44f6-164">**Пошук зв'язків**: скористайтеся текстовим пошуком у властивостях зв'язків.</span><span class="sxs-lookup"><span data-stu-id="b44f6-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="b44f6-165">Ознайомлення із засобом графічного відображення зв'язків</span><span class="sxs-lookup"><span data-stu-id="b44f6-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="b44f6-166">Засіб графічного відображення зв’язків показує схематичне зображення мережі наявних зв’язків між з’єднаними сутностями та кратність цих зв’язків.</span><span class="sxs-lookup"><span data-stu-id="b44f6-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="b44f6-167">Щоб настроїти подання, ви можете змінити розташування блоків, перетягуючи їх на полотні.</span><span class="sxs-lookup"><span data-stu-id="b44f6-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Знімок екрана: схема мережі у засобі графічного відображення зв'язків, де показано з’єднання між пов’язаними сутностями.":::

<span data-ttu-id="b44f6-169">Доступні можливості:</span><span class="sxs-lookup"><span data-stu-id="b44f6-169">Available options:</span></span> 
- <span data-ttu-id="b44f6-170">**Експортувати як зображення**: збережіть зображення поточного подання у файл.</span><span class="sxs-lookup"><span data-stu-id="b44f6-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="b44f6-171">**Змінити макет на горизонтальний/вертикальний**: змініть вирівнювання сутностей і зв'язків.</span><span class="sxs-lookup"><span data-stu-id="b44f6-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="b44f6-172">**Редагування**: змініть властивості настроюваних зв’язків в області редагування та збережіть зміни.</span><span class="sxs-lookup"><span data-stu-id="b44f6-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="b44f6-173">Керування наявними зв’язками</span><span class="sxs-lookup"><span data-stu-id="b44f6-173">Manage existing relationships</span></span> 

<span data-ttu-id="b44f6-174">На сторінці «Зв'язки» кожен зв'язок представлений окремим рядком.</span><span class="sxs-lookup"><span data-stu-id="b44f6-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="b44f6-175">Виберіть зв'язок, а тоді виберіть одну з можливостей з-поміж перелічених нижче.</span><span class="sxs-lookup"><span data-stu-id="b44f6-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="b44f6-176">**Редагування**: змініть властивості настроюваних зв’язків в області редагування та збережіть зміни.</span><span class="sxs-lookup"><span data-stu-id="b44f6-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="b44f6-177">**Видалити**: видалення настроюваних зв'язків.</span><span class="sxs-lookup"><span data-stu-id="b44f6-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="b44f6-178">**Перегляд**: перегляд успадкованих зв’язків та зв’язків, створених системою.</span><span class="sxs-lookup"><span data-stu-id="b44f6-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="b44f6-179">Наступний крок</span><span class="sxs-lookup"><span data-stu-id="b44f6-179">Next step</span></span>

<span data-ttu-id="b44f6-180">Системні та настроювані зв’язки використовуються для [створення сегментів](segments.md) на основі кількох джерел даних, які більше не є ізольованими.</span><span class="sxs-lookup"><span data-stu-id="b44f6-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
