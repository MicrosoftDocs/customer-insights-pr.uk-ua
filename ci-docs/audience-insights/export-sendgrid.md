---
title: Експорт даних Customer Insights до SendGrid
description: Дізнайтеся, як налаштувати підключення та експорт до SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976941"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="7ddfe-103">Експорт сегментів до SendGrid (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="7ddfe-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="7ddfe-104">Експортуйте сегменти уніфікованих профілів клієнтів до списків контактних осіб SendGrid і використовуйте їх для кампаній та маркетингових електронних розсилок в SendGrid.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="7ddfe-105">Попередні вимоги для підключення</span><span class="sxs-lookup"><span data-stu-id="7ddfe-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="7ddfe-106">Ви маєте [обліковий запис SendGrid](https://sendgrid.com/) і відповідні облікові дані адміністратора.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7ddfe-107">У SendGrid наявні списки контактних осіб й відповідні ідентифікатори.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="7ddfe-108">Для отримання додаткових відомостей див. [SendGrid — Керування контактними особами](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="7ddfe-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="7ddfe-109">Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="7ddfe-110">Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7ddfe-111">Відомі обмеження</span><span class="sxs-lookup"><span data-stu-id="7ddfe-111">Known limitations</span></span>

- <span data-ttu-id="7ddfe-112">До 100 000 профілів в цілому до SendGrid.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="7ddfe-113">Експорт до SendGrid обмежується сегментами.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="7ddfe-114">Експортування до 100 000 профілів до SendGrid може тривати кілька годин.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="7ddfe-115">Кількість профілів, які можна експортувати до SendGrid, залежить від сервісного договору з SendGrid.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="7ddfe-116">Налаштування підключення до SendGrid</span><span class="sxs-lookup"><span data-stu-id="7ddfe-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="7ddfe-117">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7ddfe-118">Виберіть **Додати підключення** та оберіть **SendGrid**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="7ddfe-119">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7ddfe-120">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7ddfe-121">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7ddfe-122">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-122">Choose who can use this connection.</span></span> <span data-ttu-id="7ddfe-123">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7ddfe-124">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7ddfe-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7ddfe-125">Введіть **ключ API SendGrid** [ключ API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="7ddfe-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="7ddfe-126">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7ddfe-127">Виберіть **Підключити**, щоб ініціалізувати підключення до SendGrid.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="7ddfe-128">Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7ddfe-129">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="7ddfe-130">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="7ddfe-130">Configure an export</span></span>

<span data-ttu-id="7ddfe-131">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7ddfe-132">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7ddfe-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7ddfe-133">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7ddfe-134">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7ddfe-135">У полі **Підключення для експорту** виберіть підключення з розділу SendGrid.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="7ddfe-136">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7ddfe-137">Введіть **[ідентифікатор списку SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="7ddfe-138">У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7ddfe-139">Повторіть ці самі кроки для інших необов'язкових полів, таких як **Ім'я**, **Прізвище**, **Країна або регіон**, **Штат**, **Місто** і **Поштовий індекс**.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="7ddfe-140">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-140">Select the segments you want to export.</span></span> <span data-ttu-id="7ddfe-141">Ми настійно **рекомендуємо не експортувати більше 100 000 профілів клієнтів в цілому** до SendGrid.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="7ddfe-142">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-142">Select **Save**.</span></span>

<span data-ttu-id="7ddfe-143">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7ddfe-144">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7ddfe-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7ddfe-145">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7ddfe-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7ddfe-146">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="7ddfe-146">Data privacy and compliance</span></span>

<span data-ttu-id="7ddfe-147">Коли ви вмикаєте передавання даних до SendGrid у Dynamics 365 Customer Insights, ви дозволяєте перенесення даних за межі нормативного регіону для Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7ddfe-148">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але на вас покладено усю відповідальність за забезпечення того, щоб компанія SendGrid відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="7ddfe-149">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7ddfe-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7ddfe-150">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="7ddfe-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]