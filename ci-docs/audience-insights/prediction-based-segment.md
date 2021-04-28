---
title: Сегменти на основі результатів прогнозу
description: Створюйте сегменти на основі вихідної сутності моделі прогнозування.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741454"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="ab0b5-103">Створення сегмента на основі моделі прогнозування (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="ab0b5-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="ab0b5-104">Результати прогнозів іноді відносяться лише до підмножині клієнтів.</span><span class="sxs-lookup"><span data-stu-id="ab0b5-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="ab0b5-105">Зробіть рекомендації більш особистими, створивши сегменти з результатів роботи моделей прогнозування.</span><span class="sxs-lookup"><span data-stu-id="ab0b5-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="ab0b5-106">Наприклад, ви можете надавати особливі рекомендації клієнтам, які віддають перевагу певному типу обслуговування.</span><span class="sxs-lookup"><span data-stu-id="ab0b5-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ab0b5-107">Вимоги</span><span class="sxs-lookup"><span data-stu-id="ab0b5-107">Prerequisites</span></span>

- <span data-ttu-id="ab0b5-108">Принаймні [дозволи співавтора](permissions.md) у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ab0b5-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="ab0b5-109">Модель рекомендації продуктів, відтоку транзакцій, відмови від передплати або оцінки життєвого циклу клієнта налаштована в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ab0b5-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="ab0b5-110">Ознайомтеся з вимогами для настроювання різних моделей.</span><span class="sxs-lookup"><span data-stu-id="ab0b5-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="ab0b5-111">Модель рекомендації продуктів</span><span class="sxs-lookup"><span data-stu-id="ab0b5-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="ab0b5-112">Модель відмови від передплати</span><span class="sxs-lookup"><span data-stu-id="ab0b5-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="ab0b5-113">Модель відтоку транзакцій</span><span class="sxs-lookup"><span data-stu-id="ab0b5-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="ab0b5-114">Модель оцінки життєвого циклу клієнта</span><span class="sxs-lookup"><span data-stu-id="ab0b5-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="ab0b5-115">Створення сегмента клієнтів на основі прогнозів</span><span class="sxs-lookup"><span data-stu-id="ab0b5-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="ab0b5-116">Перейдіть до розділу **Аналітика** > **Прогнози** і виберіть вкладку **Мої прогнози**.</span><span class="sxs-lookup"><span data-stu-id="ab0b5-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="ab0b5-117">Виберіть вертикальні три крапки поряд із моделлю, яку потрібно переглянути, і виберіть **Переглянути**.</span><span class="sxs-lookup"><span data-stu-id="ab0b5-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="ab0b5-118">На сторінці результатів виберіть **Створити сегмент**.</span><span class="sxs-lookup"><span data-stu-id="ab0b5-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="ab0b5-119">Додаткові відомості про сторінку результатів ви можете знайти у статті про модель.</span><span class="sxs-lookup"><span data-stu-id="ab0b5-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Знімок екрана: сторінка результатів прогнозу, де виділено дію «Створити сегмент».":::

1. <span data-ttu-id="ab0b5-121">Створіть новий сегмент на основі вихідної сутності вибраної моделі.</span><span class="sxs-lookup"><span data-stu-id="ab0b5-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="ab0b5-122">Додаткові відомості див. в розділі [Створення сегментів і керування ними](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ab0b5-122">For more information, see [Create and manage segments](segments.md).</span></span>