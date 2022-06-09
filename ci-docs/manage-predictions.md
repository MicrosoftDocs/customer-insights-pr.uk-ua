---
title: Спільні завдання для сценаріїв прогнозування
description: Дізнайтеся, як керувати прогнозами, уточнювати їх та виправляти неполадки.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c4d269e1b542e84ade8c6e63c1dadace51ddde32
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644159"
---
# <a name="manage-predictions"></a>Керування прогнозами

У цій статті розглядаються деякі завдання, спільні для більшості сценаріїв прогнозування.

## <a name="troubleshoot-a-failed-prediction"></a>Усунення проблем з помилкою прогнозів

1. Перейдіть до розділу **Аналітика** > **Прогнози** і виберіть вкладку **Мої прогнози**.

1. Виберіть вертикальні три крапки поруч із прогнозом, для яких потрібно переглянути журнал помилок.

1. Натисніть **Журнали**.

1. Перегляньте усі помилки. Може виникати кілька типів помилок, і у них описуються умови, що призвели до помилки. Наприклад, помилка, яка сповіщає, що недостатньо даних для точного прогнозування зазвичай вирішується, якщо завантажити додаткові дані до Customer Insights.

## <a name="input-data-usability-report"></a>Звіт про зручність використання вхідних даних

У звіті про зручність використання вхідних даних надається узагальнене подання помилок і попереджень, які можуть виникати при роботі готових прогнозів. Він також дає рекомендації щодо поліпшення продуктивності моделі.

Звіт стає доступним після того, як модель завершить процес навчання. Він створюється окремо для кожної моделі, незалежно від того, чи була робота моделі успішною, чи ні.

### <a name="view-the-input-data-usability-report"></a>Перегляд звіту про зручність використання вхідних даних

Після завершення кроку навчання готової моделі перегляньте звіт:
- Виберіть три крапки поруч із назвою моделі та виберіть **Звіт про зручність використання вхідних даних**.
- Виберіть стан моделі, виберіть **Відобразити звіт про зручність використання вхідних даних** на бічній панелі.
- Виберіть одну з моделей у списку, а тоді виберіть **Звіт про зручність використання вхідних даних** на панелі команд.
- Відкрийте сторінку із результатами моделі, а тоді виберіть **Звіт про зручність використання вхідних даних** на панелі команд.

### <a name="information-in-the-input-data-usability-report"></a>Відомості, що містяться у звіті про зручність використання даних

Зазначені нижче стовпці у звіті містять відомості, що є корисними для покращення даних для моделі.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Приклад звіту про зручність використання вхідних даних, де показано таблицю із помилками, попередженнями та рекомендаціями.":::

- **Ім'я:** описове ім'я помилки, попередження або рекомендація.
- **Крок:** Етап моделі, поїзд або оцінка, інформація посилається на.
- **Стан:** Тяжкість інформації (помилка, попередження, рекомендація).
- **Ім'я стовпця:** Стовпець у сутності, яку потрібно змінити для підвищення продуктивності моделі.
- **Ім'я сутності:** ім'я сутності, яку потрібно змінити для підвищення продуктивності моделі.
- **Деталі:** Відомості про помилку, попередження або рекомендацію.

## <a name="refresh-a-prediction"></a>Оновлення прогнозу

Прогнози автоматично оновлюватимуться за тим самим [розкладом, за яким оновлюються дані](system.md#schedule-tab), що налаштовується в параметрах. Їх можна також оновити вручну.

1. Перейдіть до розділу **Аналітика** > **Прогнози** і виберіть вкладку **Мої прогнози**.

1. Виберіть вертикальні три крапки поруч із прогнозом, який потрібно оновити.

1. Виберіть **Оновити**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Видалення прогнозу

Видалення прогнозу також видаляє його вихідну сутність.

1. Перейдіть до розділу **Аналітика** > **Прогнози** і виберіть вкладку **Мої прогнози**.

1. Виберіть вертикальні три крапки поруч із прогнозом, який потрібно видалити.

1. Виберіть **Видалити**.