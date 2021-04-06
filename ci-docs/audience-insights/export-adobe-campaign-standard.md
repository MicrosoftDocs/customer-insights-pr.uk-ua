---
title: Експортування даних Customer Insights до Adobe Campaign Standard
description: Дізнайтесь, як використовувати сегменти аналітичних оглядів аудиторії у Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596340"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Використовуйте сегменти Customer Insights у Adobe Campaign Standard (підготовча версія)

Як користувач аналітики аудиторії для Dynamics 365 Customer Insights, ви могли створювати сегменти, щоб зробити свої маркетингові кампанії більш ефективними завдяки націлюванню на відповідні аудиторії. Щоб використовувати сегмент з аналітики аудиторії на платформі Adobe Experience та в програмах, як-от Adobe Campaign Standard, потрібно виконати кілька кроків, наведених у цій статті.

:::image type="content" source="media/ACS-flow.png" alt-text="Схема процесів кроків, описаних у цій статті.":::

## <a name="prerequisites"></a>Вимоги

-   Ліцензія Dynamics 365 Customer Insights
-   Ліцензія Adobe Campaign Standard
-   Обліковий запис сховища Azure Blob

## <a name="campaign-overview"></a>Огляд кампанії

Щоб краще зрозуміти, як можна використовувати сегменти з аналітики аудиторії на платформі Adobe Experience, перегляньте вигадані приклади кампаній.

Припустімо, що ваша компанія пропонує клієнтам щомісячну передплату на послуги в Сполучених Штатах Америки. Вам потрібно визначити клієнтів, передплати яких мають бути продовжені впродовж наступних 8 днів, але які ще не продовжили їх. Щоб зберегти цих клієнтів, ви хочете надіслати їм акційну пропозицію електронною поштою за допомогою Adobe Campaign Standard.

У цьому прикладі ми хочемо запустити рекламну кампанію електронною поштою один раз. У цій статті не розглядається варіант використання багатократного запуску кампанії. Проте аналітичні огляди аудиторій і Adobe Campaign Standard можна настроювати також для роботи з повторюваним сценарієм кампанії.

## <a name="identify-your-target-audience"></a>Визначте цільову аудиторію

У нашому сценарії ми припускаємо, що адреси електронної пошти клієнтів доступні в аналітичних оглядах аудиторії, в їхні рекламні уподобання були проаналізовані для ідентифікації учасників сегменту.

[Сегмент, визначений у аналітичних оглядах аудиторії](segments.md), називається **ChurnProneCustomers** і ви плануєте надіслати цим клієнтам рекламну пропозицію електронною поштою.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Знімок екрана: сторінка сегментів зі створеним сегментом ChurnProneCustomers.":::

Повідомлення електронної пошти, яке необхідно надіслати, міститиме ім'я, прізвище та дату завершення передплати клієнта. Він інформує клієнтів про знижку, яку вони отримають, якщо продовжать передплату до закінчення терміну її дії.

## <a name="export-your-target-audience"></a>Експортуйте цільову аудиторію

Визначивши нашу цільову аудиторію, можна налаштувати експорту з аналітичних оглядів аудиторії до облікового запису сховища BLOB-об'єктів Azure.

1. У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.

1. У плитці **Adobe Campaign** натисніть **Налаштувати**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Плитка «Конфігурація» для Adobe Campaign Standard.":::

