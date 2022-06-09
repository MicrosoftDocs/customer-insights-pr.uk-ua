---
title: З’єднувач Power Automate | Microsoft Docs
description: Створення циклів у Microsoft Power Automate з Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d22c4c785695b23a257a89f1ffa519fdc18b443e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741204"
---
# <a name="power-automate-connector-preview"></a>З’єднувач Power Automate (підготовча версія)

Ініціюйте автоматичний запуск певних подій під час змінення даних і керуйте складнішими потоками безпосередньо в [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Відомі обмеження

- Ви можете робити максимум 100 дзвінків за 60 секунд. Ви можете викликати кінцеву точку API кілька разів за допомогою параметра $skip. [Докладніше про параметр $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Тригери Power Automate

Використовуйте тригери для створення хмарних циклів та автоматизації повторюваних завдань, таких як сповіщення або більш складні дії.

- Тригер на помилку під час оновлення джерела даних.
- Тригер на успішне оновлення джерела даних.
- Тригер на перетин межі для граничного значення для сегмента. Тригер спрацьовує лише при перевищенні обмеження.
- Тригер на перетин межі для граничного значення для бізнес-показника. Підтримуються лише бізнес-показники без вимірів. Тригер спрацьовує лише при перевищенні обмеження.
- Тригер після завершення повного оновлення (джерела даних, сегменти, показники, ...).
- Тригер після завершення оновлення процесу об'єднання.

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