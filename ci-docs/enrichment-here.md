---
title: Збагачення профілів клієнтів за допомогою ТЕХНОЛОГІЙ HERE (попередній перегляд)
description: Загальні відомості про стороннє збагачення HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052076"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Збагачення профілів клієнтів за допомогою ТЕХНОЛОГІЙ HERE (попередній перегляд)

HERE Technologies — це компанія платформи визначення місцеположення, що надає дані та послуги, орієнтовані на місцеположення. Сервіси зі збагачення даних HERE Technologies покращують точність інформації про місцезнаходження ваших клієнтів. Він забезпечує адресну нормалізацію, вилучення широти і довготи тощо.

## <a name="prerequisites"></a>вимоги

- Активна підписка here Technologies. Щоб отримати підписку, [зареєструйтеся тут](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) або [зв'яжіться безпосередньо з HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Дізнайтесь більше про збагачення даних про розташування HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Підключення [HERE](connections.md) настроєно [адміністратором](#configure-the-connection-for-here-technologies).

## <a name="configure-the-connection-for-here-technologies"></a>Налаштуйте підключення для HERE Technologies

Ви повинні бути адміністратором [Customer](permissions.md#admin) Insights і мати активний ключ HERE Technologies API.

1. Виберіть елемент **Додати підключення** під час настроювання збагачення або перейдіть до **розділу Підключення** > **адміністратора** та виберіть Настроїти **на** плитці HERE Technologies.

1. Введіть ім'я для з'єднання та дійсний ключ API HERE Technologies.

1. Перегляньте документ [Конфіденційність і відповідність даних](#data-privacy-and-compliance) і надайте згоду з його вмістом способом вибору пункту **Погоджуюся**.

1. Натисніть кнопку **Перевірити**, щоб перевірити конфігурацію, а потім натисніть кнопку **Зберегти**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Сторінка налаштування підключення HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

Під час увімкнення Dynamics 365 Customer Insights для передавання даних до HERE Technologies можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними. Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб HERE Technologies відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити використання цієї функції.

## <a name="configure-the-enrichment"></a>Налаштуйте збагачення

1. Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.

1. Виберіть "**Збагатити мої дані** про розташування **"** з плитки "Технології HERE".

   :::image type="content" source="media/HERE-tile.png" alt-text="Плитка HERE Technologies.":::

1. Перегляньте огляд і натисніть кнопку **Далі**.

1. Виберіть підключення. Зверніться до адміністратора, якщо він недоступний.

1. Виберіть **Далі**.

1. **Виберіть набір** даних клієнта та виберіть профіль або сегмент, який ви хочете збагатити даними з HERE Technologies. Компанія *Клієнта* збагачує всі ваші профілі клієнтів, тоді як сегмент збагачує лише профілі клієнтів, що містяться в цьому сегменті.

1. Визначте, який тип полів з ваших уніфікованих профілів використовувати для зіставлення: основну та/або вторинну адресу. Ви можете зазначити зіставлення полів для обох адрес і окремо збагачувати профілі для обох адрес. Наприклад, для домашньої адреси та адреси компанії. Виберіть **Далі**.

1. Зіставте свої поля з даними з HERE Technologies. Поля **Вулиця 1** і **Поштовий індекс** необхідні для вибраних основної та додаткової адрес. Для підвищення точності збігу додайте більше полів.

1. Виберіть **Далі**, щоб завершити зіставлення полів.

1. **Надайте назву** для збагачення та назву **організації виводу**.

1. Виберіть пункт **Зберегти збагачення** після того, як переглянете доступні вам варіанти вибору.

1. Натисніть кнопку **Виконати**, щоб розпочати процес збагачення, або закрити, щоб повернутися на сторінку **Збагачення**.

## <a name="view-enrichment-results"></a>Переглянути результати збагачення

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Кількість **клієнтів, збагачених родовищами**, забезпечує деталізацію покриття кожного збагаченого родовища.

## <a name="next-steps"></a>Наступні кроки

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
