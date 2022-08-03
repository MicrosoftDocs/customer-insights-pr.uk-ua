---
title: З’єднувач Power Apps (підготовча версія)
description: Підключення до Power Apps і Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196925"
---
# <a name="power-apps-connector-preview"></a>З’єднувач Power Apps (підготовча версія)

Додавайте уніфіковані профілі клієнтів до персоналізованих програм за допомогою Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Підключення до Power Apps і Dynamics 365 Customer Insights

Customer Insights – це одне із багатьох [доступних джерел даних у Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Див. документацію Power Apps, щоб дізнатися, як [додати зв’язок даних до програми](/powerapps/maker/canvas-apps/add-data-connection). Рекомендуємо також переглянути статтю про те, [як Power Apps використовує делегування для роботи із великими наборами даних у компонованих програмах](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Доступні сутності

Після додавання Customer Insights як з'єднання даних виберіть такі сутності в Power Apps:

- **Клієнт**: для використання даних з [уніфікованого профілю клієнта](customer-profiles.md).
- **UnifiedActivity**: для відображення [часової шкали справи](activities.md) в програмі.
- **ContactProfile**: для відображення контактних осіб клієнта. Ця організація доступна лише в середовищах Customer Insights для корпоративних облікових записів.

## <a name="limitations"></a>Обмеження

### <a name="retrievable-entities"></a>Сутності, які можна отримувати

За допомогою з'єднувача Power Apps можна отримувати лише сутності **Клієнт**, **UnifiedActivity** (уніфікована справа), **Сегменти** і **ContactProfile** (профіль клієнта) ContactProfile доступний лише в середовищах Customer Insights для бізнес-облікових записів. Інші сутності відображаються, оскільки з’єднувач, що лежить в основі, підтримує їх за допомогою тригерів у Power Automate.

Ви можете зробити максимум 100 дзвінків за 60 секунд. Ви можете викликати кінцеву точку API кілька разів, використовуючи параметр $skip. [Докладніше про параметр $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Делегування

Делегація працює для сутності **Клієнт** та сутності **UnifiedActivity**.

- Делегування для **сутності клієнта** : щоб використовувати делегування для цієї сутності, поля потрібно індексувати в індексі [пошуку та фільтрування](search-filter-index.md).  
- Делегування для **UnifiedActivity**: делегування для цієї сутності працює лише для полів **ActivityId** і **CustomerId**.  
- Делегування для **ContactProfile**: делегування для цієї сутності працює лише для полів **ContactId** і **CustomerId**. ContactProfile доступний лише в середовищах Customer Insights для бізнес-облікових записів.

Для отримання додаткових відомостей про делегування див. [Функції та операції Power Apps, які можна делегувати](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Приклад елемента керування «Галерея»

За потреби можна додати профілі клієнтів до [елемента керування "Галерея"](/powerapps/maker/canvas-apps/add-gallery).

1. Додайте елемент керування **галерея** до програми, яку ви створюєте.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Додавання елемента галереї.":::

1. Виберіть елемент **Клієнт** як джерело даних для елементів.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Вибір джерела даних.":::

1. Змініть панель даних праворуч, щоб вибрати поле для сутності Клієнта відображати в колекції.

1. Якщо потрібно відобразити будь-яке поле вибраного клієнта в галереї, введіть у властивості **Text** підпису так: **{Name_of_the_gallery}.Selected.{property_name}**  
    - Наприклад: _Gallery1.Selected.address1_city_

1. Щоб відобразити уніфіковану часову шкалу для клієнта, додайте елемент «галерея», а потім додайте властивість **Items**, використовуючи **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Наприклад: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
