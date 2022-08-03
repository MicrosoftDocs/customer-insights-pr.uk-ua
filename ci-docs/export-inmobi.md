---
title: Експортуйте дані Customer Insights в InMobi
description: Дізнайтеся, як налаштувати підключення та експорт в InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195913"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Експорт даних Customer Insights в InMobi (попередній перегляд)

Експортуйте списки сегментів або інші дані зі свого екземпляра Customer Insights в [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>вимоги

- Обліковий [запис](https://www.inmobi.com/) InMobi та облікові дані адміністратора.
- [Ім'я облікового запису](/azure/storage/blobs/create-data-lake-storage-account) сховища BLOB Azure і ключ облікового запису. Щоб знайти ім'я та ключ, перегляньте статтю [Керування параметрами облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).
- Контейнер [сховища](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) BLOB-об'єктів Azure для експорту даних InMobi.
- InMobi створить пряме з'єднання з вашим сховищем BLOB і налаштує автоматичний імпорт ваших даних до InMobi. Зв'яжіться зі своїм представником InMobi, щоб ініціювати процес.

## <a name="known-limitations"></a>Відомі обмеження

- Для сховища BLOB-об'єктів Azure виберіть між [стандартною продуктивністю та рівнем продуктивності Premium](/azure/storage/blobs/storage-blob-performance-tiers). Якщо вибрано рівень «Преміум-продуктивність», виберіть в якості [типу облікового запису blob-об'єкти із преміум-блоками](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Настроювання підключення до сховища BLOB-об'єктів Azure

[Налаштуйте підключення до сховища BLOB-об'єктів Azure](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Налаштування експорту

[Настроювання експорту](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
