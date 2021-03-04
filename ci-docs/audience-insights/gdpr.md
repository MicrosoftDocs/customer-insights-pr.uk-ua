---
title: Запити прав суб’єкта даних (DSR) відповідно до GDPR | Microsoft Docs
description: Відповідь на запити суб'єкта прав для можливості аналізу аудиторії в Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268711"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="2d550-103">Запити прав суб'єкта даних (DSR) відповідно до GDPR</span><span class="sxs-lookup"><span data-stu-id="2d550-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="2d550-104">Відповідь на запити про видалення суб'єкта прав GDPR для можливості аналізу аудиторії в Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2d550-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="2d550-105">«Право на видалення» шляхом видалення персональних даних з даних клієнтів організації є ключовим в Генеральному регламенті із захисту персональних даних (GDPR).</span><span class="sxs-lookup"><span data-stu-id="2d550-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="2d550-106">Видалення особистих даних передбачає видалення всіх особистих даних і журналів, створених системою, за винятком відомостей журналу відстеження.</span><span class="sxs-lookup"><span data-stu-id="2d550-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="2d550-107">Керування запитами на видалення суб’єкта даних</span><span class="sxs-lookup"><span data-stu-id="2d550-107">Manage data subject delete requests</span></span>

<span data-ttu-id="2d550-108">Аналіз аудиторії пропонує такі функції в продукті для видалення персональних даних для певного клієнта або користувача.</span><span class="sxs-lookup"><span data-stu-id="2d550-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="2d550-109">**Керування запитами на видалення для даних клієнтів**: дані клієнтів у Customer Insights потрапляють з вихідних джерел даних, що знаходяться за межами Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2d550-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="2d550-110">Усі запити на видалення в межах GDPR потрібно виконувати у вихідному джерелі даних.</span><span class="sxs-lookup"><span data-stu-id="2d550-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="2d550-111">**Керування запитами на видалення даних користувача Customer Insights**: дані для користувачів створюються Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2d550-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="2d550-112">Усі запити на видалення в межах GDPR мають виконуватися в програмі Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2d550-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="2d550-113">Керування запитами на видалення для даних клієнтів</span><span class="sxs-lookup"><span data-stu-id="2d550-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="2d550-114">Адміністратор Customer Insights може виконати зазначені нижче кроки, щоб видалити дані про клієнта, що були видалені у джерелі даних.</span><span class="sxs-lookup"><span data-stu-id="2d550-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="2d550-115">Увійти до Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2d550-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="2d550-116">У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.</span><span class="sxs-lookup"><span data-stu-id="2d550-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="2d550-117">Для кожного джерела даних у списку, що містить видалені дані про клієнта, виконайте зазначені нижче дії.</span><span class="sxs-lookup"><span data-stu-id="2d550-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="2d550-118">Виберіть (...), а потім виберіть **Оновити**.</span><span class="sxs-lookup"><span data-stu-id="2d550-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="2d550-119">Перевірте стан джерела даних в області **Стан**.</span><span class="sxs-lookup"><span data-stu-id="2d550-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="2d550-120">Галочка у полі означає, що оновлення пройшло успішно.</span><span class="sxs-lookup"><span data-stu-id="2d550-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="2d550-121">Попереджувальний трикутник означає, що сталася помилка.</span><span class="sxs-lookup"><span data-stu-id="2d550-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="2d550-122">Якщо відображається попереджувальний трикутник, зверніться за адресою D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2d550-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2d550-123">![Обробка запитів на видалення відповідно до GDPR для даних клієнтів](media/gdpr-data-sources.png "Обробка запитів на видалення відповідно до GDPR для даних клієнтів")</span><span class="sxs-lookup"><span data-stu-id="2d550-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="2d550-124">Керування запитами на видалення для даних користувача</span><span class="sxs-lookup"><span data-stu-id="2d550-124">Manage delete requests for user data</span></span>

