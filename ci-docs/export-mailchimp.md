---
title: Експорт даних Customer Insights до Mailchimp
description: Дізнайтеся, як налаштувати підключення та експорт до Mailchimp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 394287f861df69a88209aae9d857e795d3528cd7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644179"
---
# <a name="export-segments-to-mailchimp-preview"></a>Експорт сегментів до Mailchimp (підготовча версія)

Експорт сегментів уніфікованих профілів клієнтів до Mailchimp для створення інформаційних бюлетенів і кампаній електронної пошти.

## <a name="prerequisites-for-connection"></a>Попередні вимоги для підключення

-   Ви маєте [обліковий запис Mailchimp](https://mailchimp.com/) і відповідні облікові дані адміністратора.
-   У Mailchimp наявні аудиторії й відповідні ідентифікатори. Для отримання додаткових відомостей див. [Аудиторії Mailchimp](https://mailchimp.com/help/create-audience/).
-   Ви маєте [налаштовані сегменти](segments.md)
-   Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.

## <a name="known-limitations"></a>Відомі обмеження

- До 1 мільйона профілів клієнтів в кожному експорті в Mailchimp.
- Експорт до Mailchimp обмежується сегментами.
- Експортування сегментів із 1 мільйоном профілів клієнтів може тривати до трьох годин. 
- Кількість профілів клієнтів, які можна експортувати в Mailchimp, визначається та обмежується умовами вашого сервісного договору з Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Налаштування підключення до Mailchimp

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть розділ **Додати підключення**, потім виберіть **Mailchimp**, щоб налаштувати підключення.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.

1. Виберіть **Підключити**, щоб ініціалізувати підключення до Mailchimp.

1. Виберіть **Автентифікацію за допомогою Mailchimp** і надайте облікові дані Mailchimp.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**. 

## <a name="configure-the-connector"></a>Настроювання з’єднувача

Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати призначення**.

1. У полі **Підключення для експорту** виберіть підключення з розділу Mailchimp. Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. Уведіть свій **[Ідентифікатор аудиторії Mailchimp](https://mailchimp.com/help/find-audience-id/)**

1. У розділі **Зіставлення даних** у полі **Електронна пошта** виберіть поле, яке відповідає адресі електронної пошти клієнта. 

1. За бажанням ви можете експортувати **Ім'я** та **Прізвище**, щоб створювати більш персоналізовані електронні листи. Виберіть **Додати атрибут**, щоб зіставити ці поля.

1. Виберіть сегменти, які потрібно експортувати. Загалом до Mailchimp можна експортувати до 1 000 000 профілів клієнтів.

1. Виберіть **Зберегти**.

При збереженні експорт не запуститься негайно.

Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab). Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

Під час увімкнення Dynamics 365 Customer Insights для передавання даних до Mailchimp можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними. Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб компанія Mailchimp відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.

[!INCLUDE [footer-include](includes/footer-banner.md)]