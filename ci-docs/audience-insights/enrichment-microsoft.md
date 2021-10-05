---
title: Збагачуйте профілі клієнтів за рахунок даних Майкрософт
description: Використовуйте фірмові дані Майкрософт для збагачення даних клієнтів за рахунок їхнього доповнення брендами та уподобаннями в області інтересів.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 45c81a037258e42d8975e0372c104865a9d4cbfe
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466649"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Збагачення профілів клієнтів близькими брендами й інтересами (попередній перегляд)

Використовуйте фірмові дані Майкрософт для збагачення даних клієнтів за рахунок їхнього доповнення брендами та уподобаннями в області інтересів. Ці властивості ґрунтуються на даних осіб, чиї демографічні дані є подібними до даних ваших клієнтів. Ця інформація допомагає вам краще зрозуміти й сегментувати своїх клієнтів на основі їхньої близькості до конкретних брендів та інтересів.

У аналізі аудиторії виберіть **Дані** > **Збагачення**, щоб [налаштувати та переглянути збагачення](enrichment-hub.md).

Щоб налаштувати збагачення на основі прихильності до брендів, перейдіть на вкладку **Виявлення** і виберіть **Збагатити мої дані** на плитці **Бренди**.

Щоб налаштувати збагачення на основі близьких інтересів, перейдіть на вкладку **Виявлення** і виберіть **Збагатити мої дані** на плитці **Інтереси**.

   > [!div class="mx-imgBorder"]
   > ![Плитки брендів та інтересів.](media/BrandsInterest-tile-Hub.png "Плитки брендів та інтересів")

## <a name="how-we-determine-affinities"></a>Як ми визначаємо уподобання

Ми користуємося даними онлайнового пошуку Майкрософт, щоб знайти уподобання щодо брендів та інтересів у різних демографічних сегментах (що визначаються віком, статтю або розташуванням). Обсяг онлайн-пошуку бренду або інтересу визначає, наскільки близький демографічний сегмент, порівняно з іншими сегментами, до певного бренду або інтересу.

## <a name="affinity-level-and-score"></a>Рівень та оцінка відповідності

У кожному збагаченому профілі клієнта вказано два пов'язані значення: рівень відповідності та оцінка відповідності. Ці значення допомагають визначити ступінь відповідності для демографічного сегмента профілю для бренда або інтересу порівняно із іншими демографічними сегментами.

*Рівень відповідності* оцінюється чотирма рівнями, а *оцінка відповідності* розраховується за 100-бальною шкалою, що зіставляється із рівнями відповідності.


|Рівень відповідності |Оцінка відповідності  |
|---------|---------|
|Дуже багато     | 85—100       |
|Високе     | 70—84        |
|Середній     | 35—69        |
|Низьке     | 1—34        |

Залежно від потрібного вам рівня деталізації при вимірюванні відповідності ви можете використовувати рівень або оцінку відповідності. Оцінка відповідності забезпечує вищу точність при роботі.

## <a name="supported-countriesregions"></a>Країни або регіони, що підтримуються

Станом на сьогодні, ми підтримуємо такі варіанти країн або регіонів: Австралія, Канада (англійська), Франція, Німеччина, Сполучене Королівство або Сполучені Штати Америки (англійська).

Щоб вибрати країну або регіон, відкрийте розділ **Збагачення брендів** або **Збагачення інтересів**, потім виберіть пункт **Змінити** поряд із розділом **Країна/регіон**. У області **Налаштування країни або регіону** виберіть доступний варіант та виберіть **Застосувати**.

### <a name="implications-related-to-country-selection"></a>Наслідки, пов’язані із вибором країни/регіону

