---
title: Зв'язки між сутностями і шляхами до сутностей
description: Створення та керування зв'язками між сутностями з різних джерел даних.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595237"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="2fa26-103">Зв’язки між сутностями</span><span class="sxs-lookup"><span data-stu-id="2fa26-103">Relationships between entities</span></span>

<span data-ttu-id="2fa26-104">Зв’язки допомагають з’єднувати сутності та створювати графічне відображення даних, якщо сутності мають спільний ідентифікатор (зовнішній ключ), за яким можна посилатися з однієї сутності на іншу.</span><span class="sxs-lookup"><span data-stu-id="2fa26-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="2fa26-105">Зв’язані сутності дають змогу визначати сегменти та показники на основі кількох джерел даних.</span><span class="sxs-lookup"><span data-stu-id="2fa26-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="2fa26-106">Існує два типи зв’язків.</span><span class="sxs-lookup"><span data-stu-id="2fa26-106">There are two types of relationships.</span></span> <span data-ttu-id="2fa26-107">Системні зв’язки, які не можна редагувати (такі зв’язки створюються автоматично), і настроювані зв’язки (такі зв’язки створюються та налаштовуються користувачами).</span><span class="sxs-lookup"><span data-stu-id="2fa26-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="2fa26-108">Під час процесів пошуку відповідностей і злиття за лаштунками створюються системні зв’язки на основі інтелектуального зіставлення.</span><span class="sxs-lookup"><span data-stu-id="2fa26-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="2fa26-109">Ці зв’язки допомагають зв’язувати записи профілів клієнтів з іншими записами відповідних сутностей.</span><span class="sxs-lookup"><span data-stu-id="2fa26-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="2fa26-110">На схемі нижче демонструється створення трьох системних зв’язків, коли сутність клієнта зіставляється з додатковими сутностями для отримання кінцевої сутності «Профіль клієнта».</span><span class="sxs-lookup"><span data-stu-id="2fa26-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2fa26-111">![Створення зв’язку](media/relationships-entities-merge.png "Створення зв’язку")</span><span class="sxs-lookup"><span data-stu-id="2fa26-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="2fa26-112">**Зв’язок *CustomerToContact*** створено між сутністю «Клієнт» та сутністю «Контактна особа».</span><span class="sxs-lookup"><span data-stu-id="2fa26-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="2fa26-113">Сутність клієнта отримує поле ключа **Contact_contactId** для зв’язку з полем ключа сутності «Контактна особа» **contactId**.</span><span class="sxs-lookup"><span data-stu-id="2fa26-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="2fa26-114">**Зв’язок *CustomerToAccount*** створено між сутністю «Клієнт» та сутністю «Бізнес-партнер».</span><span class="sxs-lookup"><span data-stu-id="2fa26-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="2fa26-115">Сутність клієнта отримує поле ключа **Account_accountId** для зв’язку з полем ключа сутності «Бізнес-партнер» **accountId**.</span><span class="sxs-lookup"><span data-stu-id="2fa26-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="2fa26-116">**Зв’язок *CustomerToWebAccount*** створено між сутністю «Клієнт» та сутністю «Веб-бізнес-партнер».</span><span class="sxs-lookup"><span data-stu-id="2fa26-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="2fa26-117">Сутність клієнта отримує поле ключа **WebAccount_webaccountId** для зв’язку з полем ключа сутності «Веб-бізнес-партнер» **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="2fa26-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="2fa26-118">Створити зв’язок</span><span class="sxs-lookup"><span data-stu-id="2fa26-118">Create a relationship</span></span>

