---
title: З’єднувач Power Apps
description: Підключення до Power Apps і Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031820"
---
# <a name="microsoft-power-apps-connector-preview"></a>З’єднувач Microsoft Power Apps (підготовча версія)

Додавайте уніфіковані профілі клієнтів до персоналізованих програм за допомогою Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Підключення до Power Apps і Dynamics 365 Customer Insights

Customer Insights – це одне із багатьох [доступних джерел даних у Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Див. документацію Power Apps, щоб дізнатися, як [додати зв’язок даних до програми](/powerapps/maker/canvas-apps/add-data-connection). Рекомендуємо також переглянути статтю про те, [як Power Apps використовує делегування для роботи із великими наборами даних у компонованих програмах](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Доступні сутності

Після додавання Customer Insights як зв’язку даних можна вибрати зазначені нижче сутності в Power Apps.

- Клієнт: для використання даних з [уніфікованого профілю клієнта](customer-profiles.md).
- UnifiedActivity: для відображення [часової шкали справ](activities.md) для програми.

## <a name="limitations"></a>Обмеження

### <a name="retrievable-entities"></a>Сутності, які можна отримувати

За допомогою з'єднувача Power Apps можна отримувати лише сутності **Клієнт**, **UnifiedActivity** і **Сегменти**. Інші сутності відображаються, оскільки з’єднувач, що лежить в основі, підтримує їх за допомогою тригерів у Power Automate.  

### <a name="delegation"></a>Делегування

Делегація працює для сутності клієнта та об'єкта UnifiedActivity. 

- Делегування сутності **Клієнт**: щоб використати делегування для цієї сутності, поля потрібно проіндексувати в розділі [Покажчик фільтра & пошуку](search-filter-index.md).  

- Делегування для **UnifiedActivity**: делегування для цієї сутності працює лише для полів **ActivityId** і **CustomerId**.  

- Для отримання додаткових відомостей про делегування див. [Функції та операції Power Apps, які підлягають делегуванню](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Приклад елемента керування «Галерея»

Наприклад, можна додати профілі клієнтів до [елемента керування «галерея»](/powerapps/maker/canvas-apps/add-gallery).

1. Додайте елемент керування **«Галерея»** до програми, яку ви створюєте.

> [!div class="mx-imgBorder"]
> ![Додавання елемента галереї.](media/connector-powerapps9.png "Додавання елемента галереї")

1. Виберіть елемент **Клієнт** як джерело даних для елементів.

    > [!div class="mx-imgBorder"]
    > ![Вибір джерела даних.](media/choose-datasource-powerapps.png "Вибір джерела даних")

1. Панель даних можна змінити праворуч, щоб вибрати поле для сутності клієнта, яке відображатиметься в колекції.

1. Якщо потрібно відобразити будь-яке поле з вибраного клієнта в колекції, введіть у властивості тексту підпис: **{Name_of_the_gallery}.Вибрано.{property_name}**

    Приклад: Gallery1.Вибрано.address1_city

1. Щоб відобразити уніфіковану часову шкалу для клієнта, додайте елемент «Колекція», а потім додайте властивість «Items» **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Приклад: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]