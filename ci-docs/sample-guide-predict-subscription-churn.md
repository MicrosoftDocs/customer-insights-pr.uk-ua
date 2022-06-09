---
title: Зразок вказівок для прогнозу відтоку передплат
description: За допомогою зразку вказівок можна випробувати готову модель прогнозування відтоку передплат.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741436"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Зразок вказівок для прогнозу відтоку передплат

Ці вказівки пояснить вам повний приклад прогнозу відтоку підписок у Customer Insights за допомогою зразків даних, наданих нижче. 

## <a name="scenario"></a>Сценарій

Contoso — компанія, яка випускає високоякісну каву та кавомашини, які вони продають на веб-сайті компанії Contoso Coffee. Нещодавно вони почали діяльність за передплатою, щоб їхні клієнти могли отримувати каву регулярно. Їхня ціль полягає в тому, щоб розуміти, які передплачені клієнти можуть скасувати передплату на найближчі кілька місяців. Знання того, які з їхніх клієнтів **можуть бути втраченими**, може допомогти їм зекономити маркетингові зусилля, зосередивши увагу на їх збереженні.

## <a name="prerequisites"></a>Вимоги

- Принаймні [дозволи співавтора](permissions.md) у Customer Insights.
- Радимо виконати зазначені нижче кроки [в новому середовищі](manage-environments.md).

## <a name="task-1---ingest-data"></a>Завдання 1 — прийом даних

Перегляньте статті [про потрапляння](data-sources.md) даних та [імпорт джерел даних за допомогою Power Query роз'ємів](connect-power-query.md) спеціально. Наведена нижче інформація передбачає, що ви загалом ознайомилися з прийомом даних. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Прийом даних клієнта з платформи eCommerce

1. Створіть джерело даних з іменем **eCommerce**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.

1. Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadclasscontacts.

1. Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.

1. Оновіть тип даних для стовпців, зазначених нижче.

   - **DateOfBirth**: дата
   - **CreatedOn**: дата/час/зона

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Зміна дати народження на дату.":::

1. У полі **Ім'я** в області праворуч перейменуйте джерело даних **Запит** на **eCommerceContacts**

1. Збережіть джерело даних

### <a name="ingest-customer-data-from-loyalty-schema"></a>Прийом даних про клієнта зі схеми лояльності

1. Створіть джерело даних з іменем **LoyaltyScheme**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.

1. Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.

1. Оновіть тип даних для стовпців, зазначених нижче.

   - **DateOfBirth**: дата
   - **RewardsPoints**: загальна кількість
   - **CreatedOn**: дата/час

1. У полі **Ім'я** в області праворуч перейменуйте джерело даних **Запит** на **loyCustomers**.

1. Збережіть джерело даних

### <a name="ingest-subscription-information"></a>Відомості про передплату на приймання

1. Створіть джерело даних з іменем **SubscriptionHistory**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.

1. Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadchurnsubscriptionhistory.

1. Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.

1. Оновіть тип даних для стовпців, зазначених нижче.

   - **SubscriptioID**: загальна кількість
   - **SubscriptionAmount**: грошова одиниця
   - **SubscriptionEndDate**: дата/час
   - **SubscriptionStartDate**: дата/час
   - **TransactionDate**: дата й час
   - **IsRecurring**: True/False
   - **Is_auto_renew** : true/false
   - **RecurringFrequencyInMonths**: ціле число

1. У полі **Ім'я** в області праворуч перейменуйте джерело даних **Запит** на **SubscriptionHistory**.

1. Збережіть джерело даних

### <a name="ingest-customer-data-from-website-reviews"></a>Прийом дані клієнта з оглядів веб-сайтів

1. Створіть джерело даних з іменем **Веб-сайт**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.

1. Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadclasswebsite.

1. Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.

1. Оновіть тип даних для стовпців, зазначених нижче.

   - **ReviewRating**: ціле число
   - **ReviewDate**: дата

1. У полі «Ім'я» в області праворуч перейменуйте джерело даних, **Запит** на **webReviews**.

## <a name="task-2---data-unification"></a>Завдання 2 — уніфікація даних

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Завдання 3 — настроювання прогнозу відтоку передплат

Маючи уніфіковані профілі клієнтів, ми можемо запустити прогноз відтоку підписок. Докладні кроки прогноз [див](predict-subscription-churn.md). 

1. Перейдіть до розділу **Аналітика** > **Виявлення** та натисніть, щоб використати **Модель відтоку клієнтів**.

1. Виберіть параметр **Передплата** і натисніть **Почати**.

1. Назва моделі **OOB Subscription Churn Prediction** і вихідна сутність **OOBSubscriptionChurnPrediction**.

1. Визначення двох умов для моделі відтоку:

   * **Кількість днів з кінця передплати**: **принаймні 60** днів. Якщо клієнт не подовжує передплату протягом визначеного періоду після її завершення, він вважається втраченим. 

   * **Визначення відтоку**: **принаймні 93** дні. Модель передбачає тривалість відтоку клієнтів. Чим далі в майбутнє ви дивитеся, тим менш точними будуть результати.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Виберіть важелі моделі «Вікно прогнозу й визначення відтоку.":::

1. Натисніть **Додати обов'язкові дані** і виберіть параметр **Додати дані** до журналу передплат.

1. Додайте сутність **Передплата : SubscriptionHistory** і зіставте поля з eCommerce з відповідними полями, обов'язковими для моделі.

1. Приєднайтеся до сутності **Передплата: SubscriptionHistory** за допомогою **eCommerceContacts: електрона комерція**, назвіть зв'язки **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Приєднайте сутності електронної комерції.":::

1. У розділі «Справи клієнта» додайте сутність **webReviews: веб-сайт** і зіставте поля з webReviews з відповідними полями, обов'язковими для моделі. 
   - Основний ключ: ReviewId
   - Позначка часу: ReviewDate
   - Подія: ReviewRating

1. Настроювання справи для перегляду веб-сайтів. Виберіть справу **Перегляд** і приєднайтеся до сутності **webReviews : веб-сайт** **eCommerceContacts : eCommerce**.

1. Натисніть **Далі**, щоб задати розклад моделі.

   Моделі необхідно регулярно тренуватися, щоб вивчати нові моделі під час приймання нових даних. Для цього прикладу виберіть **Щомісячно**.

1. Переглянувши всі відомості, виберіть **Зберегти та запустити**.

## <a name="task-4---review-model-results-and-explanations"></a>Завдання 4 — перегляд результатів моделі та пояснення

Нехай модель завершить навчання і оцінити дані. Тепер можна ознайомитися з поясненнями моделі відтоку підписок. Для отримання додаткових відомостей див. розділ [Перегляд стану та результатів прогнозу](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Завдання 5 — створення сегмента клієнта з високою ймовірністю відтоку

Під час запуску моделі виробництва створюється нова сутність, яку можна переглянути в розділі **Дані** > **Сутності**.   

Можна створити новий сегмент на основі сутності, створеній моделлю.

1.  Перейдіть до розділу **Сегменти**. Виберіть пункт **Створити** і натисніть **Створити з** > **Аналітика**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Створення сегмента з виходом моделі.":::

1. Виберіть кінцеву точку **OOBSubscriptionChurnPrediction** і визначте сегмент: 
   - Поле: Chünscore
   - Оператор: більше ніж
   - Значення: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Налаштування сегменту відтоку підписок.":::

Тепер у вас є сегмент, який динамічно оновлюється, що визначає клієнтів з високою ймовірністю відтоку для цього бізнесу за передплатою.

Додаткові відомості див. в розділі [Створення сегментів і керування ними](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]