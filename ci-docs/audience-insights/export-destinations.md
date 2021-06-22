---
title: Експорт даних з Customer Insights
description: Керування експортом для надання спільного доступу до даних.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253065"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="d6fff-103">Огляд експорту (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="d6fff-103">Exports (preview) overview</span></span>

<span data-ttu-id="d6fff-104">На сторінці **Експорти** буде показано всі налаштовані експорти.</span><span class="sxs-lookup"><span data-stu-id="d6fff-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="d6fff-105">Експорти дозволяють надати спільний доступ до певних даних різноманітним програмам.</span><span class="sxs-lookup"><span data-stu-id="d6fff-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="d6fff-106">До таких даних можуть входити профілі або сутності клієнтів, схеми та відомості про зіставлення.</span><span class="sxs-lookup"><span data-stu-id="d6fff-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="d6fff-107">Для кожного експорту потрібне [підключення, настроєне адміністратором, щоб керувати автентифікацією та доступом](connections.md).</span><span class="sxs-lookup"><span data-stu-id="d6fff-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="d6fff-108">Відкрийте послідовно **Дані** > **Експорти**, щоб переглянути сторінку експортів.</span><span class="sxs-lookup"><span data-stu-id="d6fff-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="d6fff-109">Усі ролі користувачів мають доступ до перегляду налаштованих експортів.</span><span class="sxs-lookup"><span data-stu-id="d6fff-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="d6fff-110">Використовуйте поле пошуку на панелі команд, щоб знайти експорти за іменем, іменем підключення або типом підключення.</span><span class="sxs-lookup"><span data-stu-id="d6fff-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="d6fff-111">Налаштування нового експорту</span><span class="sxs-lookup"><span data-stu-id="d6fff-111">Set up a new export</span></span>

<span data-ttu-id="d6fff-112">Щоб налаштувати або відредагувати експорт, потрібно мати доступ до підключень.</span><span class="sxs-lookup"><span data-stu-id="d6fff-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="d6fff-113">Підключення залежатимуть від [ролі користувача](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="d6fff-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="d6fff-114">Адміністратори мають доступ до всіх підключень.</span><span class="sxs-lookup"><span data-stu-id="d6fff-114">Administrators have access to all connections.</span></span> <span data-ttu-id="d6fff-115">Вони також можуть створювати нові підключення під час налаштування експорту.</span><span class="sxs-lookup"><span data-stu-id="d6fff-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="d6fff-116">Співавтори можуть мати доступ до певних підключень.</span><span class="sxs-lookup"><span data-stu-id="d6fff-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="d6fff-117">Вони залежать від того, які підключення налаштували та надали для спільного доступу адміністратори.</span><span class="sxs-lookup"><span data-stu-id="d6fff-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="d6fff-118">У списку експортів відображаються співавтори, а також, у стовпці **Ваші дозволи**, показано, чи можуть вони редагувати або ж тільки переглядати експорти.</span><span class="sxs-lookup"><span data-stu-id="d6fff-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="d6fff-119">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d6fff-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="d6fff-120">Глядачі можуть лише переглядати наявні експорти, і не можуть створювати їх.</span><span class="sxs-lookup"><span data-stu-id="d6fff-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="d6fff-121">Визначення нового експорту</span><span class="sxs-lookup"><span data-stu-id="d6fff-121">Define a new export</span></span>

1. <span data-ttu-id="d6fff-122">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d6fff-123">Виберіть **Додати експорт**, щоб створити новий експорт.</span><span class="sxs-lookup"><span data-stu-id="d6fff-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="d6fff-124">В області **Настроювання експорту** виберіть, яке підключення слід використовувати.</span><span class="sxs-lookup"><span data-stu-id="d6fff-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="d6fff-125">Керування [Підключеннями](connections.md) виконують адміністратори.</span><span class="sxs-lookup"><span data-stu-id="d6fff-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="d6fff-126">Укажіть потрібні відомості та виберіть **Зберегти**, щоб створити експорт.</span><span class="sxs-lookup"><span data-stu-id="d6fff-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="d6fff-127">Визначення нового експорту на основі наявного експорту</span><span class="sxs-lookup"><span data-stu-id="d6fff-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="d6fff-128">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d6fff-129">У списку експортів виберіть експорт, дублікат якого потрібно створити.</span><span class="sxs-lookup"><span data-stu-id="d6fff-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="d6fff-130">Натисніть **Створити дублікат** на панелі команд, щоб відкрити область **Настройка експорту** із докладними відомостями про вибраний експорт.</span><span class="sxs-lookup"><span data-stu-id="d6fff-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="d6fff-131">Перегляньте та скоригуйте параметри експорту, а тоді виберіть **Зберегти**, щоб створити новий експорт.</span><span class="sxs-lookup"><span data-stu-id="d6fff-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="d6fff-132">Редагування експорту</span><span class="sxs-lookup"><span data-stu-id="d6fff-132">Edit an export</span></span>

1. <span data-ttu-id="d6fff-133">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d6fff-134">У списку експортів виберіть експорт, який потрібно відредагувати.</span><span class="sxs-lookup"><span data-stu-id="d6fff-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="d6fff-135">Виберіть **Редагувати** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="d6fff-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="d6fff-136">Змініть потрібні значення, а тоді виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="d6fff-137">Перегляд експортів і відомостей про експорт</span><span class="sxs-lookup"><span data-stu-id="d6fff-137">View exports and export details</span></span>

