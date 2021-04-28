---
title: Експортування даних Customer Insights до платформи Adobe Experience
description: Дізнайтесь, як використовувати сегменти аналітичних оглядів аудиторії на платформі Adobe Experience.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760126"
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

### <a name="configure-a-connection"></a>Налаштуйте підключення

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть розділ **Додати підключення**, потім виберіть **Сховище BLOB-об’єктів Azure** або виберіть **Налаштувати** на плитці **Сховище BLOB-об’єктів Azure**,

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Плитка конфігурації для сховища BLOB-об'єктів Azure."::: щоб налаштувати підключення.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть **Ім’я бізнес-партнера**, **Ключ бізнес-партнера** і **Контейнер** свого облікового запису сховища BLOB-об’єктів, до якого ви бажаєте експортувати сегмент.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Знімок екрана із конфігураціями облікового запису сховища."::: 
   
    - Щоб отримати докладніші відомості про те, як знайти ім’я облікового запису сховища BLOB-об’єктів, див. розділ [Керуйте налаштуваннями облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).
    - Щоб дізнатися, як створити контейнер, див. розділ [Створення контейнера ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Щоб завершити створення підключення, виберіть **Зберегти**. 

### <a name="configure-an-export"></a>Налаштування експорту

Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу «Сховище BLOB-об’єктів Azure». Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. Виберіть сегмент, який потрібно експортувати. У цьому прикладі це **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Знімок екрана: інтерфейс користувача вибору сегмента з вибраним сегментом ChurnProneCustomers.":::

1. Виберіть **Зберегти**.

Після того, як ви зберегли пункт призначення експорту, ви зможете знайти його в розділі **Дані** > **Експорт**.

Тепер сегмент [можна експортувати неавтоматично](export-destinations.md#run-exports-on-demand). Експорт також запускатиметься під час кожного [запланованого оновлення](system.md).

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
