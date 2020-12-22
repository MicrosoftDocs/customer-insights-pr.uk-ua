---
title: Підключення до сутностей у керованому озері Common Data Service
description: Імпорт даних із керованого озера даних Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643423"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="088ed-103">Підключення до даних в озері з керованим даними Common Data Service</span><span class="sxs-lookup"><span data-stu-id="088ed-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="088ed-104">У цій статті наведено відомості про те, як існуючі клієнти Dynamics 365 можуть швидко підключитися до своїх аналітичних сутностей у керованому озері Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="088ed-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="088ed-105">Для продовження та перегляду списку сутностей, доступних у керованому озері, ви повинні бути адміністратором організації Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="088ed-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="088ed-106">Важливі міркування</span><span class="sxs-lookup"><span data-stu-id="088ed-106">Important considerations</span></span>

<span data-ttu-id="088ed-107">Дані, що зберігаються в онлайнових службах, наприклад, Azure Data Lake Storage, можуть зберігатися в розташуванні, відмінному від того, в якому дані обробляються або зберігаються в Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="088ed-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="088ed-108">Імпортуючи дані, що зберігаються в онлайнових службах, або встановлюючи підключення до таких даних, ви надаєте згоду, що дані можуть передаватися до Dynamics 365 Customer Insights і зберігатися в цій службі.  [Дізнайтесь більше в Центрі безпеки та конфіденційності Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="088ed-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="088ed-109">Підключення до керованого озера Common Data Service</span><span class="sxs-lookup"><span data-stu-id="088ed-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="088ed-110">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="088ed-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="088ed-111">Виберіть **Додати джерело даних**.</span><span class="sxs-lookup"><span data-stu-id="088ed-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="088ed-112">Виберіть **Підключитися до Common Data Service**, а тоді виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="088ed-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="088ed-113">Введіть **Ім’я** джерела даних, потім виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="088ed-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="088ed-114">Укажіть **Адресу сервера** для організації Common Data Service, а потім виберіть **Увійти**.</span><span class="sxs-lookup"><span data-stu-id="088ed-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="088ed-115">![Діалогове вікно для введення адреси сервера Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="088ed-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="088ed-116">Виберіть сутності, які потрібно прийняти з доступного списку.</span><span class="sxs-lookup"><span data-stu-id="088ed-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="088ed-117">Якщо деякі сутності вже вибрано, вони, можливо, вже використовуються іншими програмами Dynamics 365 (наприклад, Dynamics 365 Sales Insights або Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="088ed-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="088ed-118">Цей вибір змінити не можна.</span><span class="sxs-lookup"><span data-stu-id="088ed-118">You can't change the selection.</span></span> <span data-ttu-id="088ed-119">Ці сутності стануть доступні після створення джерела даних.</span><span class="sxs-lookup"><span data-stu-id="088ed-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="088ed-120">![Діалогове вікно з відображенням списку сутностей в організації Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="088ed-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="088ed-121">Збережіть вибір, щоб почати синхронізацію вибраних сутностей із керованим озером Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="088ed-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="088ed-122">На сторінці **Джерела даних** ви побачите нещодавно додане підключення.</span><span class="sxs-lookup"><span data-stu-id="088ed-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="088ed-123">Воно стане у чергу на оновлення та відображатиме кількість сутностей 0, доки не буде синхронізовано всі сутності.</span><span class="sxs-lookup"><span data-stu-id="088ed-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="088ed-124">Лише одне джерело даних із середовища може одночасно використовувати кероване озеро Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="088ed-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="088ed-125">Редагування джерела даних керованого озера Common Data Service</span><span class="sxs-lookup"><span data-stu-id="088ed-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="088ed-126">Після створення джерела даних ви можете редагувати тільки вибір сутностей.</span><span class="sxs-lookup"><span data-stu-id="088ed-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="088ed-127">Наприклад, якщо до Common Data Service додано додаткові сутності, і їх також потрібно імпортувати.</span><span class="sxs-lookup"><span data-stu-id="088ed-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="088ed-128">Щоб підключися до іншої служби Common Data Service, [створіть нове джерело даних](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="088ed-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="088ed-129">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="088ed-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="088ed-130">Виберіть три крапки поряд із джерелом даних, яке ви бажаєте оновити.</span><span class="sxs-lookup"><span data-stu-id="088ed-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="088ed-131">Виберіть зі списку параметр **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="088ed-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="088ed-132">Виберіть додаткові сутності з доступного списку сутностей, а тоді виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="088ed-132">Select additional entities from the available list of entities and select **Save**.</span></span>
