---
title: Збагачуйте профілі клієнтів за допомогою технологій HERE (попередній перегляд)
description: Загальні відомості про стороннє збагачення HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 26de9fce863c9832b70adf3ce39cb2ae0ce43d0e
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196281"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Збагачуйте профілі клієнтів за допомогою технологій HERE (попередній перегляд)

HERE Technologies — це компанія платформи визначення місцеположення, що надає дані та послуги, орієнтовані на місцеположення. Послуги зі збагачення даних HERE Technologies покращують точність інформації про місцезнаходження ваших клієнтів. Він забезпечує нормалізацію адрес, витяг широти та довготи тощо.

## <a name="prerequisites"></a>вимоги

- Активна підписка HERE Technologies. Щоб отримати підписку, [зареєструйтеся тут](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) або [зв'яжіться безпосередньо з HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Дізнайтесь більше про збагачення даних про розташування HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Підключення [HERE](connections.md) настроюється [адміністратором](#configure-the-connection-for-here-technologies).

## <a name="configure-the-connection-for-here-technologies"></a>Налаштуйте підключення для HERE Technologies

Ви повинні бути адміністратором [Customer](permissions.md#admin) Insights і мати активний ключ API технологій HERE.

1. Виберіть елемент **Додати підключення** під час настроювання збагачення або перейдіть до **розділу Підключення** > **адміністратора** та натисніть кнопку **Настроїти** на плитці HERE Technologies.

1. Введіть ім'я з'єднання та дійсний ключ API HERE Technologies.

1. Перегляньте документ [Конфіденційність і відповідність даних](#data-privacy-and-compliance) і надайте згоду з його вмістом способом вибору пункту **Погоджуюся**.

1. Натисніть кнопку **Перевірити**, щоб перевірити конфігурацію, а потім натисніть кнопку **Зберегти**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Сторінка налаштування підключення HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

Під час увімкнення Dynamics 365 Customer Insights для передавання даних до HERE Technologies можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними. Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб HERE Technologies відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити використання цієї функції.

## <a name="configure-the-enrichment"></a>Налаштуйте збагачення

1. Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.

1. Виберіть елемент **Збагатити мої дані** на плитці **Розташування** з плитки HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Плитка HERE Technologies.":::

1. Перегляньте огляд і натисніть кнопку **Далі**.

1. Виберіть підключення. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Виберіть **Далі**.

1. Виберіть набір **даних клієнта** та виберіть профіль або сегмент, який ви хочете збагатити даними з HERE Technologies. Організація *клієнта* збагачує всі ваші профілі клієнтів, тоді як сегмент збагачує лише профілі клієнтів, що містяться в цьому сегменті.

1. Визначте, який тип полів із ваших уніфікованих профілів використовувати для зіставлення: основну та/або додаткову адресу. Ви можете зазначити зіставлення полів для обох адрес і окремо збагачувати профілі для обох адрес. Наприклад, для домашньої адреси та адреси компанії. Виберіть **Далі**.

1. Зіставте свої поля з даними з here technologies. Поля **Вулиця 1** і **Поштовий індекс** необхідні для вибраних основної та додаткової адрес. Щоб підвищити точність збігу, додайте більше полів.

1. Виберіть **Далі**, щоб завершити зіставлення полів.

1. Вкажіть ім'я **для** збагачення та ім'я **сутності виводу**.

1. Виберіть пункт **Зберегти збагачення** після того, як переглянете доступні вам варіанти вибору.

1. Натисніть кнопку **Виконати**, щоб розпочати процес збагачення, або близько, щоб повернутися на сторінку **Збагачення**.

## <a name="view-enrichment-results"></a>Переглянути результати збагачення

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Кількість **клієнтів, збагачених родовищем**, забезпечує деталізацію покриття кожного збагаченого родовища.

## <a name="next-steps"></a>Наступні кроки

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
