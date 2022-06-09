---
title: Експортуйте дані Customer Insights до ActiveCampaign
description: Дізнайтеся про те, як налаштувати підключення та експортувати дані до ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d15b9bf7383d06070ac92d7a729fc6e6e00c9d7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644067"
---
# <a name="export-segments-to-activecampaign-preview"></a>Експортуйте сегменти до ActiveCampaign (підготовча версія)

Експортуйте сегменти єдиних профілів клієнтів до ActiveCampaign і використовуйте їх для маркетингової діяльності.

## <a name="prerequisites"></a>Вимоги

-   У вас є [обліковий запис ActiveCampaign](https://www.activecampaign.com/) і відповідні облікові дані адміністратора.
-   Ви налаштували [сегменти](segments.md) в Службі статистики клієнтів.
-   Уніфіковані профілі клієнтів в експортованих сегментах містять поле з адресою електронної пошти.

## <a name="known-limitations"></a>Відомі обмеження

- Ви можете експортувати до 1 мільйона профілів клієнтів в межах одного експорту до ActiveCampaign, і цей процес може тривати до 90 хвилин.
- Експорт до ActiveCampaign обмежується сегментами.
- Кількість профілів клієнтів, які можна експортувати в ActiveCampaign, визначається умовами сервісного договору з ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Налаштуйте підключення до ActiveCampaign

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть розділ **Додати підключення**, потім виберіть **ActiveCampaign**, щоб налаштувати підключення.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть [ключ API ActiveCampaign API та ім’я хоста кінцевої точки REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Ім'я хоста кінцевої точки REST — це лише ім’я хоста, без https://. 

1. Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.

1. Виберіть **Підключити** для ініціалізації підключення до ActiveCampaign.

1. Виберіть **Додати себе як користувача експорту** та надайте облікові дані Customer Insights.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

Ви можете налаштувати експорт, якщо у вас є доступ до підключень такого типу. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати призначення**.

1. У полі **Підключення для експорту** виберіть підключення з розділу ActiveCampaign. Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. Введіть [**ідентифікатор списку ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. У розділі **Зіставлення даних** у полі **Електронна пошта** виберіть поле, яке відповідає адресі електронної пошти клієнта. Він вимагається для того, щоб експортувати сегменти до ActiveCampaign. Це не обов’язково, але ви також можете експортувати ім’я, прізвище та телефон, щоб додатково персоналізувати повідомлення електронної пошти. Виберіть Додати атрибут, щоб зіставити ці поля.

1. Виберіть **Зберегти**.

При збереженні експорт не запуститься негайно.

Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab). Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

При увімкненні Dynamics 365 Customer Insights для передавання даних до ActiveCampaign ви також надаєте дозвіл на передавання даних поза межі нормативно-правової відповідності для Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, такими як особисті дані. Майкрософт виконає передавання таких даних за вашою вказівкою, але ви несете відповідальність за забезпечення того, щоб ActiveCampaign відповідала зобов’язанням щодо конфіденційності або безпеки, які можуть у вас бути. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити це призначення експорту, щоб припинити користуватися цією функцією.