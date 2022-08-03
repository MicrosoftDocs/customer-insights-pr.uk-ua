---
title: Експорт сегментів в Facebook Ads Manager (попередній перегляд) (містить відео)
description: Дізнайтеся, як налаштувати підключення та експорт до Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195039"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Експорт сегментів в Facebook Ads Manager (попередній перегляд)

Експортуйте сегменти уніфікованих профілів клієнтів до Менеджера реклами Facebook, щоб створити кампанії у Facebook та Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>вимоги

- Рекламний [Facebook обліковий запис](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), який містить корпоративний [Facebook обліковий запис](https://business.facebook.com/).
- Права адміністратора в обліковому записі [Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Відомі обмеження

- До 10 мільйонів профілів клієнтів на експорт в Facebook Ads Manager, що може зайняти до 90 хвилин.
- Тільки сегменти.
- Facebook *список* клієнтів введіть лише в [користувацьких аудиторіях](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > У деяких випадках у розкривному списку можуть відображатися настроювані аудиторії різних типів. Якщо вибрати інший тип, відмінний від *списку* клієнтів, експорт не вдасться.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Налаштування підключення до Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати з'єднання** та виберіть **Facebook Менеджер** оголошень.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. [Дозволити співавторам використовувати з'єднання для експорту](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Пройдіть автентифікацію на Facebook Ads:

   1. Виберіть пункт **Продовжити в Facebook**, щоб виконати вхід до облікового запису рекламодавця Facebook.

   1. Надайте дозвіл **ads_management** після автентифікація за допомогою Facebook.

   1. Виберіть **Рекламний обліковий запис Facebook**, в якому потрібно працювати.

   1. Із розкривного списку виберіть **Наявну спеціальну аудиторію** або створіть **Нову спеціальну аудиторію**.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть Додати **експорт**.

1. **У полі Підключення для експорту** виберіть підключення в Facebook розділі Менеджер оголошень. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім'я експорту.

1. **У полі Підключити дані** виберіть **пункт Електронна пошта**, **Ім'я та адреса** або **Телефон**, який потрібно надіслати в Facebook Менеджер оголошень.

1. Зіставте відповідні атрибути з об’єднаної сутності клієнта для вибраного ідентифікатора ключа.
   > [!TIP]
   > Кращі шанси на відповідність будуть тоді, коли вибрати **Електронну пошту** як основний ідентифікатор. Зіставлення може покращитися, якщо додавати додаткові ідентифікатори.

1. Виберіть **Додати атрибут**, щоб зіставити інші атрибути, що надсилатимуться до Facebook Ads Manager. Атрибути з Facebook Ads Manager зіставляються з такими зрозумілими іменами: **FN** = **Ім'я**, **LN** = **Прізвище**, **FI** = **Ініціали**, **PHONE** = **Телефон**, **GEN** = **Стать**, **DOB** = **Дата народження**, **ST** = **Область**, **CT** = **Місто**, **ZIP** = **Поштовий код/індекс**, **КРАЇНА** = **Країна/регіон**

1. Виберіть сегменти, які потрібно експортувати.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
