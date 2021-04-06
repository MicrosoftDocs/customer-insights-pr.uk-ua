---
title: Експортування даних Customer Insights до платформи Adobe Experience
description: Дізнайтесь, як використовувати сегменти аналітичних оглядів аудиторії на платформі Adobe Experience.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596294"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Використовуйте сегменти Customer Insights на платформі Adobe Experience (підготовча версія)

Як користувач аналітики аудиторії для Dynamics 365 Customer Insights, ви могли створювати сегменти, щоб зробити свої маркетингові кампанії більш ефективними завдяки націлюванню на відповідні аудиторії. Щоб використовувати сегмент з аналітики аудиторії на платформі Adobe Experience та в програмах, як-от Adobe Campaign Standard, потрібно виконати кілька кроків, наведених у цій статті.

:::image type="content" source="media/AEP-flow.png" alt-text="Схема процесів кроків, описаних у цій статті.":::

## <a name="prerequisites"></a>Вимоги

-   Ліцензія Dynamics 365 Customer Insights
-   Ліцензія платформи Adobe Experience
-   Ліцензія Adobe Campaign Standard
-   Обліковий запис сховища Azure Blob

## <a name="campaign-overview"></a>Огляд кампанії

Щоб краще зрозуміти, як можна використовувати сегменти з аналітики аудиторії на платформі Adobe Experience, перегляньте вигадані приклади кампаній.

Припустімо, що ваша компанія пропонує клієнтам щомісячну передплату на послуги в Сполучених Штатах Америки. Вам потрібно визначити клієнтів, передплати яких мають бути продовжені впродовж наступних 8 днів, але які ще не продовжили їх. Щоб зберегти цих клієнтів, ви хочете надіслати їм акційну пропозицію електронною поштою за допомогою платформи Adobe Experience.

У цьому прикладі ми хочемо запустити рекламну кампанію електронною поштою один раз. У цій статті не розглядається варіант використання багатократного запуску кампанії.

## <a name="identify-your-target-audience"></a>Визначте цільову аудиторію

У нашому сценарії ми припускаємо, що адреси електронної пошти клієнтів доступні в аналітичних оглядах аудиторії, в їхні рекламні уподобання були проаналізовані для ідентифікації учасників сегменту.

[Сегмент, визначений у аналітичних оглядах аудиторії](segments.md), називається **ChurnProneCustomers** і ви плануєте надіслати цим клієнтам рекламну пропозицію електронною поштою.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Знімок екрана: сторінка сегментів зі створеним сегментом ChurnProneCustomers.":::

Повідомлення електронної пошти, яке необхідно надіслати, міститиме ім'я, прізвище та дату завершення передплати клієнта. Він інформує клієнтів про знижку, яку вони отримають, якщо продовжать передплату до закінчення терміну її дії.

## <a name="export-your-target-audience"></a>Експортуйте цільову аудиторію

Визначивши нашу цільову аудиторію, можна налаштувати експорту з аналітичних оглядів аудиторії до облікового запису сховища BLOB-об'єктів Azure.

1. У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.

1. У плитці **Сховище BLOB-об'єктів Azure**" натисніть **Налаштувати**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Плитка конфігурації для сховища BLOB-об'єктів Azure.":::

1. Вкажіть **Коротке ім'я** для нового призначення експорту і введіть **Ім'я облікового запису**, **Ключ облікового запису** і **Контейнер** облікового запису сховища Blob-об'єктів Azure, до якого потрібно експортувати сегмент.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Знімок екрана із конфігураціями облікового запису сховища."::: 

   - Докладніше про те, як знайти обліковий запис сховища BLOB-об’єктів Azure і ключ облікового запису, див. у розділі [Керування настройками облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).

   - Щоб дізнатися, як створити контейнер, див. розділ [Створення контейнера ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Виберіть **Далі**.

1. Виберіть сегмент, який потрібно експортувати. У цьому прикладі це **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Знімок екрана: інтерфейс користувача вибору сегмента з вибраним сегментом ChurnProneCustomers.":::

1. Виберіть **Зберегти**.

Після збереження призначення експорту його можна знайти в меню **Адміністратор** > **Експортування** > **Мої призначення експорту**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Знімок екрана зі списком експортів і виділеним прикладом сегменту.":::

Тепер сегмент [можна експортувати неавтоматично](export-destinations.md#export-data-on-demand). Експорт також запускатиметься під час кожного [запланованого оновлення](system.md).

> [!NOTE]
> Переконайтеся, що кількість записів у експортованому сегменті перебуває в межах дозволеного ліміту вашої ліцензії Adobe Campaign Standard.

Експортовані дані зберігаються в контейнері сховища BLOB-об'єктів Azure, який було настроєно вище. У контейнері автоматично створюється такий перелік дій:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* для експортованих сутностей розташовується на рівні *%ExportDestinationName%*.

Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Визначення моделі даних досвіду (XDM) на платформі Adobe Experience

Перед тим, як експортовані дані з аналітичних оглядів аудиторії можна буде використовувати в межах платформи Adobe Experience, потрібно визначити схему моделі даних досвіду та [налаштувати дані для профілю користувача в реальному часі](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Дізнайтеся, [що таке XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) і зрозумійте [основи створення схем](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Імпортування даних до платформи Adobe Experience

Тепер, коли все готово, необхідно імпортувати підготовлені дані про аудиторію аналітичних оглядів аудиторії до платформи Adobe Experience.

Спочатку [створіть підключення до джерела сховища Blob-об'єктів Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Після визначення підключення до джерела [налаштуйте потік даних](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) для підключення до хмарного сховища для імпорту виводу сегменту з аналітичних оглядів до платформи Adobe Experience.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Створення аудиторії у Adobe Campaign Standard

Ми використовуватимемо Adobe Campaign Standard, щоб надіслати електронний лист до цієї кампанії. Після імпорту даних до платформи Adobe Experience потрібно [створити аудиторію](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) в Adobe Campaign Standard за допомогою даних на платформі Adobe Experience.

Інформація про [використання конструктора сегменту](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) в Adobe Campaign Standard для визначення аудиторії на основі даних на платформі Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Створення та надсилання електронної пошти за допомогою Adobe Campaign Standard

Створіть вміст електронної пошти, а потім [перевірте та надішліть](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) повідомлення електронної пошти.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Зразок повідомлення електронної пошти із пропозицією оновлення за допомогою Adobe Campaign Standard.":::