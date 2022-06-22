---
title: Збагачення за допомогою стороннього постачальника послуг збагачення HERE Technologies
description: Загальні відомості про стороннє збагачення HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 171ead92427924083a13e2a3d52e7a7da417c801
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953698"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Збагачення профілів клієнтів за допомогою HERE Technologies (попередній перегляд)

HERE Technologies — це компанія платформи визначення місцеположення, що надає дані та послуги, орієнтовані на місцеположення. Послуги зі збагачення даних HERE Technologies покращують точність інформації про місцезнаходження ваших клієнтів. Він забезпечує нормалізацію адреси, видобуток широти та довготи тощо.

## <a name="prerequisites"></a>вимоги

- Активна підписка HERE Technologies. Щоб отримати підписку, [зареєструйтеся тут](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) або [зв'яжіться безпосередньо з HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Дізнайтесь більше про збагачення даних про розташування HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Підключення [HERE](connections.md) налаштовано [адміністратором](#configure-the-connection-for-here-technologies).

## <a name="configure-the-connection-for-here-technologies"></a>Налаштуйте підключення для HERE Technologies

Ви повинні бути адміністратором [в](permissions.md#admin) Customer Insights і мати активний ключ API HERE Technologies.

1. Виберіть додати **підключення** під час настроювання збагачення або перейдіть до розділу **Підключення** > **адміністратора** та виберіть **налаштувати** на плитці HERE Technologies.

1. Введіть ім'я підключення та дійсний ключ API HERE Technologies.

1. Перегляньте документ [Конфіденційність і відповідність даних](#data-privacy-and-compliance) і надайте згоду з його вмістом способом вибору пункту **Погоджуюся**.

1. Натисніть кнопку **Перевірити**, щоб перевірити конфігурацію, а потім натисніть кнопку **Зберегти**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Сторінка налаштування підключення HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

Під час увімкнення Dynamics 365 Customer Insights для передавання даних до HERE Technologies можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними. Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб HERE Technologies відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити використання цієї функції.

## <a name="configure-the-enrichment"></a>Налаштуйте збагачення

1. Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.

1. Виберіть Збагатити **мої дані** на **місцезнаходження** з плитки HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Плитка HERE Technologies.":::

1. Перегляньте огляд і натисніть кнопку **Далі**.

1. Виберіть підключення. Зверніться до адміністратора, якщо він недоступний.

1. Виберіть **Далі**.

1. **Виберіть набір** даних Клієнта та виберіть профіль або сегмент, який ви хочете збагатити даними з HERE Technologies. Організація *Клієнта* збагачує всі ваші профілі клієнтів, тоді як сегмент збагачує лише профілі клієнтів, що містяться в цьому сегменті.

1. Визначте, який тип полів з об'єднаних профілів використовувати для зіставлення: основна та/або додаткова адреса. Ви можете зазначити зіставлення полів для обох адрес і окремо збагачувати профілі для обох адрес. Наприклад, для домашньої адреси та адреси компанії. Виберіть **Далі**.

1. Зіставте свої поля з даними з HERE Technologies. Поля **Вулиця 1** і **Поштовий індекс** необхідні для вибраних основної та додаткової адрес. Для більш високої точності відповідності додайте більше полів.

1. Виберіть **Далі**, щоб завершити зіставлення полів.

1. Укажіть ім'я **для** збагачення та ім'я **вихідної** сутності.

1. Виберіть пункт **Зберегти збагачення** після того, як переглянете доступні вам варіанти вибору.

1. Натисніть кнопку **Виконати,** щоб розпочати процес збагачення, або близько, щоб повернутися до **сторінки "Збагачення** ".

## <a name="enrichment-results"></a>Результати збагачення

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Кількість **клієнтів, збагачених полем**, забезпечує деталізацію в покритті кожного збагаченого поля.

## <a name="next-steps"></a>Наступні кроки

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
