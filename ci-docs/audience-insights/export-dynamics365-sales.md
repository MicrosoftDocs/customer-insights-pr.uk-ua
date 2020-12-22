---
title: Експорт даних Customer Insights до Dynamics 365 Sales
description: Дізнайтесь, як налаштувати підключення до Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643843"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>З'єднувач для Dynamics 365 Sales (попередній перегляд)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Використовуйте дані клієнта для створення маркетингових списків, подальших робочих циклів і надсилання промо-акцій з даними Dynamics 365 Sales.

## <a name="prerequisite"></a>Передумова

Записи контактів [з переданого Dynamics 365 Sales за допомогою Common Data Service](connect-power-query.md).

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
