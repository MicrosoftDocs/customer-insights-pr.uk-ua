---
title: Експорт даних Customer Insights до Adobe Campaign Standard
description: Дізнайтеся, як використовувати сегменти статистики клієнтів у Adobe стандарті кампанії.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644075"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Використання сегментів Customer Insights у Adobe Campaign Standard (підготовча версія)

Як користувач Dynamics 365 Customer Insights, ви, можливо, створили сегменти, щоб зробити свої маркетингові кампанії більш ефективними, націлюючись на відповідні аудиторії. Щоб використовувати сегмент зі статистики Adobe Experience Platform клієнтів і таких програм, як Adobe Стандарт кампанії, потрібно виконати кілька кроків, описаних у цій статті.

:::image type="content" source="media/ACS-flow.png" alt-text="Схема процесів кроків, описаних у цій статті.":::

## <a name="prerequisites"></a>Вимоги

-   Ліцензія Dynamics 365 Customer Insights
-   Ліцензія Adobe Campaign Standard
-   Обліковий запис сховища Azure Blob

## <a name="campaign-overview"></a>Огляд кампанії

Щоб краще зрозуміти, як ви можете використовувати сегменти з Customer Insights в Adobe Experience Platform, давайте подивимося на фіктивний зразок кампанії.

Припустімо, що ваша компанія пропонує клієнтам щомісячну передплату на послуги в Сполучених Штатах Америки. Вам потрібно визначити клієнтів, передплати яких мають бути продовжені впродовж наступних 8 днів, але які ще не продовжили їх. Щоб зберегти цих клієнтів, варто надіслати їм акційну пропозицію електронною поштою за допомогою Adobe Campaign Standard.

У цьому прикладі ми хочемо запустити рекламну кампанію електронною поштою один раз. У цій статті не розглядається варіант використання багатократного запуску кампанії. Однак статистику клієнтів і Adobe стандарт кампанії можна настроїти на роботу для повторюваного сценарію кампанії.

## <a name="identify-your-target-audience"></a>Визначте цільову аудиторію

У нашому сценарії ми припускаємо, що адреси електронної пошти клієнтів доступні, а їх рекламні уподобання були проаналізовані для ідентифікації членів сегмента.

Сегмент [, який ви визначили в Customer Insights](segments.md), називається **ChurnProneCustomers**, і ви плануєте надіслати цим клієнтам рекламну кампанію електронною поштою.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Знімок екрана: сторінка сегментів зі створеним сегментом ChurnProneCustomers.":::

Повідомлення електронної пошти, яке необхідно надіслати, міститиме ім'я, прізвище та дату завершення передплати клієнта. Він інформує клієнтів про знижку, яку вони отримають, якщо продовжать передплату до закінчення терміну її дії.

## <a name="export-your-target-audience"></a>Експортуйте цільову аудиторію

### <a name="configure-a-connection"></a>Налаштуйте підключення

Визначивши нашу цільову аудиторію, ми можемо налаштувати експорт на обліковий запис Azure Blob Storage.

1. У розділі Статистика клієнтів перейдіть до розділу **AdminConnections** > **·**.

