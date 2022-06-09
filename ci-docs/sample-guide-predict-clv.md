---
title: Зразок посібника з прогнозування оцінки життєвого циклу клієнта
description: Скористайтеся цим зразком посібника, щоб випробувати модель прогнозування оцінки життєвого циклу клієнта.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 351946c734f5a1054eb3769b2d9cced3bed48e15
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740836"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Зразок посібника з прогнозування оцінки життєвого циклу клієнта (CLV)

У цьому посібнику крок за кроком, від початку до кінця, розглядається процес прогнозування оцінки життєвого циклу клієнта (CLV) для зразків даних в Customer Insights.

## <a name="scenario"></a>Сценарій

Contoso - це компанія, яка виробляє високоякісні кавові та кавові машини. Вони продають продукцію через свій веб-сайт Contoso Coffee. Компанія хоче зрозуміти, яку суму (дохід) можна отримати від клієнтів протягом наступних 12 місяців. Якщо вони знатимуть орієнтовну цінність клієнтів протягом 12 місяців, це допоможе скерувати маркетингові зусилля на роботу із найціннішими клієнтами.

## <a name="prerequisites"></a>вимоги

- Принаймні [дозволи співавтора](permissions.md) у Customer Insights.
- Радимо виконати зазначені нижче кроки [в новому середовищі](manage-environments.md).

## <a name="task-1---ingest-data"></a>Завдання 1 — прийом даних

Перегляньте статті [про проковтування](data-sources.md) даних та [імпорт джерел даних за допомогою Power Query сполучних ліній](connect-power-query.md). Наведена нижче інформація передбачає, що ви загалом ознайомилися з прийомом даних.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Прийом даних клієнта з платформи eCommerce

1. Створіть джерело даних з іменем **eCommerce**, виберіть імпорт, а тоді виберіть з'єднувач **Текст/CSV**.

1. Введіть URL-адресу для контактів eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.

1. Оновіть тип даних для стовпців, зазначених нижче.
   - **DateOfBirth**: дата
   - **CreatedOn**: дата/час/зона

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Зміна дати народження на дату.":::

1. У полі «Ім'я» в області праворуч перейменуйте джерело даних, **Запит** на **eCommerceContacts**

1. **Збережіть** джерело даних.

### <a name="ingest-online-purchase-data"></a>Прийом даних про придбання онлайн

1. Додайте ще один набір даних до того самого джерела даних **eCommerce**. Виберіть знову з'єднувач **Text/CSV**.

1. Введіть URL-адресу для даних про **Онлайн-придбання** https://aka.ms/ciadclassonline.

1. Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.

1. Оновіть тип даних для стовпців, зазначених нижче.
   - **PurchasedOn**: дата/час
   - **TotalPrice**: грошова одиниця

1. У полі **Ім'я** в бічній області перейменуйте джерело даних **Запит** на **eCommercePurchases**.

1. **Збережіть** джерело даних.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Прийом даних про клієнта зі схеми лояльності

1. Створіть джерело даних з іменем **LoyaltyScheme**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.

1. Введіть URL-адресу для контактів eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.

1. Оновіть тип даних для стовпців, зазначених нижче.
   - **DateOfBirth**: дата
   - **RewardsPoints**: загальна кількість
   - **CreatedOn**: дата/час

1. У полі **Ім'я** в області праворуч перейменуйте джерело даних **Запит** на **loyCustomers**.

1. **Збережіть** джерело даних.

### <a name="ingest-customer-data-from-website-reviews"></a>Прийом дані клієнта з оглядів веб-сайтів

1. Створіть джерело даних з іменем **Веб-сайт**, виберіть параметр імпорту та натисніть з'єднувач **Тext/CSV**.

1. Введіть URL-адресу для контактів eCommerce https://aka.ms/CI-ILT/WebReviews.

1. Під час редагування даних натисніть **Трансформувати**, а потім **Використати перший рядок як заголовок**.

1. Оновіть тип даних для стовпців, зазначених нижче.

   - **ReviewRating**: десяткове число
   - **ReviewDate**: дата

1. У полі «Ім'я» в області праворуч перейменуйте джерело даних з **Запит** на **Рецензії**.

1. **Збережіть** джерело даних.

## <a name="task-2---data-unification"></a>Завдання 2 — уніфікація даних

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Завдання 3 – налаштування прогнозування цінності життєвого циклу клієнта

Тепер, коли уніфіковані профілі клієнтів готові, ми можемо запустити прогнозування цінності життєвого циклу клієнта. Докладні кроки прогноз [див](predict-customer-lifetime-value.md).

1. Відкрийте **Аналітика**  > **Прогнози** та виберіть **Модель цінності життєвого циклу клієнта**.

1. Продивіться відомості на бічній панелі та виберіть **Почати**.

1. Назвіть модель **OOB eCommerce CLV Prediction** («Прогноз CLV OOB eCommerce») та вихідну сутність **OOBeCommerceCLVPrediction**.

