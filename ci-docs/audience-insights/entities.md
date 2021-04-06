---
title: Сутності та набори даних
description: Перегляд даних на сторінці «Сутності».
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596432"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="526e1-103">Сутності в аналізі аудиторії</span><span class="sxs-lookup"><span data-stu-id="526e1-103">Entities in audience insights</span></span>

<span data-ttu-id="526e1-104">Після [налаштування джерел даних](data-sources.md) перейдіть на сторінку **Сутності**, щоб оцінити якість доданих даних.</span><span class="sxs-lookup"><span data-stu-id="526e1-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="526e1-105">Сутності вважаються наборами даних.</span><span class="sxs-lookup"><span data-stu-id="526e1-105">Entities are considered datasets.</span></span> <span data-ttu-id="526e1-106">На основі цих сутностей створені численні можливості Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="526e1-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="526e1-107">Їх докладний перегляд допоможе перевірити вихідні дані цих можливостей.</span><span class="sxs-lookup"><span data-stu-id="526e1-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="526e1-108">На сторінці **Сутності** відображаються сутності та містяться кілька стовпців:</span><span class="sxs-lookup"><span data-stu-id="526e1-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="526e1-109">**Ім’я**: ім’я сутності даних.</span><span class="sxs-lookup"><span data-stu-id="526e1-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="526e1-110">Якщо поруч із іменем сутності відображається символ попередження, це означає, що дані для цієї сутності завантажено з помилкою.</span><span class="sxs-lookup"><span data-stu-id="526e1-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="526e1-111">**Джерело**: тип джерела даних, яке додало сутність</span><span class="sxs-lookup"><span data-stu-id="526e1-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="526e1-112">**Автор**: ім’я особи, яка створила сутність</span><span class="sxs-lookup"><span data-stu-id="526e1-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="526e1-113">**Створено**: дата й час створення сутності</span><span class="sxs-lookup"><span data-stu-id="526e1-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="526e1-114">**Автор оновлення**: ім’я особи, яка оновила сутність</span><span class="sxs-lookup"><span data-stu-id="526e1-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="526e1-115">**Дата останнього оновлення**: дата й час останнього оновлення сутності</span><span class="sxs-lookup"><span data-stu-id="526e1-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="526e1-116">**Останнє оновлення**: дата й час останнього оновлення даних</span><span class="sxs-lookup"><span data-stu-id="526e1-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="526e1-117">Ознайомлення з даними певної сутності</span><span class="sxs-lookup"><span data-stu-id="526e1-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="526e1-118">Виберіть сутність для ознайомлення з різними полями та записами, що містяться в цій сутності.</span><span class="sxs-lookup"><span data-stu-id="526e1-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="526e1-119">![Вибір сутності](media/data-manager-entities-data.png "Вибір сутності")</span><span class="sxs-lookup"><span data-stu-id="526e1-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="526e1-120">Вкладку **Дані** вибрано за замовчуванням. На цій вкладці відображається таблиця з переліком відомостей про окремі записи сутності.</span><span class="sxs-lookup"><span data-stu-id="526e1-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="526e1-121">![Таблиця полів](media/data-manager-entities-fields.PNG "Таблиця полів")</span><span class="sxs-lookup"><span data-stu-id="526e1-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="526e1-122">На вкладці **Поля** відображається таблиця, в якій можна переглянути докладні відомості про вибрану сутність (наприклад, імена полів, типи даних і типи).</span><span class="sxs-lookup"><span data-stu-id="526e1-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="526e1-123">У стовпці **Тип** відображаються зв’язані типи даних Common Data Model, які автоматично визначені системою або [зіставлені вручну](map-entities.md) користувачами.</span><span class="sxs-lookup"><span data-stu-id="526e1-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="526e1-124">Це семантичні типи, які можуть відрізнятися від типів даних атрибутів. Наприклад, поле *Адреса електронної пошти* нижче має тип даних *Тест*, але його (семантичний) тип Common Data Model може бути *Адреса електронної пошти* або *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="526e1-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="526e1-125">У обох таблицях відображаються лише приклади даних сутності.</span><span class="sxs-lookup"><span data-stu-id="526e1-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="526e1-126">Щоб переглянути повний набір даних, перейдіть на сторінку **Джерела даних**, виберіть сутність, виберіть елемент **Редагувати**, а потім перегляньте дані цієї сутності за допомогою редактора Power Query, як описано в розділі [Джерела даних](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="526e1-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="526e1-127">Для отримання додаткових відомостей про додані до сутності дані, стовпець **Зведення** надає кілька важливих характеристик даних (наприклад, Null-значення, відсутні значення, унікальні значення, кількість і розподіли) відповідно до ваших даних.</span><span class="sxs-lookup"><span data-stu-id="526e1-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="526e1-128">Виберіть піктограму діаграми, щоб переглянути зведені дані.</span><span class="sxs-lookup"><span data-stu-id="526e1-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="526e1-129">![Символ зведення](media/data-manager-entities-summary.png "Зведена таблиця даних")</span><span class="sxs-lookup"><span data-stu-id="526e1-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="526e1-130">Наступний крок...</span><span class="sxs-lookup"><span data-stu-id="526e1-130">Next step</span></span>

<span data-ttu-id="526e1-131">Див. розділ [Уніфікація](data-unification.md), щоб дізнатися, як *зіставляти*, *шукати відповідності* та *об’єднувати* додані дані.</span><span class="sxs-lookup"><span data-stu-id="526e1-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]