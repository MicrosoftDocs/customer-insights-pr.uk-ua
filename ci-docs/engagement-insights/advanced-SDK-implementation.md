---
title: Розширені сценарії SDK для вебу
description: Розширені сценарії, на які потрібно зважати, під час додавання інструментів на веб-сайт за допомогою SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 4c6646ecadbb604000d6c95b685cf6e420969a6d
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558727"
---
# <a name="advanced-web-sdk-instrumentation"></a>Додавання інструментів на веб-сайт за допомогою розширеного SDK для вебу

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

У цій статті описано розширені сценарії, на які потрібно зважати під час [додавання інструментів на веб-сайт](instrument-website.md) за допомогою пакета SDK для засобу аналітичних висновків щодо взаємодії в Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Налаштування відомостей про користувача для своєї події

SDK дозволяє вам визначити відомості про користувача, які можуть надсилатися з кожною подією. Ви можете вказати відомості про користувача у властивості під назвою `user` (очікуваними даними для цієї властивості є об’єкт `IUser`), подібно до `src`, `name` і `cfg` у конфігурації фрагмента коду.

Об’єкт `IUser` містить наступні властивості рядка:

- **localId**: локальний ідентифікатор користувача.
- **authId**: ідентифікатор автентифікованого користувача.
- **authType**: тип автентифікації, що використовувався для отримання ідентифікатора автентифікованого користувача.
- **name**: ім’я користувача.
- **email**: адреса електронної пошти користувача.

Наступний приклад показує фрагмент коду, що надсилає відомості про користувача. Якщо ви бачите функції, яким передує символ зірочки (*), замініть цю функцію своїм настроюваним розгортанням.

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Інформацію про користувача можна також вказати за допомогою API `setUser(user: IUser)`. Телеметрія, надіслана після виклику API `setUser` міститиме відомості про користувача.

## <a name="adding-custom-properties-for-each-event"></a>Додавання настроюваних властивостей для кожної події

SDK дозволяє вам указати настроювані властивості, які можуть надсилатися з кожною подією. Ви можете вказати настроювані властивості як об’єкт, що містить пари ключ-значення (значення може бути типу `string | number | boolean`). Об’єкт можна додати у властивість під назвою `props`, аналогічно до `src`, `name` і `cfg` у конфігурації фрагменту коду.

Наступний приклад показує фрагмент коду, що надсилає настроювані властивості:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Настроювані властивості можна також вказати окремо за допомогою API `setProperty(name: string, value: string | number | boolean)`.

## <a name="sending-custom-events"></a>Надсилання настроюваних подій

Ви можете використовувати цей пакет SDK для надсилання настроюваних подій. Ви маєте вказати ім’я для події та властивості для надсилання з цією подією.

Наступний приклад показує фрагмент коду, що відстежує настроювану подію. "NAME" — це значення в ключі `name` у конфігурації фрагменту. Це також ім’я змінної у об’єкті вікна, де завантажено SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
