---
title: Запити прав суб’єкта даних (DSR) відповідно до GDPR | Microsoft Docs
description: Відповідь на запити суб'єкта прав для можливості аналізу аудиторії в Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6faaeb6a1ee34c3e5c8e7d465b37cee589bc920c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483718"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Запити прав суб'єкта даних (DSR) відповідно до GDPR

Генеральний регламент із захисту персональних даних Європейського Союзу набув чинності 25 травня 2018 року. Він дає особам значні права щодо їхніх даних. GDPR говорить про захист та вводить в дію право осіб на конфіденційність. Ви можете прочитати більше про зобов’язання корпорації Майкрософт щодо захисту та відповідності вимогам у [Центрі безпеки та конфіденційності Microsoft](https://www.microsoft.com/trust-center).

Ми дбаємо про те, щоб допомагати клієнтам задовольняти вимоги GDPR. Він включає право видаляти та експортувати дані, які містять особисті відомості, наприклад ідентифікатори користувачів, номери телефонів і адреси електронної пошти. Адміністратори можуть реалізувати запити користувачів на видалення або експорт особистих відомостей.

## <a name="audience-insights"></a>Аналіз аудиторії

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Відповідь на запити про видалення суб'єкта прав GDPR для можливості аналізу аудиторії в Dynamics 365 Customer Insights.

«Право на видалення» шляхом видалення персональних даних з даних клієнтів організації є ключовим в Генеральному регламенті із захисту персональних даних (GDPR). Видалення особистих даних передбачає видалення всіх особистих даних і журналів, створених системою, за винятком відомостей журналу відстеження.

#### <a name="manage-data-subject-delete-requests"></a>Керування запитами на видалення суб’єкта даних

Аналіз аудиторії пропонує такі функції в продукті для видалення персональних даних для певного клієнта або користувача.

- **Керування запитами на видалення для даних клієнтів**: дані клієнтів у Customer Insights потрапляють з вихідних джерел даних, що знаходяться за межами Customer Insights. Усі запити на видалення в межах GDPR потрібно виконувати у вихідному джерелі даних.
- **Керування запитами на видалення даних користувача Customer Insights**: дані для користувачів створюються Customer Insights. Усі запити на видалення в межах GDPR мають виконуватися в програмі Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Керування запитами на видалення даних клієнтів

Адміністратор Customer Insights може виконати зазначені нижче кроки, щоб видалити дані про клієнта, що були видалені у джерелі даних.

1. Увійти до Dynamics 365 Customer Insights.
2. У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.
3. Для кожного джерела даних у списку, що містить видалені дані про клієнта, виконайте зазначені нижче дії.
   1. Виберіть (...), а потім виберіть **Оновити**.
   2. Перевірте стан джерела даних в області **Стан**. Галочка у полі означає, що оновлення пройшло успішно. Попереджувальний трикутник означає, що сталася помилка. Якщо відображається попереджувальний трикутник, зверніться за адресою D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Обробка запитів на видалення відповідно до GDPR для даних клієнтів.](audience-insights/media/gdpr-data-sources.png "Обробка запитів на видалення відповідно до GDPR для даних клієнтів")

##### <a name="manage-delete-requests-for-user-data"></a>Керування запитами на видалення для даних користувача

Адміністратор Customer Insights може виконати ці кроки, щоб видалити дані користувача Customer Insights.

1. Увійти до Dynamics 365 Customer Insights.
2. У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Дозволи**.
3. Установіть прапорець навпроти користувача, якого потрібно видалити.
4. Натисніть **Видалити**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Відповідь на запити на експорт суб’єкта даних GDPR

У рамках виконання наших зобов’язань підтримувати партнерство з вами на шляху до Генерального регламенту із захисту персональних даних (GDPR) ми розробили документацію, яка допоможе вам підготуватися. У цій документації описано кроки, які можна вжити сьогодні для підтримки відповідності GDPR під час використання аналізу аудиторії.

#### <a name="manage-export-and-view-requests"></a>Керування запитами на експорт і перегляд

Право на перенесення даних дозволяє суб’єктам даних запитувати копію своїх особистих даних у електронному форматі (за визначенням, у «структурованому, загальновживаному та сумісному форматі, що може бути зчитаний машиною»), яка може бути передана до іншого контролера даних.

##### <a name="export-customer-data-tenant-admin"></a>Експорт даних клієнтів (адміністратор клієнта)

Щоб експортувати дані, адміністратор клієнта може має виконати такі кроки.

1. Надіслати повідомлення електронної пошти на адресу D365CI@microsoft.com, в якому вказати адресу електронної пошти клієнта в заявці. Команда Customer Insights надішле електронне повідомлення на зареєстровану адресу електронної пошти адміністратора клієнта із запитом підтвердження експорту даних.
2. Отримати підтвердження експорту даних для клієнта, щодо якого створено запит.
3. Отримати експортовані дані на адресу електронної пошти адміністратора клієнта.

##### <a name="export-user-data-tenant-admin"></a>Експорт даних користувачів (адміністратор клієнта).

