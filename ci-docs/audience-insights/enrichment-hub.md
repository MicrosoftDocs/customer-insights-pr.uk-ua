---
title: Збагачення уніфікованих профілів клієнта
description: Скористайтеся можливостями для збагачення даних клієнтів.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597720"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="84a39-103">Збагачення для профілів клієнтів (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="84a39-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="84a39-104">Використовуйте дані з таких джерел, як Microsoft і інші партнери, щоб збагатити дані клієнтів.</span><span class="sxs-lookup"><span data-stu-id="84a39-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Сторінка центру збагачення":::

<span data-ttu-id="84a39-106">В аналізі аудиторії виберіть **Дані** > **Збагачення** для роботи з варіантам збагачення.</span><span class="sxs-lookup"><span data-stu-id="84a39-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="84a39-107">Щоб створити або змінити збагачення, потрібно мати дозволи співавтора або адміністратора.</span><span class="sxs-lookup"><span data-stu-id="84a39-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="84a39-108">Додаткові відомості див. в розділі [Дозволи](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="84a39-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="84a39-109">На вкладці **Виявлення** можна знайти перелічені нижче збагачення.</span><span class="sxs-lookup"><span data-stu-id="84a39-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="84a39-110">[Бренди](enrichment-microsoft-graph.md) надаються з Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="84a39-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="84a39-111">[Інтереси](enrichment-microsoft-graph.md) надаються з Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="84a39-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="84a39-112">[Дані компанії](enrichment-leadspace.md) надаються Leadspace</span><span class="sxs-lookup"><span data-stu-id="84a39-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="84a39-113">[Демографічні дані](enrichment-experian.md) надаються Experian</span><span class="sxs-lookup"><span data-stu-id="84a39-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="84a39-114">[Дані про розташування ](enrichment-here.md), надані HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="84a39-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="84a39-115">[Настроювані дані](enrichment-SFTP-custom-import.md) через протокол Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="84a39-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="84a39-116">На вкладці **Мої збагачення** можна переглянути збагачення, які ви налаштували, і змінити їхні властивості.</span><span class="sxs-lookup"><span data-stu-id="84a39-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="84a39-117">Керування наявними збагаченнями</span><span class="sxs-lookup"><span data-stu-id="84a39-117">Manage existing enrichments</span></span>

<span data-ttu-id="84a39-118">Перейдіть до **Мої збагачення**, щоб побачити усі налаштовані збагачення.</span><span class="sxs-lookup"><span data-stu-id="84a39-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="84a39-119">Кожне збагачення представлене рядком, у якому присутні додаткові відомості про це збагачення.</span><span class="sxs-lookup"><span data-stu-id="84a39-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="84a39-120">Виберіть збагачення, щоб переглянути список доступних можливостей.</span><span class="sxs-lookup"><span data-stu-id="84a39-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="84a39-121">Крім того, ви можете вибрати три крапки (...) для елемента списку, щоб побачити можливості.</span><span class="sxs-lookup"><span data-stu-id="84a39-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Можливості керування у списку збагачень":::

- <span data-ttu-id="84a39-123">**Перегляд** відомостей про збагачення із кількістю збагачених профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="84a39-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="84a39-124">**Редагування** конфігурації збагачення.</span><span class="sxs-lookup"><span data-stu-id="84a39-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="84a39-125">**Виконати** збагачення, щоб оновити профілі клієнтів найновішими даними.</span><span class="sxs-lookup"><span data-stu-id="84a39-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="84a39-126">**Вимкнення** існуючого збагачення, щоб воно припинило автоматично оновлюватись під час кожного запланованого оновлення.</span><span class="sxs-lookup"><span data-stu-id="84a39-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="84a39-127">Дані з останнього успішного оновлення залишаться доступними.</span><span class="sxs-lookup"><span data-stu-id="84a39-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="84a39-128">**Увімкнення** неактивного збагачення, щоб знов почати автоматичне оновлення під час кожного запланованого оновлення.</span><span class="sxs-lookup"><span data-stu-id="84a39-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="84a39-129">**Видалення** збагачення.</span><span class="sxs-lookup"><span data-stu-id="84a39-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="84a39-130">Можна виконати або вимкнути кілька збагачень одночасно, вибравши їх у списку.</span><span class="sxs-lookup"><span data-stu-id="84a39-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="84a39-131">Можливості перегляду та редагування недоступні для групових операцій та працюють лише для окремо вибраних збагачень.</span><span class="sxs-lookup"><span data-stu-id="84a39-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]