---
title: Експорт сегментів Статистики клієнтів до Adobe стандарту кампанії (попередній перегляд)
description: Дізнайтеся, як використовувати сегменти Customer Insights у стандарті Adobe кампанії.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195545"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Експорт сегментів Статистики клієнтів до Adobe стандарту кампанії (попередній перегляд)

Експортуйте сегменти, націлені на релевантні аудиторії, до Adobe стандарту кампанії.

:::image type="content" source="media/ACS-flow.png" alt-text="Схема процесів кроків, описаних у цій статті.":::

## <a name="prerequisites"></a>вимоги

- Стандартна Adobe ліцензія кампанії.
- [Ім'я облікового запису](/azure/storage/blobs/create-data-lake-storage-account) сховища BLOB Azure і ключ облікового запису. Щоб знайти ім'я та ключ, перегляньте статтю [Керування параметрами облікового запису сховища на порталі Azure](/azure/storage/common/storage-account-manage).
- Контейнер [для зберігання блоґа-ляпів Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Огляд кампанії

Щоб краще зрозуміти, як можна використовувати сегменти від Customer Insights в Adobe Experience Platform, давайте розглянемо фіктивну вибіркову кампанію.

Припустімо, що ваша компанія пропонує клієнтам щомісячну передплату на послуги в Сполучених Штатах Америки. Вам потрібно визначити клієнтів, передплати яких мають бути продовжені впродовж наступних 8 днів, але які ще не продовжили їх. Щоб зберегти цих клієнтів, варто надіслати їм акційну пропозицію електронною поштою за допомогою Adobe Campaign Standard.

У цьому прикладі ми хочемо запустити рекламну кампанію електронною поштою один раз. У цій статті не розглядається варіант використання багатократного запуску кампанії. Однак Customer Insights і Adobe Campaign Standard також можна налаштувати на роботу для повторюваного сценарію кампанії.

## <a name="identify-your-target-audience"></a>Визначте цільову аудиторію

У нашому сценарії ми припускаємо, що адреси електронної пошти клієнтів доступні в Customer Insights, а їхні рекламні уподобання були проаналізовані для ідентифікації учасників сегмента.

Сегмент [, який ви визначили в Customer Insights](segments.md), називається **ChurnProneCustomers**, і ви плануєте надіслати цим клієнтам просування електронною поштою.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Знімок екрана: сторінка сегментів зі створеним сегментом ChurnProneCustomers.":::

Повідомлення електронної пошти, яке необхідно надіслати, міститиме ім'я, прізвище та дату завершення передплати клієнта. Він інформує клієнтів про знижку, яку вони отримають, якщо продовжать передплату до закінчення терміну її дії.

## <a name="export-your-target-audience"></a>Експортуйте цільову аудиторію

### <a name="set-up-connection-to-adobe-campaign"></a>Настроювання підключення до Adobe Кампанії

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати підключення** та виберіть **Adobe Кампанія**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть ім'я **облікового** запису, **ключ** бізнес-партнера та **контейнер** для свого облікового запису сховища BLOB.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Знімок екрана із конфігураціями облікового запису сховища.":::

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

### <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть Додати **експорт**.

1. У полі **Підключення для експорту**, виберіть підключення з розділу Adobe Campaign. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім'я експорту.

1. Виберіть сегмент, який потрібно експортувати. У цьому прикладі це **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Знімок екрана: інтерфейс користувача вибору сегмента з вибраним сегментом ChurnProneCustomers.":::

1. Виберіть **Далі**.

1. **Зіставте поля Source** із сегмента Customer Insights з **іменами цільових** полів у схемі Adobe профілю Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Зіставлення полів для з'єднувача Adobe Campaign Standard.":::

   Щоб додати більше атрибутів, виберіть **Додати атрибут**. Ім'я цілі може відрізнятися від імені вихідного поля, тому ви все одно можете зіставити виведення сегмента з Customer Insights до Adobe Campaign Standard, якщо поля не мають однакового імені в двох системах.

   > [!NOTE]
   > Адреса електронної пошти використовується як поле для ідентифікації, але ви можете використовувати будь-який інший ідентифікатор із профілю клієнта, щоб зіставити дані зі Adobe стандартом Campaign Standard.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Переконайтеся, що кількість записів у експортованому сегменті не перевищує граничне значення ліцензії Adobe Campaign Standard.

Експортовані дані зберігаються в контейнері сховища BLOB-об'єктів Azure, який було налаштовано вище. У вашому контейнері автоматично створюється наступний шлях до папки: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Приклад: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Налаштування Adobe Campaign Standard

Експортовані сегменти містять стовпці, які ви виділили під час налаштування експорту. Ці дані можна використовувати для [створення профілів у Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Щоб використовувати сегмент у Adobe стандартній кампанії, [розширте схему](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) профілю в Adobe стандартній кампанії, додавши два додаткових поля.

У нашому прикладі такими полями є Ім'я сегмента та Дата сегмента. Ми використаємо ці поля для розпізнавання потрібних для цієї кампанії кінцевих профілів у Adobe Campaign Standard.

Якщо в Adobe Campaign Standard немає інших записів, окрім імпортованих, пропустіть цей крок.

## <a name="import-data-into-adobe-campaign-standard"></a>Імпортування даних до Adobe Campaign Standard

Імпортуйте підготовлені дані про аудиторію з Customer Insights у Adobe стандарт кампанії, щоб [створити профілі за допомогою робочого процесу](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Робочий процес імпорту на зображенні нижче настроєно на виконання кожні вісім годин і пошук експортованих сегментів Customer Insights (.csv файл у сховищі BLOB-об'єктів Azure). Робочий цикл отримує вміст .csv-файлу у вказаному порядку стовпців. Цей робочий цикл створено для виконання базової обробки помилок і перевірки наявності адреси електронної пошти в кожному записі має перед заповненням даних у Adobe Campaign Standard. Цей робочий цикл також витягає ім'я сегмента з імені файлу перед його вставленням в дані профілю Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Знімок екрана: робочий цикл імпорту в інтерфейсі користувача Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Отримання аудиторії в Adobe Campaign Standard

Після імпорту даних у Adobe стандарт [кампанії створіть робочий цикл](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) і [попросіть](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) клієнтів на основі назви сегмента та дати сегмента вибрати профілі, визначені для нашої вибіркової кампанії.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Створення та надсилання повідомлення електронної пошти за допомогою Adobe Campaign Standard

Створіть вміст електронної пошти, а потім [перевірте та надішліть](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) повідомлення електронної пошти.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Зразок повідомлення електронної пошти з пропозицією поновлення від Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
