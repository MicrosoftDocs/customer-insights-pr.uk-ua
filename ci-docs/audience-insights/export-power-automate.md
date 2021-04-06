---
title: З’єднувач Power Automate | Microsoft Docs
description: Створення циклів у Microsoft Power Automate з Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597950"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="a5cd0-103">З’єднувач Power Automate (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="a5cd0-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="a5cd0-104">Ініціюйте автоматичний запуск певних подій під час змінення даних і керуйте складнішими потоками безпосередньо в [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="a5cd0-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="a5cd0-105">Тригери Power Automate</span><span class="sxs-lookup"><span data-stu-id="a5cd0-105">Power Automate triggers</span></span>

<span data-ttu-id="a5cd0-106">Використовуйте тригери для створення хмарних циклів та автоматизації повторюваних завдань, таких як сповіщення або більш складні дії.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="a5cd0-107">Тригер на помилку під час оновлення джерела даних.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="a5cd0-108">Тригер на успішне оновлення джерела даних.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="a5cd0-109">Тригер на перетин межі для граничного значення для сегмента.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="a5cd0-110">Тригер спрацьовує лише при перевищенні обмеження.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="a5cd0-111">Тригер на перетин межі для граничного значення для бізнес-показника.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="a5cd0-112">Тригер спрацьовує лише при перевищенні обмеження.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="a5cd0-113">Тригер після завершення повного оновлення (джерела даних, сегменти, показники,...).</span><span class="sxs-lookup"><span data-stu-id="a5cd0-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="a5cd0-114">Ініціюється, коли завершується оновлення процесу уніфікації (зіставлення, відповідність, злиття).</span><span class="sxs-lookup"><span data-stu-id="a5cd0-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="a5cd0-115">[Налаштування тригерів у Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="a5cd0-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="a5cd0-116">Дії Power Automate</span><span class="sxs-lookup"><span data-stu-id="a5cd0-116">Power Automate actions</span></span>
<span data-ttu-id="a5cd0-117">З'єднувач Power Automate, окрім тригерів, пропонує й інші дії.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="a5cd0-118">Додаткову інформацію наведено в посібнику[Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="a5cd0-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="a5cd0-119">Створіть цикл Power Automate</span><span class="sxs-lookup"><span data-stu-id="a5cd0-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="a5cd0-120">У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a5cd0-121">На плитці **Power Automate** виберіть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="a5cd0-122">Відкриється з’єднувач Customer Insights (підготовча версія) у Power Automate.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="a5cd0-123">**Увійти до** Power Automate.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="a5cd0-124">Виберіть один із доступних тригерів і додайте більше кроків до нового циклу.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="a5cd0-125">Додаткові відомості: [Створення хмарних циклів у Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="a5cd0-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="a5cd0-126">Приклади використання циклів:</span><span class="sxs-lookup"><span data-stu-id="a5cd0-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="a5cd0-127">Надішліть повідомлення в канал Microsoft Teams, якщо оновлення джерела даних невдале.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="a5cd0-128">Надсилайте повідомлення електронної пошти власникам даних, коли буде досягнуто граничне значення для сегмента.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]