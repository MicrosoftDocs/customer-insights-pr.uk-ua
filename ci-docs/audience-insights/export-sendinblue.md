---
title: Експортуйте дані Customer Insights до Sendinblue
description: Дізнайтеся про те, як налаштувати підключення та експортувати дані до Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: be52554763b57e1c1ef2f960d52bbae79ac9827913c97ac73b429f66bbf4db37
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036080"
---
# <a name="export-segments-to-sendinblue-preview"></a>Експортуйте сегменти до Sendinblue (підготовча версія)

Експортуйте сегменти єдиних профілів клієнтів, щоб створювати кампанії, здійснювати маркетинг електронною поштою, а також використовуйте за допомогою Sendinblue спеціальні групи клієнтів.

## <a name="prerequisites-for-connection"></a>Попередні вимоги для підключення

-   У вас є [обліковий запис Sendinblue](https://www.sendinblue.com/) і відповідні облікові дані адміністратора.
-   У Sendinblue вже є наявні списки та відповідні ідентифікатори.
-   Ви маєте [налаштовані сегменти](segments.md).
-   Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.

## <a name="known-limitations"></a>Відомі обмеження

- До Sendinblue можна експортувати до одного мільйона профілів.
- Експорт до Sendinblue обмежується сегментами.
- Процедура експортування сегментів із одним мільйоном профілів може займати до 90 хвилин часу. 
- Кількість профілів, які ви можете експортувати до Sendinblue, визначається й обмежується сервісним договором із Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Налаштуйте підключення до Sendinblue

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть розділ **Додати підключення**, потім виберіть **Sendinblue**, щоб налаштувати підключення.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За замовчуванням це будуть лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть **[ключ API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Виберіть пункт **Погоджуюся**, щоб підтвердити обов’язковість розділу **Конфіденційність і відповідність даних**, потім виберіть **Підключитися** для ініціалізації підключення до Sendinblue.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати призначення**.

1. У полі **Підключення для експорту** виберіть підключення з розділу Sendinblue. Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. Введіть **Ідентифікатор списку Sendinblue** 

1. У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта. 

1. Додатково ви можете експортувати **Ім’я**, **Прізвище** й **Телефон**, щоб створювати персоналізовані повідомлення електронної пошти. Виберіть **Додати атрибут**, щоб зіставити ці поля.

1. Виберіть сегменти, які потрібно експортувати. 

1. Виберіть **Зберегти**.

При збереженні експорт не запуститься негайно.

Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab). Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

При увімкненні Dynamics 365 Customer Insights для передавання даних до Sendinblue ви також надаєте дозвіл на передавання даних поза межі нормативно-правової відповідності для Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, такими як особисті дані. Майкрософт виконає передавання таких даних за вашою вказівкою, але ви несете відповідальність за забезпечення того, щоб Sendinblue відповідала зобов’язанням щодо конфіденційності або безпеки, які можуть у вас бути. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити це призначення експорту, щоб припинити користуватися цією функцією.


[!INCLUDE[footer-include](../includes/footer-banner.md)]