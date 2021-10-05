---
title: Інтеграція веб-даних від аналітичних висновків щодо взаємодії із аналізом аудиторії
description: Додайте до аналізу аудиторії відомості про клієнтів, отримані з аналітичних висновків щодо взаємодії.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2789a7d1379e0cf56511b272a763c904d8a3d347058ea9e029aaff0f723a028
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033794"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Інтеграція веб-даних від аналітичних висновків щодо взаємодії із аналізом аудиторії

Клієнти часто виконують повсякденні транзакції в Інтернеті на тих або інших веб-сайтах. Функція аналітичних висновків щодо взаємодії (підготовча версія) в Dynamics 365 Customer Insights є зручним рішенням із інтеграції веб-даних як джерела. На додаток до транзакційних, демографічних або поведінкових даних, ми можемо бачити діяльність в Інтернеті в уніфікованих профілях клієнтів. Ми можемо користуватися цими профілями для отримання додаткових аналітичних висновків, таких як сегменти, міри або прогнози для активації аудиторії.

У цій статті описано кроки, які дозволять використовувати відомості щодо діяльності ваших клієнтів на веб-сторінках, отримані з аналітичних висновків щодо взаємодії, у наявному середовищі аналізу аудиторії.

У цьому прикладі ми вважатимемо, що існує середовище із уніфікованими профілями клієнтів. Профілі були уніфіковані з джерелами з опитувань, роздрібних продажів та системи запитів. Також відображаються пов'язані справи клієнтів. 

Тепер ми хочемо дізнатись, чи відвідує певний клієнт наші веб-майданчики та вивчити його справи. Справи можуть складатись з, наприклад, відвіданих веб-сторінок або сторінок продуктів, відкритих за посиланням з повідомлення електронної пошти.

## <a name="prerequisites"></a>Вимоги

Щоб інтегрувати дані з аналітичних висновків щодо взаємодії, необхідно виконати кілька попередніх умов. 

- Інтегруйте SDK аналітичних висновків щодо взаємодії із вашим веб-сайтом. Докладніші відомості див. у розділі [Огляд ресурсів розробника](../engagement-insights/developer-resources.md).
- Для експорту веб-подій із аналітичних висновків щодо взаємодії потрібен доступ до облікового запису Azure Data Lake Storage, який буде використовуватися для обробки даних веб-подій щодо аналізу аудиторії. Додаткові відомості: [Експорт подій](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Налаштування скоригованих подій у аналітичних висновках щодо взаємодії

Після того, як адміністратор оснастить веб-сайт інструментами у вигляді SDK аналітичних висновків щодо взаємодії, коли користувач переглядає веб-сторінку або клацає в будь-якому місці, збираються *базові події*. Базові події, як правило, містять велику кількість подробиць. Залежно від вашого завдання, вам знадобиться лише підмножина даних з базової події. Аналітичні в висновки щодо взаємодії дозволяють створити *скориговані події*, які містять лише вибрані вами властивості базової події.     

Додаткові відомості: [Створення та редагування скоригованих подій](../engagement-insights/refined-events.md).

Нижче наведено деякі міркування щодо створення скоригованих подій. 

- Вказуйте зрозуміле ім'я для скоригованої події. Це використовуватиметься як ім’я справи в аналізі аудиторії.
- Щоб створити справу в аналізі аудиторії, виберіть принаймні такі властивості: 
    - Signal.Action.Name – зазначає відомості про справу.
    - Signal.User.Id – використовується для зіставлення з індикатором клієнта.
    - Signal.View.Uri – використовується як веб-адреса у вигляді основи для сегментів або мір.
    - Signal.Export.Id – використовується як первинний ключ для подій.
    - Signal.Timestamp – визначає дату та час справи.

Виберіть фільтри, щоб зосередитися на подіях і сторінках, які важливі для поточного завдання. У цьому прикладі ми використовуватимемо назву справи «Розповсюдження електронної пошти».

## <a name="export-the-refined-web-events"></a>Експортуйте уточнені веб-події 

Після визначення уточненої події ви маєте налаштувати експорт даних події до Azure Data Lake Storage, яке можна налаштувати як джерело даних для обробки в аналітиці аудиторії. Експорт відбуватиметься постійно при надходженні подій з веб-майданчика.

Додаткові відомості: [Експорт подій](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Отримання даних подій у аналізу аудиторії

Тепер, коли ви визначили скориговану подію та налаштували її експорт, час переходити до внесення даних до аналізу аудиторії. Потрібно створити нове джерело даних на основі папки Common Data Model. Введіть відомості облікового запису сховища, куди експортуються події. У файлі *default.cdm.json* виберіть скориговану подію для передавання та створіть сутність в аналізі аудиторії.

Докладніші відомості див. у розділі [Підключення до папки Common Data Model із використанням облікового запису Azure Data Lake](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Посилання на дані скоригованої події як на справу профілю клієнта

Після завершення прийому сутності можна налаштувати справу для профілю клієнта.

Додаткові відомості див. в розділі [Справи клієнта](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Сторінка справ із розгорнутою областю редагування справи та заповненими полями.":::

Налаштуйте нову справу, скориставшись таким зіставленням: 

- **Первинний ключ**: Signal.Export.Id – це унікальний ідентифікатор, доступний для кожного запису події в аналітичних висновках щодо взаємодії. Ця властивість створюється автоматично.

- **Позначка часу**: Signal.Timestamp у властивості події.

- **Подія**: Signal.Name – ім'я події, яку ви бажаєте відстежувати.

- **Веб-адреса**: Signal.View.Uri – стосується URI сторінки, на якій створено подію.

- **Докладні відомості**: Signal.Action.Name – представляє собою інформацію, яку передбачається пов’язати з подією. Вибрана властивість у даному випадку означає, що подія стосується розповсюдження електронної пошти.

- **Тип справи**: у цьому прикладі ми вибрали наявний тип справи WebLog. Цей вибір дає зручну можливість запускати моделі прогнозування або створювати сегменти, основані на цьому типі справи.

- **Настроювання зв'язку**: цей важливий параметр пов'язує справу з наявними профілями клієнтів. **Signal.User.Id** — це ідентифікатор, налаштований у SDK, який повинен бути отриманий та відповідає ідентифікатору користувача в інших джерелах даних, налаштований у аналізі аудиторії. У цьому прикладі ми налаштовуємо зв’язок між Signal.User.Id і RetailCustomers:CustomerRetailId, що є первинним ключем, визначеним на кроці зіставлення процесу уніфікації даних.

Після обробки справ можна переглянути записи клієнтів і відкрити картку клієнта, щоб переглянути справи з аналітичних висновків щодо взаємодії на часовій шкалі. 

> [!TIP]
> Щоб дізнатись ідентифікатор клієнта, для якого виконано справу в аналітичних висновках щодо взаємодії, перейдіть до **Сутності** й перегляньте дані для сутності UnifiedActivity. ActivityTypeDisplay = WebLog – містить справу з аналітичних висновків щодо взаємодії, налаштовану в наведеному вище прикладі. Скопіюйте ідентифікатор клієнта для одного з цих записів і знайдіть цей ідентифікатор на сторінці **Клієнти**.

## <a name="next-steps"></a>Наступні кроки

Тепер можна створювати [сегменти](segments.md), [показники](measures.md) та [прогнози](predictions.md), щоб налагоджувати змістовні зв'язки із клієнтами.


[!INCLUDE[footer-include](../includes/footer-banner.md)]