1. Визначте параметри моделі для моделі CLV.
   - **Часовий період прогнозу**: **12 місяців або 1 рік**. Цей параметр визначає, на який термін у майбутньому прогнозуватиметься цінність життєвого циклу клієнта.
   - **Активні клієнти**: зазначте, який клієнт вважається активним у вашій компанії. Установіть часові рамки в минулому, в межах яких клієнт повинен мати принаймні одну транзакцію, щоб вважатися активним. Модель прогнозуватиме CLV лише для активних клієнтів. Виберіть з двох варіантів – дозвольте моделі обчислити період часу на основі ретроспективних даних транзакцій або ж задайте певні часові рамки. У цьому зразку посібника ми **дозволяємо моделі обчислити інтервал придбання**, і це є варіантом за замовчуванням.
   - **Важливі клієнти**: визначте важливих клієнтів як процентиль клієнтів, що платять найбільше. Модель використовує це значення, щоб надавати результати, які відповідатимуть вашому визначенню важливих клієнтів. Ви можете дозволити моделі визначити важливих клієнтів. При цьому для виведення процентиля використовується евристичне правило. Ви можете також визначити важливих клієнтів як процентиль клієнтів, що у майбутньому платитимуть найбільше. У цьому зразку посібника ми вручну визначаємо важливих клієнтів як **перші 30 % від клієнтів, що активно платять**, і переходимо **Далі**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Крок параметрів в інтерфейсі з підказками для моделі CLV.":::

1. На кроці **Необхідні дані** виберіть **Додати дані**, щоб надати дані журналу транзакцій.

1. Додайте сутність **eCommercePurchases : eCommerce** та зіставте атрибути, необхідні для моделі.
   - Ідентифікатор транзакції: eCommerce.eCommercePurchases.PurchaseId
   - Дата транзакції: eCommerce.eCommercePurchases.PurchasedOn
   - Сума транзакції: eCommerce.eCommercePurchases.TotalPrice
   - Ідентифікатор продукту: eCommerce.eCommercePurchases.ProductId

1. Виберіть **Далі**.

1. Установіть зв'язок між сутністю **eCommercePurchases : eCommerce** та **eCommerceContacts : eCommerce**.

1. На кроці **Додаткові дані (необов'язково)** ви можете додати інші дані справ клієнтів. Ці дані дозволять отримати більше аналітичних відомостей щодо взаємодій клієнтів із вашою компанією, що може вплинути на CLV. Додавання таких ключових взаємодій клієнтів, як, наприклад веб-журналів, журналів обслуговування клієнтів або ретроспективних даних про участь в програмах винагород може підвищити точність прогнозування. Виберіть **Додати дані**, щоб додати інші дані справ клієнтів.

1. Додайте сутність справи клієнта та зіставте імена її полів із відповідними полями, необхідними для моделі:
   - Сутність справи клієнта: Reviews:Website
   - Первинний ключ: Website.Reviews.ReviewId
   - Позначка часу: Website.Reviews.ReviewDate
   - Подія (назва справи): Website.Reviews.ActivityTypeDisplay
   - Докладні відомості (сума або значення): Website.Reviews.ReviewRating

1. Виберіть **Далі** та налаштуйте справу і зв'язок між даними транзакції та даними клієнта, як показано нижче.  
   - Тип справи: виберіть наявний
   - Мітка справи: Рецензія
   - Відповідний підпис: Website.Reviews.UserId
   - Сутність клієнта: eCommerceContacts:eCommerce
   - Зв'язок: WebsiteReviews

1. Натисніть **Далі**, щоб задати розклад моделі.

   Модель має постійно навчатися, щоб дізнаватись про нові шаблони, якщо з’являтимуться нові дані. У нашому прикладі виберіть **Щомісяця**.

1. Переглянувши всі відомості, виберіть **Зберегти та запустити**.

## <a name="task-4---review-model-results-and-explanations"></a>Завдання 4 — перегляд результатів моделі та пояснення

Нехай модель завершить навчання і оцінити дані. Тепер ви можете переглянути результати роботи моделі CLV із поясненнями. Для отримання додаткових відомостей див. розділ [Перегляд стану та результатів прогнозу](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Завдання 5 – створення сегмента з важливих клієнтів

При запуску моделі створюється нова сутність, яку можна побачити в розділі **Дані** > **Сутності**. Ви можете створити новий сегмент на основі сутності, створеної моделлю.

1. Перейдіть до розділу **Сегменти**. 

1. Виберіть **Створити** і натисніть **Створити з** > **Аналітика**.

   ![Створення сегмента з виходом моделі.](media/segment-intelligence.png)

1. Виберіть сутність **OOBeCommerceCLVPrediction** і визначте сегмент, як показано нижче.
  - Поле: CLVScore
  - Оператор: більше ніж
  - Значення: 1500

1. Виберіть **Переглянути**, а тоді **Збережіть** сегмент.

Тепер у вас є сегмент, в якому визначено клієнтів, що, згідно прогнозу, створять більше, ніж $ 1500 доходу протягом наступних 12 місяців. Цей сегмент динамічно оновлюється при отриманні нових даних.

Додаткові відомості див. в розділі [Створення сегментів і керування ними](segments.md).