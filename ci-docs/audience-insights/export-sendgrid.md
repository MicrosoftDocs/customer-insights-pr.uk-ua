---
title: Експорт даних Customer Insights до SendGrid
description: Дізнайтеся, як налаштувати підключення та експорт до SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 03df2ab5fce1da1f4f662e1975533f2b538b47dbdd5cf96aae4f1007163e3729
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036126"
---
# <a name="export-segments-to-sendgrid-preview"></a>Експорт сегментів до SendGrid (підготовча версія)

Експортуйте сегменти уніфікованих профілів клієнтів до списків контактних осіб SendGrid і використовуйте їх для кампаній та маркетингових електронних розсилок в SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Попередні вимоги для підключення

-   Ви маєте [обліковий запис SendGrid](https://sendgrid.com/) і відповідні облікові дані адміністратора.
-   У SendGrid наявні списки контактних осіб й відповідні ідентифікатори. Для отримання додаткових відомостей див. [SendGrid — Керування контактними особами](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Ви маєте [налаштовувані сегменти](segments.md) у аналізах аудиторії.
-   Уніфіковані профілі клієнтів у експортованих сегментах містять поле, що представляє адресу електронної пошти.

## <a name="known-limitations"></a>Відомі обмеження

- До 100 000 профілів в цілому до SendGrid.
- Експорт до SendGrid обмежується сегментами.
- Експортування до 100 000 профілів до SendGrid може тривати кілька годин. 
- Кількість профілів, які можна експортувати до SendGrid, залежить від сервісного договору з SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Налаштування підключення до SendGrid

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення** та оберіть **SendGrid**, щоб налаштувати підключення.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть **ключ API SendGrid** [ключ API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.

1. Виберіть **Підключити**, щоб ініціалізувати підключення до SendGrid.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати призначення**.

1. У полі **Підключення для експорту** виберіть підключення з розділу SendGrid. Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. Введіть **[ідентифікатор списку SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. У розділі **Зіставлення даних** в полі **Електронна пошті**, виберіть поле в уніфікованому профілі клієнта, в якому відображено адресу електронної пошти клієнта. Повторіть ці самі кроки для інших необов'язкових полів, таких як **Ім'я**, **Прізвище**, **Країна або регіон**, **Штат**, **Місто** і **Поштовий індекс**.

1. Виберіть сегменти, які потрібно експортувати. Ми настійно **рекомендуємо не експортувати більше 100 000 профілів клієнтів в цілому** до SendGrid. 

1. Виберіть **Зберегти**.

При збереженні експорт не запуститься негайно.

Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab). Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

Коли ви вмикаєте передавання даних до SendGrid у Dynamics 365 Customer Insights, ви дозволяєте перенесення даних за межі нормативного регіону для Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними. Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але на вас покладено усю відповідальність за забезпечення того, щоб компанія SendGrid відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.


[!INCLUDE[footer-include](../includes/footer-banner.md)]