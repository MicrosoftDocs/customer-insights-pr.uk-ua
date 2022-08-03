---
title: Експорт даних до сховища BLOB-об'єктів Azure (попередній перегляд)
description: Дізнайтеся, як налаштувати підключення та експорт до сховища BLOB-об'єктів Azure.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195729"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Експорт даних до сховища BLOB-об'єктів Azure (попередній перегляд)

Зберігайте дані Customer Insights у сховищі BLOB-об’єктів Azure або використовуйте його для передавання даних до інших програм.

## <a name="prerequisites"></a>вимоги

- [Ім'я облікового запису](/azure/storage/blobs/create-data-lake-storage-account) сховища BLOB Azure і ключ облікового запису. Щоб знайти ім'я та ключ, перегляньте статтю [Керування параметрами облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).
- Контейнер [для зберігання блоґа-ляпів Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Відомі обмеження

- Для сховища BLOB-об'єктів Azure виберіть між [стандартною продуктивністю та рівнем продуктивності Premium](/azure/storage/blobs/storage-blob-performance-tiers). Якщо вибрано рівень «Преміум-продуктивність», виберіть в якості [типу облікового запису blob-об'єкти із преміум-блоками](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Настроювання підключення до сховища BLOB

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть Додати **підключення** та виберіть Azure **BLOB Storage**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть **Ім’я бізнес-партнера**, **Ключ бізнес-партнера** та **Контейнер** для облікового запису сховища BLOB-об'єктів Azure.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

Щоб налаштувати цей експорт, необхідно мати [дозвіл на](export-destinations.md#set-up-a-new-export) цей тип підключення.

> [!IMPORTANT]
> Якщо ввімкнути параметр [м'якого](/azure/storage/blobs/soft-delete-blob-enable) видалення для облікового запису сховища BLOB-об'єктів Azure, експортувати буде не вдалось. Щоб експортувати дані в BLOB-об'єктів, вимкніть видалення.

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть Додати **експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу «Сховище BLOB-об’єктів Azure». Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім'я експорту.

1. Введіть ім'я папки для сховища BLOB- об'єктів.

1. Установіть прапорець поруч із кожною із сутностей, які ви хочете експортувати до цього призначення.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Експортовані дані зберігаються в контейнері сховища BLOB-об'єктів, який ви налаштували. У контейнері автоматично створюються наведені далі шляхи папок.

- Для сутностей джерел і сутностей, згенерованих у системі:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Приклад: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Експорт об'єктів, які містять велику кількість даних, може призвести до появи декількох файлів CSV в одній папці для кожного експорту. Розділення експорту відбувається з міркувань продуктивності, щоб мінімізувати час, необхідний для завершення експорту.

- Model.json для експортованих об'єктів знаходиться на *%ExportDestinationName%* рівні.  
  
  Приклад: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
