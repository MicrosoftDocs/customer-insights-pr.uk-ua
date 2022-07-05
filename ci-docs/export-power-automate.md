---
title: Power Automate сполучна лінія (попередній перегляд) | Документи Microsoft
description: Створення циклів у Microsoft Power Automate з Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29a861dad926072f6f849d738d868f0f3b9306be
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082460"
---
# <a name="power-automate-connector-preview"></a>З’єднувач Power Automate (підготовча версія)

Ініціюйте автоматичний запуск певних подій під час змінення даних і керуйте складнішими потоками безпосередньо в [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Відомі обмеження

- Ви можете зробити максимум 100 дзвінків за 60 секунд. Ви можете викликати кінцеву точку API кілька разів, використовуючи параметр $skip. [Дізнайтеся більше про параметр $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Тригери Power Automate

Використовуйте тригери для створення хмарних циклів та автоматизації повторюваних завдань, таких як сповіщення або більш складні дії.

- Тригер на помилку під час оновлення джерела даних.
- Тригер на успішне оновлення джерела даних.
- Тригер на перетин межі для граничного значення для сегмента. Тригер спрацьовує лише при перевищенні обмеження.
- Тригер на перетин межі для граничного значення для бізнес-показника. Підтримуються лише бізнес-показники без вимірів. Тригер спрацьовує лише при перевищенні обмеження.
- Тригер після завершення повного оновлення (джерела даних, сегменти, показники, ...).
- Спрацьовують, коли оновлення процесу об'єднання завершено.

[Налаштуйте свої тригери в Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Дії Power Automate

З'єднувач Power Automate, окрім тригерів, пропонує й інші дії. Додаткову інформацію наведено в посібнику[Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Створіть цикл Power Automate

1. Відкрийте **Адміністрування** > **Призначення експорту**.

1. На плитці **Power Automate** виберіть **Налаштувати**.

1. Відкриється з’єднувач Customer Insights (підготовча версія) у Power Automate. **Увійти до** Power Automate.

1. Виберіть один із доступних тригерів і додайте більше кроків до нового циклу. Додаткові відомості: [Створення хмарних циклів у Power Automate](/power-automate/get-started-logic-flow).

Приклади використання циклів. 
- Надішліть повідомлення в канал Microsoft Teams, якщо оновлення джерела даних невдале. 
- Надсилайте повідомлення електронної пошти власникам даних, коли буде досягнуто граничне значення для сегмента.



[!INCLUDE [footer-include](includes/footer-banner.md)]
