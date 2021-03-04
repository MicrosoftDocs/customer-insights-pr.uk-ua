---
title: Експорт даних Customer Insights до Dynamics 365 Marketing
description: Дізнайтесь, як налаштувати підключення до Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269079"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>З'єднувач для Dynamics 365 Marketing (попередній перегляд)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Використовуйте [сегменти](segments.md), щоб формувати кампанії та специфічні групи клієнтів за допомогою Dynamics 365 Marketing. Для отримання додаткових відомостей див. [Використання сегментів з Dynamics 365 Customer Insights у Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Передумова

- Записи контактних осіб мають бути присутніми в Dynamics 365 Marketing, щоб ви змогли експортувати сегмент з Customer Insights до Marketing. Дізнайтеся більше про те, як прийняти контактних осіб у [Dynamics 365 Marketing, використовуючи Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Експортування сегментів з аналізу аудиторії до Marketing не призведе до створення нових записів контактних осіб в інсталяціях Marketing. Записи контактних осіб з Marketing повинні бути прийняті в аналізі аудиторії та мають використовуватися, як джерело даних. Їх також потрібно включити в уніфіковану сутність «Клієнт», щоб зіставити ідентифікатори клієнтів із ідентифікаторами контактних осіб, перш ніж можна буде експортувати сегменти.

## <a name="configure-the-connector-for-marketing"></a>Налаштування з'єднувача для Marketing

1. У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.

1. В області **Dynamics 365 Marketing** виберіть **Налаштувати**.

1. Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.

1. Введіть URL-адресу Marketing вашої організації в полі **Адреса сервера**.

1. У розділі **Обліковий запис адміністратора сервера** виберіть **Увійти** і оберіть обліковий запис Dynamics 365 Marketing.

1. Зіставте поле ІДЕНТИФІКАТОРА клієнта з ІДЕНТИФІКАТОРОМ контакту Dynamics 365.

1. Виберіть **Далі**.

1. Виберіть один або кілька сегментів.

1. Виберіть **Зберегти**.

## <a name="export-the-data"></a>Експорт даних

Ви можете [експортувати дані вручну](export-destinations.md). Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]