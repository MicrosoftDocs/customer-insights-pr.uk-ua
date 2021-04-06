---
title: Експорт даних Customer Insights до сховища BLOB-об'єктів Azure
description: Дізнайтесь, як налаштувати підключення до сховища BLOB-об'єктів Azure.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596202"
---
# <a name="connector-for-azure-blob-storage-preview"></a>З'єднувач для сховища BLOB-об'єктів Azure (попередній перегляд)

Зберігайте дані Customer Insights у сховищі BLOB-об’єктів Azure або використовуйте його для передавання даних в інші програми.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Налаштування з'єднувача для сховища BLOB-об'єктів Azure

1. У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.

1. У розділі **Сховище BLOB-об'єктів Azure** виберіть **Налаштувати**.

1. Введіть **Ім'я облікового запису**, **Ключ облікового запису** та **Контейнер** свого облікового запису сховища BLOB-об'єктів Azure.
    - Докладніше про те, як знайти обліковий запис сховища BLOB-об’єктів Azure і ключ облікового запису, див. у розділі [Керування настройками облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).
    - Щоб дізнатися, як створити контейнер, див. розділ [Створення контейнера ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Дайте своєму призначенню ім’я, яке легко впізнати, в полі **Коротке ім’я**.

1. Виберіть **Далі**.

1. Установіть прапорець поруч із кожною із сутностей, які ви хочете експортувати до цього призначення.

1. Виберіть **Зберегти**.

Експортовані дані зберігаються в налаштованому контейнері сховища BLOB-об'єктів Azure. У контейнері автоматично створюються наведені далі шляхи папок.

- Для сутностей джерел і сутностей, згенерованих у системі: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Приклад: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- model.json для експортованих сутностей розташовується на рівні %ExportDestinationName%
  - Приклад: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Експорт даних

Ви можете [експортувати дані вручну](export-destinations.md#export-data-on-demand). Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]