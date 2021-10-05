---
title: Підключення до таблиць у Microsoft Dataverse
description: Імпорт даних із керованого озера даних Microsoft Dataverse.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033105"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Підключення до даних в озері з керованим даними Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

У цій статті наведено інформацію про те, як користувачі Dataverse можуть швидко підключатися до своїх аналітичних сутностей у керованому озері Dataverse. Для продовження та перегляду списку сутностей, доступних у керованому озері, ви повинні бути адміністратором організації Dataverse.

## <a name="important-considerations"></a>Важливі міркування

Дані, що зберігаються в онлайнових службах, наприклад, Azure Data Lake Storage, можуть зберігатися в розташуванні, відмінному від того, в якому дані обробляються або зберігаються в Dynamics 365 Customer Insights.Імпортуючи дані, що зберігаються в онлайнових службах, або встановлюючи підключення до таких даних, ви надаєте згоду, що дані можуть передаватися до Dynamics 365 Customer Insights і зберігатися в цій службі.  [Дізнайтесь більше в Центрі безпеки та конфіденційності Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Підключення до керованого озера Dataverse

1. У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.

2. Виберіть **Додати джерело даних**.

3. Натисніть **Підключитися до керованого озера Microsoft Dataverse** і виберіть **Далі**.

4. Введіть **Ім’я** джерела даних, потім виберіть **Далі**. Рекомендації щодо імен: 
   - Починайте з букви.
   - Використовуйте лише букви та цифри. Не можна використовувати спеціальні символи та пробіли.
   - Використовуйте від 3 до 64 символів.

5. Укажіть **Адресу сервера** для організації Dataverse і виберіть **Увійти в систему**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Екран на кроці обробки даних, де користувач може ввести URL-адресу середовища Dataverse.":::

6. Виберіть таблиці, які необхідно додати як сутності для аналізу аудиторії, у списку доступних.    

   > [!NOTE]
   > Якщо деякі таблиці вже вибрано, то їх можуть використовувати інші програми Dynamics 365 (наприклад, Dynamics 365 Sales Insights або Customer Service Insights). Цей вибір змінити не можна. Ці таблиці будуть доступні як сутності після створення джерела даних.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Діалогове вікно, в якому відображається список сутностей у середовищі Dataverse.":::

7. Збережіть вибір, щоб почати синхронізацію вибраних таблиць із Dataverse. На сторінці **Джерела даних** ви побачите нещодавно додане підключення. Його буде поставлено в чергу на оновлення, кількість сутності буде 0 поки не будуть синхронізовані вибрані таблиці.

Лише одне джерело даних із середовища може одночасно використовувати кероване озеро Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Редагування джерела даних керованого озера Dataverse

Після створення джерела даних ви можете редагувати тільки вибір сутностей. Наприклад, якщо до Dataverse додано додаткові сутності, і їх також потрібно імпортувати.    
Щоб підключитися до іншого озера даних Dataverse, [створіть нове джерело даних](#connect-to-a-dataverse-managed-lake).

1. У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.

2. Виберіть три крапки поряд із джерелом даних, яке ви бажаєте оновити.

3. Виберіть зі списку параметр **Редагувати**.

4. Виберіть додаткові сутності з доступного списку сутностей, а тоді виберіть **Зберегти**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]