---
title: Експорт даних Customer Insights до Adobe Campaign Standard
description: Дізнайтесь, як використовувати сегменти аналітичних оглядів аудиторії у Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d301b4f0cb875303fb3d373b77177acd1c1f5219cd6f23c2a1d29ce67a222eab
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032188"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Використання сегментів Customer Insights у Adobe Campaign Standard (підготовча версія)

Як користувач аналітичних оглядів аудиторії в Dynamics 365 Customer Insights, ви могли створювати сегменти для підвищення ефективності своїх маркетингових кампаній способом націлювання рекламного матеріалу на доречні аудиторії. Щоб скористатися сегментом з аналітичних оглядів аудиторії в Adobe Experience Platform та програмах на кшталт Adobe Campaign Standard, слід виконати кілька кроків, описаних у цій статті.

:::image type="content" source="media/ACS-flow.png" alt-text="Схема процесів кроків, описаних у цій статті.":::

## <a name="prerequisites"></a>Вимоги

-   Ліцензія Dynamics 365 Customer Insights
-   Ліцензія Adobe Campaign Standard
-   Обліковий запис сховища Azure Blob

## <a name="campaign-overview"></a>Огляд кампанії

Щоб краще зрозуміти, як можна використовувати сегменти з аналітичних оглядів аудиторії в Adobe Experience Platform, розгляньмо вигаданий приклад кампанії.

Припустімо, що ваша компанія пропонує клієнтам щомісячну передплату на послуги в Сполучених Штатах Америки. Вам потрібно визначити клієнтів, передплати яких мають бути продовжені впродовж наступних 8 днів, але які ще не продовжили їх. Щоб зберегти цих клієнтів, варто надіслати їм акційну пропозицію електронною поштою за допомогою Adobe Campaign Standard.

У цьому прикладі ми хочемо запустити рекламну кампанію електронною поштою один раз. У цій статті не розглядається варіант використання багатократного запуску кампанії. Проте, аналітичні огляди аудиторії та Adobe Campaign Standard також можна налаштувати для роботи з повторюваним сценарієм кампанії.

## <a name="identify-your-target-audience"></a>Визначте цільову аудиторію

У нашому сценарії ми припускаємо, що адреси електронної пошти клієнтів доступні в аналітичних оглядах аудиторії, в їхні рекламні уподобання були проаналізовані для ідентифікації учасників сегменту.

[Сегмент, визначений у аналітичних оглядах аудиторії](segments.md), називається **ChurnProneCustomers** і ви плануєте надіслати цим клієнтам рекламну пропозицію електронною поштою.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Знімок екрана: сторінка сегментів зі створеним сегментом ChurnProneCustomers.":::

Повідомлення електронної пошти, яке необхідно надіслати, міститиме ім'я, прізвище та дату завершення передплати клієнта. Він інформує клієнтів про знижку, яку вони отримають, якщо продовжать передплату до закінчення терміну її дії.

## <a name="export-your-target-audience"></a>Експортуйте цільову аудиторію

### <a name="configure-a-connection"></a>Налаштуйте підключення

Визначивши нашу цільову аудиторію, можна налаштувати експорту з аналітичних оглядів аудиторії до облікового запису сховища BLOB-об'єктів Azure.

1. У аналітиці аудиторії перейдіть до розділу **Адміністратор** > **Підключення**.

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

1. Тепер ми зіставимо **вихідні** поля із сегменту аналітичного оглядів аудиторії з іменами **кінцевих** полів у схемі профілю Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Зіставлення полів для з'єднувача Adobe Campaign Standard.":::

   Щоб додати більше атрибутів, виберіть **Додати атрибут**. Кінцеве ім'я може відрізнятися від імені вихідного поля, щоб можна було зіставити результати сегмента з аналітичних оглядів аудиторії та Adobe Campaign Standard, навіть якщо поля в системах мають різні імена.

   > [!NOTE]
   > Адреса електронної пошти використовується як поле ідентифікації, але можна використовувати будь-який інший ідентифікатор з профілю клієнта аналітичних оглядів аудиторії для зіставлення даних з Adobe Campaign Standard.

1. Виберіть **Зберегти**.

Після того, як ви зберегли пункт призначення експорту, ви зможете знайти його в розділі **Дані** > **Експорт**.

Тепер сегмент [можна експортувати неавтоматично](export-destinations.md#run-exports-on-demand). Експорт також запускатиметься під час кожного [запланованого оновлення](system.md).

> [!NOTE]
> Переконайтеся, що кількість записів у експортованому сегменті не перевищує граничне значення ліцензії Adobe Campaign Standard.

Експортовані дані зберігаються в контейнері сховища BLOB-об'єктів Azure, який було налаштовано вище. У контейнері автоматично створюється такий перелік дій:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Налаштування Adobe Campaign Standard

У разі експортування сегмента аналітичного огляду аудиторії він містить стовпці, вибрані під час визначення призначення експорту в попередньому кроці. Ці дані можна використовувати для [створення профілів у Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Щоб скористатися сегментом у Adobe Campaign Standard, необхідно розширити схему профілю в Adobe Campaign Standard, додавши ще два поля. Дізнайтесь, як [розширити ресурс профілю](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) новими полями у Adobe Campaign Standard.

У цьому прикладі такими полями є: *«Назва сегмента» та «Дата сегмента» (необов'язково)*.

Ми використаємо ці поля для розпізнавання потрібних для цієї кампанії кінцевих профілів у Adobe Campaign Standard.

Якщо в Adobe Campaign Standard немає інших записів, крім тих, які ви збираєтесь імпортувати, цей крок можна пропустити.

## <a name="import-data-into-adobe-campaign-standard"></a>Імпортування даних до Adobe Campaign Standard

Тепер, коли все на місці, потрібно імпортувати підготовлені дані аудиторії з аналітичних оглядів аудиторії в Adobe Campaign Standard, щоб створити профілі. Дізнайтесь, як [імпортувати профілі в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) за допомогою робочого циклу.

Робочий цикл імпорту на наведеному нижче зображенні налаштовано для запуску кожні вісім годин, коли цей цикл виконуватиме пошук експортованих сегментів аналітичних оглядів аудиторії (файлу .csv у Сховищі BLOB-об’єктів Azure). Робочий цикл отримує вміст .csv-файлу у вказаному порядку стовпців. Цей робочий цикл створено для виконання базової обробки помилок і перевірки наявності адреси електронної пошти в кожному записі має перед заповненням даних у Adobe Campaign Standard. Цей робочий цикл також витягає ім'я сегмента з імені файлу перед його вставленням в дані профілю Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Знімок екрана: робочий цикл імпорту в інтерфейсі користувача Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Отримання аудиторії в Adobe Campaign Standard

Після імпорту даних до Adobe Campaign Standard, можна [створити робочий цикл](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ввести [запит](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) до клієнтів на основі *Імені сегмента* та *Дати сегмента*, щоб вибрати профілі, розпізнані для нашого зразку кампанії.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Створення та надсилання повідомлення електронної пошти за допомогою Adobe Campaign Standard

Створіть вміст електронної пошти, а потім [перевірте та надішліть](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) повідомлення електронної пошти.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Зразок повідомлення електронної пошти з пропозицією поновлення від Adobe Campaign Standard.":::
