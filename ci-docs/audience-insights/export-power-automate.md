---
title: З’єднувач Power Automate | Microsoft Docs
description: Створення циклів у Microsoft Power Automate із Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407232"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="c6100-103">З’єднувач Power Automate (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="c6100-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="c6100-104">Ініціюйте автоматичний запуск певних подій під час змінення даних і керуйте складнішими потоками безпосередньо в [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="c6100-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="c6100-105">Тригери Power Automate</span><span class="sxs-lookup"><span data-stu-id="c6100-105">Power Automate triggers</span></span>

<span data-ttu-id="c6100-106">Ви можете використовувати різноманітні тригери, які дозволять створювати потоки для автоматизації повторюваних завдань, наприклад, сповіщень або інших додаткових дій.</span><span class="sxs-lookup"><span data-stu-id="c6100-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="c6100-107">Тригер на помилку під час оновлення джерела даних.</span><span class="sxs-lookup"><span data-stu-id="c6100-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="c6100-108">Тригер на успішне оновлення джерела даних.</span><span class="sxs-lookup"><span data-stu-id="c6100-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="c6100-109">Тригер на перетин межі для граничного значення для сегмента.</span><span class="sxs-lookup"><span data-stu-id="c6100-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="c6100-110">Тригер спрацьовує лише при перевищенні обмеження.</span><span class="sxs-lookup"><span data-stu-id="c6100-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="c6100-111">Тригер на перетин межі для граничного значення для бізнес-показника.</span><span class="sxs-lookup"><span data-stu-id="c6100-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="c6100-112">Тригер спрацьовує лише при перевищенні обмеження.</span><span class="sxs-lookup"><span data-stu-id="c6100-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="c6100-113">Тригер після завершення повного оновлення (джерела даних, сегменти, показники,...).</span><span class="sxs-lookup"><span data-stu-id="c6100-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="c6100-114">Ініціюється, коли завершується оновлення процесу уніфікації (зіставлення, відповідність, злиття).</span><span class="sxs-lookup"><span data-stu-id="c6100-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="c6100-115">[Налаштування тригерів у Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="c6100-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="c6100-116">Дії Power Automate</span><span class="sxs-lookup"><span data-stu-id="c6100-116">Power Automate actions</span></span>
<span data-ttu-id="c6100-117">З'єднувач Power Automate, окрім тригерів, пропонує й інші дії.</span><span class="sxs-lookup"><span data-stu-id="c6100-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="c6100-118">Додаткову інформацію наведено в посібнику[Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="c6100-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="c6100-119">Створення потоку Power Automate у аналізі аудиторій</span><span class="sxs-lookup"><span data-stu-id="c6100-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="c6100-120">У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Система**.</span><span class="sxs-lookup"><span data-stu-id="c6100-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="c6100-121">На сторінці **Система** перейдіть на вкладку **Стан**.</span><span class="sxs-lookup"><span data-stu-id="c6100-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="c6100-122">У розділі **Джерела даних** виберіть **Потоки**, а потім виберіть **Створити потік** із розкривного списку.</span><span class="sxs-lookup"><span data-stu-id="c6100-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c6100-123">![З’єднувач Power Automate: дія "Створити цикл"](media/power-automate-connector-create-flow.png "З’єднувач Power Automate: дія "Створити цикл"")</span><span class="sxs-lookup"><span data-stu-id="c6100-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="c6100-124">У Power Automate виберіть один із доступних тригерів для створення потрібного потоку.</span><span class="sxs-lookup"><span data-stu-id="c6100-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="c6100-125">Під час створення першого циклу спочатку потрібно буде пройти автентифікацію за допомогою з’єднувача Power Automate.</span><span class="sxs-lookup"><span data-stu-id="c6100-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
