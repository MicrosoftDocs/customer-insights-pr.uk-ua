---
title: Підключення до сутностей у керованому озері Common Data Service
description: Імпорт даних із керованого озера даних Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643423"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Підключення до даних в озері з керованим даними Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

У цій статті наведено відомості про те, як існуючі клієнти Dynamics 365 можуть швидко підключитися до своїх аналітичних сутностей у керованому озері Common Data Service. Для продовження та перегляду списку сутностей, доступних у керованому озері, ви повинні бути адміністратором організації Common Data Service.

## <a name="important-considerations"></a>Важливі міркування

Дані, що зберігаються в онлайнових службах, наприклад, Azure Data Lake Storage, можуть зберігатися в розташуванні, відмінному від того, в якому дані обробляються або зберігаються в Dynamics 365 Customer Insights.Імпортуючи дані, що зберігаються в онлайнових службах, або встановлюючи підключення до таких даних, ви надаєте згоду, що дані можуть передаватися до Dynamics 365 Customer Insights і зберігатися в цій службі.  [Дізнайтесь більше в Центрі безпеки та конфіденційності Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Підключення до керованого озера Common Data Service

1. У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.

2. Виберіть **Додати джерело даних**.

3. Виберіть **Підключитися до Common Data Service**, а тоді виберіть **Далі**.

4. Введіть **Ім’я** джерела даних, потім виберіть **Далі**.

5. Укажіть **Адресу сервера** для організації Common Data Service, а потім виберіть **Увійти**.

   > [!div class="mx-imgBorder"]
   > ![Діалогове вікно для введення адреси сервера Common Data Service](media/enter-CDS-org-details.png)

6. Виберіть сутності, які потрібно прийняти з доступного списку.    

   > [!NOTE]
   > Якщо деякі сутності вже вибрано, вони, можливо, вже використовуються іншими програмами Dynamics 365 (наприклад, Dynamics 365 Sales Insights або Customer Service Insights). Цей вибір змінити не можна. Ці сутності стануть доступні після створення джерела даних.

   > [!div class="mx-imgBorder"]
   > ![Діалогове вікно з відображенням списку сутностей в організації Common Data Service](media/select-analytical-entities.png)

7. Збережіть вибір, щоб почати синхронізацію вибраних сутностей із керованим озером Common Data Service. На сторінці **Джерела даних** ви побачите нещодавно додане підключення. Воно стане у чергу на оновлення та відображатиме кількість сутностей 0, доки не буде синхронізовано всі сутності.

Лише одне джерело даних із середовища може одночасно використовувати кероване озеро Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Редагування джерела даних керованого озера Common Data Service

Після створення джерела даних ви можете редагувати тільки вибір сутностей. Наприклад, якщо до Common Data Service додано додаткові сутності, і їх також потрібно імпортувати.    
Щоб підключися до іншої служби Common Data Service, [створіть нове джерело даних](#connect-to-a-common-data-service-managed-lake).

1. У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.

2. Виберіть три крапки поряд із джерелом даних, яке ви бажаєте оновити.

3. Виберіть зі списку параметр **Редагувати**.

4. Виберіть додаткові сутності з доступного списку сутностей, а тоді виберіть **Зберегти**.
