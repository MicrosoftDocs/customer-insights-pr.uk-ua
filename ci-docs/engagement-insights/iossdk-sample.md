---
title: Запустіть зразок SDK iOS
description: Зразок проекту, який допоможе дізнатися про SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232867"
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
