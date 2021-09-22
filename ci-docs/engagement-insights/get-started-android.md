---
title: Почати роботу з SDK Android
description: Дізнайтеся про те, як персоналізувати й запустити SDK Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036943"
---
# <a name="get-started-with-the-android-sdk"></a>Почати роботу з SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

У цьому посібнику наводяться відомості про процес додавання інструментів до програми Android за допомогою SDK для аналітичних висновків щодо взаємодії в Dynamics 365 Customer Insights. Через п’ять хвилин або навіть швидше ви почнете бачити події на своєму порталі.

## <a name="configuration-options"></a>Параметри конфігурації
До SDK можна перенести наведену далі конфігурацію.

- **ingestionKey**: ключ обробки використовується для надсилання подій до своєї робочої області.

## <a name="prerequisites"></a>Вимоги

- Android Studio

- Мінімальний рівень API Android API: 16 (Jelly Bean)

- Ключ обробки (див. нижче інструкцію щодо того, як його отримати)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Крок 1. Інтегруйте SDK до своєї програми
Процес слід почати так: виберіть робочу область, виберіть мобільну платформу Android, потім завантажте SDK Android.

- Скористайтеся перемикачем робочої області, розташованим у області ліворуч, щоб вибрати потрібну робочу область.

- Якщо у вас немає наявної робочої області, виберіть пункт **Створити робочу область**, потім дотримуйтеся відповідних кроків, для створення [нової робочої області](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Крок 2. Налаштуйте SDK

1. Після створення робочої області перейдіть до розділу **Адміністратор** > **Робоча область**, потім виберіть **Посібник з інсталяції**. 

1. Завантажте [SDK аналітичних висновків щодо взаємодії Android](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip), потім помістіть файл `eiandroidsdk-debug.aar` у папку `libs`.

1. Відкрийте файл рівня проекту `build.gradle` й додайте наведені далі фрагменти.
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Задайте конфігурацію SDK аналітичних висновків щодо взаємодії за допомогою файлу `AndroidManifest.xml`, розташованого в папці `manifests`. 
1. Скопіюйте фрагмент XML із **Посібника з інсталяції**. `Your-Ingestion-Key` заповнюються автоматично.

   > [!NOTE]
   > Замінювати розділ `${applicationId}` необхідності немає. Він заповнюються автоматично.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Ви можете увімкнути або вимкнути автоматичне записування подій `View` способом налаштування для поля `autoCapture` значення `true` або `false`.

1. (Необов'язково) Інші конфігурації включають настроювання URL-адреси з’єднувача кінцевої точки. Їх можна додати в метадані ключа обробки в `AndroidManifest.xml`.
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Крок 3. Ініціалізуйте SDK з MainActivity 

Після ініціалізації SDK ви можете працювати з подіями та їхніми властивостями в середовищі MainActivity.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Задайте властивість для всіх подій (необов’язково)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

У контексті властивостей подій підтримуються наведені далі типи.
- String
- датою
- Подвійні
- Довге значення
- Boolean
- UUID

### <a name="track-an-event"></a>Відстежте подію

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Налаштуйте відомості користувача для своєї події (необов’язково)

SDK дозволяє вам визначити відомості про користувача, які можуть надсилатися з кожною подією. Ви можете задати інформацію користувача способом виклику API `setUser(user: User)` на рівні `Analytics` level.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Клас даних `User` містить наведені далі властивості рядка.

- **localId**: локальний ідентифікатор користувача.
- **authId**: ідентифікатор автентифікованого користувача.
- **authType**: тип автентифікації, який використовується для отримання автентифікованого ідентифікатора користувача.
- **name**: ім’я користувача.
- **email**: адреса електронної пошти користувача.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
