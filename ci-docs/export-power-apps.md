---
title: З’єднувач Power Apps (підготовча версія)
description: Підключення до Power Apps і Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 0b71f723d1e491d422d24b1be6616d2f33c95d40
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055285"
---
# <a name="power-apps-connector-preview"></a>З’єднувач Power Apps (підготовча версія)

Додавайте уніфіковані профілі клієнтів до персоналізованих програм за допомогою Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Підключення до Power Apps і Dynamics 365 Customer Insights

Customer Insights – це одне із багатьох [доступних джерел даних у Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Див. документацію Power Apps, щоб дізнатися, як [додати зв’язок даних до програми](/powerapps/maker/canvas-apps/add-data-connection). Рекомендуємо також переглянути статтю про те, [як Power Apps використовує делегування для роботи із великими наборами даних у компонованих програмах](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Доступні сутності

Після додавання Customer Insights як зв’язку даних можна вибрати зазначені нижче сутності в Power Apps.

- **Клієнт**: для використання даних з [уніфікованого профілю клієнта](customer-profiles.md).
- **UnifiedActivity**: для відображення [часової шкали справи](activities.md) в програмі.
- **ContactProfile**: для відображення контактних осіб клієнта. Ця організація доступна лише в середовищах Customer Insights для бізнес-облікових записів.

## <a name="limitations"></a>Обмеження

### <a name="retrievable-entities"></a>Сутності, які можна отримувати

За допомогою з'єднувача Power Apps можна отримувати лише сутності **Клієнт**, **UnifiedActivity** (уніфікована справа), **Сегменти** і **ContactProfile** (профіль клієнта) Функція ContactProfile доступна лише у екземплярі Customer Insights для бізнес-облікових записів. Інші сутності відображаються, оскільки з’єднувач, що лежить в основі, підтримує їх за допомогою тригерів у Power Automate.

Ви можете зробити максимум 100 дзвінків за 60 секунд. Ви можете викликати кінцеву точку API кілька разів, використовуючи параметр $skip. [Дізнайтеся більше про параметр $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Делегування

Делегація працює для сутності **Клієнт** та сутності **UnifiedActivity**. 

- Делегування сутності **Клієнт**: щоб використати делегування для цієї сутності, поля потрібно проіндексувати в розділі [Покажчик фільтра & пошуку](search-filter-index.md).  
- Делегування для **UnifiedActivity**: делегування для цієї сутності працює лише для полів **ActivityId** і **CustomerId**.  
- Делегування для **ContactProfile**: делегування для цієї сутності працює лише для полів **ContactId** і **CustomerId**. ContactProfile доступний лише в середовищах Customer Insights для бізнес-облікових записів.

Для отримання додаткових відомостей про делегування див. [Функції та операції Power Apps, які можна делегувати](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Приклад елемента керування «Галерея»

Профілі клієнтів можна додати до [елемента керування «галерея»](/powerapps/maker/canvas-apps/add-gallery).

1. Додайте елемент керування **галерея** до програми, яку ви створюєте.

    > [!div class="mx-imgBorder"]
    > ![Додавання елемента галереї.](media/connector-powerapps9.png "Додайте елемент галереї.")

2. Виберіть елемент **Клієнт** як джерело даних для елементів.

    > [!div class="mx-imgBorder"]
    > ![Вибір джерела даних.](media/choose-datasource-powerapps.png "Виберіть джерело даних.")

3. Панель даних можна змінити праворуч, щоб вибрати поле для сутності клієнта, яке відображатиметься в колекції.

4. Якщо потрібно відобразити будь-яке поле вибраного клієнта в галереї, введіть у властивості **Text** підпису так: **{Name_of_the_gallery}.Selected.{property_name}**  
    - Наприклад: _Gallery1.Selected.address1_city_

5. Щоб відобразити уніфіковану часову шкалу для клієнта, додайте елемент «галерея», а потім додайте властивість **Items**, використовуючи **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Наприклад: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
