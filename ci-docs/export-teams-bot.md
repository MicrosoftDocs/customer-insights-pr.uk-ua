---
title: Бот команди для Dynamics 365 Customer Insights (попередній перегляд)
description: Пошук уніфікованих профілів клієнтів за допомогою Microsoft Teams з допомогою бота.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195867"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Бот команди для Dynamics 365 Customer Insights (попередній перегляд)

Підключайтеся до Microsoft Teams, щоб дозволити боту шукати уніфіковані профілі клієнтів у каналах команди.

:::image type="content" source="media/teams-bot.png" alt-text="Бот для Teams, що показує запис клієнта":::

## <a name="prerequisites"></a>вимоги

- Додано принаймні один [джерело даних](data-sources.md).
- Завершено [процес уніфікації](data-unification.md).
- Поля додаються до індексу [пошуку та фільтрування](search-filter-index.md).
- Customer Insights і Teams відносяться до однієї організації.
- У вашому середовищі основну цільову аудиторію задано як індивідуальні клієнти. Ділові бізнес-партнери не підтримуються.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Настроювання бота

1. Відкрийте **Адміністрування** > **Підключення**.
1. На плитці Microsoft Teams виберіть елемент **Налаштувати**.
1. Вас буде переспрямовано до області **Програми** в Teams. Також можна відкрити Teams і вибрати **Програми** в нижньому лівому куті або [отримати програму безпосередньо з AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Знайдіть **Customer Insights** та виберіть програму.
1. Виберіть **Додати**.
1. увійдіть в Customer Insights в Teams. Відобразиться привітальне повідомлення.

## <a name="things-you-can-do-with-the-bot"></a>Можливості, які забезпечує бот

Бот дозволяє здійснювати пошук об’єднаних профілів клієнтів.

- Введіть **пошук**, а потім ім'я, адресу електронної пошти або будь-яке інше поле в уніфікованому профілі клієнта, яке додається до індексу пошуку та фільтрування.

  Відобразиться картка, що містить до 15 полів із профілю клієнта, отриманого в результаті пошуку. У разі декількох збігів відображається список результатів, у якому можна вибрати профіль. Щоб знайти точну відповідність, додайте пошуковий термін у подвійних лапках.

- Якщо у вашій організації підтримується кілька середовищ Customer Insights в одній організації, введіть **switchinstance**, щоб вибрати, до якого середовища ви хочете підключити бота.

- Уведіть **довідка**, щоб відобразився список доступних команд для бота.  

[!INCLUDE [footer-include](includes/footer-banner.md)]