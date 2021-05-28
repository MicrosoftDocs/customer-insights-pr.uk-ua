---
title: Експорт даних Customer Insights до сховища BLOB-об'єктів Azure
description: Дізнайтеся, як налаштувати підключення та експорт до сховища BLOB-об'єктів Azure.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976206"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Експортуйте список сегментів та інші дані до сховища BLOB-об'єктів Azure (підготовча версія)

Зберігайте дані Customer Insights у сховищі BLOB-об’єктів Azure або використовуйте його для передавання даних до інших програм.

## <a name="set-up-the-connection-to-blob-storage"></a>Налаштуйте підключення до сховища BLOB-об'єктів Azure

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення**, потім виберіть **Сховище BLOB-об'єктів Azure**, щоб налаштувати підключення.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть **Ім’я бізнес-партнера**, **Ключ бізнес-партнера** та **Контейнер** для облікового запису сховища BLOB-об'єктів Azure.
    - Щоб отримати докладніші відомості про те, як знайти ім’я облікового запису сховища BLOB-об’єктів, див. розділ [Керуйте налаштуваннями облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).
    - Щоб дізнатися, як створити контейнер, див. розділ [Створення контейнера ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Щоб завершити створення підключення, виберіть **Зберегти**. 

## <a name="configure-an-export"></a>Налаштування експорту

Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати призначення**.

1. У полі **Підключення для експорту** виберіть підключення з розділу «Сховище BLOB-об’єктів Azure». Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. Установіть прапорець поруч із кожною із сутностей, які ви хочете експортувати до цього призначення.

1. Виберіть **Зберегти**.

При збереженні експорт не запуститься негайно.

Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab).     
Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand). 

Експортовані дані зберігаються в контейнері сховища BLOB-об'єктів, який ви налаштували. У контейнері автоматично створюються наведені далі шляхи папок.

- Для сутностей джерел і сутностей, згенерованих у системі: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Приклад: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Файл model.json для експортованих сутностей буде на рівні %ExportDestinationName%
  - Приклад: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
