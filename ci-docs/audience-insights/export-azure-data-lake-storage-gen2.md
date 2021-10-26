---
title: Експорт даних Customer Insights до Azure Data Lake Storage Gen2
description: Дізнайтесь, як налаштувати підключення до Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 934c396559d4c4be8e640917d2265805753eb62d
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605928"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Експортування списку сегментів та інших даних до Azure Data Lake Storage Gen2 (підготовча версія)

Зберігайте дані Customer Insights в обліковому записі сховища Azure Data Lake Storage Gen2 або використовуйте його для передавання даних в інші програми.

## <a name="known-limitations"></a>Відомі обмеження

1. Для Azure Data Lake Storage Gen2 під час створення облікового запису сховища для зберігання даних можна обрати між [рівнями ефективності «Стандартна продуктивність» і «Преміум-продуктивність»](/azure/storage/blobs/create-data-lake-storage-account). Якщо вибрано рівень «Преміум-продуктивність», виберіть в якості типу облікового запису blob-об'єкти із преміум-блоками. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Налаштування підключення до Azure Data Lake Storage Gen2 


1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення**, потім виберіть **Azure Data Lake Gen 2**, щоб налаштувати підключення.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть **Ім’я облікового запису**, **Ключ облікового запису** і **Контейнер** для Azure Data Lake Storage Gen2.
    - Щоб дізнатися, як створити обліковий запис сховища для використання з Azure Data Lake Storage Gen2, див. [Створення облікового запису сховища](/azure/storage/blobs/create-data-lake-storage-account). 
    - Щоб отримати докладніші відомості про те, як знайти ім’я облікового запису сховища Azure Data Lake Gen2, див. розділ [Керуйте налаштуваннями облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).

1. Щоб завершити створення підключення, виберіть **Зберегти**. 

## <a name="configure-an-export"></a>Налаштування експорту

Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу **Azure Data Lake**. Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. Установіть прапорець поруч із кожною із сутностей, які ви хочете експортувати до цього призначення.

1. Виберіть **Зберегти**.

При збереженні експорт не запуститься негайно.

Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab). Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand). 

Експортовані дані зберігаються в контейнері сховища Azure Data Lake Gen 2, який ви налаштували. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
