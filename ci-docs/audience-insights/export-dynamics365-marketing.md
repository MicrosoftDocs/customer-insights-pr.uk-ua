---
title: Експорт даних Customer Insights до Dynamics 365 Marketing
description: Дізнайтеся, як налаштувати підключення та експорт до Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759662"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="e19ce-103">Використання сегментів у Dynamics 365 Marketing (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="e19ce-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e19ce-104">Використовуйте [сегменти](segments.md), щоб формувати кампанії та специфічні групи клієнтів за допомогою Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="e19ce-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="e19ce-105">Для отримання додаткових відомостей див. [Використання сегментів з Dynamics 365 Customer Insights у Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="e19ce-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="e19ce-106">Попередня вимога для підключення</span><span class="sxs-lookup"><span data-stu-id="e19ce-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="e19ce-107">Записи контактних осіб мають бути присутніми в Dynamics 365 Marketing, щоб ви змогли експортувати сегмент з Customer Insights до Marketing.</span><span class="sxs-lookup"><span data-stu-id="e19ce-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="e19ce-108">Дізнайтеся більше про те, як прийняти контактних осіб у [Dynamics 365 Marketing, використовуючи Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e19ce-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="e19ce-109">Експортування сегментів з аналізу аудиторії до Marketing не призведе до створення нових записів контактних осіб в інсталяціях Marketing.</span><span class="sxs-lookup"><span data-stu-id="e19ce-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="e19ce-110">Записи контактних осіб з Marketing повинні бути прийняті в аналізі аудиторії та мають використовуватися, як джерело даних.</span><span class="sxs-lookup"><span data-stu-id="e19ce-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="e19ce-111">Їх також потрібно включити в уніфіковану сутність «Клієнт», щоб зіставити ідентифікатори клієнтів із ідентифікаторами контактних осіб, перш ніж можна буде експортувати сегменти.</span><span class="sxs-lookup"><span data-stu-id="e19ce-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="e19ce-112">Налаштування підключення до Marketing</span><span class="sxs-lookup"><span data-stu-id="e19ce-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="e19ce-113">Відкрийте **Адміністрування** > **Підключення**.</span><span class="sxs-lookup"><span data-stu-id="e19ce-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e19ce-114">Виберіть **Додати підключення** та оберіть **Dynamics 365 Marketing**, щоб налаштувати підключення.</span><span class="sxs-lookup"><span data-stu-id="e19ce-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="e19ce-115">Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати.</span><span class="sxs-lookup"><span data-stu-id="e19ce-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e19ce-116">Ім’я та тип підключення описують це підключення.</span><span class="sxs-lookup"><span data-stu-id="e19ce-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e19ce-117">Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.</span><span class="sxs-lookup"><span data-stu-id="e19ce-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e19ce-118">Виберіть користувачів, які зможуть використовувати це підключення.</span><span class="sxs-lookup"><span data-stu-id="e19ce-118">Choose who can use this connection.</span></span> <span data-ttu-id="e19ce-119">Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори.</span><span class="sxs-lookup"><span data-stu-id="e19ce-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e19ce-120">Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e19ce-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e19ce-121">Введіть URL-адресу Marketing вашої організації в полі **Адреса сервера**.</span><span class="sxs-lookup"><span data-stu-id="e19ce-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="e19ce-122">У розділі **Обліковий запис адміністратора сервера** виберіть **Увійти** і оберіть обліковий запис Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="e19ce-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="e19ce-123">Зіставте поле ІДЕНТИФІКАТОРА клієнта з ІДЕНТИФІКАТОРОМ контакту Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e19ce-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="e19ce-124">Щоб завершити створення підключення, виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="e19ce-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="e19ce-125">Налаштування експорту</span><span class="sxs-lookup"><span data-stu-id="e19ce-125">Configure an export</span></span>

<span data-ttu-id="e19ce-126">Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу.</span><span class="sxs-lookup"><span data-stu-id="e19ce-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e19ce-127">Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e19ce-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e19ce-128">Відкрийте **Дані** > **Експорти**.</span><span class="sxs-lookup"><span data-stu-id="e19ce-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e19ce-129">Щоб створити новий експорт, виберіть **Додати призначення**.</span><span class="sxs-lookup"><span data-stu-id="e19ce-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e19ce-130">У полі **Підключення для експорту** виберіть підключення з розділу Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="e19ce-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="e19ce-131">Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.</span><span class="sxs-lookup"><span data-stu-id="e19ce-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e19ce-132">Виберіть один або кілька сегментів.</span><span class="sxs-lookup"><span data-stu-id="e19ce-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="e19ce-133">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="e19ce-133">Select **Save**.</span></span>

<span data-ttu-id="e19ce-134">При збереженні експорт не запуститься негайно.</span><span class="sxs-lookup"><span data-stu-id="e19ce-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e19ce-135">Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e19ce-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e19ce-136">Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e19ce-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
