---
title: Експорт даних Customer Insights до Dynamics 365 Marketing
description: Дізнайтеся, як налаштувати підключення та експорт до Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642966"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Використання сегментів у Dynamics 365 Marketing (підготовча версія)



Використовуйте [сегменти](segments.md), щоб формувати кампанії та специфічні групи клієнтів за допомогою Dynamics 365 Marketing. Для отримання додаткових відомостей див. [Використання сегментів з Dynamics 365 Customer Insights у Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Якщо ви використовуєте нові можливості Dynamics 365 Marketing для оркестрації шляху клієнта в реальному часі в організації Dataverse, то створювати стандартний експорт до Dynamics 365 Marketing не потрібно. Контакти та сегменти з Customer Insights доступні безпосередньо в Dynamics 365 Marketing після підключення маркетингу та статистики клієнтів. Перш ніж видалити наявний експорт, перегляньте документацію про [підключення статистики клієнтів і динаміки 365 маркетингу шлях клієнта оркестровки](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Попередня вимога для підключення

- Записи контактних осіб мають бути присутніми в Dynamics 365 Marketing, щоб ви змогли експортувати сегмент з Customer Insights до Marketing. Дізнайтеся більше про те, як прийняти контактних осіб у [Dynamics 365 Marketing, використовуючи Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Експорт сегментів зі статистики клієнтів до маркетингу не призведе до створення нових записів контактів у екземплярах маркетингу. Контактні записи з маркетингу повинні потрапляти в статистику клієнтів і використовуватися як джерело даних. Їх також потрібно включити в уніфіковану сутність «Клієнт», щоб зіставити ідентифікатори клієнтів із ідентифікаторами контактних осіб, перш ніж можна буде експортувати сегменти.

## <a name="set-up-connection-to-marketing"></a>Налаштування підключення до Marketing

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення** та оберіть **Dynamics 365 Marketing**, щоб налаштувати підключення.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть URL-адресу Marketing вашої організації в полі **Адреса сервера**.

1. У розділі **Обліковий запис адміністратора сервера** виберіть **Увійти** і оберіть обліковий запис Dynamics 365 Marketing.

1. Зіставте поле Ідентифікатор контакту в сутності клієнта з ідентифікатором контакту Dynamics 365.

1. Щоб завершити створення підключення, виберіть **Зберегти**. 

## <a name="configure-an-export"></a>Налаштування експорту

Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати призначення**.

1. У полі **Підключення для експорту** виберіть підключення з розділу Dynamics 365 Marketing. Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. Виберіть один або кілька сегментів.

1. Виберіть **Зберегти**.

При збереженні експорт не запуститься негайно.

Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab). Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]