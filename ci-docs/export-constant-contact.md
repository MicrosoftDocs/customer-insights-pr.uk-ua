---
title: Експортування даних Customer Insights до Constant Contact
description: Дізнайтеся, як налаштувати підключення та експорт до Constant Contact.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 310de0355f71829346f0e35508487e5962d6e912
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644144"
---
# <a name="export-segments-to-constant-contact-preview"></a>Експорт сегментів до Constant Contact (підготовча версія)

Експортуйте сегменти, що складаються з уніфікованих профілів клієнтів, до Constant Contact і використовуйте їх для маркетингової діяльності. 

## <a name="prerequisites-for-a-connection"></a>Попередні вимоги для підключення

-   У вас є [обліковий запис Constant Contact](https://www.constantcontact.com/account-home) і відповідні облікові дані адміністратора.
-   Ви налаштували [сегменти](segments.md) в Службі статистики клієнтів.
-   Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.

## <a name="known-limitations"></a>Відомі обмеження

- В межах одного експорту до Constant Contact можна експортувати до 1 мільйона профілів клієнтів.
- Експортувати в Constant Contact можна тільки сегменти.
- Експортування до 1 мільйона профілів клієнтів до Constant Contact може тривати до 1 години. 
- Кількість профілів клієнтів, які можна експортувати в Constant Contact, визначається та обмежується умовами вашого сервісного договору з Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>Налаштуйте підключення до Constant Contact

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення**, потім виберіть **Constant Contact**, щоб налаштувати підключення.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.

1. Виберіть **Підключити**, щоб ініціалізувати підключення до Constant Contact.

1. Натисніть **Автентифікація за допомогою Constant Contact** і вкажіть свої облікові дані адміністратора для Constant Contact. 

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати призначення**.

1. У полі **Підключення для експорту** виберіть підключення з розділу «Constant Contact». Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. Введіть свій [**ідентифікатор списку Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Відкрийте список у Constant Contact, щоб знайти ідентифікатор списку в URL-адресі.

1. У розділі **Зіставлення даних** у полі **Електронна пошта** виберіть поле, яке відповідає адресі електронної пошти клієнта. Це необхідно для експорту сегментів до Constant Contact.

1. Додатково можна експортувати Ім'я та Прізвище у вигляді додаткових полів для створення додаткових персоналізованих електронних листів. Виберіть **Додати атрибут**, щоб зіставити ці поля.

1. Виберіть сегменти, які потрібно експортувати.

1. Виберіть **Зберегти**.

При збереженні експорт не запуститься негайно.

Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab). Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

Коли ви дозволяєте Dynamics 365 Customer Insights передавати дані до Constant Contact, ви дозволяєте передавати дані за межі нормативного регіону Dynamics 365 Customer Insights, зокрема й такі потенційно конфіденційні дані, як персональна інформація. Майкрософт передаватиме такі дані за вашим розпорядженням, але ви несете відповідальність за забезпечення відповідності Constant Contact будь-яким вимогам щодо конфіденційності та безпеки, що можуть виникати. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.