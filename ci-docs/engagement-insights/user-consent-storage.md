---
title: Керування файлами cookie та згодою користувачів на збереження даних користувачів у Dynamics 365 Customer Insights
description: Проаналізуйте, як файли cookie та вміст користувача використовується для ідентифікації відвідувачів веб-сайту.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229010"
---
# <a name="manage-cookies-and-user-consent"></a>Керування файлами cookie та згодою користувача

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Функція Аналітика взаємодії Dynamics 365 Customer Insights використовує файли cookie та ключі (`localStorage`) для визначення відвідувачів веб-сайтів.

Файли cookie — це маленькі файли, які зберігають біти інформації про взаємодії користувача з веб-сайтом. Вони зберігаються у веб-браузерах. Коли користувачі відвідують веб-сайт, для якого ваші користувачі зберегли файли cookie, браузер надсилає цю інформацію на сервер, який повертає інформацію, яка є унікальною для цих користувачів. Це технологія, яка дозволяє, наприклад, кошику інтернет-магазина зберігати вибрані товари, навіть якщо користувач переходить на інший веб-сайт.

## <a name="user-consent"></a>Згода користувача

[Генеральний регламент із захисту персональних даних (GDPR)](/dynamics365/get-started/gdpr/) – це регламент ЄС, який визначає, як організації мають працювати з конфіденційністю та безпекою користувачів. Файли cookie часто зберігають або збирають персональні дані, наприклад онлайн-ідентифікатор, який регулюється GDPR. Якщо ваша компанія наймає та/або продає суб’єктам даних в ЄС, на вас розповсюджується дія GDPR. [Докладніше про те, як корпорація Майкрософт може допомогти вам відповідати вимогам GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Щоб дозволити SDK для аналітичних висновків щодо взаємодії зберігати файли cookie або іншу конфіденційну інформацію, ви маєте вказати, чи надали ваші користувачі згоду. Це відбувається під час ініціалізації пакета SDK за допомогою установки поля `userConsent` у конфігурації.

Якщо ви зазначаєте, що немає згоди користувача, SDK не буде зберігати дані та не буде надсилати події, які можуть бути використані для відстеження поведінки користувача. Усі раніше збережені дані буде видалено з браузера.

Якщо не вказано значення згоди користувача, SDK вважатиме, що користувач надав згоду. Це означає, що, якщо ви (як наш клієнт), не вкажете значення для згоди користувача в SDK, дані будуть збиратися. Якщо ви вкажете, що значення для згоди користувача потребує значення "true", дані не будуть збиратися, якщо користувач відмовиться надати або не надасть явну згоду.

Нижче наведено список фрагмент коду для ініціалізації SDK для веб-платформи зі згодою користувачів.
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Зберігання даних відвідувача в засобі аналітичних висновків щодо взаємодії

### <a name="cookies"></a>Cookies

- _msei
    - Зберігає ідентифікатор анонімного користувача. Цей файл cookie установлено в домені клієнта, термін його дії спливає через 365 днів.

### <a name="local-storage"></a>Локальне сховище

Функція Аналітика взаємодії також дає змогу використовувати ключі (`localStorage`) для відстеження неконфіденційних даних. Ці дані повністю зберігаються в самому браузері, жодний трафік не надсилається на ваші сервери або з них.

- *EISession.Id*
    - Зберігає відомості про поточний сеанс користувача, наприклад ідентифікатор сеансу, час його початку та час завершення терміну дії.
- *EISession.Previous*
    - Зберігає URL-адресу раніше відвіданої сторінки в поточному сеансі.

Термін дії ключів у локальному сховищі не завершується автоматично, і їх буде скинуто під час наступного сеансу SDK.

## <a name="deleting-cookies"></a>Видалення файлів cookie

Ваші клієнти можуть вручну видаляти файли cookie та ключі локального сховища в будь-який час у настройках браузера.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
