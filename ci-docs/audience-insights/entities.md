---
title: Сутності та набори даних
description: Перегляд даних на сторінці «Сутності».
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 137de726b243b501491fcbe7866820aaee26097fcf379270c423c277374ae9a4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033840"
---
# <a name="entities-in-audience-insights"></a>Сутності в аналізі аудиторії

Після [налаштування джерел даних](data-sources.md) перейдіть на сторінку **Сутності**, щоб оцінити якість доданих даних. Сутності вважаються наборами даних. На основі цих сутностей створені численні можливості Dynamics 365 Customer Insights. Їх докладний перегляд допоможе перевірити вихідні дані цих можливостей.

На сторінці **Сутності** відображаються сутності та містяться кілька стовпців:

- **Ім’я**: ім’я сутності даних. Якщо поруч із іменем сутності відображається символ попередження, це означає, що дані для цієї сутності завантажено з помилкою.
- **Джерело**: тип джерела даних, яке додало сутність
- **Автор**: ім’я особи, яка створила сутність
- **Створено**: дата й час створення сутності
- **Автор оновлення**: ім’я особи, яка оновила сутність
- **Дата останнього оновлення**: дата й час останнього оновлення сутності
- **Останнє оновлення**: дата й час останнього оновлення даних

## <a name="explore-a-specific-entitys-data"></a>Ознайомлення з даними певної сутності

Виберіть сутність для ознайомлення з різними полями та записами, що містяться в цій сутності.

> [!div class="mx-imgBorder"]
> ![Виберіть сутність.](media/data-manager-entities-data.png "Вибір сутності")

- На вкладці **Дані** відображається таблиця із даними про окремі записи цієї сутності.

> [!div class="mx-imgBorder"]
> ![Таблиця полів.](media/data-manager-entities-fields.PNG "Таблиця полів")

- Вкладка **Атрибути** вибрана за замовчуванням і містить таблицю, де можна переглянути відомості про вибрану сутність, наприклад імена полів, типи даних і типи. У стовпці **Тип** відображаються зв’язані типи даних Common Data Model, які автоматично визначені системою або [зіставлені вручну](map-entities.md) користувачами. Це типи семантичних типів, які можуть відрізнятися від типів даних атрибутів. Наприклад поле *Електронна пошта* нижче має тип даних *Текст*, але її (семантичний) тип Common Data Model може бути *Електронна пошта* або *Адреса електронної пошти*.

> [!NOTE]
> У обох таблицях відображаються лише приклади даних сутності. Щоб переглянути повний набір даних, перейдіть на сторінку **Джерела даних**, виберіть сутність, виберіть елемент **Редагувати**, а потім перегляньте дані цієї сутності за допомогою редактора Power Query, як описано в розділі [Джерела даних](data-sources.md).

Для отримання додаткових відомостей про додані до сутності дані, стовпець **Зведення** надає кілька важливих характеристик даних (наприклад, Null-значення, відсутні значення, унікальні значення, кількість і розподіли) відповідно до ваших даних.

Виберіть піктограму діаграми, щоб переглянути зведені дані.

> [!div class="mx-imgBorder"]
> ![Символ зведення.](media/data-manager-entities-summary.png "Зведена таблиця даних")

## <a name="entity-specific-information"></a>Відомості про сутність

У наступному розділі наведено інформацію про деякі створені системою сутності.

### <a name="corrupted-data-sources"></a>Джерело даних пошкоджено

Поля з підготовленого джерела даних можуть містити пошкоджені дані. Записи з пошкодженими полями показані в створених системою сутностях. Відомості про пошкоджені записи допомагають визначити, які дані слід переглядати та оновлювати у вихідній системі. Після наступного оновлення джерело даних виправлені записи потрапляють в Customer Insights і передаються до наступних процесів. 

Наприклад, стовпець «день народження» має тип даних, установлений як «дата». Запис клієнта має свій день народження, введений як "01/01/19777". Система позначить цей запис як пошкоджений. Тепер хтось може змінити день народження у вихідній системі на «1977». Після автоматичного оновлення джерел даних поле тепер має припустимий формат, і запис буде видалено з пошкодженої сутності. 

Перейдіть до меню **Дані** > **Сутності** і перегляньте пошкоджені сутності в розділі **Система**. Схема іменування пошкоджених сутностей: «DataSourceName_EntityName_corrupt».

Customer Insights все ще обробляє пошкоджені записи. Проте вони можуть спричинити проблеми під час роботи з уніфікованими даними.

Для показу пошкоджених записів виконуються наведені нижче перевірки. 

- Значення поля не збігається з типом даних у стовпці.
- Поля містять символи, які призводь до того, що стовпці не збігаються з очікуваною схемою. Наприклад, неправильно відформатовані цінові пропозиції, нерозголошені цінові пропозиції або символи нового рядку.
- Якщо стовпці дата й час/дата/datetimeoffset мають бути вказані у форматі, якщо вони не будуть дотримуватися стандартного формату ISO.



[!INCLUDE[footer-include](../includes/footer-banner.md)]