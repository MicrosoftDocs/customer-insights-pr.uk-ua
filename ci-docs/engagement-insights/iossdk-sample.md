---
title: Запустіть зразок SDK iOS
description: Зразок проекту, який допоможе дізнатися про SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036853"
---
# <a name="run-the-ios-sdk-sample"></a>Запустіть зразок SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Цей зразок проекту iOS допоможе зрозуміти, як саме SDK працює в програмі. Вам не потрібно писати код. Просто додайте ключ обробки й відразу зможете побачити події в своїй робочій області.

## <a name="prerequisites"></a>Вимоги

- [Xcode версії 9+](https://developer.apple.com/xcode/downloads/)
- [Ключ обробки](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Завантажте зразок SDK iOS

1. [Завантажте зразок аналітичних висновків SDK iOS](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Розпакуйте стиснутий файл `ei-ios-sample.zip`.
1. Відкрийте проект прикладу програми в Xcode.
1. У файлі `EIConfig.plist` замініть рядок `“YOUR-INGESTION-KEY”` у полі `ingestionKey` ключем обробки своєї робочої області з аналітичних висновків щодо взаємодії в розділі **Адміністратор** > **Робоча область** > **Посібник з інсталяції**.
1. Щоб запустити зразок проекту, виберіть пункт **Виконати**.
1. Переглядайте події в своїй робочій області.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
