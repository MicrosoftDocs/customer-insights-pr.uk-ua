---
title: Бот для Microsoft Teams
description: Пошук уніфікованих профілів клієнтів за допомогою Microsoft Teams з допомогою бота.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407265"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="3d87d-103">Бот команди для Dynamics 365 Customer Insights (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="3d87d-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="3d87d-104">Підключайтеся до Microsoft Teams, щоб дозволити боту шукати уніфіковані профілі клієнтів у каналах команди.</span><span class="sxs-lookup"><span data-stu-id="3d87d-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3d87d-105">![Бот для Teams, що показує запис клієнта](media/teams-bot.png "Бот для Teams, що показує запис клієнта")</span><span class="sxs-lookup"><span data-stu-id="3d87d-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3d87d-106">Вимоги</span><span class="sxs-lookup"><span data-stu-id="3d87d-106">Prerequisites</span></span>

<span data-ttu-id="3d87d-107">Для налаштування та настроювання бота повинні виконуватися нижчезазначені передумови.</span><span class="sxs-lookup"><span data-stu-id="3d87d-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3d87d-108">Додано щонайменше одне [джерело даних](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="3d87d-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="3d87d-109">Завершено [процес уніфікації](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="3d87d-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="3d87d-110">До [покажчика пошуку і фільтрації](search-filter-index.md) додано поля.</span><span class="sxs-lookup"><span data-stu-id="3d87d-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="3d87d-111">Customer Insights і Teams відносяться до однієї організації.</span><span class="sxs-lookup"><span data-stu-id="3d87d-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="3d87d-112">Настроювання бота</span><span class="sxs-lookup"><span data-stu-id="3d87d-112">Configure the bot</span></span>

1. <span data-ttu-id="3d87d-113">У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.</span><span class="sxs-lookup"><span data-stu-id="3d87d-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="3d87d-114">На плитці Microsoft Teams виберіть елемент **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="3d87d-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="3d87d-115">Вас буде переспрямовано до області **Програми** в Teams.</span><span class="sxs-lookup"><span data-stu-id="3d87d-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="3d87d-116">Також можна відкрити Teams і вибрати **Програми** в нижньому лівому куті або [отримати програму безпосередньо з AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="3d87d-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="3d87d-117">Знайдіть **Customer Insights** та виберіть програму.</span><span class="sxs-lookup"><span data-stu-id="3d87d-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="3d87d-118">Виберіть **Додати**.</span><span class="sxs-lookup"><span data-stu-id="3d87d-118">Select **Add**.</span></span>
1. <span data-ttu-id="3d87d-119">Після входу до Customer Insights у Teams відобразиться привітання, і ви зможете розпочати роботу.</span><span class="sxs-lookup"><span data-stu-id="3d87d-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="3d87d-120">Можливості, які забезпечує бот</span><span class="sxs-lookup"><span data-stu-id="3d87d-120">Things you can do with the bot</span></span>

<span data-ttu-id="3d87d-121">Бот дозволяє здійснювати пошук об’єднаних профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="3d87d-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="3d87d-122">Уведіть **знайти**, а потім ім’я, адресу електронної пошти або будь-яке інше поле в об’єднаному профілі клієнта, додане до покажчика пошуку та фільтрації.</span><span class="sxs-lookup"><span data-stu-id="3d87d-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="3d87d-123">Відобразиться картка, що містить до 15 полів із профілю клієнта, отриманого в результаті пошуку.</span><span class="sxs-lookup"><span data-stu-id="3d87d-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="3d87d-124">У разі декількох збігів відображається список результатів, у якому можна вибрати профіль.</span><span class="sxs-lookup"><span data-stu-id="3d87d-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="3d87d-125">Можна додати пошуковий термін у подвійних лапках, щоб знайти точний збіг.</span><span class="sxs-lookup"><span data-stu-id="3d87d-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="3d87d-126">Якщо в організації є кілька середовищ Customer Insights з клієнтів в одній організації, можна ввести **switchinstance**, щоб вибрати середовище, до якого потрібно підключити бот.</span><span class="sxs-lookup"><span data-stu-id="3d87d-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="3d87d-127">Уведіть **довідка**, щоб відобразився список доступних команд для бота.</span><span class="sxs-lookup"><span data-stu-id="3d87d-127">Enter **help** to see a list of available commands for the bot.</span></span>  