<span data-ttu-id="2d550-125">Адміністратор Customer Insights може виконати ці кроки, щоб видалити дані користувача Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2d550-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="2d550-126">Увійти до Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2d550-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="2d550-127">У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Дозволи**.</span><span class="sxs-lookup"><span data-stu-id="2d550-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="2d550-128">Установіть прапорець навпроти користувача, якого потрібно видалити.</span><span class="sxs-lookup"><span data-stu-id="2d550-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="2d550-129">Натисніть **Видалити**.</span><span class="sxs-lookup"><span data-stu-id="2d550-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2d550-130">![Обробка запитів GDPR на видалення даних користувача](media/gdpr-permissions.png "Обробка запитів GDPR на видалення для даних користувача")</span><span class="sxs-lookup"><span data-stu-id="2d550-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="2d550-131">Відповідь на запити на експорт суб’єкта даних GDPR</span><span class="sxs-lookup"><span data-stu-id="2d550-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="2d550-132">У рамках виконання наших зобов’язань підтримувати партнерство з вами на шляху до Генерального регламенту із захисту персональних даних (GDPR) ми розробили документацію, яка допоможе вам підготуватися.</span><span class="sxs-lookup"><span data-stu-id="2d550-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="2d550-133">У цій документації описано кроки, які можна вжити сьогодні для підтримки відповідності GDPR під час використання аналізу аудиторії.</span><span class="sxs-lookup"><span data-stu-id="2d550-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="2d550-134">Керування запитами на експорт і перегляд</span><span class="sxs-lookup"><span data-stu-id="2d550-134">Manage export and view requests</span></span>

<span data-ttu-id="2d550-135">Право на перенесення даних дозволяє суб’єктам даних запитувати копію своїх особистих даних у електронному форматі (за визначенням, у «структурованому, загальновживаному та сумісному форматі, що може бути зчитаний машиною»), яка може бути передана до іншого контролера даних.</span><span class="sxs-lookup"><span data-stu-id="2d550-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="2d550-136">Експорт даних клієнтів (адміністратор клієнта)</span><span class="sxs-lookup"><span data-stu-id="2d550-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="2d550-137">Щоб експортувати дані, адміністратор клієнта може має виконати такі кроки.</span><span class="sxs-lookup"><span data-stu-id="2d550-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="2d550-138">Надіслати повідомлення електронної пошти на адресу D365CI@microsoft.com, в якому вказати адресу електронної пошти клієнта в заявці.</span><span class="sxs-lookup"><span data-stu-id="2d550-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="2d550-139">Команда Customer Insights надішле електронне повідомлення на зареєстровану адресу електронної пошти адміністратора клієнта із запитом підтвердження експорту даних.</span><span class="sxs-lookup"><span data-stu-id="2d550-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="2d550-140">Отримати підтвердження експорту даних для клієнта, щодо якого створено запит.</span><span class="sxs-lookup"><span data-stu-id="2d550-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="2d550-141">Отримати експортовані дані на адресу електронної пошти адміністратора клієнта.</span><span class="sxs-lookup"><span data-stu-id="2d550-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="2d550-142">Експорт даних користувачів (адміністратор клієнта).</span><span class="sxs-lookup"><span data-stu-id="2d550-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="2d550-143">Надіслати повідомлення електронної пошти на адресу D365CI@microsoft.com, в якому вказати адресу електронної пошти користувача в заявці.</span><span class="sxs-lookup"><span data-stu-id="2d550-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="2d550-144">Команда Customer Insights надішле електронне повідомлення на зареєстровану адресу електронної пошти адміністратора клієнта із запитом підтвердження експорту даних.</span><span class="sxs-lookup"><span data-stu-id="2d550-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="2d550-145">Отримати підтвердження експорту даних для користувача, щодо якого створено запит.</span><span class="sxs-lookup"><span data-stu-id="2d550-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="2d550-146">Отримати експортовані дані на адресу електронної пошти адміністратора клієнта.</span><span class="sxs-lookup"><span data-stu-id="2d550-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]