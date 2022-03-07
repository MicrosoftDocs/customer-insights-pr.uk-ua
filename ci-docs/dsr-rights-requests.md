---
title: Запити прав суб’єкта даних (DSR) відповідно до GDPR | Microsoft Docs
description: Відповідь на запити суб'єкта прав для можливості аналізу аудиторії в Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350294"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Запити прав суб'єкта даних (DSR) відповідно до GDPR

Генеральний регламент із захисту персональних даних Європейського Союзу набув чинності 25 травня 2018 року. Він дає особам значні права щодо їхніх даних. GDPR говорить про захист та вводить в дію право осіб на конфіденційність. Ви можете прочитати більше про зобов’язання корпорації Майкрософт щодо захисту та відповідності вимогам у [Центрі безпеки та конфіденційності Microsoft](https://www.microsoft.com/trust-center).

Ми дбаємо про те, щоб допомагати клієнтам задовольняти вимоги GDPR. Він включає право видаляти та експортувати дані, які містять особисті відомості, наприклад ідентифікатори користувачів, номери телефонів і адреси електронної пошти. Адміністратори можуть реалізувати запити користувачів на видалення або експорт особистих відомостей.

## <a name="audience-insights"></a>Аналіз аудиторії

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Відповідь на запити про видалення суб'єкта прав GDPR для можливості аналізу аудиторії в Dynamics 365 Customer Insights.

«Право на видалення» шляхом видалення персональних даних з даних клієнтів організації є ключовим в Генеральному регламенті із захисту персональних даних (GDPR). Видалення особистих даних передбачає видалення всіх особистих даних і журналів, створених системою, за винятком відомостей журналу відстеження.

#### <a name="manage-data-subject-delete-requests"></a>Керування запитами на видалення суб’єкта даних

Аналіз аудиторії пропонує такі функції в продукті для видалення персональних даних для певного клієнта або користувача.

- **Керування запитами на видалення для даних клієнтів**: дані клієнтів у Customer Insights потрапляють з вихідних джерел даних, що знаходяться за межами Customer Insights. Усі запити на видалення в межах GDPR потрібно виконувати у вихідному джерелі даних.
- **Керування запитами на видалення даних користувача Customer Insights**: дані для користувачів створюються Customer Insights. Усі запити на видалення в межах GDPR мають виконуватися в програмі Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Керування запитами на видалення даних клієнтів

Адміністратор Customer Insights може виконати зазначені нижче кроки, щоб видалити дані про клієнта, що були видалені у джерелі даних.

1. Увійти до Dynamics 365 Customer Insights.
2. У розділі «Аналіз аудиторії» виберіть **Дані** > **Джерела даних**.
3. Для кожного джерела даних у списку, що містить видалені дані про клієнта, виконайте зазначені нижче дії.
   1. Виберіть (...), а потім виберіть **Оновити**.
   2. Перевірте стан джерела даних в області **Стан**. Галочка у полі означає, що оновлення пройшло успішно. Попереджувальний трикутник означає, що сталася помилка. Якщо відображається попереджувальний трикутник, зверніться за адресою D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Обробка запитів на видалення відповідно до GDPR для даних клієнтів.](audience-insights/media/gdpr-data-sources.png "Обробка запитів на видалення відповідно до GDPR для даних клієнтів")

##### <a name="manage-delete-requests-for-user-data"></a>Керування запитами на видалення для даних користувача

Адміністратор Customer Insights може виконати ці кроки, щоб видалити дані користувача Customer Insights.

1. Увійти до Dynamics 365 Customer Insights.
2. У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Дозволи**.
3. Установіть прапорець навпроти користувача, якого потрібно видалити.
4. Натисніть **Видалити**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Відповідь на запити на експорт суб’єкта даних GDPR

У рамках виконання наших зобов’язань підтримувати партнерство з вами на шляху до Генерального регламенту із захисту персональних даних (GDPR) ми розробили документацію, яка допоможе вам підготуватися. У цій документації описано кроки, які можна вжити сьогодні для підтримки відповідності GDPR під час використання аналізу аудиторії.

#### <a name="manage-export-and-view-requests"></a>Керування запитами на експорт і перегляд

Право на перенесення даних дозволяє суб’єктам даних запитувати копію своїх особистих даних у електронному форматі (за визначенням, у «структурованому, загальновживаному та сумісному форматі, що може бути зчитаний машиною»), яка може бути передана до іншого контролера даних.

##### <a name="export-customer-data-tenant-admin"></a>Експорт даних клієнтів (адміністратор клієнта)

Щоб експортувати дані, адміністратор клієнта може має виконати такі кроки.

1. Надіслати повідомлення електронної пошти на адресу D365CI@microsoft.com, в якому вказати адресу електронної пошти клієнта в заявці. Команда Customer Insights надішле електронне повідомлення на зареєстровану адресу електронної пошти адміністратора клієнта із запитом підтвердження експорту даних.
2. Отримати підтвердження експорту даних для клієнта, щодо якого створено запит.
3. Отримати експортовані дані на адресу електронної пошти адміністратора клієнта.

##### <a name="export-user-data-tenant-admin"></a>Експорт даних користувачів (адміністратор клієнта).

1. Надіслати повідомлення електронної пошти на адресу D365CI@microsoft.com, в якому вказати адресу електронної пошти користувача в заявці. Команда Customer Insights надішле електронне повідомлення на зареєстровану адресу електронної пошти адміністратора клієнта із запитом підтвердження експорту даних.
2. Отримати підтвердження експорту даних для користувача, щодо якого створено запит.
3. Отримати експортовані дані на адресу електронної пошти адміністратора клієнта.

## <a name="consent-management-preview"></a>Керування згодою (попередній перегляд)

Можливість керування згодою не збирає дані користувача безпосередньо. Він імпортує та обробляє дані згоди, які надаються користувачами в інших програмах.

Щоб видалити дані про згоду щодо певних користувачів, видаліть їх у джерелах даних, які поширилися на можливість керування згодою. Після оновлення джерело даних видалені дані також буде видалено в Центрі згоди. Застосунки, які використовують сутність згоди, також видалятимуть дані, видалені з джерела після [оновлення](audience-insights/system.md#refresh-processes). Ми рекомендуємо швидко оновлювати джерела даних після відповіді на запит суб'єкта даних, щоб видалити дані користувача з усіх інших процесів і програм.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]