---
title: Експорт сегментів у Adobe Experience Platform (попередній перегляд)
description: Дізнайтеся, як використовувати сегменти Customer Insights у розділі Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195315"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Експорт сегментів у Adobe Experience Platform (попередній перегляд)

Експортуйте сегменти, націлені на релевантні аудиторії до Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Схема процесів кроків, описаних у цій статті.":::

## <a name="prerequisites"></a>вимоги

- Ліцензія Adobe Experience Platform.
- Стандартна Adobe ліцензія кампанії.
- [Ім'я облікового запису](/azure/storage/blobs/create-data-lake-storage-account) сховища BLOB Azure і ключ облікового запису. Щоб знайти ім'я та ключ, перегляньте статтю [Керування параметрами облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).
- Контейнер [для зберігання блоґа-ляпів Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Огляд кампанії

Щоб краще зрозуміти, як можна використовувати сегменти від Customer Insights в Adobe Experience Platform, давайте розглянемо фіктивну вибіркову кампанію.

Припустімо, що ваша компанія пропонує клієнтам щомісячну передплату на послуги в Сполучених Штатах Америки. Вам потрібно визначити клієнтів, передплати яких мають бути продовжені впродовж наступних 8 днів, але які ще не продовжили їх. Щоб зберегти цих клієнтів, варто надіслати їм акційну пропозицію електронною поштою за допомогою Adobe Experience Platform.

У цьому прикладі ми хочемо запустити рекламну кампанію електронною поштою один раз. У цій статті не розглядається варіант використання багатократного запуску кампанії.

## <a name="identify-your-target-audience"></a>Визначте цільову аудиторію

У нашому сценарії ми припускаємо, що адреси електронної пошти клієнтів доступні в Customer Insights, а їхні рекламні уподобання були проаналізовані для ідентифікації учасників сегмента.

Сегмент [, який ви визначили в Customer Insights](segments.md), називається **ChurnProneCustomers**, і ви плануєте надіслати цим клієнтам просування електронною поштою.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Знімок екрана: сторінка сегментів зі створеним сегментом ChurnProneCustomers.":::

Повідомлення електронної пошти, яке необхідно надіслати, міститиме ім'я, прізвище та дату завершення передплати клієнта. Він інформує клієнтів про знижку, яку вони отримають, якщо продовжать передплату до закінчення терміну її дії.

## <a name="export-your-target-audience"></a>Експортуйте цільову аудиторію

Ми налаштуємо експорт із Customer Insights до облікового запису сховища BLOB-об'єктів Azure.

### <a name="set-up-connection-to-azure-blob-storage"></a>Настроювання підключення до сховища BLOB-об'єктів Azure

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть Додати **підключення** та виберіть Azure **BLOB Storage**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть **Ім’я бізнес-партнера**, **Ключ бізнес-партнера** та **Контейнер** для облікового запису сховища BLOB-об’єктів, до якого ви бажаєте експортувати сегмент.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Знімок екрана із конфігураціями облікового запису сховища.":::

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

### <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть Додати **експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу «Сховище BLOB-об’єктів Azure». Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім'я експорту.

1. Виберіть сегмент, який потрібно експортувати. У цьому прикладі це **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Знімок екрана: інтерфейс користувача вибору сегмента з вибраним сегментом ChurnProneCustomers.":::

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Переконайтеся, що кількість записів у експортованому сегменті не перевищує граничне значення ліцензії Adobe Campaign Standard.

Експортовані дані зберігаються в настроєному контейнері сховища BLOB-об'єктів Azure. У контейнері автоматично створюються наведені далі шляхи папок.

- Для сутностей джерел і сутностей, згенерованих у системі:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- *model.json* для експортованих сутностей розташовується на рівні *%ExportDestinationName%*.

  Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Визначення моделі даних досвіду (XDM) у Adobe Experience Platform

Перед тим, як експортувати дані з Customer Insights можна буде використовувати всередині Adobe Experience Platform, визначте схему моделі даних досвіду та [налаштуйте дані для профілю](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) клієнта в режимі реального часу.

Дізнайтеся, [що таке XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) і зрозумійте [основи створення схем](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Імпорт даних до Adobe Experience Platform

Імпортуйте підготовлені дані про аудиторію з Customer Insights в Adobe Experience Platform.

1. [Створіть підключення до сховища BLOB-об'єктів](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started) Azure.

1. [Налаштуйте потік](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) даних для пакетного підключення хмарного сховища, щоб імпортувати вихід сегмента з Customer Insights в Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Створення аудиторії в Adobe Campaign Standard

Щоб надіслати повідомлення електронної пошти для цієї кампанії ми скористаємося Adobe Campaign Standard.

1. [Створіть аудиторію](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) в Adobe Campaign Standard, використовуючи дані в Adobe Experience Platform.

1. [Використовуйте конструктор сегментів](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) у Adobe стандарті кампанії, щоб визначити аудиторію на основі даних у Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Створення та надсилання повідомлення електронної пошти за допомогою Adobe Campaign Standard

Створіть вміст електронної пошти, а потім [перевірте та надішліть](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) повідомлення електронної пошти.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Зразок повідомлення електронної пошти з пропозицією поновлення від Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
