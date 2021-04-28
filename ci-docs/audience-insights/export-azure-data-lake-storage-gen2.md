---
title: Експорт даних Customer Insights до Azure Data Lake Storage Gen2
description: Дізнайтесь, як налаштувати підключення до Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760076"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Налаштуйте підключення до Azure Data Lake Storage Gen2 (підготовча версія)

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
