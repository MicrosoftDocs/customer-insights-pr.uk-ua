---
title: Використовуйте власний обліковий Azure Data Lake Storage запис Gen2
author: mukeshpo
description: Дізнайтеся про вимоги до використання власного Azure Data Lake Storage облікового запису для зберігання даних Customer Insights.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304406"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Використовуйте власний обліковий Azure Data Lake Storage запис Gen2

Dynamics 365 Customer Insights дає вам можливість зберігати всі ваші дані в [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction). Зберігаючи дані в Data Lake Storage, ви погоджуєтеся, що дані будуть передані та збережені у відповідному географічному розташуванні для цього облікового запису сховища Azure. Щоб отримати додаткові відомості, перегляньте [Центр безпеки та конфіденційності Microsoft](https://www.microsoft.com/trust-center).

Адміністратори в Customer Insights можуть [створювати середовища](create-environment.md) та [вказувати параметр](create-environment.md#step-2-configure-data-storage) зберігання даних у процесі.

## <a name="prerequisites"></a>вимоги

- Azure Data Lake Storage облікові записи мають знаходитися в тому самому регіоні Azure, який ви вибрали під час створення середовища Customer Insights. Щоб дізнатися регіон навколишнього середовища, перейдіть до **розділу Про** > **адміністративну** > **систему** в Customer Insights.
- Обліковий запис Data Lake Storage має бути Gen2. Облікові записи сховища Azure Data Lake Gen1 не підтримуються.
- В обліковому записі Data Lake Storage має бути [ввімкнено](/azure/storage/blobs/data-lake-storage-namespace) ієрархічний простір імен.
- На рахунку зберігання має існувати тара з іменем`customerinsights`. Створіть його, перш ніж використовувати власне сховище Data Lake в Customer Insights.
- Адміністратор, який настроює середовище Customer Insights, потребує ролі постачальника даних BLOB-даних сховища або власника даних BLOB-сервера сховища в обліковому записі сховища або контейнері`customerinsights`. Щоб отримати додаткові відомості про призначення дозволу в обліковому записі сховища, перегляньте статтю [Створення облікового запису](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) сховища.

## <a name="connect-customer-insights-with-your-storage-account"></a>Зв’яжіть Customer Insights зі своїм обліковим записом сховища

Коли ви створюєте нове середовище, переконайтеся, що обліковий запис Data Lake Storage існує і всі передумови виконані.

1. **На етапі зберігання** даних під час створення середовища встановіть параметр **Зберегти вихідні дані** в Gen2 **Azure Data Lake Storage**.
1. Виберіть спосіб **підключення сховища**. Ви можете вибрати між опцією на основі ресурсів і опцією на основі підписки для автентифікації. Щоб отримати додаткові відомості, перегляньте статтю [Підключення до облікового Azure Data Lake Storage запису за допомогою принципала](connect-service-principal.md) служби Azure.
   - Для **передплати** Azure виберіть **передплату**, **групу** ресурсів і **обліковий запис** Сховища, який містить `customerinsights` контейнер.
   - У полі **Ключ** облікового запису вкажіть **ім’я** облікового запису та ключ **облікового** запису для облікового запису Data Lake Storage. Використання цього методу автентифікації означає, що ви отримаєте сповіщення, якщо ваша організація обертає ключі. Ви повинні [оновити конфігурацію](manage-environments.md#edit-an-existing-environment) середовища новою клавішею, коли вона повертається.
1. Виберіть, чи потрібно використовувати Azure Private Link для підключення до облікового запису сховища та [створення підключення до приватного посилання](security-overview.md#set-up-an-azure-private-link).

Коли системні процеси, такі як прийом даних, завершуються, система створює відповідні папки в обліковому записі сховища. Файли даних і файли model.json створюються та додаються до папок залежно від імені процесу.

Якщо створити кілька середовищ Customer Insights і вибрати зберігання вихідних сутності з цих середовищ до вашого облікового запису сховища, Customer Insights створює окремі папки для кожного середовища із `ci_environmentID` в контейнері.