- При [виборі власних брендів](#define-your-brands-or-interests) система надаватиме пропозиції залежно від вибраної країни або регіону.

- [Вибираючи галузь](#define-your-brands-or-interests), ви побачите найбільш відповідні бренди та інтереси для вибраної країни або регіону.

- При [збагаченні профілів](#refresh-enrichment) ми збагачуємо всі профілі клієнтів, для яких ми отримуємо дані щодо вибраних брендів та інтересів, включно з профілями, що не перебувають у вибраній країні чи регіоні. Наприклад, якщо ви вибрали Німеччину, ми виконаємо збагачення профілів, розташованих у Сполучених Штатах, якщо матимемо доступні дані для вибраних брендів та інтересів у США.

## <a name="configure-enrichment"></a>Налаштуйте збагачення

Екскурсія під керівництвом екскурсовода допоможе пройти етапи налаштування збагачень. 

### <a name="define-your-brands-or-interests"></a>Визначте свої бренди або інтереси

Виберіть до п'яти брендів або інтересів, використовуючи один або обидва з перелічених нижче варіантів.

- **Галузь**: виберіть свою галузь із розкривного списку, потім виберіть перші за значенням бренди або інтереси для цієї галузі.
- **Виберіть власний**: введіть бренд або інтерес, важливий для вашої організації, а потім оберіть пропозицію з-поміж тих, що відповідають умові. Якщо в списку немає потрібного бренду або інтересу, надішліть нам відгук за допомогою посилання **Запропонувати**.

### <a name="review-enrichment-preferences"></a>Перегляд параметрів збагачення

Перегляньте параметри збагачень за замовчуванням і за потреби оновіть їх.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Знімок екрана із вікном параметрів збагачень.":::

### <a name="select-entity-to-enrich"></a>Виберіть сутність для збагачення

Виберіть **Збагачену сутність**, потім виберіть набір даних, який ви бажаєте збагатити за рахунок корпоративних даних Майкрософт. Можна вибрати сутність «Клієнт», щоб збагатити всі профілі клієнтів, або вибрати сутність сегмента для збагачення лише профілів клієнтів, що містяться в цьому сегменті.

### <a name="map-your-fields"></a>Зіставлення полів

Зіставте поля з уніфікованої сутності клієнта, щоб визначити демографічний сегмент, який система має використовувати для збагачення даних клієнтів. Зіставте країну або регіон і, принаймні, атрибути дати народження або статі. Крім того, слід зіставити принаймні місто (і область/республіку) або поштовий індекс. Виберіть елемент **Редагувати**, щоб зіставити поля. Коли завершите, натисніть копку **Застосувати**. Натисніть кнопку **Зберегти**, щоб завершити зіставлення полів.

Підтримуються зазначені нижче значення та формати (регістр букв не має значення).

- **Дата народження**: рекомендуємо під час приймання даних перетворити дату народження у тип Дата й час. Альтернативно це може бути рядок у форматі [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) «рррр-ММ-дд» чи «рррр-ММ-ддГГ:хв:сс».
- **Стать**: чоловік, жінка, невідомо.
- **Поштовий індекс**: п’ятизначний поштовий індекс для Сполучених Штатів, стандартний поштовий індекс у будь-яких інших розташуваннях.
- **Місто**: назва міста англійською мовою.
- **Область/Республіка**: скорочення із двох літер для США та Канади. Скорочення з двох або трьох літер для Австралії. Не застосовується для Франції, Німеччини та Сполученого Королівства.
- **Країна або регіон**:

  - US: Сполучені Штати Америки, Сполучені Штати, США, US, Америка
  - CA: Канада, CA
  - GB: Сполучене Королівство, UK, Велика Британія, GB, Сполучене Королівство Великої Британії та Північної Ірландії, Сполучене Королівство Великої Британії
  - AU: Австралія, AU, Співдружність Австралії
  - FR: Франція, FR, Французька Республіка
  - DE: Німеччина, German, Deutschland, Allemagne, DE, Федеративна Республіка Німеччина, Республіка Німеччина

## <a name="review-and-name-the-enrichment"></a>Перегляньте це збагачення та надайте йому ім’я

Нарешті ви маєте переглянути інформацію та вказати ім'я для збагачення.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Сторінка перегляду й іменування інтересів.":::

## <a name="refresh-enrichment"></a>Оновлення збагачень

Виконайте збагачення після настроювання брендів, інтересів і зіставлення полів для демографічних показників. Щоб почати процес, виберіть **Виконати** на сторінці налаштування брендів та інтересів. Додатково ви можете дозволити системі автоматично проводити збагачення в межах запланованого оновлення.

Завершення процесу збагачення може тривати кілька хвилин, залежно від розміру даних клієнта.

> [!TIP]
> Існує [шість типів станів](system.md#status-types) для завдань/процесів. Крім того, більшість процесів [залежать від інших низхідних процесів](system.md#refresh-policies). Можна вибрати стан процесу, щоб переглянути докладні відомості про перебіг виконання всієї роботи. Після вибору пункту **Див. докладні відомості** для одного із робочих завдань ви побачите наведені далі докладні відомості: час обробки, дата останньої обробки, помилки та попередження, пов’язані із завданням.

## <a name="enrichment-results"></a>Результати збагачення

Після запуску процесу збагачення перейдіть на сторінку **Мої збагачення**, щоб переглянути загальну кількість збагачених клієнтів і структуру брендів або інтересів у збагачених профілях клієнтів.

:::image type="content" source="media/my-enrichments.png" alt-text="Зразок результатів для попереднього перегляду після збагачення.":::

Перегляньте збагачені дані, вибравши **Переглянути збагачені дані** на діаграмі. Збагачені дані для брендів містяться в сутності **BrandAffinityFromMicrosoft**. Дані для інтересів – у сутності **InterestAffinityFromMicrosoft**. Ви також знайдете ці сутності в списку групи **Збагачення**, розташованої тут: **Дані** > **Сутності**.

Ви побачите діаграму із кількістю збагачених профілів клієнтів із плином часу та попередній перегляд збагаченої сутності. Виберіть **Показати більше** в плитці попереднього перегляду, щоб відкрити збагачену сутність.

## <a name="see-enrichment-data-on-the-customer-card"></a>Перегляд даних збагачення на картці клієнта

Інформацію про близькість до брендів та інтересів також можна переглядати на окремих картках клієнтів. Перейдіть до розділу **Клієнти** та виберіть профіль клієнта. У картці клієнта ви знайдете діаграми брендів або інтересів, які є близькими клієнтові згідно до його демографічного профілю.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Картка клієнта зі збагаченими даними.":::

## <a name="next-steps"></a>Наступні кроки

Створюйте на основі збагачених даних клієнтів. Створюйте [Сегменти](segments.md) й [Міри](measures.md), а також [експортуйте дані](export-destinations.md) задля забезпечення індивідуальної взаємодії для своїх клієнтів.


[!INCLUDE[footer-include](../includes/footer-banner.md)]