---
title: Загальні відомості щодо підтримуваних сценаріїв прогнозування
description: Сценарії прогнозування та варіанти, доступні в програмі Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095761"
---
# <a name="predictions-overview"></a><span data-ttu-id="43f3f-103">Огляд прогнозів</span><span class="sxs-lookup"><span data-stu-id="43f3f-103">Predictions overview</span></span>

<span data-ttu-id="43f3f-104">Dynamics 365 Customer Insights постачається з різноманітними можливостями, які використовують ШІ та машинне навчання для прогнозування даних.</span><span class="sxs-lookup"><span data-stu-id="43f3f-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="43f3f-105">Готові моделі</span><span class="sxs-lookup"><span data-stu-id="43f3f-105">Out-of-box models</span></span>

<span data-ttu-id="43f3f-106">Найпростішим способом почати прогнозування даних є використання попередньо визначених моделей, які часто називають готовими моделями.</span><span class="sxs-lookup"><span data-stu-id="43f3f-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="43f3f-107">Для швидкого створення аналітичних оглядів за допомогою таких моделей потрібні лише певні дані та структура.</span><span class="sxs-lookup"><span data-stu-id="43f3f-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="43f3f-108">Моделі, що доступні станом на сьогодні, перелічено нижче.</span><span class="sxs-lookup"><span data-stu-id="43f3f-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="43f3f-109">[Прогнозована оцінка життєвого циклу клієнта](predict-customer-lifetime-value.md): прогнозує потенційний дохід, що може бути створений клієнтом протягом усього терміну взаємодії з компанією.</span><span class="sxs-lookup"><span data-stu-id="43f3f-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="43f3f-110">[Рекомендації продуктів](predict-product-recommendation.md): пропонує набори прогнозних рекомендацій продуктів, виходячи з поведінки покупця та аналізуючи дії клієнтів зі схожою поведінкою.</span><span class="sxs-lookup"><span data-stu-id="43f3f-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="43f3f-111">[Відтік передплат](predict-subscription-churn.md): прогнозує, чи є загроза того, що клієнт перестане користуватися доступними за передплатою продуктами чи послугами вашої компанії.</span><span class="sxs-lookup"><span data-stu-id="43f3f-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="43f3f-112">[Відтік транзакцій](predict-transactional-churn.md): прогнозує, чи припинить клієнт купляти продукти або послуги вашої компанії протягом певного терміну.</span><span class="sxs-lookup"><span data-stu-id="43f3f-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="43f3f-113">Інтеграція машинного навчання Azure</span><span class="sxs-lookup"><span data-stu-id="43f3f-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="43f3f-114">Якщо організація вже реалізує певні сценарії машинного навчання на основі експериментів машинного навчання Azure, функція настроюваних моделей в Customer Insights допоможе зрозуміти, що до чого.</span><span class="sxs-lookup"><span data-stu-id="43f3f-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="43f3f-115">Створіть робочі цикли, які допоможуть обрати дані для створення аналітичних висновків та зіставити результати із уніфікованими профілями ваших клієнтів.</span><span class="sxs-lookup"><span data-stu-id="43f3f-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="43f3f-116">Додаткові відомості див. в розділі [Настроювані моделі машинного навчання](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="43f3f-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="43f3f-117">Прогноз AI Builder</span><span class="sxs-lookup"><span data-stu-id="43f3f-117">AI Builder prediction</span></span>

<span data-ttu-id="43f3f-118">Іноді набори даних виявляються неповними, і деякі значення відсутні.</span><span class="sxs-lookup"><span data-stu-id="43f3f-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="43f3f-119">Customer Insights може допомогти спрогнозувати відсутні значення для сутності «Клієнт» та сегментів.</span><span class="sxs-lookup"><span data-stu-id="43f3f-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="43f3f-120">Додаткові відомості: [Доповнення часткових даних за допомогою прогнозів](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="43f3f-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
