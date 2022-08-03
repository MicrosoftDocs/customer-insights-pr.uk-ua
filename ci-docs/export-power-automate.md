---
title: Power Automate сполучна лінія (попередній перегляд) | Документи корпорації Майкрософт
description: Створення циклів у Microsoft Power Automate з Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196143"
---
# <a name="power-automate-connector-preview"></a>З’єднувач Power Automate (підготовча версія)

Ініціюйте автоматичний запуск певних подій під час змінення даних і керуйте складнішими потоками безпосередньо в [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Відомі обмеження

- Максимум 100 дзвінків за 60 секунд. [Використовуйте параметр](/connectors/customerinsights/#get-items-from-an-entity) $skip, щоб викликати кінцеву точку API кілька разів.

## <a name="power-automate-triggers"></a>Тригери Power Automate

Використовуйте тригери для створення хмарних циклів та автоматизації повторюваних завдань, таких як сповіщення або більш складні дії. Використовуйте тригери, коли:

- Оновлення джерело даних не вдається.
- Оновлення джерело даних вдається.
- На відрізку переступають поріг. Тригер спрацьовує лише при перевищенні обмеження.
- На діловому заході переступає поріг. Підтримуються лише бізнес-показники без вимірів. Тригер спрацьовує лише при перевищенні обмеження.
- Завершено повне заплановане оновлення. Цей тригер не працює для оновлення, розпочатого вручну.
- Завершується оновлення процесу об'єднання.

[Налаштуйте свої тригери в Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Дії Power Automate

З'єднувач Power Automate, окрім тригерів, пропонує й інші дії. Додаткову інформацію наведено в посібнику[Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Створіть цикл Power Automate

1. Відкрийте **Адміністрування** > **Підключення**.

1. На плитці **Power Automate** виберіть **Налаштувати**.

1. Відкриється з’єднувач Customer Insights (підготовча версія) у Power Automate. **Увійти до** Power Automate.

1. Виберіть один із доступних тригерів і додайте більше кроків до нового циклу. Додаткові відомості: [Створення хмарних циклів у Power Automate](/power-automate/get-started-logic-flow).

Приклади використання циклів. 
- Надішліть повідомлення в канал Microsoft Teams, якщо оновлення джерела даних невдале. 
- Надсилайте повідомлення електронної пошти власникам даних, коли буде досягнуто граничне значення для сегмента.

[!INCLUDE [footer-include](includes/footer-banner.md)]
