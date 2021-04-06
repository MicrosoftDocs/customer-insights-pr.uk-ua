---
title: Експорт даних Customer Insights до Dynamics 365 Sales
description: Дізнайтесь, як налаштувати підключення до Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598134"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>З'єднувач для Dynamics 365 Sales (попередній перегляд)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Використовуйте дані клієнта для створення маркетингових списків, подальших робочих циклів і надсилання промо-акцій з даними Dynamics 365 Sales.

## <a name="prerequisite"></a>Передумова

1. Записи контактних осіб мають бути присутніми в Dynamics 365 Sales, щоб ви змогли експортувати сегмент з Customer Insights до Sales. Дізнайтеся більше про те, як прийняти контактних осіб у [Dynamics 365 Sales, використовуючи Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Експортування сегментів з аналізу аудиторії до Sales не призведе до створення нових записів контактних осіб в інсталяціях Sales. Записи контактних осіб з Sales повинні бути прийняті в аналізі аудиторії та мають використовуватися, як джерело даних. Їх також потрібно включити в уніфіковану сутність «Клієнт», щоб зіставити ідентифікатори клієнтів із ідентифікаторами контактних осіб, перш ніж можна буде експортувати сегменти.

## <a name="configure-the-connector-for-sales"></a>Налаштування з'єднувача для Sales

1. У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.

1. В області **Dynamics 365 Sales** виберіть **Налаштувати**.

1. Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.

1. Введіть URL-адресу Sales вашої організації в полі **Адреса сервера**.

1. У розділі **Обліковий запис адміністратора сервера** виберіть **Увійти** і оберіть обліковий запис Dynamics 365 Sales.

1. Зіставте поле ІДЕНТИФІКАТОРА клієнта з ІДЕНТИФІКАТОРОМ контакту Dynamics 365.

1. Виберіть **Далі**.

1. Виберіть один або кілька сегментів.

1. Виберіть **Зберегти**.

## <a name="export-the-data"></a>Експорт даних

Ви можете [експортувати дані вручну](export-destinations.md). Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]