---
title: Визнання веб-подій від раніше автентифікованих відвідування з невідомими до відомих
description: Функція перетворення невідомого на відоме дає змогу зв'язувати події на веб-сайті з користувачами, які проходили автентифікацію раніше.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230705"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Визнання веб-подій від раніше автентифікованих відвідувачів

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Функція перетворення **невідомого на відоме** в аналітиках взаємодії дозволяє зв'язувати події на веб-сайті з відвідувачами, які проходили автентифікацію раніше. Якщо функцію вимкнуто, відвідувачі, які проходили автентифікацію під час попереднього відвідування, після чого залишилися, не будуть виявлені, якщо вони не проходитимуть автентифікацію знову після повернення. 

Наприклад, користувач, який відвідав веб-сайт минулого тижня, увійшов до свого облікового запису на сайті та переглядав каталог продуктів. Користувач повертає наступний тиждень, щоб переглядати інші продукти, не входячи в обліковий запис. Відповідальний за сайт, що використовує функцію перетворення **невідомого на відоме**, знав, що та сама особа повернулася та що вона зробила на цьому сайті. Це дозволяє точніше звітувати та аналізувати справи на веб-сайті.

## <a name="enable-unknown-to-known"></a>Увімкнути функцію перетворення невідомого на відоме

Для ввімкнення цієї функції потрібні дозволи адміністратора [робочої області](user-roles.md). 

1. В аналітиці взаємодії перейдіть до меню **Адміністрування** > **Робоча область**. 
2. Виберіть вкладку **Параметри**.
3. У розділі **Перетворити невідоме на відоме** встановіть перемикач на значення **Увімкнуто**.

![Увімкнути функцію перетворення невідомого на відоме](media/U2Ktoggle.png "Увімкнути функцію перетворення невідомого на відоме")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Додавання коду JavaScript до фрагменту відстеження веб-сайту.

Веб-сайт може записати **user authId** з наведеним прикладом JavaScript за допомогою [аналітики взаємодії на веб-сайті SDK](advanced-SDK-implementation.md). Щоб мати змогу працювати з функцію перетворення **невідомого на відоме**, потрібно записати authId *і* ввімкнути userMapping:True у фрагменті JavaScript, як показано в прикладі нижче.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