<span data-ttu-id="d6fff-138">Після створення призначень експорту вони відобразяться в розділі **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="d6fff-139">Усі користувачі зможуть побачити, до яких даних надано спільний доступ, а також останній стан даних.</span><span class="sxs-lookup"><span data-stu-id="d6fff-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="d6fff-140">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d6fff-141">Користувачі, які не мають дозволів на редагування, для перегляду відомостей експорту повинні вибирати **Перегляд** замість **Редагувати**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="d6fff-142">На бічній панелі показано налаштування експорту.</span><span class="sxs-lookup"><span data-stu-id="d6fff-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="d6fff-143">Без дозволів на редагування змінювати значення не можна.</span><span class="sxs-lookup"><span data-stu-id="d6fff-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="d6fff-144">Виберіть **Закрити**, щоб повернутися до сторінки експортів.</span><span class="sxs-lookup"><span data-stu-id="d6fff-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="d6fff-145">Створення розкладу та запуск експортів</span><span class="sxs-lookup"><span data-stu-id="d6fff-145">Schedule and run exports</span></span>

<span data-ttu-id="d6fff-146">Для кожного експорту, який ви налаштовані, має розклад оновлення.</span><span class="sxs-lookup"><span data-stu-id="d6fff-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="d6fff-147">При оновлення система шукає нові або оновлені дані, які слід включити до експорту.</span><span class="sxs-lookup"><span data-stu-id="d6fff-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="d6fff-148">За замовчуванням експорти виконуються під час кожного [запланованого в системі оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d6fff-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d6fff-149">Можна настроїти розклад оновлень або вимкнути його і запускати експорти вручну.</span><span class="sxs-lookup"><span data-stu-id="d6fff-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="d6fff-150">Розклади експортів залежать від стану середовища.</span><span class="sxs-lookup"><span data-stu-id="d6fff-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="d6fff-151">Якщо на час запланованого запуску експорту іде процес оновлень [залежностей](system.md#refresh-policies), система спочатку завершить роботу із залежностями, а тоді запустить експорт.</span><span class="sxs-lookup"><span data-stu-id="d6fff-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="d6fff-152">Ви можете побачити, коли востаннє оновлювався експорт, у стовпці **Оновлено**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="d6fff-153">Планування експортів</span><span class="sxs-lookup"><span data-stu-id="d6fff-153">Schedule exports</span></span>

<span data-ttu-id="d6fff-154">Ви можете визначити користувацький розклад оновлень для окремого експорту або ж одразу для кількох експортів.</span><span class="sxs-lookup"><span data-stu-id="d6fff-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="d6fff-155">Поточний розклад, визначений для експорту, можна побачити у стовпці **Розклад** у списку експортів.</span><span class="sxs-lookup"><span data-stu-id="d6fff-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="d6fff-156">Для змінення розкладу потрібен такий самий дозвіл, як для [редагування та визначення експортів](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d6fff-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="d6fff-157">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d6fff-158">Виберіть експорт, для якого потрібно створити розклад.</span><span class="sxs-lookup"><span data-stu-id="d6fff-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="d6fff-159">Виберіть **Розклад** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="d6fff-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="d6fff-160">В області **Розклад експорту** установіть для параметра **Запланувати запуск** значення **Увімкнуто**, щоб виконувати експорт автоматично.</span><span class="sxs-lookup"><span data-stu-id="d6fff-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="d6fff-161">Щоб оновлювати експорт вручну, установіть тут значення **Вимкнуто**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="d6fff-162">Для тих експортів, що оновлюються автоматично, виберіть значення **Повторення** та вкажіть для нього відомості.</span><span class="sxs-lookup"><span data-stu-id="d6fff-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="d6fff-163">Визначений час застосовується до всіх екземплярів повторення.</span><span class="sxs-lookup"><span data-stu-id="d6fff-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="d6fff-164">Це час, коли експорт має почати оновлення.</span><span class="sxs-lookup"><span data-stu-id="d6fff-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="d6fff-165">Застосуйте та активуйте зміни, вибравши **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="d6fff-166">Під час редагування розкладу для кількох експортів потрібно зробити вибір в області **Залишити або змінити розклади**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="d6fff-167">**Зберегти окремі розклади**: залиште раніше визначений розклад для вибраних експортів, лише вимкніть або увімкніть їх.</span><span class="sxs-lookup"><span data-stu-id="d6fff-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="d6fff-168">**Визначити новий розклад для всіх вибраних експортів**: змініть наявні розклади для вибраних експортів.</span><span class="sxs-lookup"><span data-stu-id="d6fff-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="d6fff-169">Запуск експортів на вимогу</span><span class="sxs-lookup"><span data-stu-id="d6fff-169">Run exports on demand</span></span>

<span data-ttu-id="d6fff-170">Щоб експортувати дані, не чекаючи запланованого оновлення, відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="d6fff-171">Щоб виконати всі експорти, виберіть **Виконати все** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="d6fff-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="d6fff-172">При виконанні цієї дії запустяться лише ті експорти, що мають активний розклад.</span><span class="sxs-lookup"><span data-stu-id="d6fff-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="d6fff-173">Щоб запустити один окремий експорт, виберіть його у списку, а тоді виберіть **Запуск** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="d6fff-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="d6fff-174">Так можна запускати експорти без активного розкладу.</span><span class="sxs-lookup"><span data-stu-id="d6fff-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="d6fff-175">Видалення експорту</span><span class="sxs-lookup"><span data-stu-id="d6fff-175">Remove an Export</span></span>

1. <span data-ttu-id="d6fff-176">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="d6fff-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d6fff-177">Виберіть експорт, який потрібно видалити.</span><span class="sxs-lookup"><span data-stu-id="d6fff-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="d6fff-178">Виберіть **Видалити** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="d6fff-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="d6fff-179">Щоб підтвердити видалення, виберіть **Видалити** на екрані підтвердження.</span><span class="sxs-lookup"><span data-stu-id="d6fff-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
