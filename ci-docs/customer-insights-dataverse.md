---
title: Робота із даними Customer Insights у Microsoft Dataverse
description: Дізнайтеся, як підключити статистику клієнтів і Microsoft Dataverse зрозуміти вихідні сутності, експортовані до програми Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 252723b8c174cb1ec488388c26fd2a1d398e9002
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011582"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Робота із даними Customer Insights у Microsoft Dataverse

Статистика клієнтів надає можливість зробити вихідні сутності доступними як [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ця інтеграція дозволяє легко обмінюватися даними та індивідуальну розробку за допомогою низького підходу коду / без коду. Вихідні [сутності](#output-entities) доступні як таблиці в Dataverse середовищі. Дані можна використовувати для будь-якої іншої програми на Dataverse основі таблиць. У цих таблицях містяться такі сценарії, як автоматичні робочі цикли або Power Automate створення програм за допомогою програми за допомогою програми Power Apps.

Підключення до вашого Dataverse середовища також дозволяє отримувати [дані з локальний джерел даних за допомогою Power Platform потоків даних і шлюзів](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>вимоги

- Статистика клієнтів і Dataverse середовища повинні розміщуватися в одному регіоні.
- Ви повинні мати глобальну роль адміністратора в навколишньому Dataverse середовищі. Перевірте, чи пов'язане це [Dataverse середовище з](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) певними групами безпеки, і переконайтеся, що ви додані до цих груп безпеки.
- Жодне інше середовище статистики клієнтів не пов'язане з середовищем, Dataverse яке потрібно підключити. Дізнайтеся, [як видалити наявне підключення до Dataverse середовища](#remove-an-existing-connection-to-a-dataverse-environment).
- Середовище Microsoft Dataverse може підключатися лише до одного облікового запису сховища. Він застосовується, лише якщо настроїти середовище для [використання програми Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Dataverse Підключення середовища до статистики клієнтів

Цей **Microsoft Dataverse** крок дає змогу підключити статистику клієнтів із середовищем Dataverse під час [створення середовища](create-environment.md) статистики клієнтів.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="спільний доступ до даних з Microsoft Dataverse автоматичним увімкненням для чистих нових середовищ.":::

Адміністратори можуть настроїти статистику клієнтів для підключення наявного Dataverse середовища. Надаючи URL-адресу навколишньому середовищу Dataverse, вона прикріплюється до їх нового середовища статистики клієнтів.

Якщо ви не хочете використовувати існуюче Dataverse середовище, система створює нове середовище для даних Статистики клієнта у вашому клієнті. [Power Platform адміністратори можуть контролювати, хто може створювати середовища](/power-platform/admin/control-environment-creation). Коли ви налаштовуєте нове середовище статистики клієнтів, і адміністратор вимкнув створення Dataverse середовищ для всіх, крім адміністраторів, можливо, ви не зможете створити нове середовище.

**Увімкніть спільний доступ до** Dataverse даних, встановивши прапорець Спільний доступ до даних.

Якщо використовується власний обліковий запис сховища даних Lake, вам також потрібен **ідентифікатор** дозволів. Щоб отримати додаткові відомості про отримання ідентифікатора дозволу, перегляньте наведений нижче розділ.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Увімкнути спільний доступ до даних із Dataverse власного Azure Data Lake Storage (Попередній перегляд)

Увімкнення спільного доступу до даних, Microsoft Dataverse коли ваше середовище [використовує ваш власний Azure Data Lake Storage обліковий запис](own-data-lake-storage.md), потребує додаткової конфігурації. Користувач, який налаштовує середовище Customer Insights, повинен мати принаймні **дозволи засобу** читання *даних blob-об'єктів сховища на контейнері CustomerInsights* в обліковому записі Azure Data Lake Storage.

1. Створіть дві групи безпеки під час передплати Azure – одну **групу безпеки Reader** і одну **групу безпеки Вкладника** та встановіть службу Microsoft Dataverse як власника для обох груп безпеки.
2. Керуйте списком керування доступом (ACL) у контейнері CustomerInsights у своєму обліковому записі сховища за допомогою цих груп безпеки. Додайте службу Microsoft Dataverse та будь-які Dataverse бізнес-застосунки, такі як Dynamics 365 Marketing, до **групи безпеки Reader** із **дозволами лише** для читання. Додайте *лише* програму "Статистика клієнтів" **до групи безпеки "Постачальник",** щоб надати дозволи на **читання та записування** для записування профілів та статистики.

### <a name="limitations"></a>Обмеження

Існує два обмеження при використанні Dataverse з власним Azure Data Lake Storage обліковим записом:

- Між організацією та обліковим записом Dataverse відбувається зіставлення один на Azure Data Lake Storage один. Dataverse Після підключення організації до облікового запису сховища не вдається підключитися до іншого облікового запису сховища. Це обмеження запобігає тому, що A Dataverse не заповнює кілька облікових записів онлайнове пул носіїв.
- Спільний доступ до даних не працюватиме, якщо для доступу до облікового Azure Data Lake Storage запису потрібна настройка Azure Private Link, оскільки вона стоїть за брандмауером. Dataverse наразі не підтримує підключення до приватних кінцевих точок через приватне посилання.

### <a name="set-up-powershell"></a>Настроювання оболонки PowerShell

Щоб виконати сценарії PowerShell, спочатку потрібно відповідним чином налаштувати PowerShell.

1. Інсталюйте останню [Azure Active Directory версію PowerShell для графіка](/powershell/azure/active-directory/install-adv2).
   1. На комп'ютері натисніть клавішу Windows на клавіатурі, знайдіть **Windows PowerShell** і виберіть **Запуск від імені адміністратора**.
   1. У вікні PowerShell, що відкриється, введіть `Install-Module AzureAD`.
2. Імпорт трьох модулів.
    1. У вікні PowerShell введіть `Install-Module -Name Az.Accounts` і виконайте кроки.
    1. Повторіть для `Install-Module -Name Az.Resources` і `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Кроки з налаштування

1. Завантажте два сценарії PowerShell, які вам потрібно запустити з репо [нашого інженера](https://github.com/trin-msft/byol) GitHub.
    1. `CreateSecurityGroups.ps1`
       - Для запуску цього сценарію PowerShell потрібні *дозволи адміністратора* клієнта.
       - Цей сценарій PowerShell створює дві групи безпеки під час передплати Azure. Одна для групи Reader, а інша для групи Вкладник і зробить Microsoft Dataverse службу в якості власника для обох цих груп безпеки.
       - Виконайте цей сценарій PowerShell у Windows PowerShell, надавши ідентифікатор передплати Azure, що містить ваш Azure Data Lake Storage. Відкрийте сценарій PowerShell у редакторі, щоб переглянути додаткову інформацію та реалізовану логіку.
       - Збережіть обидва значення ідентифікатора групи безпеки, створені цим сценарієм, оскільки ми будемо використовувати їх у `ByolSetup.ps1` сценарії.

        > [!NOTE]
        > Створення групи безпеки можна вимкнути для вашого клієнта. У цьому випадку знадобиться ручне налаштування, і адміністратор Azure AD повинен [буде ввімкнути створення](/azure/active-directory/enterprise-users/groups-self-service-management) групи безпеки.

    2. `ByolSetup.ps1`
        - Для запуску цього сценарію потрібні *дозволи власника* даних blob-об'єкта сховища на рівні облікового запису сховища/контейнера, інакше цей сценарій створить його для вас. Призначення ролі можна видалити вручну після успішного запуску сценарію.
        - Цей сценарій PowerShell додає необхідний tole основі контролю доступу (RBAC) для Microsoft Dataverse служби та будь-яких Dataverse бізнес-додатків на основі. Він також оновлює список керування доступом (ACL) на контейнері CustomerInsights для груп безпеки, створених за допомогою сценарію `CreateSecurityGroups.ps1`. Група "Постачальник" матиме *дозвіл rwx*, а група читачів матиме *лише дозвіл r-x*.
        - Виконайте цей сценарій PowerShell у Windows PowerShell, надавши ідентифікатор передплати Azure, що містить Azure Data Lake Storage ім'я облікового запису сховища, ім'я групи ресурсів, а також ідентифікатор групи безпеки Reader і Contributor. Відкрийте сценарій PowerShell у редакторі, щоб переглянути додаткову інформацію та реалізовану логіку.
        - Скопіюйте вихідний рядок після успішного запуску сценарію. Вихідний рядок виглядає так: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Введіть вихідний рядок, скопійований зверху, **у поле Ідентифікатор** дозволів кроку конфігурації середовища для Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Параметри конфігурації для ввімкнення спільного доступу до даних із власного Azure Data Lake Storage за допомогою Microsoft Dataverse програми .":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Видалення наявного підключення до Dataverse середовища

Під Вільний час Dataverse підключення до середовища, протокол IMAP **про помилку Ця організація CDS вже приєднана до іншого екземпляра** статистики клієнта означає, що Dataverse середовище вже використовується в середовищі статистики клієнта. Наявне підключення можна видалити як глобального адміністратора в Dataverse навколишньому середовищі. Це може зайняти кілька годин, щоб заповнити зміни.

1. Перейти до [Power Apps](https://make.powerapps.com).
1. Виберіть середовище з палітри середовища.
1. Перейти до **вирішення**
1. Видаліть або видаліть рішення з назвою **Dynamics 365 Customer Insights Надбудова картки клієнта (Попередній перегляд)**.

АБО

1. Відкрийте своє Dataverse середовище.
1. Перейдіть до розділу **Додаткові рішення для** > **налаштування**.
1. **Видаліть рішення CustomerInsightsCustomerCard**.

Якщо видалення з'єднання не вдається через залежності, потрібно також видалити залежності. Для отримання додаткових [відомостей див](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Вихідні сутності

Деякі вихідні сутності зі статистики клієнтів доступні як таблиці в Dataverse програмі. У розділах нижче описано очікувану схему таких таблиць.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Збагачення](#enrichment)
- [Прогноз](#prediction)
- [Членство в сегменті](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Ця таблиця містить уніфікований профіль клієнта з Customer Insights. Схема для уніфікованого профілю клієнта залежить від сутностей і атрибутів, які використовуються в процесі об'єднання даних. Схема профілю клієнта зазвичай містить підмножину атрибутів із [визначення CustomerProfile в Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

У таблиці AlternateKey містяться ключі сутностей, які брали участь в процесі уніфікації.

|Column  |Ввести  |Опис  |
|---------|---------|---------|
|DataSourceName    |String         | Ім'я джерела даних. Наприклад: `datasource5`        |
|EntityName        | String        | Ім'я сутності в Службі статистики клієнтів. Наприклад: `contact1`        |
|AlternateValue    |String         |Альтернативний ідентифікатор, зіставлений з ідентифікатором клієнта. Приклад: `cntid_1078`         |
|KeyRing           | Багаторядковий текст        | Значення JSON  </br> Зразок: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|Ідентифікатор клієнта         | String        | Ідентифікатор уніфікованого профілю клієнта.         |
|AlternateKeyId     | GUID         |  Визначальний ідентифікатор GUID AlternateKey на основі msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Зразок: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Ця таблиця містить справи різних користувачів, доступних в Customer Insights.

| Column            | Ввести        | Опис                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| Ідентифікатор клієнта        | String      | Ідентифікатор профілю клієнта                                                                      |
| ActivityId        | String      | Внутрішній ідентифікатор справи клієнта (первинний ключ)                                       |
| SourceEntityName  | String      | Ім'я сутності-джерела                                                                |
| SourceActivityId  | String      | Первинний ключ із сутності-джерела                                                       |
| ActivityType      | String      | Семантичний тип справи або ім'я користувацької справи                                        |
| ActivityTimeStamp | DATETIME    | Позначка часу справи                                                                      |
| Посада             | String      | Назва або ім’я справи                                                               |
| Опис       | String      | Опис справи                                                                     |
| URL-адреса               | String      | Посилання на зовнішню URL-адресу, унікальну для цієї справи                                         |
| SemanticData      | Рядок JSON | Містить список пар ключ-значення для семантичного зіставлення полів, характерних для типу справи |
| RangeIndex        | String      | Позначка часу Unix, яка використовується для сортування часової шкали справ та запитів ефективного діапазону |
| mydynci_unifiedactivityid   | GUID | Внутрішній ідентифікатор справи клієнта (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

У цій таблиці містяться вихідні дані про показники, що залежать від атрибутів клієнта.

| Column             | Ввести             | Опис                 |
|--------------------|------------------|-----------------------------|
| Ідентифікатор клієнта         | String           | Ідентифікатор профілю клієнта        |
| Показники           | Рядок JSON      | Містить список пар ключ-значення із іменами показників та значеннями для певного клієнта | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Ідентифікатор профілю клієнта |


### <a name="enrichment"></a>Збагачення

У цій таблиці містяться результати процесу збагачення.

| Column               | Ввести             |  Опис                                          |
|----------------------|------------------|------------------------------------------------------|
| Ідентифікатор клієнта           | String           | Ідентифікатор профілю клієнта                                 |
| EnrichmentProvider   | String           | Ім’я постачальника збагачення                                  |
| EnrichmentType       | String           | Тип збагачення                                      |
| Значення               | Рядок JSON      | Список атрибутів, створених під час процесу збагачення |
| msdynci_enrichmentid | GUID             | Визначальний ідентифікатор GUID, створений на основі msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Прогноз

У цій таблиці містяться результати прогнозів моделі.

| Column               | Ввести        | Опис                                          |
|----------------------|-------------|------------------------------------------------------|
| Ідентифікатор клієнта           | String      | Ідентифікатор профілю клієнта                                  |
| ModelProvider        | String      | Ім’я постачальника моделі                                      |
| Модель                | String      | Ім’я моделі                                                |
| Значення               | Рядок JSON | Список атрибутів, створених моделлю |
| msdynci_predictionid | GUID        | Визначальний ідентифікатор GUID, створений на основі msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Членство в сегменті

Ця таблиця містить відомості про членство в сегменті профілів клієнтів.

| Column        | Ввести | Опис                        |
|--------------------|--------------|-----------------------------|
| Ідентифікатор клієнта        | String       | Ідентифікатор профілю клієнта        |
| SegmentProvider      | String       | Додаток, який публікує сегменти.      |
| Тип перетину сегмента | String       | Тип клієнта цього запису членства в сегменті. Підтримує кілька типів, таких як клієнт, контакт або бізнес-партнер. Типове значення: Клієнт  |
| Сегменти       | Рядок JSON  | Список унікальних сегментів профілю клієнта є членом      |
| msdynci_identifier  | String   | Унікальний ідентифікатор запису членства в сегменті. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детермінований GUID, створений з`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
