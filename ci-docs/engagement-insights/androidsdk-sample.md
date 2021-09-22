---
title: Зразок Android SDK
description: Зразок проекту, який допоможе дізнатися про Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035851"
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
