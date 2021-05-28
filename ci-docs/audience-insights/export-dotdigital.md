---
title: Експорт даних Customer Insights до DotDigital
description: Дізнайтеся, як налаштувати підключення та експорт до DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976871"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="ee3ca-103">Експорт списків сегментів до DotDigital (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="ee3ca-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="ee3ca-104">Експорт сегментів уніфікованих профілів клієнтів до адресних книг DotDigital і використання їх для кампаній, маркетингових повідомлень і створення сегментів клієнтів за допомогою DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ee3ca-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="ee3ca-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ee3ca-106">Ви маєте [обліковий запис DotDigital](https://dotdigital.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ee3ca-107">Наявні адресні книги в DotDigital і відповідні ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="ee3ca-108">ІДЕНТИФІКАТОР можна знайти в URL-адресі, якщо вибрати та відкрити адресну книгу.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="ee3ca-109">Для отримання додаткових відомостей див. [адресні книги DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ee3ca-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="ee3ca-110">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ee3ca-111">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ee3ca-112">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="ee3ca-112">Known limitations</span></span>

- <span data-ttu-id="ee3ca-113">До 1 000 000 профілів на експорт до DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="ee3ca-114">Експорт до DotDigital обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="ee3ca-115">Експортування сегментів загальною кількістю 1 000 000 профілів може тривати до 3 годин через обмеження з боку постачальника.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="ee3ca-116">Кількість профілів, які можна експортувати до DotDigital, залежить від сервісного договору з DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="ee3ca-117">Налаштування підключення до DotDigital</span><span class="sxs-lookup"><span data-stu-id="ee3ca-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="ee3ca-118">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ee3ca-119">Виберіть **Додати підключення** та оберіть **DotDigital**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="ee3ca-120">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ee3ca-121">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ee3ca-122">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ee3ca-123">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-123">Choose who can use this connection.</span></span> <span data-ttu-id="ee3ca-124">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ee3ca-125">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ee3ca-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ee3ca-126">Введіть ваше **ім’я користувача DotDigital та пароль**.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="ee3ca-127">Введіть **[ідентифікатор адресної книги DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="ee3ca-128">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ee3ca-129">Виберіть **З'єднати**, щоб ініціалізувати підключення до DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="ee3ca-130">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ee3ca-131">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="ee3ca-132">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="ee3ca-132">Configure an export</span></span>

<span data-ttu-id="ee3ca-133">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ee3ca-134">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ee3ca-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ee3ca-135">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ee3ca-136">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ee3ca-137">У полі **Підключення для експорту** виберіть підключення з розділу DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="ee3ca-138">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="ee3ca-139">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ee3ca-140">Повторіть ці самі кроки для інших необов'язкових полів, наприклад **Ім'я**, **Прізвище**, **Повне ім'я**, **Стать** і **Поштовий індекс**.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="ee3ca-141">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-141">Select the segments you want to export.</span></span> <span data-ttu-id="ee3ca-142">Загалом до DotDigital можна експортувати до 1 000 000 профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="ee3ca-143">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-143">Select **Save**.</span></span>

<span data-ttu-id="ee3ca-144">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ee3ca-145">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ee3ca-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ee3ca-146">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ee3ca-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="ee3ca-147">Тепер у DotDigital можна знайти сегменти в [адресних книгах DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ee3ca-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ee3ca-148">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="ee3ca-148">Data privacy and compliance</span></span>

<span data-ttu-id="ee3ca-149">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до DotDigital можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ee3ca-150">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія DotDigital відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ee3ca-151">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ee3ca-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ee3ca-152">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="ee3ca-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
