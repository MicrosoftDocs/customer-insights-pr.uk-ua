---
title: Збагачення уніфікованих профілів клієнта
description: Скористайтеся можливостями для збагачення даних клієнтів.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896030"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="78acf-103">Збагачення для профілів клієнтів (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="78acf-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="78acf-104">Використовуйте дані з таких джерел, як Microsoft і інші партнери, щоб збагатити дані клієнтів.</span><span class="sxs-lookup"><span data-stu-id="78acf-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Сторінка центру збагачення":::

<span data-ttu-id="78acf-106">В аналізі аудиторії виберіть **Дані** > **Збагачення** для роботи з варіантам збагачення.</span><span class="sxs-lookup"><span data-stu-id="78acf-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="78acf-107">Щоб створити або змінити збагачення, потрібно мати дозволи співавтора або адміністратора.</span><span class="sxs-lookup"><span data-stu-id="78acf-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="78acf-108">Додаткові відомості див. в розділі [Дозволи](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="78acf-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="78acf-109">На вкладці **Виявлення** можна знайти перелічені нижче збагачення.</span><span class="sxs-lookup"><span data-stu-id="78acf-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="78acf-110">[Бренди](enrichment-microsoft.md), надані Майкрософт</span><span class="sxs-lookup"><span data-stu-id="78acf-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="78acf-111">[Інтереси](enrichment-microsoft.md), надані Майкрософт</span><span class="sxs-lookup"><span data-stu-id="78acf-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="78acf-112">[Дані компанії](enrichment-leadspace.md) надаються Leadspace</span><span class="sxs-lookup"><span data-stu-id="78acf-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="78acf-113">[Демографічні дані](enrichment-experian.md) надаються Experian</span><span class="sxs-lookup"><span data-stu-id="78acf-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="78acf-114">[Дані про розташування ](enrichment-here.md), надані HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="78acf-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="78acf-115">[Настроювані дані](enrichment-SFTP-custom-import.md) через протокол Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="78acf-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="78acf-116">На вкладці **Мої збагачення** можна переглянути збагачення, які ви налаштували, і змінити їхні властивості.</span><span class="sxs-lookup"><span data-stu-id="78acf-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="78acf-117">Керування наявними збагаченнями</span><span class="sxs-lookup"><span data-stu-id="78acf-117">Manage existing enrichments</span></span>

<span data-ttu-id="78acf-118">Перейдіть до **Мої збагачення**, щоб побачити усі налаштовані збагачення.</span><span class="sxs-lookup"><span data-stu-id="78acf-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="78acf-119">Кожне збагачення представлене рядком, у якому присутні додаткові відомості про це збагачення.</span><span class="sxs-lookup"><span data-stu-id="78acf-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="78acf-120">Виберіть збагачення, щоб переглянути список доступних можливостей.</span><span class="sxs-lookup"><span data-stu-id="78acf-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="78acf-121">Ви також можете вибрати три крапки (...) в елементі списку, щоб переглянути параметри.</span><span class="sxs-lookup"><span data-stu-id="78acf-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Можливості керування у списку збагачень":::

- <span data-ttu-id="78acf-123">**Перегляд** відомостей про збагачення із кількістю збагачених профілів клієнтів.</span><span class="sxs-lookup"><span data-stu-id="78acf-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="78acf-124">**Редагування** конфігурації збагачення.</span><span class="sxs-lookup"><span data-stu-id="78acf-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="78acf-125">**Виконати** збагачення, щоб оновити профілі клієнтів найновішими даними.</span><span class="sxs-lookup"><span data-stu-id="78acf-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="78acf-126">**Вимкнення** існуючого збагачення, щоб воно припинило автоматично оновлюватись під час кожного запланованого оновлення.</span><span class="sxs-lookup"><span data-stu-id="78acf-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="78acf-127">Дані з останнього успішного оновлення залишаться доступними.</span><span class="sxs-lookup"><span data-stu-id="78acf-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="78acf-128">**Увімкнення** неактивного збагачення, щоб знов почати автоматичне оновлення під час кожного запланованого оновлення.</span><span class="sxs-lookup"><span data-stu-id="78acf-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="78acf-129">**Видалення** збагачення.</span><span class="sxs-lookup"><span data-stu-id="78acf-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="78acf-130">Можна виконати або вимкнути кілька збагачень одночасно, вибравши їх у списку.</span><span class="sxs-lookup"><span data-stu-id="78acf-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="78acf-131">Можливості перегляду та редагування недоступні для групових операцій та працюють лише для окремо вибраних збагачень.</span><span class="sxs-lookup"><span data-stu-id="78acf-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="78acf-132">Збагачення та підключення</span><span class="sxs-lookup"><span data-stu-id="78acf-132">Enrichments and connections</span></span>

<span data-ttu-id="78acf-133">Сторонні збагачення налаштовуються за допомогою [підключень](connections.md), які за допомогою облікових даних налаштовує адміністратор, який потім надає згоду на передавання даних.</span><span class="sxs-lookup"><span data-stu-id="78acf-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="78acf-134">Таке підключення можуть використовувати адміністратори та автори для налаштування збагачень.</span><span class="sxs-lookup"><span data-stu-id="78acf-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="78acf-135">Кілька збагачень одного й того самого типу</span><span class="sxs-lookup"><span data-stu-id="78acf-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="78acf-136">Сутність, яка підлягає збагаченню, зазначається під час налаштування збагачення. Це дозволяє збагачувати лише підгрупу профілів.</span><span class="sxs-lookup"><span data-stu-id="78acf-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="78acf-137">Наприклад, виконайте збагачення даних виключно для окремого сегмента.</span><span class="sxs-lookup"><span data-stu-id="78acf-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="78acf-138">Ви можете налаштувати кілька збагачень одного типу та повторно скористатися одним і тим самим підключенням.</span><span class="sxs-lookup"><span data-stu-id="78acf-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="78acf-139">Деякі збагачення будуть мати обмеження кількості збагачень одного й того самого типу, які можна створити.</span><span class="sxs-lookup"><span data-stu-id="78acf-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="78acf-140">На сторінці **Збагачення** можна побачити ці обмеження та поточні обсяги використання.</span><span class="sxs-lookup"><span data-stu-id="78acf-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
