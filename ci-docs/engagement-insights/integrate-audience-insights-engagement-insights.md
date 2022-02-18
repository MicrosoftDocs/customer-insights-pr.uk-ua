---
title: Створення зв'язку між аналітичними оглядами аудиторії та аналітичними оглядами взаємодії
description: Створіть активний зв'язок між аналітичними оглядами аудиторії та аналітичними оглядами взаємодії, щоб дозволити двосторонній обмін даними.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6aadd6b5018f63362f86c0e3e3ce085e94c47391
ms.sourcegitcommit: 5dd32dc2b18027cf2aa954356dded4bc6aab9801
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/12/2022
ms.locfileid: "8116039"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Створення зв'язку між аналітичними оглядами аудиторії та аналітичними оглядами взаємодії

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Інтеграція між аналітичними оглядами взаємодії та аудиторії зв'язує середовища з обома можливостями, та дозволяє двосторонній обмін даними між ними.

Використовуйте єдині профілі та сегменти з аналітичних оглядів аудиторії для отримання додаткових параметрів аналізу в аналітичних оглядах взаємодії. Експортуйте події, з великими перевагами для компанії з аналітичних оглядів взаємодії. Використайте ці події, щоб додати дані у єдині профілі в аналітичних оглядах аудиторії.

## <a name="prerequisites"></a>Вимоги

- Профілі аналітичних оглядів аудиторії мають зберігатися в обліковому записі Azure Data Lake Storage, за який ви відповідаєте, або в data lake, керованому [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash;. 
- Ваше середовище аналізу аудиторії повинно мати пов'язане середовище Dataverse. А якщо це середовище також використовує Dataverse для зберігання даних, переконайтеся, що в аналізі аудиторії вибрано параметр **Дозволити спільний доступ до даних**. Для отримання додаткових відомостей див. [Створення та налаштування середовища в аналізі аудиторії](../audience-insights/create-environment.md).
- Вам необхідні дозволи адміністратора для середовищ аналітичних оглядів як аудиторії, так і взаємодії.
- Зв'язані середовища мають знаходитись в тому самому географічному регіоні.

> [!NOTE]
> - Якщо ваша передплата на аналіз аудиторії — це ознайомлювальна версія, в якій використовується озеро даних, що керується зсередини аналізу аудиторій, зверніться по допомогу до [pirequest@microsoft.com](mailto:pirequest@microsoft.com). 
> - Якщо в середовищі аналітичних оглядів аудиторії ви використовуєте власне Azure Data Lake Storage, необхідно додати принципала служби аналітичних оглядів взаємодії Azure до облікового запису сховища. Щоб отримати докладні відомості, перейдіть до пункту розділу [Підключення до облікового запису Azure Data Lake Storage за допомогою принципала служби Azure для аналітичних оглядів аудиторії](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Створення зв'язку з середовищем

Посилання на середовище можна створити, оновивши налаштування **Адміністратор** > **Середовище** в аналітичних оглядах взаємодії.

**Для встановлення активного зв'язку між аналітичними оглядами аудиторії та аналітичними оглядами взаємодії**

1. На сторінці **Адміністратор середовища** виберіть вкладку **Зв'язати середовища**.

    :::image type="content" source="media/integrate1.png" alt-text="Налаштування середовища.":::

1. Натисніть **Середовища інсталяції** у верхньому лівому куті або в нижній частині екрана.

     :::image type="content" source="media/integrate2.png" alt-text="Виберіть середовище аналітичних оглядів аудиторії.":::

1. Виберіть середовище аналітичних оглядів аудиторії, та натисніть **Далі**, щоб завершити. Тепер можна вибрати додаткові функції для зв'язаних середовищ.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Увімкнення атрибутів та сегментів єдиних профілів аналітичних оглядів аудиторії

Зв'язавши середовища, можна вибрати додаткові функції для зв'язаних середовищ. Ці функції дозволяють використовувати атрибути та сегменти єдиного профілю з аналітичних оглядів аудиторії для інтерактивного аналізу даних клієнтів.

> [!IMPORTANT]
> Щоб сегменти аналітичних оглядів аудиторії з'являлись в аналітичних оглядах взаємодії, слід спочатку [виконати злиття та низхідні процеси](../audience-insights/merge-entities.md). Низхідні процеси важливі, оскільки вони створюють унікальну таблицю, яка готує сегменти аналітичних оглядів аудиторії до передачі аналітичним оглядам взаємодії. (Якщо заплановано оновлення системи, воно автоматично включатиме вниз низхідні процеси.)

**Для аналізу веб-даних в аналітичних оглядах взаємодії**

1. На сторінці **Адміністратор середовища** ввімкніть перемикач **Надати спільний доступ до даних з аналітичних оглядів аудиторії аналітичним оглядам взаємодій**, а потім натисніть кнопку **Далі**.

    :::image type="content" source="media/integrate4.png" alt-text="Вибір функцій.":::

1. Виберіть атрибути єдиних профілів, які стануть вимірами в аналітичних оглядах взаємодії. (Не всі атрибути корисні в якості вимірів. Наприклад, для аналізу подій веб-сайтів вам навряд чи знадобляться такі атрибути, як **Ім'я** чи **Прізвище**.)

    :::image type="content" source="media/integrate5.png" alt-text="Добір вимірів.":::

   >[!NOTE]
   > Всі атрибути профілю аналітичних оглядів аудиторії, які представляють ідентифікатори (наприклад **Ідентифікатор** та **Альтернативний ідентифікатор**) виділяються з доступних атрибутів та стають вимірами в аналітичних оглядах взаємодії.

1. Після завершення вибору атрибутів натисніть кнопку **Далі**.
1. Додайте користувачів, які зможуть переглядати виміри та сегменти профілю аналітичних оглядів аудиторії в аналітичних оглядах взаємодії.

    :::image type="content" source="media/integrate6.png" alt-text="Керування доступом до даних клієнта.":::

   > [!IMPORTANT]
   > Якщо ви не додасте користувачів явно на цьому кроці, дані будуть приховані для користувачів в аналітичних оглядах взаємодії.
   > Щоб сегменти аналітичних оглядів аудиторії з'являлись в аналітичних оглядах взаємодії, слід спочатку [виконати злиття та низхідні процеси](../audience-insights/merge-entities.md). Низхідні процеси важливі, оскільки вони створюють унікальну таблицю, яка готує сегменти аналітичних оглядів аудиторії до передачі аналітичним оглядам взаємодії. (Якщо заплановано оновлення системи, воно автоматично включатиме вниз низхідні процеси.)

1. Перегляньте вибране, а потім натисніть кнопку **Готово**.

    :::image type="content" source="media/integrate7.png" alt-text="Перегляньте параметри даних клієнтів.":::

## <a name="export-refined-events-to-audience-insights"></a>Експорт уточнених подій до аналітичних оглядів аудиторії

Після створення зв'язку між середовищами можна експортувати уточнені події з аналітичних оглядів взаємодії до аналітичних оглядів аудиторії та додати їх в якості нового джерела даних. 

Для отримання додаткових відомостей перейдіть до сторінки [Інтеграція веб-даних з аналітичних оглядів взаємодії з аналітичними оглядами аудиторії](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
