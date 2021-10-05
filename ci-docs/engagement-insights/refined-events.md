---
title: Створення та змінення уточнених подій
description: Як створити та змінити уточнені події.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034799"
---
# <a name="create-and-modify-refined-events"></a>Створення та змінення уточнених подій

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Подія — це дані, які представляють поведінку користувача, наприклад активність на веб-сайті.

- *Базова* подія записує, коли користувач переглядає сторінку (подія перегляду) або взаємодіє з вмістом (подія дії).
- *Уточнена* подія — це віртуальне подання базової події. Ви визначаєте уточнені події, видаляючи та додаючи властивості або фільтруючи події, що базуються на значеннях властивості.

Використовуйте уточнені події для зменшення об’єму базової події для [експорту](export-events.md) або для видалення властивостей, які не є обов’язковими для відображення.

## <a name="create-refined-events"></a>Створення вдосконалених подій

Існує три способи створення уточненої події з базової події. 

1. Перейдіть до розділу **Дані**> **Події** та виберіть один із наведених нижче варіантів:
    - Виберіть **Нові події**, а потім виберіть **Створити уточнені події**.
    - Виберіть базову подію, щоб відкрити докладне подання, та виберіть **Створити уточнені події** у верхньому меню.
    - Виберіть **Додатково [...]**, щоб відкрити контекстне меню для базової події. Потім виберіть **Створити уточнені події**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Варіанти для створення уточнених подій.":::

1. У діалоговому вікні **Створити уточнені події** введіть такі відомості:

- Виберіть подію з розкривного списку **Базові події**, якщо ви створюєте нову подію.
- Введіть ім’я в полі **Коротке ім’я уточнених подій**.
- За потреби оновіть рекомендоване **Фактичне ім’я** без використання пробілів.

3. Натисніть кнопку **Створити**, щоб застосувати настройки.

1. У докладному поданні уточненої події, виберіть **Додати та видалити властивості**, щоб відкрити панель **Змінити властивості**. 

1. Використовуйте прапорці, щоб вибрати властивості, які ви хочете відобразити, та властивості, які потрібно приховати. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Редагування властивостей для уточнених подій.":::

1. Натисніть кнопку **Підтвердити**, щоб застосувати вибір.

1. Щоб зберегти конфігурацію, натисніть кнопку **Зберегти**.

## <a name="edit-refined-events"></a>Редагування уточнених подій

Ви можете змінити ім’я та властивості уточненої події.

### <a name="edit-event-name"></a>Зміна ім’я події

1. Перейдіть до розділу **Дані** > **Події**. 
1. Виберіть **Додатково [...]** для події, а потім — **Змінити ім’я**.
1. Оновіть ім’я події та виберіть **Перейменувати**.

### <a name="edit-selected-properties"></a>Редагування вибраних властивостей

1. Перейдіть до розділу **Дані** > **Події**, а потім виберіть уточнені події, щоб відкрити докладне подання.
1. Виберіть **Додати та видалити властивості**. 
1. Змініть вибір прапорців.
1. Виберіть **Підтвердити**, а потім — **Зберегти**, щоб застосувати зміни.

Щоб отримати відомості про експорт подій, див. [Експорт подій](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]