---
title: Бот для Microsoft Teams
description: Пошук уніфікованих профілів клієнтів за допомогою Microsoft Teams з допомогою бота.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 9bf401124b0ffb21b046954056141e7703386d4911f89f34ffc0fcb84bf0f4be
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032507"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Бот команди для Dynamics 365 Customer Insights (попередній перегляд)

Підключайтеся до Microsoft Teams, щоб дозволити боту шукати уніфіковані профілі клієнтів у каналах команди.

> [!div class="mx-imgBorder"]
> ![Бот для Teams, що показує запис клієнта.](media/teams-bot.png "Бот для Teams, що показує запис клієнта")

## <a name="prerequisites"></a>Вимоги

Для налаштування та настроювання бота повинні виконуватися нижчезазначені передумови.

- Додано щонайменше одне [джерело даних](data-sources.md).
- Завершено [процес уніфікації](data-unification.md).
- До [покажчика пошуку і фільтрації](search-filter-index.md) додано поля.
- Customer Insights і Teams відносяться до однієї організації.

## <a name="configure-the-bot"></a>Настроювання бота

1. У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.
1. На плитці Microsoft Teams виберіть елемент **Налаштувати**.
1. Вас буде переспрямовано до області **Програми** в Teams. Також можна відкрити Teams і вибрати **Програми** в нижньому лівому куті або [отримати програму безпосередньо з AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Знайдіть **Customer Insights** та виберіть програму.
1. Виберіть **Додати**.
1. Після входу до Customer Insights у Teams відобразиться привітання, і ви зможете розпочати роботу.

## <a name="things-you-can-do-with-the-bot"></a>Можливості, які забезпечує бот

Бот дозволяє здійснювати пошук об’єднаних профілів клієнтів.

- Уведіть **знайти**, а потім ім’я, адресу електронної пошти або будь-яке інше поле в об’єднаному профілі клієнта, додане до покажчика пошуку та фільтрації.

  Відобразиться картка, що містить до 15 полів із профілю клієнта, отриманого в результаті пошуку. У разі декількох збігів відображається список результатів, у якому можна вибрати профіль. Можна додати пошуковий термін у подвійних лапках, щоб знайти точний збіг.

- Якщо в організації є кілька середовищ Customer Insights з клієнтів в одній організації, можна ввести **switchinstance**, щоб вибрати середовище, до якого потрібно підключити бот.

- Уведіть **довідка**, щоб відобразився список доступних команд для бота.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]