<span data-ttu-id="2fa26-119">Визначте настроювані зв’язки на сторінці **Зв’язки**.</span><span class="sxs-lookup"><span data-stu-id="2fa26-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="2fa26-120">Кожний зв’язок складається з вихідної сутності (сутності, що містить зовнішній ключ) і цільової сутності (сутності, на яку вказує зовнішній ключ вихідної сутності).</span><span class="sxs-lookup"><span data-stu-id="2fa26-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="2fa26-121">У розділі «Аналіз аудиторії» виберіть **Дані** > **Зв'язки**.</span><span class="sxs-lookup"><span data-stu-id="2fa26-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="2fa26-122">Виберіть елемент **Створити зв’язок**.</span><span class="sxs-lookup"><span data-stu-id="2fa26-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="2fa26-123">В області **Додати зв’язок** введіть зазначені нижче відомості.</span><span class="sxs-lookup"><span data-stu-id="2fa26-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2fa26-124">![Введіть відомості про зв’язок](media/relationships-add.png "Введіть відомості про зв’язок")</span><span class="sxs-lookup"><span data-stu-id="2fa26-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="2fa26-125">**Ім’я зв’язку**: ім’я, яке відображає ціль зв’язку (наприклад, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="2fa26-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="2fa26-126">**Опис**: опис зв’язку.</span><span class="sxs-lookup"><span data-stu-id="2fa26-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="2fa26-127">**Вихідна сутність**: виберіть сутність, яка використовується як джерело у зв’язку (наприклад, WebLog).</span><span class="sxs-lookup"><span data-stu-id="2fa26-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="2fa26-128">**Кратність**: виберіть кратність записів вихідної сутності.</span><span class="sxs-lookup"><span data-stu-id="2fa26-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="2fa26-129">Наприклад, «багато» означає, що кілька записів Weblog зв’язано з одним веб-бізнес-партнером.</span><span class="sxs-lookup"><span data-stu-id="2fa26-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="2fa26-130">**Поле вихідного ключа**: це відповідає полю зовнішнього ключа у вихідній сутності.</span><span class="sxs-lookup"><span data-stu-id="2fa26-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="2fa26-131">Наприклад, WebLog має поле зовнішнього ключа **accountId**.</span><span class="sxs-lookup"><span data-stu-id="2fa26-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="2fa26-132">**Цільова сутність**: виберіть сутність, яка використовується як цільовий об’єкт у зв’язку (наприклад, веб-бізнес-партнер).</span><span class="sxs-lookup"><span data-stu-id="2fa26-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="2fa26-133">**Кратність цільового об’єкта**: виберіть кратність записів цільової сутності.</span><span class="sxs-lookup"><span data-stu-id="2fa26-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="2fa26-134">Наприклад, «один» означає, що кілька записів Weblog зв’язано з одним веб-бізнес-партнером.</span><span class="sxs-lookup"><span data-stu-id="2fa26-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="2fa26-135">**Поле цільового ключа**: це відповідає полю ключа цільової сутності.</span><span class="sxs-lookup"><span data-stu-id="2fa26-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="2fa26-136">Наприклад, веб-бізнес-партнер має поле ключа **accountId**.</span><span class="sxs-lookup"><span data-stu-id="2fa26-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="2fa26-137">Підтримуються лише зв’язки «багато-до-одного» та «один-до-одного».</span><span class="sxs-lookup"><span data-stu-id="2fa26-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="2fa26-138">Зв’язки «багато-до-багатьох» можна створити за допомогою двох зв’язків «багато-до-одного» та сутності зв’язування (сутності, що використовується для зв’язування вихідної сутності та цільової сутності).</span><span class="sxs-lookup"><span data-stu-id="2fa26-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="2fa26-139">Видалення зв’язку</span><span class="sxs-lookup"><span data-stu-id="2fa26-139">Delete a relationship</span></span>

1. <span data-ttu-id="2fa26-140">У розділі «Аналіз аудиторії» виберіть **Дані** > **Зв'язки**.</span><span class="sxs-lookup"><span data-stu-id="2fa26-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="2fa26-141">Установіть прапорці навпроти зв’язків, які потрібно видалити.</span><span class="sxs-lookup"><span data-stu-id="2fa26-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="2fa26-142">Натисніть кнопку **Видалити** у верхній частині таблиці **Зв’язку**.</span><span class="sxs-lookup"><span data-stu-id="2fa26-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="2fa26-143">Підтвердьте видалення.</span><span class="sxs-lookup"><span data-stu-id="2fa26-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="2fa26-144">Наступний крок...</span><span class="sxs-lookup"><span data-stu-id="2fa26-144">Next step</span></span>

<span data-ttu-id="2fa26-145">Системні та настроювані зв’язки використовуються для створення сегментів на основі кількох джерел даних, які більше не є ізольованими.</span><span class="sxs-lookup"><span data-stu-id="2fa26-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="2fa26-146">Додаткові відомості див. в розділі [Сегменти](segments.md).</span><span class="sxs-lookup"><span data-stu-id="2fa26-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]