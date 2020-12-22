---
title: Експорт даних Customer Insights до сховища BLOB-об'єктів Azure
description: Дізнайтесь, як налаштувати підключення до сховища BLOB-об'єктів Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667164"
---
# <a name="connector-for-azure-blob-storage-preview"></a>З'єднувач для сховища BLOB-об'єктів Azure (попередній перегляд)

Зберігайте дані Customer Insights у сховищі BLOB-об’єктів Azure або використовуйте його для передавання даних в інші програми.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Налаштування з'єднувача для сховища BLOB-об'єктів Azure

1. У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.

1. У розділі **Сховище BLOB-об'єктів Azure** виберіть **Налаштувати**.

1. Введіть **Ім'я облікового запису**, **Ключ облікового запису** та **Контейнер** свого облікового запису сховища BLOB-об'єктів Azure.
    - Докладніше про те, як знайти обліковий запис сховища BLOB-об’єктів Azure і ключ облікового запису, див. у розділі [Керування настройками облікового запису сховища на порталі Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Щоб дізнатися, як створити контейнер, див. розділ [Створення контейнера ](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Дайте своєму призначенню ім’я, яке легко впізнати, в полі **Коротке ім’я**.

1. Виберіть **Далі**.

1. Установіть прапорець поруч із кожною із сутностей, які ви хочете експортувати до цього призначення.

1. Виберіть **Зберегти**.

Експортовані дані зберігаються в налаштованому контейнері сховища BLOB-об'єктів Azure. У контейнері автоматично створюються наведені далі шляхи папок.

- Для сутностей джерел і сутностей, згенерованих у системі: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Приклад: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Файл model.json для експортованих сутностей буде розміщено на рівні %ExportDestinationName%
  - Приклад: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Експорт даних

Ви можете [експортувати дані вручну](/export-destinations.md#export-data-on-demand). Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).
