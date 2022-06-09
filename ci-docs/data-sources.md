---
title: Використання джерел даних для прийому даних
description: Дізнайтесь, як імпортувати дані з різних джерел.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 355d52eabde90e0764817cf479821264ebb2e5eb
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800491"
---
# <a name="data-sources-overview"></a>Огляд джерел даних



Dynamics 365 Customer Insights підключається до даних з широкого набору джерел. Підключення до джерела даних часто називається процесом *отримання даних*. Після того як дані буде отримано, ви можете [уніфікувати](data-unification.md) їх та виконувати із ними дії.

## <a name="add-a-data-source"></a>Додати джерело даних

Зверніться до докладних статей, щоб дізнатися, як додати джерело даних, залежно від вибраного параметра.

Можна додати такі джерела даних:

- [Через десятки Power Query роз'ємів](connect-power-query.md)
- [З папки Common Data Model](connect-common-data-model.md)
- [З власного озера Microsoft Dataverse](connect-dataverse-managed-lake.md)
- [Azure Synapse Analytics З бази даних](connect-synapse.md)

## <a name="add-data-from-on-premises-data-sources"></a>Додавайте дані з локальних джерел даних

Потрапляння даних з локальний джерел даних підтримується на Microsoft Power Platform основі потоків даних. Ви можете ввімкнути Потоки даних у службі статистики клієнтів, надавши [Microsoft Dataverse URL-адресу](create-environment.md) середовища під час налаштування середовища.

Джерела даних, створені після зв'язування середовища зі статистикою Dataverse клієнта, використовують [Power Platform потоки](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) даних за промовчанням. Потоки даних підтримують локальне підключення за допомогою шлюзу даних. Можна видалити та відтворити джерела даних, які існували до того, як Dataverse середовище було пов'язане [за допомогою локальний шлюзів](/data-integration/gateway/service-gateway-app) даних.

Шлюзи даних із наявного середовища Power BI або Power Apps будуть видимі, й ви можете повторно користуватися Customer Insights. На сторінці джерел даних відображено посилання для переходу до середовища Microsoft Power Platform, де ви можете переглянути та налаштувати локальні шлюзи даних.

> [!IMPORTANT]
> Переконайтеся, що шлюзи оновлено до останньої версії. Ви можете встановити оновлення та переналаштувати шлюз з підказки, показаної безпосередньо на екрані шлюзу, або [завантажити останню версію](https://powerapps.microsoft.com/downloads/). Якщо ви не використовуєте останню версію шлюзу, оновлення потоку даних не вдається з повідомленнями про помилки, наприклад **Ключове слово не підтримується: властивості конфігурації. Ім'я параметра: ключове слово**.

## <a name="review-ingested-data"></a>Перегляд отриманих даних
Якщо середовище містить Power Platform потоки даних, на **сторінці Джерела** даних перелічено три розділи: 
- **Спільний** доступ: джерела даних, якими можуть керувати всі адміністратори статистики клієнтів. Power BI потоки даних, власний обліковий запис сховища та приєднання до керованого Dataverse озера даних – це приклади спільних джерел даних.
- **Керований мною**: Power Platform потоки даних створені і можуть керуватися тільки вами. Інші адміністратори статистики клієнтів можуть переглядати лише ці потоки даних, але не редагувати, оновлювати або видаляти їх.
- **Керовані іншими**: Power Platform потоки даних, створені іншими адміністраторами. Ви можете тільки переглядати їх. Він перераховує власника потоку даних, щоб зв'язатися за будь-якою допомогою.
> [!NOTE]
> Всі сутності можуть переглядатися та використовуватися іншими користувачами. Контекстуальність користувача застосовується лише до джерел даних, а не до сутностей, які є результатом цих потоків даних.

Якщо не Power Platform використовуються потоки даних, групи або розділи не відображатимуться. Сторінка Джерела **даних** містить лише список усіх джерел даних.

Ви побачите ім'я кожного отриманого джерела даних, його стан та час останнього оновлення даних для цього джерела. Список джерел даних можна сортувати за кожним стовпцем.

> [!div class="mx-imgBorder"]
> ![Додане джерело даних.](media/configure-data-datasource-added.png "Додане джерело даних")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Завантаження даних може тривати значний час. Після успішного оновлення, додані дані можна переглянути на сторінці **Сутності**. Додаткові відомості див. в розділі [Сутності](entities.md).

## <a name="refresh-a-data-source"></a>Оновлення джерела даних

Джерела даних можна оновити за автоматичним розкладом або оновити вручну за запитом. 

Перейдіть до меню **Адміністратор** > **Система** > [**Розклад**](system.md#schedule-tab), щоб налаштувати заплановані оновлення всіх ваших прийнятих джерел даних.

Щоб оновити джерело даних на вимогу, виконайте такі дії.

1. Відкрийте **Дані** > **Джерела даних**.

2. Виберіть вертикальні три крапки (&vellip;) поруч із джерело даних, який потрібно оновити, і виберіть у розкривному списку пункт **Оновити**.

3. Тепер джерело даних запускається для оновлення вручну. При оновленні джерела даних виконається оновлення як схеми сутності, так і даних для всіх сутностей, зазначених у джерелі даних.

4. Виберіть **Зупинити оновлення**, якщо потрібно скасувати наявне оновлення, і джерело даних повернеться до останнього стану оновлення.

## <a name="delete-a-data-source"></a>Видалення джерела даних

1. Відкрийте **Дані** > **Джерела даних**.

2. Виберіть вертикальні три крапки () поруч&vellip; із джерело даних, який потрібно видалити, і виберіть Видалити **зі** спадного меню.

3. Підтвердьте видалення.


[!INCLUDE [footer-include](includes/footer-banner.md)]