---
title: Експорт сегментів у Dynamics 365 Marketing (попередній перегляд)
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
ms.openlocfilehash: fed4ae1b017cca2b6060c4dda155859cd77e0daf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054641"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Експорт сегментів у Dynamics 365 Marketing (попередній перегляд)

Використовуйте [сегменти](segments.md), щоб формувати кампанії та специфічні групи клієнтів за допомогою Dynamics 365 Marketing. Для отримання додаткових відомостей див. [Використання сегментів з Dynamics 365 Customer Insights у Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Якщо ви використовуєте нові можливості Dynamics 365 Marketing для оркестрації шляху клієнта в реальному часі в організації Dataverse, то створювати стандартний експорт до Dynamics 365 Marketing не потрібно. Контакти та сегменти з Customer Insights доступні безпосередньо в Dynamics 365 Marketing після підключення marketing та Customer Insights. Перш ніж видаляти наявні експорти, перегляньте документацію про [те, як підключити Customer Insights і Dynamics 365 Marketing шлях клієнта оркестровку](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Попередня вимога для підключення

- Записи контактних осіб мають бути присутніми в Dynamics 365 Marketing, щоб ви змогли експортувати сегмент з Customer Insights до Marketing. Дізнайтеся більше про те, як прийняти контактних осіб у [Dynamics 365 Marketing, використовуючи Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Експорт сегментів із Customer Insights до Marketing не створить нових записів контактів у маркетингових інстанціях. Записи контактів із відділу маркетингу повинні надходити в Customer Insights і використовуватися як джерело даних. Їх також потрібно включити в уніфіковану сутність «Клієнт», щоб зіставити ідентифікатори клієнтів із ідентифікаторами контактних осіб, перш ніж можна буде експортувати сегменти.

## <a name="set-up-connection-to-marketing"></a>Налаштування підключення до Marketing

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення** та оберіть **Dynamics 365 Marketing**, щоб налаштувати підключення.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть URL-адресу Marketing вашої організації в полі **Адреса сервера**.

1. У розділі **Обліковий запис адміністратора сервера** виберіть **Увійти** і оберіть обліковий запис Dynamics 365 Marketing.

1. Зіставте поле «Ідентифікатор контакту» в організації клієнта з ідентифікатором контакту Dynamics 365.

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
