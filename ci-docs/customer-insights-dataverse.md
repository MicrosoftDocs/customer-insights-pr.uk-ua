---
title: Робота із даними Customer Insights у Microsoft Dataverse
description: Дізнайтеся, як підключити Customer Insights і Microsoft Dataverse зрозуміти вихідні об'єкти, які експортуються в Dataverse.
ms.date: 07/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 89ff629033230de3c6252b6a3a16816d9b3c1287
ms.sourcegitcommit: 85b198de71ff2916fee5500ed7c37c823c889bbb
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/15/2022
ms.locfileid: "9153429"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Робота із даними Customer Insights у Microsoft Dataverse

Customer Insights надає можливість зробити вихідні об'єкти доступними як [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ця інтеграція забезпечує легкий обмін даними та індивідуальну розробку за допомогою підходу з низьким кодом /без коду. Вихідні [сутності](#output-entities) доступні у вигляді таблиць у середовищі Dataverse. Ви можете використовувати дані для будь-якого іншого додатка на Dataverse основі таблиць. Ці таблиці вмикають такі сценарії, як автоматизовані робочі процеси через Power Automate або створення програм за допомогою Power Apps.

Підключення до середовища Dataverse також дає змогу [отримувати дані з локальний джерел даних за допомогою Power Platform потоків даних і шлюзів](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>вимоги

- Статистику клієнтів і Dataverse середовища потрібно розміщувати в одному регіоні.
- Ви повинні мати глобальну роль адміністратора в навколишньому Dataverse середовищі. Перевірте, чи пов'язано це [Dataverse середовище з](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) певними групами безпеки, і переконайтеся, що вас додано до цих груп безпеки.
- Жодне інше середовище Customer Insights вже не пов'язане з середовищем, Dataverse яке ви хочете підключити. Дізнайтеся, як [видалити наявне підключення до Dataverse середовища](#remove-an-existing-connection-to-a-dataverse-environment).
- Середовище Microsoft Dataverse може підключатися лише до одного облікового запису сховища. Це застосовується лише в тому випадку, якщо ви налаштували середовище для [використання вашого Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse право на ємність сховища

Передплата Customer Insights дає право на додаткові можливості для наявного [Dataverse обсягу](/power-platform/admin/capacity-storage) сховища вашої організації. Додаткова ємність залежить від кількості профілів, які використовує ваша підписка.

**Приклад:**

Припускаючи, що ви отримуєте 15 ГБ пам'яті бази даних і 20 ГБ файлової пам'яті на 100 000 профілів клієнтів. Якщо ваша передплата включає 300 000 профілів клієнтів, загальний обсяг пам'яті становитиме 45 ГБ (3 x 15 ГБ) пам'яті бази даних і 60 ГБ пам'яті (3 x 20 ГБ). Аналогічно, якщо у вас є підписка на B2B з обліковими записами 30K, ваш загальний обсяг пам'яті становитиме 45 ГБ (3 x 15 ГБ) пам'яті бази даних і 60 ГБ файлової пам'яті (3 x 20 ГБ).

Лог-ємність не є додатковою та фіксованою для вашої організації.

Докладні відомості про докладні права на пропускну здатність наведено в [Посібнику з](https://go.microsoft.com/fwlink/?LinkId=866544) ліцензування Dynamics 365.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Dataverse Підключення середовища до Customer Insights

Цей **Microsoft Dataverse** крок дозволяє зв'язати Customer Insights зі своїм Dataverse середовищем, створюючи [середовище](create-environment.md) Customer Insights.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="обмін даними з Microsoft Dataverse автоматичним увімкненням для нових мережевих середовищ.":::

Адміністратори можуть настроїти Customer Insights для підключення наявного Dataverse середовища. Надаючи URL-адресу навколишньому середовищу Dataverse, він підключається до свого нового середовища Customer Insights. Після встановлення зв'язку між Customer Insights і Dataverse, не змінюйте назву організації для навколишнього Dataverse середовища. Назва організації використовується в URL-адресі Dataverse, а змінене ім'я розриває зв'язок із Customer Insights.

Якщо ви не хочете використовувати наявне Dataverse середовище, система створює нове середовище для даних Customer Insights у вашому клієнті. [Power Platform адміністратори можуть контролювати, хто може створювати середовища](/power-platform/admin/control-environment-creation). Якщо ви настроюєте нове середовище Customer Insights, а адміністратор вимкнув Dataverse створення середовищ для всіх, крім адміністраторів, можливо, ви не зможете створити нове середовище.

**Увімкніть спільний доступ до** Dataverse даних, установивши прапорець Для обміну даними.

Якщо ви використовуєте власний обліковий запис сховища Data Lake Storage, вам також потрібен **ідентифікатор дозволів**. Щоб отримати ідентифікатор дозволу, перегляньте наведений нижче розділ.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Увімкнення спільного доступу до даних із Dataverse власного Azure Data Lake Storage (Попередній перегляд)

Увімкнення обміну даними, Microsoft Dataverse коли ваше середовище [використовує ваш власний Azure Data Lake Storage обліковий запис](own-data-lake-storage.md), потребує додаткової конфігурації. Користувач, який настроює середовище Customer Insights, повинен мати принаймні **дозволи зчитувача** даних BLOB-даних сховища для *контейнера CustomerInsights* в обліковому записі Azure Data Lake Storage.

1. Створіть дві групи безпеки за передплатою Azure – одну **групу безпеки Reader** і одну **групу безпеки співавтора** та встановіть Microsoft Dataverse службу як власника для обох груп безпеки.
2. За допомогою цих груп безпеки керуйте списком контролю доступу (ACL) у контейнері CustomerInsights у своєму обліковому записі сховища. Додайте службу Microsoft Dataverse та будь-які Dataverse бізнес-програми на основі, як-от Dynamics 365 Marketing, до **групи безпеки Reader** з **дозволами лише для** читання. Додайте *лише* програму Customer Insights до **групи безпеки співавторів,** щоб надавати дозволи на **читання та записування** профілів та аналітичних даних.

### <a name="limitations"></a>Обмеження

Є два обмеження при використанні Dataverse з власним обліковим Azure Data Lake Storage записом:

- Існує індивідуальне зіставлення між організацією Dataverse та обліковим записом Azure Data Lake Storage. Dataverse Після підключення організації до облікового запису сховища вона не може підключитися до іншого облікового запису сховища. Це обмеження запобігає тому, що a Dataverse не заповнює кілька облікових записів сховища.
- Обмін даними не працюватиме, якщо для доступу до вашого Azure Data Lake Storage облікового запису знадобиться настройка Azure Private Link, оскільки вона знаходиться за брандмауером. Dataverse в даний час не підтримує з'єднання з приватними кінцевими точками через Private Link.

### <a name="set-up-powershell"></a>Настроювання powershell

Щоб виконати сценарії PowerShell, спочатку потрібно відповідно налаштувати PowerShell.

1. Встановіть останню версію [Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/install-adv2).
   1. На комп'ютері натисніть клавішу Windows на клавіатурі, знайдіть **Windows PowerShell** і виберіть **Запуск від імені адміністратора**.
   1. У вікні PowerShell, що відкриється, введіть `Install-Module AzureAD`.
2. Імпортуйте три модулі.
    1. У вікні PowerShell введіть `Install-Module -Name Az.Accounts` і виконайте вказівки.
    1. Повторіть для `Install-Module -Name Az.Resources` і `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Кроки з налаштування

1. Завантажте два сценарії PowerShell, які вам потрібно запустити, з репо [GitHub нашого інженера](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Щоб запустити цей сценарій PowerShell, потрібні *дозволи адміністратора* клієнта.
       - Цей сценарій PowerShell створює дві групи безпеки у вашій передплаті Azure. Один для групи Reader, а інший для групи співавторів і стане Microsoft Dataverse власником обох цих груп безпеки.
       - Виконайте цей сценарій PowerShell у Windows PowerShell, надавши ідентифікатор передплати Azure, який містить ваш Azure Data Lake Storage. Відкрийте скрипт PowerShell в редакторі, щоб переглянути додаткову інформацію і реалізовану логіку.
       - Збережіть обидва значення ідентифікатора групи безпеки, створені цим сценарієм, оскільки ми будемо використовувати їх у `ByolSetup.ps1` сценарії.

        > [!NOTE]
        > У клієнті можна вимкнути створення групи безпеки. У цьому випадку знадобиться ручне налаштування, і ваш Azure AD адміністратор повинен [буде ввімкнути створення групи безпеки](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Для запуску цього сценарію вам потрібні *дозволи власника* даних BLOB сховища на рівні облікового запису/контейнера сховища, інакше цей сценарій створить його для вас. Призначення ролей можна видалити вручну після успішного запуску сценарію.
        - Цей сценарій PowerShell додає необхідний рольовий контроль доступу для Microsoft Dataverse служби та будь-яких Dataverse бізнес-програм на основі. Він також оновлює список контролю доступу (ACL) у контейнері CustomerInsights для груп безпеки, створених за допомогою сценарію `CreateSecurityGroups.ps1`. Група співавторів матиме *дозвіл rwx,* а група читачів матиме *лише дозвіл r-x*.
        - Виконайте цей сценарій PowerShell у Windows PowerShell, надавши ідентифікатор передплати Azure, який міститиме Azure Data Lake Storage ім'я облікового запису сховища, ім'я групи ресурсів, а також значення ідентифікатора групи безпеки переглядача та співавтора. Відкрийте скрипт PowerShell в редакторі, щоб переглянути додаткову інформацію і реалізовану логіку.
        - Скопіюйте рядок виводу після успішного запуску сценарію. Рядок виводу виглядає так: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Введіть скопійований зверху рядок виводу **в поле Ідентифікатор** дозволів кроку конфігурації середовища для Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Параметри конфігурації для можливості обміну даними з вашого власного Azure Data Lake Storage за допомогою Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Видалення наявного підключення до Dataverse середовища

Під час Dataverse підключення до середовища повідомлення **про помилку Ця організація CDS уже додається до іншого екземпляра** Customer Insights означає, що Dataverse середовище вже використовується в середовищі Customer Insights. Можна видалити наявне підключення від імені глобального адміністратора в середовищі Dataverse. Заповнення змін може зайняти пару годин.

1. Перейти до [Power Apps](https://make.powerapps.com).
1. Виберіть середовище з засобу вибору середовища.
1. Перейти до **рішень**
1. Видаліть або видаліть рішення з іменем **Dynamics 365 Customer Insights «Додаткова версія картки клієнта» (Попередній перегляд).**.

АБО

1. Відкрийте своє Dataverse оточення.
1. Перейдіть до **додаткових рішень налаштувань** > **·**.
1. **Видаліть рішення CustomerInsightsCustomerCard**.

Якщо видалення підключення не вдається через залежності, потрібно також видалити залежності. Для отримання додаткової інформації дивіться [Видалення залежностей](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Вихідні сутності

Деякі вихідні об'єкти з Customer Insights доступні у вигляді таблиць у Dataverse. У розділах нижче описано очікувану схему таких таблиць.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Збагачення](#enrichment)
- [Прогноз](#prediction)
- [Членство в сегменті](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Ця таблиця містить уніфікований профіль клієнта з Customer Insights. Схема для уніфікованого профілю клієнта залежить від сутностей та атрибутів, що використовуються в процесі уніфікації даних. Схема профілю клієнта зазвичай містить підмножину атрибутів із [визначення CustomerProfile в Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

У таблиці AlternateKey містяться ключі сутностей, які брали участь в процесі уніфікації.

|Column  |Ввести  |Опис  |
|---------|---------|---------|
|DataSourceName    |String         | Ім'я джерела даних. Наприклад: `datasource5`        |
|EntityName        | String        | Назва юридичної особи в Customer Insights. Наприклад: `contact1`        |
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

Ця таблиця містить інформацію про членство в сегментах профілів клієнтів.

| Column        | Ввести | Опис                        |
|--------------------|--------------|-----------------------------|
| Ідентифікатор клієнта        | String       | Ідентифікатор профілю клієнта        |
| СегментПровидер      | String       | Додаток, який публікує сегменти.      |
| СегментЧленствоТип | String       | Тип клієнта в цьому сегменті запису про членство. Підтримує кілька типів, таких як Клієнт, Контакт або Обліковий запис. За замовчуванням: клієнт  |
| Сегменти       | Рядок JSON  | Список унікальних сегментів, учасниками яких є профіль клієнта      |
| msdynci_identifier  | String   | Унікальний ідентифікатор запису про членство в сегменті. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детермінований GUID, створений на основі`msdynci_identifier`          |

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
