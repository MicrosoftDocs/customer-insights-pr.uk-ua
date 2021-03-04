---
title: Експорт даних Customer Insights до Azure Data Lake Storage Gen2
description: Дізнайтесь, як налаштувати підключення до Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477204"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>З'єднувач для Azure Data Lake Storage Gen2 (підготовча версія)

Зберігайте дані Customer Insights у Azure Data Lake Storage Gen2 або використовуйте його для передавання даних в інші програми.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Налаштування з’єднувача Azure Data Lake Storage Gen2

1. У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.

1. У розділі **Azure Data Lake Storage Gen2** виберіть **Налаштувати**.

1. Дайте своєму призначенню ім’я, яке легко впізнати, в полі **Коротке ім’я**.

1. Введіть **Ім’я облікового запису**, **Ключ облікового запису** і **Контейнер** для Azure Data Lake Storage Gen2.
    - Щоб дізнатися, як створити обліковий запис сховища для використання з Azure Data Lake Storage Gen2, див. [Створення облікового запису сховища](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Докладніше про те, як знайти ім'я облікового запису й ключ облікового запису сховища Azure Data Lake Gen2, див. тут: [Керування параметрами облікового запису сховища на порталі Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Виберіть **Далі**.

1. Установіть прапорець поруч із кожною із сутностей, які ви хочете експортувати до цього призначення.

1. Виберіть **Зберегти**.

## <a name="export-the-data"></a>Експорт даних

Ви можете [експортувати дані вручну](export-destinations.md#export-data-on-demand). Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).
