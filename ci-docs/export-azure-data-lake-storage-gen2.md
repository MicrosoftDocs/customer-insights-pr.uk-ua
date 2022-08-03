---
title: Експорт даних у Azure Data Lake Storage Gen2 (попередній перегляд)
description: Дізнайтесь, як налаштувати підключення до Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196465"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Експорт даних у Azure Data Lake Storage Gen2 (попередній перегляд)

Зберігайте дані Customer Insights в обліковому записі сховища Azure Data Lake Storage Gen2 або використовуйте його для передавання даних в інші програми.

## <a name="prerequisites"></a>вимоги

- Обліковий [запис сховища для використання з Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Щоб знайти ім'я та ключ облікового запису сховища, перегляньте статтю [Керування параметрами облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).
- Контейнер [для зберігання блоґа-ляпів Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Відомі обмеження

- Для Azure Data Lake Storage Gen2 вибирайте між [стандартною продуктивністю та рівнем продуктивності](/azure/storage/blobs/create-data-lake-storage-account) Premium. Якщо вибрано рівень «Преміум-продуктивність», виберіть в якості [типу облікового запису blob-об'єкти із преміум-блоками](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Налаштування підключення до Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати з'єднання** та виберіть **Azure Data Lake Gen 2**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть **Ім’я облікового запису**, **Ключ облікового запису** і **Контейнер** для Azure Data Lake Storage Gen2.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть Додати **експорт**.

1. **У полі Підключення для експорту** виберіть підключення в розділі Azure Data Lake. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім'я експорту.

1. Введіть ім'я папки Azure Data Lake Storage для сховища Gen2.

1. Установіть прапорець поруч із кожною із сутностей, які ви хочете експортувати до цього призначення.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Експортовані дані зберігаються в контейнері сховища Azure Data Lake Gen 2, який ви налаштували.

> [!TIP]
> Експорт об'єктів, які містять велику кількість даних, може призвести до появи декількох файлів CSV в одній папці для кожного експорту. Розділення експорту відбувається з міркувань продуктивності, щоб мінімізувати час, необхідний для завершення експорту.

[!INCLUDE [footer-include](includes/footer-banner.md)]
