---
title: Експорт даних Customer Insights до Dynamics 365 Marketing
description: Дізнайтесь, як налаштувати підключення до Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643798"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>З'єднувач для Dynamics 365 Marketing (попередній перегляд)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Використовуйте [сегменти](segments.md), щоб формувати кампанії та специфічні групи клієнтів за допомогою Dynamics 365 Marketing. Для отримання додаткових відомостей див. [Використання сегментів з Dynamics 365 Customer Insights у Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Передумова

Записи контактів [з прийнятого Dynamics 365 Marketing Common Data Service](connect-power-query.md).

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
