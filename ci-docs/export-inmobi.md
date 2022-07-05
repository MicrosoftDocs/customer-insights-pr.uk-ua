---
title: Експортуйте дані Customer Insights в InMobi
description: Дізнайтеся, як налаштувати з'єднання та експортувати в InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059621"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Експорт списку сегментів та інших даних в InMobi (попередній перегляд)

Експортуйте списки сегментів або інші дані зі свого екземпляра Customer Insights в [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>вимоги

1. У вас є обліковий [запис](https://www.inmobi.com/) InMobi та облікові дані адміністратора.
1. У вас є ім'я облікового запису сховища BLOB Azure і відповідний ключ облікового запису. Щоб отримати додаткові відомості, перегляньте статтю [Керування настройками облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage). В обліковому записі сховища є контейнер для експорту даних inMobi. Щоб отримати додаткові відомості, перегляньте статтю [Створення контейнера](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi створить пряме з'єднання з вашим Blob Storage і налаштує автоматичний імпорт ваших даних в InMobi. Зв'яжіться зі своїм представником InMobi, щоб ініціювати процес.

## <a name="known-limitations"></a>Відомі обмеження

1. Для сховища BLOB Azure ви можете вибрати між [стандартною продуктивністю та рівнем продуктивності преміум-класу](/azure/storage/blobs/storage-blob-performance-tiers). Якщо вибрано рівень «Преміум-продуктивність», виберіть в якості [типу облікового запису blob-об'єкти із преміум-блоками](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Налаштування підключення до сховища ляпів Azure і настройте експорт

1. Дотримуйтеся вказівок, щоб [настроїти підключення до сховища ляпів](export-azure-blob-storage.md) Azure.
2. Дотримуйтеся вказівок, щоб [настроїти експорт](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
