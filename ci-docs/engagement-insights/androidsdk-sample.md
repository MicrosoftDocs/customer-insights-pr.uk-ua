---
title: Зразок Android SDK
description: Зразок проекту, який допоможе дізнатися про Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229943"
---
# <a name="run-the-android-sdk-sample"></a>Запустіть зразок Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Цей зразок проекту Android допоможе зрозуміти, як саме SDK працює в програмі. Вам не потрібно писати код. Просто додайте ключ обробки й відразу зможете побачити події в своїй робочій області.

## <a name="prerequisites"></a>Вимоги

- [Android Studio](https://developer.android.com/studio)
- [Ключ обробки](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Завантажте зразок Android SDK

1. [Завантажте зразок аналітичних висновків Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Розпакуйте стиснутий файл `ei-android-sample.zip`.
1. Відкрийте не запаковану папку в Android Studio.
1. У файлі `AndroidManifest.xml` замініть рядок `"Your-Ingestion-Key"` ключем обробки своєї робочої області з аналітичних оглядів у розділі **Адміністратор** > **Робоча область** > **Керівництво з інсталяції**. 

   > [!NOTE]
   > Замінювати розділ `${applicationId}` необхідності немає. Він заповнюються автоматично.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Щоб запустити зразок проекту, виберіть пункт **Виконати**.
1. Переглядайте події в своїй робочій області.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
