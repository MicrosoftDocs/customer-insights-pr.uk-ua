---
title: Експорт даних Customer Insights до Dynamics 365 Sales
description: Дізнайтеся, як налаштувати підключення та експорт до Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759629"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="1b628-103">Використання сегментів у Dynamics 365 Sales (підготовча версія).</span><span class="sxs-lookup"><span data-stu-id="1b628-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1b628-104">Використовуйте дані клієнта для створення маркетингових списків, подальших робочих циклів і надсилання промо-акцій з даними Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="1b628-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="1b628-105">Попередня вимога для підключення</span><span class="sxs-lookup"><span data-stu-id="1b628-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="1b628-106">Записи контактних осіб мають бути присутніми в Dynamics 365 Sales, щоб ви змогли експортувати сегмент з Customer Insights до Sales.</span><span class="sxs-lookup"><span data-stu-id="1b628-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="1b628-107">Дізнайтеся більше про те, як прийняти контактних осіб у [Dynamics 365 Sales, використовуючи Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="1b628-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="1b628-108">Експортування сегментів з аналізу аудиторії до Sales не призведе до створення нових записів контактних осіб в інсталяціях Sales.</span><span class="sxs-lookup"><span data-stu-id="1b628-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="1b628-109">Записи контактних осіб з Sales повинні бути прийняті в аналізі аудиторії та мають використовуватися, як джерело даних.</span><span class="sxs-lookup"><span data-stu-id="1b628-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="1b628-110">Їх також потрібно включити в уніфіковану сутність «Клієнт», щоб зіставити ідентифікатори клієнтів із ідентифікаторами контактних осіб, перш ніж можна буде експортувати сегменти.</span><span class="sxs-lookup"><span data-stu-id="1b628-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="1b628-111">Налаштування підключення до Sales</span><span class="sxs-lookup"><span data-stu-id="1b628-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="1b628-112">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="1b628-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1b628-113">Виберіть **Додати підключення** та оберіть **Dynamics 365 Sales**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="1b628-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="1b628-114">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="1b628-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1b628-115">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="1b628-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1b628-116">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="1b628-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1b628-117">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="1b628-117">Choose who can use this connection.</span></span> <span data-ttu-id="1b628-118">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="1b628-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1b628-119">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1b628-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1b628-120">Введіть URL-адресу Sales вашої організації в полі **Адреса сервера**.</span><span class="sxs-lookup"><span data-stu-id="1b628-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="1b628-121">У розділі **Обліковий запис адміністратора сервера** виберіть **Увійти** і оберіть обліковий запис Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="1b628-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="1b628-122">Зіставте поле ІДЕНТИФІКАТОРА клієнта з ІДЕНТИФІКАТОРОМ контакту Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1b628-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="1b628-123">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="1b628-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="1b628-124">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="1b628-124">Configure an export</span></span>

<span data-ttu-id="1b628-125">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="1b628-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1b628-126">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1b628-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1b628-127">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="1b628-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1b628-128">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="1b628-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1b628-129">У полі **Підключення для експорту** виберіть підключення з розділу Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="1b628-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="1b628-130">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="1b628-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1b628-131">Виберіть один або кілька сегментів.</span><span class="sxs-lookup"><span data-stu-id="1b628-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="1b628-132">Виберіть **Зберегти**</span><span class="sxs-lookup"><span data-stu-id="1b628-132">Select **Save**</span></span>

<span data-ttu-id="1b628-133">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="1b628-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1b628-134">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1b628-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1b628-135">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1b628-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
