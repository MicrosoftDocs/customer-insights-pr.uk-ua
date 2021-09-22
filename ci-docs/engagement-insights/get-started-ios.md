---
title: Початок роботи з SDK iOS
description: Дізнайтеся про те, як персоналізувати й запустити SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036898"
---
# <a name="get-started-with-the-ios-sdk"></a>Почати роботу з SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

У цьому посібнику наводяться відомості про процес додавання інструментів до програми iOS за допомогою SDK для аналітичних висновків щодо взаємодії в Dynamics 365 Customer Insights. Через п’ять хвилин або навіть швидше ви почнете бачити події на своєму порталі.

## <a name="configuration-options"></a>Параметри конфігурації

За допомогою файлу `EIConfig.plist`, який надається, до SDK можна перенести наведені далі параметри конфігурації.

- **ingestionKey**: цей ключ обробки використовується для надсилання подій до вашого проекту.
- **autocollectAction**: це логічне значення, яке дозволяє увімкнути або вимкнути автоматичне оснащення інструментами події справи.
- **autocollectView**: це логічне значення, яке дозволяє увімкнути або вимкнути автоматичне оснащення інструментами події перегляду.
- **endpointUrl**: це URL-адреса, до якої спрямовуватимуться події.

## <a name="prerequisites"></a>Вимоги

- Xcode версії 9+
- iOS версії 8.2+
- Ключ обробки (див. нижче інструкцію щодо того, як його отримати)

## <a name="integrate-the-sdk-into-your-application"></a>Інтегруйте SDK до своєї програми

Процес слід почати так: виберіть робочу область, у якій працюватимете, виберіть мобільну платформу iOS, потім завантажте SDK.

- Скористайтеся перемикачем робочої області, розташованим у області ліворуч, щоб вибрати потрібну робочу область.

- Якщо у вас немає наявної робочої області, виберіть пункт **Створити робочу область**, потім дотримуйтеся відповідних кроків, для створення [нової робочої області](create-workspace.md).

## <a name="configure-the-sdk"></a>Налаштуйте SDK

Після завантаження пакета SDK можна працювати з ним у Xcode, щоб вмикати та визначати події.

1. Після створення робочої області перейдіть до розділу **Адміністратор** > **Робоча область**, потім виберіть **Посібник з інсталяції**.

1. Завантажте [SDK аналітичних висновків щодо взаємодії iOS](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip), потім помістіть файл `EIObjC.xcframework` у папку `Frameworks`.

1. Якщо папки `Frameworks` немає, створіть її в папці проекту.

## <a name="enable-auto-instrumentation"></a>Увімкніть автоматичне оснащення інструментами
 
Ви можете легко увімкнути автоматичне оснащення інструментами без необхідності писати код. Після запуску проекту він буде автоматично відстежувати події `view` і `action` із використанням налаштованого ключа обробки. 

1. Оновіть і додайте включений файл `EIConfig.plist` до своєї папки каталогу проекту для наведених далі полів.
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = ТАК
    - autocollectAction = ТАК

2. Потім додайте до свого проекту файл `EIConfig.plist` у Xcode. 



Щоб вимкнути автоматичне оснащення інструментами, оновіть наведені далі поля у включеному файлі `EIConfig.plist` у папці каталогу проекту. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Виконайте імплементацію настроюваних подій

1. Відкрийте свій проект у Xcode, потім перейдіть до **Загальних** настройок. 
1. У розділі «Платформи, бібліотеки та вбудований вміст» додайте `EIObjC.xcframework` до проекту.

1. Імпортуйте файл заголовка платформи в AppDelegate.m із таким фрагментом:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Ініціалізуйте SDK для аналітичних висновків щодо взаємодії з програми: didFinishLaunchingWithOptions.
1. Скопіюйте фрагмент XML із **Посібника з інсталяції**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Відстежуйте подію.

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Налаштуйте відомості користувача для своєї події

SDK дозволяє вам визначити відомості про користувача, які можуть надсилатися з кожною подією. Ви можете задати інформацію користувача способом виклику API `setUser:(nonnull EIUser *)user` в SDK.

Якщо зазначити відомості користувача на рівні `Analytics`, це означає, що ця інформація буде в усій телеметрії. Однак якщо ви зазначите ці відомості на рівні події способом виклику API `setUser:(nonnull EIUser *)user` у об’єкті EIEvent, ці відомості будуть міститися лише в цій конкретній події.

Клас даних `EIUser` містить наведені далі властивості NSString.

- **localId**: локальний ідентифікатор користувача.
- **authId**: ідентифікатор автентифікованого користувача.
- **authType**: тип автентифікації, що використовувався для отримання ідентифікатора автентифікованого користувача.
- **name**: ім’я користувача.
- **email**: адреса електронної пошти користувача.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
