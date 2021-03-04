---
title: З’єднувач Power Automate | Microsoft Docs
description: Створення циклів у Microsoft Power Automate із Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268849"
---
# <a name="power-automate-connector-preview"></a>З’єднувач Power Automate (підготовча версія)

Ініціюйте автоматичний запуск певних подій під час змінення даних і керуйте складнішими потоками безпосередньо в [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Тригери Power Automate

Використовуйте тригери для створення хмарних циклів та автоматизації повторюваних завдань, таких як сповіщення або більш складні дії. 

- Тригер на помилку під час оновлення джерела даних. 
- Тригер на успішне оновлення джерела даних.
- Тригер на перетин межі для граничного значення для сегмента. Тригер спрацьовує лише при перевищенні обмеження.
- Тригер на перетин межі для граничного значення для бізнес-показника. Тригер спрацьовує лише при перевищенні обмеження.
- Тригер після завершення повного оновлення (джерела даних, сегменти, показники,...).
- Ініціюється, коли завершується оновлення процесу уніфікації (зіставлення, відповідність, злиття).

[Налаштування тригерів у Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Дії Power Automate
З'єднувач Power Automate, окрім тригерів, пропонує й інші дії. Додаткову інформацію наведено в посібнику[Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Створіть цикл Power Automate

1. У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.

1. На плитці **Power Automate** виберіть **Налаштувати**.

1. Відкриється з’єднувач Customer Insights (підготовча версія) у Power Automate. **Увійти до** Power Automate.

1. Виберіть один із доступних тригерів і додайте більше кроків до нового циклу. Додаткові відомості: [Створення хмарних циклів у Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Приклади використання циклів: 
- Надішліть повідомлення в канал Microsoft Teams, якщо оновлення джерела даних невдале. 
- Надсилайте повідомлення електронної пошти власникам даних, коли буде досягнуто граничне значення для сегмента.



[!INCLUDE[footer-include](../includes/footer-banner.md)]