---
title: Аналітичні огляди сегментів для наявних сегментів
description: Отримуйте аналітичні висновки щодо наявних сегментів, щоб побачити відмінності та схожість.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 977d250e5f8c52551b9f3ae9c5e805e946f2579fbe7b04f97fbac880debbac2a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035921"
---
# <a name="segment-insights-preview"></a>Аналітичні висновки для сегментів (підготовча версія)

Отримайте додаткові відомості та аналітичні висновки, що стосуються ваших наявних сегментів. З'ясуйте, що відрізняє один сегмент від іншого, і що між ними спільного.

## <a name="segment-overlap"></a>Перекриття сегментів

Аналіз перекриття сегментів показує, які клієнти належать одразу до двох або більше сегментів, а також підраховує кількість таких клієнтів. Наприклад, наскільки сегмент постійних клієнтів співпадає з сегментом, що містить клієнтів, які задоволені вашими послугами або продукцією.
Крім того, можна проаналізувати, як змінюється перекриття залежно від різних атрибутів.

### <a name="run-an-overlap-analysis"></a>Виконання аналізу перекриття

1. Відкрийте **Сегменти** та виберіть вкладку **Аналітичні висновки (підготовча версія)**.

1. Виберіть **Створити** та виберіть пункт **Перекриття** в області **Виберіть тип аналітичного висновку**.

1. Виберіть сегменти, що вас цікавлять, а тоді виберіть **Далі**.

1. Крім того, виберіть одне або кілька полів, що вас цікавлять, щоб проаналізувати перекриття для усіх можливих значень цих полів, а тоді виберіть **Далі**.

1. Укажіть ім'я для цього аналізу перекриття, необов'язкове коротке ім’я та опис.

1. Виберіть **Зберегти**, щоб розпочати аналіз. Аналіз перекриття буде готовий, коли стан зміниться з «Оновлюється» на «Успішно».

### <a name="view-and-optimize-an-overlap-analysis"></a>Перегляд і оптимізація аналізу перекриття

Після завершення аналізу знайдіть подробиці аналітичного висновку у розділі **Сегменти** > **Аналітичні висновки (підготовча версія)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Подробиці аналітичного висновку щодо перекриття сегментів.":::

Виберіть аналітичний висновок, щоб переглянути результати аналізу.

- Кількість учасників, що належать до сегментів, які брали участь в аналізі.
- Кількість учасників, включених до одного з сегментів, але відсутні в інших сегментах.
- Якщо під час налаштування аналізу перекриття було вибрано поля, ви можете знайти їх на відповідних вкладках. Ви можете скористатися розкривним списком фільтрів, щоб вибрати будь-який рівень інтересу атрибутів, при цьому в таблиці знизу відобразяться відповідні дані.

## <a name="segment-differentiators"></a>Вирізняльні властивості сегмента

Відмінності в сегментах дозволяють дізнатися, що відрізняє сегмент від інших користувачів або від іншого сегмента. Потрібно лише вибрати сегмент, а система визначить атрибути профілю та показники, які відрізняють вибраний сегмент.

### <a name="run-a-differentiator-analysis"></a>Виконання аналізу відмінностей

1. Відкрийте **Сегменти** та виберіть вкладку **Аналітичні висновки (підготовча версія)**.

1. Виберіть **Створити** та виберіть пункт **Перекриття** в області **Виберіть тип аналітичного висновку**.

1. Виберіть сегмент, який необхідно проаналізувати в якості **Первинного сегмента**, потім виберіть **Далі**.

1. Виберіть **Усі клієнти** або **Вторинний сегмент** для порівняння із первинним сегментом, й виберіть **Далі**.

1. Додатково ви можете вибрати одне або кілька полів, що вас цікавлять, щоб зосередити аналіз на певних атрибутах; після цього виберіть **Далі**.

1. Укажіть ім'я для цього аналізу перекриття, необов'язкове коротке ім’я та опис.

1. Виберіть **Зберегти**, щоб розпочати аналіз. Аналіз перекриття буде готовий, коли стан зміниться з «Оновлюється» на «Успішно».

### <a name="view-and-optimize-a-differentiators-analysis"></a>Перегляд і оптимізація аналізу відмінностей

Після завершення аналізу знайдіть подробиці аналітичного висновку у розділі **Сегменти** > **Аналітичні висновки (підготовча версія)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Подробиці аналітичного висновку щодо відмінностей сегментів.":::

Виберіть аналітичний висновок, щоб переглянути результати аналізу. Аналіз відмінностей містить дві вкладки. На вкладці **Атрибути** перелічено атрибути профілю, що їх визначено як відмінності. На вкладці **Показники** перелічено відмінності. Кожна вкладка містить зазначені нижче відомості.

- Ранговий список відмінностей, відсортованих за оцінкою відмінності.
- **Оцінка відмінності** для кожної відмінності. Оцінка відмінності представляє ступінь відмінності для атрибута у двох сегментах. Чим вища оцінка відмінності, тим сильніше атрибути відрізняються у двох сегментах. Виберіть оцінку, щоб відкрити область **Оцінка відмінності**, де наведено розподіл значень для певного атрибуту.

## <a name="manage-segment-insights"></a>Керування аналітичними висновками щодо сегментів

За допомогою панелі команд можна виконувати наведені нижче дії стосовно аналітичних висновків.

- **Назад**, щоб повернутися до списку аналітичних висновків
- **Оновити**, щоб знову виконати аналіз
- **Видалити**, щоб видалити цей аналітичний висновок


[!INCLUDE[footer-include](../includes/footer-banner.md)]