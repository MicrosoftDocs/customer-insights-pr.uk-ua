---
title: З’єднувач Power Automate | Microsoft Docs
description: Створення циклів у Microsoft Power Automate із Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407232"
---
# <a name="power-automate-connector-preview"></a>З’єднувач Power Automate (підготовча версія)

Ініціюйте автоматичний запуск певних подій під час змінення даних і керуйте складнішими потоками безпосередньо в [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Тригери Power Automate

Ви можете використовувати різноманітні тригери, які дозволять створювати потоки для автоматизації повторюваних завдань, наприклад, сповіщень або інших додаткових дій. 

- Тригер на помилку під час оновлення джерела даних. 
- Тригер на успішне оновлення джерела даних.
- Тригер на перетин межі для граничного значення для сегмента. Тригер спрацьовує лише при перевищенні обмеження.
- Тригер на перетин межі для граничного значення для бізнес-показника. Тригер спрацьовує лише при перевищенні обмеження.
- Тригер після завершення повного оновлення (джерела даних, сегменти, показники,...).
- Ініціюється, коли завершується оновлення процесу уніфікації (зіставлення, відповідність, злиття).

[Налаштування тригерів у Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Дії Power Automate
З'єднувач Power Automate, окрім тригерів, пропонує й інші дії. Додаткову інформацію наведено в посібнику[Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Створення потоку Power Automate у аналізі аудиторій

1. У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Система**.

1. На сторінці **Система** перейдіть на вкладку **Стан**.

1. У розділі **Джерела даних** виберіть **Потоки**, а потім виберіть **Створити потік** із розкривного списку.
   > [!div class="mx-imgBorder"]
   > ![З’єднувач Power Automate: дія "Створити цикл"](media/power-automate-connector-create-flow.png "З’єднувач Power Automate: дія &quot;Створити цикл&quot;")

1. У Power Automate виберіть один із доступних тригерів для створення потрібного потоку. Під час створення першого циклу спочатку потрібно буде пройти автентифікацію за допомогою з’єднувача Power Automate.