1. Надіслати повідомлення електронної пошти на адресу D365CI@microsoft.com, в якому вказати адресу електронної пошти користувача в заявці. Команда Customer Insights надішле електронне повідомлення на зареєстровану адресу електронної пошти адміністратора клієнта із запитом підтвердження експорту даних.
2. Отримати підтвердження експорту даних для користувача, щодо якого створено запит.
3. Отримати експортовані дані на адресу електронної пошти адміністратора клієнта.

## <a name="engagement-insights"></a>Аналітика взаємодії

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Видалення та експорт даних про події, що містять персональні дані кінцевого користувача

Наступні сценарії описують, як видалити та експортувати дані про події, що можуть містити персональні дані.

Щоб видалити або експортувати дані:

1. Позначте властивості події, які містять дані з особистими відомостями.
2. Видаліть або експортуйте дані, пов’язані з певними значеннями (наприклад, вказаний ідентифікатор користувача).

#### <a name="tag-and-update-event-properties"></a>Позначення та оновлення властивостей подій

Персональні дані позначаються на рівні властивості події. Спочатку позначте відомості, які призначено для видалення або експорту.

Щоб позначити властивість події як ту, що містить особисті відомості, виконайте ці кроки:

1. Відкрийте робочу області, що містить подію.

1. Перейдіть до розділу **Дані** > **Події**, щоб переглянути список подій у вибраній робочій області.
  
1. Виберіть подію, яку потрібно позначити.

1. Виберіть **Змінити властивості**, щоб відкрити панель з переліком усіх властивостей вибраної події.
     
1. Виберіть **...**, а потім виберіть **Змінити**, щоб відкрити діалогове вікно **Оновити властивість**.

   ![Змінити подію.](engagement-insights/media/edit-event.png "Змінити подію")

1. У вікні **Оновити властивості**, виберіть **...** у верхньому правому куті, а потім виберіть поле **Містить EUII**. Натисніть кнопку **Оновити**, щоб застосувати зміни.

   ![Зберегти зміни.](engagement-insights/media/update-property.png "Зберегти зміни")

   > [!NOTE]
   > Кожний раз, коли змінюється схема події або ви створюєте нову подію, рекомендується оцінити властивості пов’язаної події та позначити їх як ті, що містять персональні дані, або зняти таку позначку, якщо необхідно.

#### <a name="delete-or-export-tagged-event-data"></a>Видалення або експорт позначених даних подій

Якщо всі властивості події було відповідно позначено, як описано на попередньому кроці, адміністратор середовища може видати запит на видалення щодо позначених даних події.

Керування запитами на видалення та експорт EUII

1. Перейдіть до розділу **Адміністратор** > **Середовище** > **Настройки**.

1. У розділі **Керування персональними даними кінцевого користувача (EUII)** виберіть **Керування EUII**.

##### <a name="deletion"></a>Видалення

Для видалення ви можете ввести розділений комами список ідентифікаторів користувачів у розділі **Видалення персональних даних кінцевого користувача (EUII)**. Ці ідентифікатори потім буде порівняно з усіма позначеними властивостями подій усіх проектів у поточному середовищі через точне зіставлення рядків. 

Якщо значення властивості збігається з одним з наданих ідентифікаторів, пов’язану подію буде остаточно видалено. Через незворотний характер цієї дії ви маєте підтвердити видалення після натискання кнопки **Видалити**.

##### <a name="export"></a>Export

Процес експорту ідентичний процесу видалення у тому, що стосується визначення значень властивостей події в розділі **Експорт персональних даних кінцевого користувача (EUII)**. Також вам буде потрібно надати **URL-адресу сховища BLOB-даних Azure**, щоб указати місце призначення експорту. URL-адреса BLOB-об’єкта Azure має включати [Підпис спільного доступу (SAS)](/azure/storage/common/storage-sas-overview).

Після вибору елемента **Експорт** усі події поточної робочої групи, що містять відповідні позначені властивості, будуть експортовані у формат CSV у місце призначення експорту.

### <a name="good-practices"></a>Рекомендації

* Спробуйте уникнути надсилання будь-яких подій, щоб містять персональні дані.
* Якщо вам потрібно надіслати події, що містять дані EUII, обмежте кількість подій і властивості подій, що містять дані EUII. В ідеалі обмежтеся однією такою подією.
* Переконайтеся, що якнайменше користувачів мають доступ до надісланих персональних даних.
* Для подій, що містять персональні дані, переконайтеся, що ви налаштували одну властивість для виділення унікального ідентифікатора, який можна легко зв’язати з конкретним користувачем (наприклад, ідентифікатор користувача). Це полегшує ізоляцію даних і експорт або видалення правильних даних.
* Позначте лише одну властивість для однієї події як ту, що містить персональні дані. В ідеалі, ту, що містить лише унікальний ідентифікатор.
* Не позначайте властивості, що містять детальні значення (наприклад, увесь текст запиту). Засіб аналітичних висновків щодо взаємодії використовує точне зіставлення рядків, коли вирішує, які події видалити або експортувати.

[!INCLUDE[footer-include](includes/footer-banner.md)]