1. Вкажіть **Коротке ім'я** для нового призначення експорту і введіть **Ім'я облікового запису**, **Ключ облікового запису** і **Контейнер** облікового запису сховища Blob-об'єктів Azure, до якого потрібно експортувати сегмент.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Знімок екрана із конфігураціями облікового запису сховища."::: 

   - Докладніше про те, як знайти обліковий запис сховища BLOB-об’єктів Azure і ключ облікового запису, див. у розділі [Керування настройками облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).

   - Щоб дізнатися, як створити контейнер, див. розділ [Створення контейнера ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Виберіть **Далі**.

1. Виберіть сегмент, який потрібно експортувати. У цьому прикладі це **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Знімок екрана: інтерфейс користувача вибору сегмента з вибраним сегментом ChurnProneCustomers.":::

1. Виберіть **Далі**.

1. Тепер ми зіставляємо поля **Джерело** з сегменту аналітичних оглядів аудиторії з іменами поля **Ціль** у схемі профілю Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Зіставлення полів для стандартного з'єднувача Adobe Campaign Standard.":::

   Щоб додати більше атрибутів, виберіть **Додати атрибут**. Кінцеве ім'я може відрізнятися від вихідного імені поля, м=тому ви все одно можете зіставити вивід сегмента х аналітичних оглядів аудиторії з Adobe Campaign Standard, якщо поля не мають однакового імені в двох системах.

   > [!NOTE]
   > Адреса електронної пошти використовується як поле посвідчення, але можна використовувати будь-який інший ідентифікатор з профілю клієнта аналітичних оглядів аудиторії, щоб зіставити дані в Adobe Campaign Standard.

1. Виберіть **Зберегти**.

Після збереження призначення експорту його можна знайти в меню **Адміністратор** > **Експортування** > **Мої призначення експорту**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Знімок екрана зі списком експортів і виділеним прикладом сегменту.":::

Тепер сегмент [можна експортувати неавтоматично](export-destinations.md#export-data-on-demand). Експорт також запускатиметься під час кожного [запланованого оновлення](system.md).

> [!NOTE]
> Переконайтеся, що кількість записів у експортованому сегменті перебуває в межах дозволеного ліміту вашої ліцензії Adobe Campaign Standard.

Експортовані дані зберігаються в контейнері сховища BLOB-об'єктів Azure, який було настроєно вище. У контейнері автоматично створюється такий перелік дій:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Налаштування Adobe Campaign Standard

У разі експортування сегмента аналітичного огляду аудиторії він містить стовпці, вибрані під час визначення призначення експорту в попередньому кроці. Ці дані можна використовувати для [створення профілів у Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Для використання сегменту в Adobe Campaign Standard, потрібно розширити схему профілю в Adobe Campaign Standard , щоб додати два додаткові поля. Навчіться [розширювати ресурс профілю](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) за допомогою нових полів у Adobe Campaign Standard.

У нашому прикладі це поля *«Назва сегмента» та «Дата сегмента» (необов'язково).*

Ці поля використовуватимуться для визначення профілів у Adobe Campaign Standard, визначених для цієї кампанії.

Якщо в Adobe Campaign Standard немає інших записів, що відрізняються від тих, які ви хочете імпортувати, ви можете пропустити цей крок.

## <a name="import-data-into-adobe-campaign-standard"></a>Імпортування даних до Adobe Campaign Standard

Тепер, коли все готово, необхідно імпортувати підготовлені дані про аудиторію аналітичних оглядів аудиторії до Adobe Campaign Standard, щоб створити профілі. Дізнайтеся [як імпортувати профілі в Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) за допомогою робочого циклу.

Робочий цикл імпорту на зображенні нижче настроєний для запуску кожні 8 годин і шукає експортовані сегменти аналітичних оглядів аудиторії (.csv-файл у сховищі BLOB-об'єктів Azure). Робочий цикл отримує вміст .csv-файлу у вказаному порядку стовпців. Цей робочий цикл створено для виконання базової обробки помилок і забезпечення того, щоб кожен запис мав адресу електронної пошти перед зливом даних у Adobe Campaign Standard. Робочий цикл також отримує ім'я сегмента з імені файлу перед вставлянням у дані профілю ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Знімок екрана: робочий цикл імпорту в інтерфейсі користувача Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Отримання аудиторії у Adobe Campaign Standard

Після імпорту даних у Adobe Campaign Standard [можна створити робочий цикл](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) і [запит](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) клієнтів на основі *Імені сегмента* і *Дати сегменту* для вибору профілів, визначених для нашого прикладу кампанії.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Створення та надсилання електронної пошти за допомогою Adobe Campaign Standard

Створіть вміст електронної пошти, а потім [перевірте та надішліть](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) повідомлення електронної пошти.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Зразок повідомлення електронної пошти із пропозицією оновлення за допомогою Adobe Campaign Standard.":::