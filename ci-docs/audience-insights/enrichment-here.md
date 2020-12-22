---
title: Збагачення за допомогою стороннього збагачення HERE Technologies
description: Загальні відомості про стороннє збагачення HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668703"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Збагачення профілів клієнтів за допомогою HERE Technologies (попередній перегляд)

HERE Technologies — це компанія платформи визначення місцеположення, що надає дані та послуги, орієнтовані на місцеположення. За допомогою служб збагачення даних HERE Technologies можна отримати точніше розуміння відомостей про місцезнаходження клієнтів, використовуючи нормалізацію адрес, отримання довготи та широти тощо.

## <a name="prerequisites"></a>Вимоги

Для настроювання збагачення HERE Technologies необхідно виконати зазначені нижче передумови.

- Ви повинні мати активну передплату на HERE Technologies. Щоб отримати передплату, можна [зареєструватися тут](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) або [зв'язатися безпосередньо з HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Дізнайтесь більше про збагачення даних про розташування HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Ви маєте ключ API від HERE Technologies.

- Ви маєте дозволи [Адміністратора](permissions.md#administrator).

## <a name="configuration"></a>Конфігурація

1. Перейдіть до розділу **Дані** > **Збагачення**.

1. Виберіть параметр **Збагачення моїх даних** у плитці HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![Плитка HERE Technologies](media/HERE-tile.png "Плитка HERE Technologies")

1. Введіть активний **Ключ API HERE Technologiesy**. Перегляньте та прийміть умови **конфіденційності й відповідності даних**, установивши прапорець **Приймаю**. 

1. Підтвердьте обидва введення, вибравши параметр **З'єднати з HERE**.

1. Виберіть **Додати дані** та вкажіть, з основною чи додатковою адресою потрібно зіставити поля. Можна задати зіставлення поля для обох адрес (наприклад, домашньої і ділової) і збагатити профілі для обох адрес окремо. Виберіть **Далі**.

1. Визначте, які поля з ваших уніфікованих профілів слід використовувати для пошуку відповідних даних щодо розташування у HERE Technologies. Поля **Вулиця 1** і **Поштовий індекс** необхідні для вибраних основної та додаткової адрес. Для підвищення точності зіставлення можна додати більше полів.

   > [!div class="mx-imgBorder"]
   > ![Сторінка налаштування збагачення HERE Technologies](media/enrichment-HERE-configuration.png "Сторінка налаштування збагачення HERE Technologies")

1. Натисніть **Застосувати**, щоб заповнити поля, що зіставляються.

## <a name="enrichment-results"></a>Результати збагачення

Щоб почати процес збагачення, натисніть **Виконати** на панелі команд. Також можна дозволити системі автоматично запустити збагачення в рамках [запланованого оновлення](system.md#schedule-tab). Час обробки буде залежати від розміру даних клієнтів і часу відгуку API з HERE Technologies.

Після завершення процесу збагачення можна переглянути нові збагачені профілі клієнтів у розділі **Мої збагачення**. Крім того, можна знайти час останнього оновлення та кількість збагачених профілів.

Можна отримати доступ до докладного подання кожного збагаченого профілю, вибравши елемент **Переглянути збагачені дані**.

## <a name="next-steps"></a>Наступні кроки

Створюйте на основі збагачених даних клієнтів. Створіть [сегменти](segments.md), [міри](measures.md) та навіть [експортуйте дані](export-destinations.md), щоб надати клієнтам персоналізовані можливості.

## <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

Під час увімкнення Dynamics 365 Customer Insights для передавання даних до HERE Technologies можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними. Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб HERE Technologies відповідала будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш адміністратор Dynamics 365 Customer Insights може видалити це збагачення в будь-який момент, щоб припинити користуватися цією функцією.
