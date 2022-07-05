---
title: Експорт сегментів у Adobe Experience Platform (попередній перегляд)
description: Дізнайтеся, як використовувати сегменти Customer Insights у Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: c29b8264019669ffd954a298ce3a633c852477fa
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052536"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Експорт сегментів у Adobe Experience Platform (попередній перегляд)

Як користувач Dynamics 365 Customer Insights, ви, можливо, створили сегменти, щоб зробити свої маркетингові кампанії більш ефективними, націлюючись на відповідні аудиторії. Щоб використовувати сегмент із Customer Insights у Adobe Experience Platform та таких програмах, як Adobe Campaign Standard, вам потрібно виконати кілька кроків, описаних у цій статті.

:::image type="content" source="media/AEP-flow.png" alt-text="Схема процесів кроків, описаних у цій статті.":::

## <a name="prerequisites"></a>Вимоги

-   Ліцензія Dynamics 365 Customer Insights
-   Ліцензія Adobe Experience Platform
-   Ліцензія Adobe Campaign Standard
-   Обліковий запис сховища Azure Blob

## <a name="campaign-overview"></a>Огляд кампанії

Щоб краще зрозуміти, як ви можете використовувати сегменти від Customer Insights in Adobe Experience Platform, давайте розглянемо фіктивну вибіркову кампанію.

Припустімо, що ваша компанія пропонує клієнтам щомісячну передплату на послуги в Сполучених Штатах Америки. Вам потрібно визначити клієнтів, передплати яких мають бути продовжені впродовж наступних 8 днів, але які ще не продовжили їх. Щоб зберегти цих клієнтів, варто надіслати їм акційну пропозицію електронною поштою за допомогою Adobe Experience Platform.

У цьому прикладі ми хочемо запустити рекламну кампанію електронною поштою один раз. У цій статті не розглядається варіант використання багатократного запуску кампанії.

## <a name="identify-your-target-audience"></a>Визначте цільову аудиторію

У нашому сценарії ми припускаємо, що адреси електронної пошти клієнтів доступні в Customer Insights, а їх рекламні переваги були проаналізовані для ідентифікації учасників сегмента.

Сегмент [, який ви визначили в Customer Insights](segments.md), називається **ChurnProneCustomers**, і ви плануєте надіслати цим клієнтам рекламне просування електронною поштою.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Знімок екрана: сторінка сегментів зі створеним сегментом ChurnProneCustomers.":::

Повідомлення електронної пошти, яке необхідно надіслати, міститиме ім'я, прізвище та дату завершення передплати клієнта. Він інформує клієнтів про знижку, яку вони отримають, якщо продовжать передплату до закінчення терміну її дії.

## <a name="export-your-target-audience"></a>Експортуйте цільову аудиторію

За допомогою нашої цільової аудиторії ми можемо налаштувати експорт із Customer Insights до облікового запису Azure Blob Storage.

### <a name="configure-a-connection"></a>Налаштуйте підключення

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть розділ **Додати підключення**, потім виберіть **Сховище BLOB-об’єктів Azure** або виберіть **Налаштувати** на плитці **Сховище BLOB-об’єктів Azure**, щоб налаштувати підключення.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Плитка конфігурації для сховища BLOB-об'єктів Azure."::: 

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть **Ім’я бізнес-партнера**, **Ключ бізнес-партнера** та **Контейнер** для облікового запису сховища BLOB-об’єктів, до якого ви бажаєте експортувати сегмент.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Знімок екрана із конфігураціями облікового запису сховища."::: 
   
    - Щоб отримати докладніші відомості про те, як знайти ім’я облікового запису сховища BLOB-об’єктів, див. розділ [Керуйте налаштуваннями облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).
    - Щоб дізнатися, як створити контейнер, див. розділ [Створення контейнера ](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Щоб завершити створення підключення, виберіть **Зберегти**. 

### <a name="configure-an-export"></a>Налаштування експорту

Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу «Сховище BLOB-об’єктів Azure». Якщо ви не бачите імені цього розділу, це означає, що для вас не доступні будь-які підключення цього типу.

1. Виберіть сегмент, який потрібно експортувати. У цьому прикладі це **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Знімок екрана: інтерфейс користувача вибору сегмента з вибраним сегментом ChurnProneCustomers.":::

1. Виберіть **Зберегти**.

Після того, як ви зберегли пункт призначення експорту, ви зможете знайти його в розділі **Дані** > **Експорт**.

Тепер сегмент [можна експортувати неавтоматично](export-destinations.md#run-exports-on-demand). Експорт також запускатиметься під час кожного [запланованого оновлення](system.md).

> [!NOTE]
> Переконайтеся, що кількість записів у експортованому сегменті не перевищує граничне значення ліцензії Adobe Campaign Standard.

Експортовані дані зберігаються в контейнері сховища BLOB-об'єктів Azure, який було налаштовано вище. У контейнері автоматично створюється такий перелік дій:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* для експортованих сутностей розташовується на рівні *%ExportDestinationName%*.

Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Визначення моделі даних досвіду (XDM) у Adobe Experience Platform

Перш ніж експортувати дані з Customer Insights можна буде використовувати всередині Adobe Experience Platform, нам потрібно визначити схему моделі даних Experience і [налаштувати дані для профілю](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) клієнта в режимі реального часу.

Дізнайтеся, [що таке XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) і зрозумійте [основи створення схем](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Імпорт даних до Adobe Experience Platform

Тепер, коли все на місці, нам потрібно імпортувати підготовлені дані аудиторії з Customer Insights в Adobe Experience Platform.

Спочатку [створіть підключення до джерела сховища Blob-об'єктів Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Після визначення вихідного з'єднання налаштуйте потік [даних для пакетного підключення хмарного сховища,](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) щоб імпортувати вихід сегмента з Customer Insights в Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Створення аудиторії в Adobe Campaign Standard

Щоб надіслати повідомлення електронної пошти для цієї кампанії ми скористаємося Adobe Campaign Standard. Після імпорту даних до Adobe Experience Platform, необхідно [створити аудиторію](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) в Adobe Campaign Standard за допомогою даних в Adobe Experience Platform.


Дізнайтесь, як [використовувати конструктор сегментів](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) у Adobe Campaign Standard для визначення аудиторії на основі даних у Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Створення та надсилання повідомлення електронної пошти за допомогою Adobe Campaign Standard

Створіть вміст електронної пошти, а потім [перевірте та надішліть](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) повідомлення електронної пошти.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Зразок повідомлення електронної пошти з пропозицією поновлення від Adobe Campaign Standard.":::