1. Натисніть **Додати підключення** та виберіть **Adobe Campaign**, щоб налаштувати підключення, або натисніть **Налаштувати** на плитці **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Плитка налаштування для Adobe Campaign Standard.":::

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Введіть **Ім’я бізнес-партнера**, **Ключ бізнес-партнера** і **Контейнер** у сховищі BLOB-об’єктів Azure, до якого ви бажаєте експортувати сегмент.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Знімок екрана із конфігураціями облікового запису сховища."::: 

   - Докладніше про те, як знайти обліковий запис сховища BLOB-об’єктів Azure і ключ облікового запису, див. у розділі [Керування настройками облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).

   - Щоб дізнатися, як створити контейнер, див. розділ [Створення контейнера ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Щоб завершити створення підключення, виберіть **Зберегти**.

### <a name="configure-an-export"></a>Налаштування експорту

Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати експорт**.

1. У полі **Підключення для експорту**, виберіть підключення з розділу Adobe Campaign. Якщо ви не бачите імені цього розділу, це означає, що для вас не доступні будь-які підключення цього типу.

1. Виберіть сегмент, який потрібно експортувати. У цьому прикладі це **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Знімок екрана: інтерфейс користувача вибору сегмента з вибраним сегментом ChurnProneCustomers.":::

1. Виберіть **Далі**.

1. Тепер ми зіставляємо **поля Джерело** з сегмента Статистика клієнтів з іменами полів "Цільові **"** в схемі Adobe профілю "Стандартна кампанія".

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Зіставлення полів для з'єднувача Adobe Campaign Standard.":::

   Щоб додати більше атрибутів, виберіть **Додати атрибут**. Цільове ім'я може відрізнятися від імені вихідного поля, щоб ви все ще могли зіставляти вивід сегмента від Customer Insights до Adobe Стандарту кампанії, якщо поля не мають однакового імені в двох системах.

   > [!NOTE]
   > Адреса електронної пошти використовується як поле посвідчення, але ви можете використовувати будь-який інший ідентифікатор з профілю клієнта для зіставлення даних зі Adobe Стандартом кампанії.

1. Виберіть **Зберегти**.

Після того, як ви зберегли пункт призначення експорту, ви зможете знайти його в розділі **Дані** > **Експорт**.

Тепер сегмент [можна експортувати неавтоматично](export-destinations.md#run-exports-on-demand). Експорт також запускатиметься під час кожного [запланованого оновлення](system.md).

> [!NOTE]
> Переконайтеся, що кількість записів у експортованому сегменті не перевищує граничне значення ліцензії Adobe Campaign Standard.

Експортовані дані зберігаються в контейнері сховища BLOB-об'єктів Azure, який було налаштовано вище. У контейнері автоматично створюється такий перелік дій:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Налаштування Adobe Campaign Standard

Експортовані сегменти містять стовпці, вибрані під час визначення місця призначення експорту на попередньому кроці. Ці дані можна використовувати для [створення профілів у Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Щоб скористатися сегментом у Adobe Campaign Standard, необхідно розширити схему профілю в Adobe Campaign Standard, додавши ще два поля. Дізнайтесь, як [розширити ресурс профілю](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) новими полями у Adobe Campaign Standard.

У цьому прикладі такими полями є: *«Назва сегмента» та «Дата сегмента» (необов'язково)*.

Ми використаємо ці поля для розпізнавання потрібних для цієї кампанії кінцевих профілів у Adobe Campaign Standard.

Якщо в Adobe Campaign Standard немає інших записів, крім тих, які ви збираєтесь імпортувати, цей крок можна пропустити.

## <a name="import-data-into-adobe-campaign-standard"></a>Імпортування даних до Adobe Campaign Standard

Тепер, коли все на місці, нам потрібно імпортувати підготовлені дані аудиторії з Customer Insights до Adobe стандарту кампанії, щоб створити профілі. Дізнайтесь, як [імпортувати профілі в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) за допомогою робочого циклу.

Робочий процес імпорту на зображенні нижче настроєно на запуск кожні вісім годин і шукати експортовані сегменти статистики клієнтів (.csv файл у сховищі Azure Blob Storage). Робочий цикл отримує вміст .csv-файлу у вказаному порядку стовпців. Цей робочий цикл створено для виконання базової обробки помилок і перевірки наявності адреси електронної пошти в кожному записі має перед заповненням даних у Adobe Campaign Standard. Цей робочий цикл також витягає ім'я сегмента з імені файлу перед його вставленням в дані профілю Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Знімок екрана: робочий цикл імпорту в інтерфейсі користувача Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Отримання аудиторії в Adobe Campaign Standard

Після імпорту даних до Adobe Campaign Standard, можна [створити робочий цикл](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ввести [запит](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) до клієнтів на основі *Імені сегмента* та *Дати сегмента*, щоб вибрати профілі, розпізнані для нашого зразку кампанії.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Створення та надсилання повідомлення електронної пошти за допомогою Adobe Campaign Standard

Створіть вміст електронної пошти, а потім [перевірте та надішліть](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) повідомлення електронної пошти.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Зразок повідомлення електронної пошти з пропозицією поновлення від Adobe Campaign Standard.":::