---
title: Сегменти на основі результатів прогнозу
description: Створюйте сегменти на основі вихідної сутності моделі прогнозування.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0b3357cdf3c049bd92f6c3f690f27433df9117b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644136"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Створення сегмента на основі моделі прогнозування (підготовча версія)

Результати прогнозів іноді відносяться лише до підмножині клієнтів. Зробіть рекомендації більш особистими, створивши сегменти з результатів роботи моделей прогнозування. Наприклад, ви можете надавати особливі рекомендації клієнтам, які віддають перевагу певному типу обслуговування. 

## <a name="prerequisites"></a>Вимоги

- Принаймні [дозволи співавтора](permissions.md) у Customer Insights.

- Модель рекомендації продуктів, відтоку транзакцій, відмови від передплати або оцінки життєвого циклу клієнта налаштована в Customer Insights. Ознайомтеся з вимогами для настроювання різних моделей.

  - [Модель рекомендації продуктів](predict-product-recommendation.md)
  - [Модель відмови від передплати](predict-subscription-churn.md)
  - [Модель відтоку транзакцій](predict-transactional-churn.md)
  - [Модель оцінки життєвого циклу клієнта](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Створення сегмента клієнтів на основі прогнозів

1. Перейдіть до розділу **Аналітика** > **Прогнози** і виберіть вкладку **Мої прогнози**.

1. Виберіть вертикальні три крапки поряд із моделлю, яку потрібно переглянути, і виберіть **Переглянути**.

1. На сторінці результатів виберіть **Створити сегмент**. Додаткові відомості про сторінку результатів ви можете знайти у статті про модель.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Знімок екрана: сторінка результатів прогнозу, де виділено дію «Створити сегмент».":::

1. Створіть новий сегмент на основі вихідної сутності вибраної моделі. Додаткові відомості див. в розділі [Створення сегментів і керування ними](segments.md).