---
title: Робота із даними Customer Insights у Microsoft Dataverse
description: Дізнайтеся, як підключити Customer Insights та Microsoft Dataverse зрозуміти сутності виводу, які експортуються до Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671276"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Робота із даними Customer Insights у Microsoft Dataverse

Customer Insights дозволяє зробити вихідні сутності доступними в [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ця інтеграція забезпечує легкий обмін даними та спеціальну розробку за допомогою підходу з низьким кодом/відсутністю коду. Вихідні [сутності](#output-entities) доступні у вигляді таблиць у Dataverse середовищі. Ви можете використовувати дані для будь-якого іншого додатка на основі Dataverse таблиць. Ці таблиці вмикають такі сценарії, як автоматизовані робочі процеси або Power Automate створення програм за допомогою Power Apps.

Підключення до середовища Dataverse також дозволяє [отримувати дані з локальний джерел даних за допомогою Power Platform потоків даних і шлюзів](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>вимоги

- Інформація про клієнтів і Dataverse середовища повинні розміщуватися в одному регіоні.
- Роль глобального адміністратора, настроєна Dataverse в середовищі. Перевірте, чи пов’язане [Dataverse це](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) середовище з певними групами безпеки, і переконайтеся, що вас додано до цих груп безпеки.
- Жодне інше середовище Customer Insights вже не пов’язане з середовищем, яке Dataverse ви хочете підключити. Дізнайтеся, [як видалити наявне підключення до Dataverse середовища](#remove-an-existing-connection-to-a-dataverse-environment).
- Середовище, підключене Microsoft Dataverse до одного облікового запису сховища, якщо ви налаштували середовище на [використання вашого Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse право на зберігання ємності

Передплата на Customer Insights дає право на додаткову ємність наявного [Dataverse сховища](/power-platform/admin/capacity-storage) вашої організації. Додана ємність залежить від кількості профілів, які використовує ваша підписка.

**Приклад:**

Якщо припустити, що ви отримаєте 15 ГБ пам’яті бази даних і 20 ГБ пам’яті на 100 000 профілів клієнтів. Якщо ваша передплата включає 300 000 профілів клієнтів, загальний обсяг сховища становить 45 ГБ (3 x 15 ГБ) сховища бази даних і 60 ГБ простору в сховищі файлів (3 x 20 ГБ). Аналогічно, якщо у вас є підписка B-to-B з обліковими записами 30K, загальний обсяг пам’яті становить 45 ГБ (3 x 15 ГБ) сховища бази даних і 60 ГБ пам’яті файлів (3 x 20 ГБ).

Пропускна здатність журналу не є інкрементною та фіксованою для вашої організації.

Докладнішу інформацію про права на пропускну здатність можна знайти в [Посібнику](https://go.microsoft.com/fwlink/?LinkId=866544) з ліцензування Dynamics 365.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Підключення Dataverse середовища до Customer Insights

Цей **Microsoft Dataverse** крок дозволяє пов’язати Customer Insights зі своїм Dataverse середовищем [, створюючи середовище](create-environment.md) Customer Insights.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="обмін даними з Microsoft Dataverse автоматичним увімкненням для нових середовищ.":::

1. Надайте URL-адресу своєму Dataverse середовищу або залиште пустою, щоб її було створено для вас.

   > [!NOTE]
   > Встановивши зв’язок між Customer Insights і Dataverse, не змінюйте назву організації для Dataverse середовища. Назва організації використовується в URL-адресі Dataverse, а змінена назва розриває зв’язок із Customer Insights.

   [Power Platform Адміністратори можуть контролювати, хто може створювати нове Dataverse середовище](/power-platform/admin/control-environment-creation). Якщо ви намагаєтеся налаштувати нове середовище Customer Insights, але не можете цього зробити, можливо, адміністратор вимкнув створення Dataverse середовищ для всіх, крім адміністраторів.

1. Якщо ви використовуєте власний обліковий запис Data Lake Storage:
   1. Виберіть **Увімкнути спільний доступ** до даних за допомогою Dataverse.
   1. Введіть **ідентифікатор дозволів**. Щоб отримати ідентифікатор дозволу, [увімкніть спільний доступ до Dataverse даних із власного Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Увімкнення спільного доступу до даних із Dataverse власного Azure Data Lake Storage (попередній перегляд)

У [власному Azure Data Lake Storage обліковому записі переконайтеся, що користувач, який налаштовує середовище Customer Insights, має принаймні](own-data-lake-storage.md) дозволи зчитувача даних Blob-сховища **на контейнері в обліковому** записі сховища `customerinsights`.

> [!NOTE]
> Обмін даними застосовується лише в тому випадку, якщо ви використовуєте власний Azure Data Lake Storage обліковий запис. Цей параметр недоступний, якщо в середовищі Customer Insights використовується сховище за замовчуванням Dataverse.

### <a name="limitations"></a>Обмеження

- Лише відображення один на один між Dataverse організацією та обліковим записом Azure Data Lake Storage. Dataverse Підключивши організацію до облікового запису сховища, вона не зможе підключитися до іншого облікового запису сховища. Це обмеження запобігає Dataverse заповненню кількох облікових записів сховища.
- Обмін даними не працюватиме, якщо для доступу до вашого Azure Data Lake Storage облікового запису потрібне налаштування Azure Private Link, оскільки він знаходиться за брандмауером. Dataverse наразі не підтримує підключення до приватних кінцевих точок через Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Самостійне настроювання груп безпеки Azure Data Lake Storage

1. Створіть дві групи безпеки у своїй передплаті Azure – одну групу безпеки Reader **і одну** **групу безпеки постачальника** та встановіть Microsoft Dataverse службу як власника для обох груп безпеки.

1. Керуйте списком контролю доступу (ACL) на контейнері в обліковому записі `customerinsights` сховища за допомогою цих груп безпеки.
   1. Microsoft Dataverse Додайте службу та будь-які Dataverse бізнес-програми, такі як Dynamics 365 Marketing, **до групи безпеки Reader** із **дозволами лише** для читання.
   1. Додайте *лише додаток Customer Insights до групи безпеки постачальників* **, щоб надавати дозволи** на **читання та запис** для написання профілів та аналітичних даних.

### <a name="set-up-powershell"></a>Настроювання оболонки PowerShell

Налаштуйте PowerShell для виконання сценаріїв PowerShell.

1. Інсталюйте останню версію [Azure Active Directory PowerShell для графіка](/powershell/azure/active-directory/install-adv2).
   1. На комп'ютері натисніть клавішу Windows на клавіатурі, знайдіть **Windows PowerShell** і виберіть **Запуск від імені адміністратора**.
   1. У вікні PowerShell, що відкриється, введіть `Install-Module AzureAD`.

1. Імпортуйте три модулі.
   1. У вікні PowerShell введіть `Install-Module -Name Az.Accounts` і дотримуйтеся вказівок.
   1. Повторіть для `Install-Module -Name Az.Resources` і `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Виконайте сценарії PowerShell та отримайте ідентифікатор дозволів

1. Завантажте два сценарії PowerShell, які вам потрібно запустити, з репозиторію [GitHub нашого інженера](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Потрібні дозволи адміністратора клієнта.
   - `ByolSetup.ps1`: Потрібні дозволи власника даних Storage Blob на рівні облікового запису/контейнера зберігання. Цей сценарій створить дозвіл для вас. Призначення ролей можна видалити вручну після успішного запуску сценарію.

1. Виконайте `CreateSecurityGroups.ps1` в оболонці Windows PowerShell, надавши ідентифікатор передплати Azure, який містить ваш Azure Data Lake Storage. Відкрийте скрипт PowerShell в редакторі, щоб переглянути додаткову інформацію і реалізовану логіку.

   Цей сценарій створює дві групи безпеки у вашій підписці Azure: одну для групи Reader, а іншу для групи співавторів. Microsoft Dataverse сервіс є власником обох цих груп безпеки.

1. Збережіть обидва значення ідентифікатора групи безпеки, створені цим сценарієм, для використання в `ByolSetup.ps1` сценарії.

   > [!NOTE]
   > Створення групи безпеки може бути відключено для вашого клієнта. У цьому випадку знадобиться ручне налаштування, і ваш Azure AD адміністратор повинен буде [ввімкнути створення групи безпеки](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Виконайте `ByolSetup.ps1` в оболонці Windows PowerShell, надавши ідентифікатор передплати Azure, який містить ім’я вашого облікового запису сховища, ім’я Azure Data Lake Storage групи ресурсів, а також значення ідентифікатора групи безпеки Reader і Contributor. Відкрийте скрипт PowerShell в редакторі, щоб переглянути додаткову інформацію і реалізовану логіку.

   Цей сценарій додає необхідний рольовий контроль доступу для Microsoft Dataverse служби та будь-яких Dataverse бізнес-додатків. Він також оновлює список контролю доступу (ACL) на контейнері `customerinsights` для груп безпеки, створених за допомогою `CreateSecurityGroups.ps1` сценарію. Групі співавторів надається дозвіл rwx, а групі читачів надається *лише* дозвіл r-x *.*

1. Скопіюйте рядок виводу, який має такий вигляд: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Введіть скопійований рядок виводу в **поле Ідентифікатор** дозволів на кроці конфігурації середовища для Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Параметри конфігурації для забезпечення обміну даними з власного Azure Data Lake Storage за допомогою Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Видалення наявного підключення до Dataverse середовища

Під час підключення до середовища повідомлення Dataverse про помилку Ця організація CDS уже прикріплена до **іншого екземпляра** Customer Insights означає, що Dataverse середовище вже використовується в середовищі Customer Insights. Ви можете видалити наявне підключення як глобальний адміністратор у Dataverse середовищі. На заповнення змін може піти пара годин.

1. Перейти до [Power Apps](https://make.powerapps.com).
1. Виберіть середовище з засобу вибору середовища.
1. Перейдіть до **розділу Рішення**.
1. Видаліть або видаліть рішення з іменем **Dynamics 365 Customer Insights Надбудова картки клієнта (Preview)**.

АБО

1. Відкрийте своє Dataverse оточення.
1. Перейдіть до **додаткових налаштувань** > **рішень**.
1. Видаліть **рішення CustomerInsightsCustomerCard**.

Якщо видалення з’єднання не вдається через залежності, потрібно видалити і залежності. Для отримання додаткових відомостей дивіться [Видалення залежностей](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Вихідні сутності

Деякі вихідні сутності з Customer Insights доступні у вигляді таблиць у Dataverse. У розділах нижче описано очікувану схему таких таблиць.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Збагачення](#enrichment)
- [Прогноз](#prediction)
- [Членство в сегменті](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Ця таблиця містить уніфікований профіль клієнта з Customer Insights. Схема єдиного профілю клієнта залежить від сутностей і атрибутів, що використовуються в процесі уніфікації даних. Схема профілю клієнта зазвичай містить підмножину атрибутів із [визначення CustomerProfile в Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Для сценарію B-to-B профіль клієнта містить уніфіковані облікові записи, а схема зазвичай містить підмножину атрибутів з [визначення Загальної моделі даних облікового запису](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

КонтактПрофіль містить уніфіковані відомості про контакт. Контакти – це [особи, які зіставлені з обліковим записом](data-unification-contacts.md) у сценарії B-to-B.

| Column                       | Ввести                | Опис     |
| ---------------------------- | ------------------- | --------------- |
|  Дата народження            | DateTime       |  Дата народження контакту               |
|  Місто                 | SMS |  Місто контактної адреси               |
|  Контактний ідентифікатор            | SMS |  Ідентифікатор профілю контакту               |
|  КонтактПрофільІд     | Унікальний ідентифікатор   |  Ідентифікатор GUID для контакту               |
|  КраїнаАбо Регіон      | SMS |  Країна/регіон контактної адреси               |
|  Ідентифікатор клієнта           | SMS |  ідентифікатор облікового запису, з яким зіставлено контакт               |
|  EntityName           | SMS |  Сутність, з якої походять дані                |
|  FirstName            | SMS |  ім’я контакту               |
|  Стать               | SMS |  Стать контакту               |
|  Ідентифікатор                   | SMS |  Детермінований GUID на основі`Identifier`               |
|  Identifier           | SMS |  Внутрішній ідентифікатор профілю контакту: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | SMS |  Посада контакту               |
|  LastName             | SMS |  прізвище контакту               |
|  PostalCode           | SMS |  ПОШТОВИЙ індекс контактної адреси               |
|  Первинна електронна пошта         | SMS |  Адреса електронної пошти контакту               |
|  Основний телефон         | SMS |  Телефон контактної особи               |
|  Область або республіка      | SMS |  Адреса контактної адреси штату або провінції               |
|  Адреса-стріт        | SMS |  Вулиця контактної адреси               |

### <a name="alternatekey"></a>AlternateKey

У таблиці AlternateKey містяться ключі сутностей, які брали участь в процесі уніфікації.

|Column  |Ввести  |Опис  |
|---------|---------|---------|
|DataSourceName    |SMS         | Ім'я джерела даних. Наприклад: `datasource5`        |
|EntityName        | SMS        | Назва юридичної особи в Customer Insights. Наприклад: `contact1`        |
|AlternateValue    |SMS         |Альтернативний ідентифікатор, зіставлений з ідентифікатором клієнта. Приклад: `cntid_1078`         |
|KeyRing           | SMS        | Значення JSON  </br> Зразок: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|Ідентифікатор клієнта         | SMS        | Ідентифікатор уніфікованого профілю клієнта.         |
|AlternateKeyId     | Унікальний ідентифікатор        |  Детермінований GUID AlternateKey на основі`Identifier`      |
|Identifier |   SMS      |   `DataSourceName|EntityName|AlternateValue`  </br> Зразок: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Ця таблиця містить справи різних користувачів, доступних в Customer Insights.

| Column            | Ввести        | Опис                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| Ідентифікатор клієнта        | SMS      | Ідентифікатор профілю клієнта                                                                      |
| ActivityId        | SMS      | Внутрішній ідентифікатор справи клієнта (первинний ключ)                                       |
| SourceEntityName  | SMS      | Ім'я сутності-джерела                                                                |
| SourceActivityId  | SMS      | Первинний ключ із сутності-джерела                                                       |
| ActivityType      | SMS      | Семантичний тип справи або ім'я користувацької справи                                        |
| ActivityTimeStamp | DateTime    | Позначка часу діяльності                                                                      |
| Звання             | SMS      | Назва або ім’я справи                                                               |
| Опис       | SMS      | Опис справи                                                                     |
| URL-адреса               | SMS      | Посилання на зовнішню URL-адресу, унікальну для цієї справи                                         |
| SemanticData      | SMS | Містить список пар ключ-значення для семантичного зіставлення полів, характерних для типу справи |
| RangeIndex        | SMS      | Позначка часу Unix, яка використовується для сортування часової шкали справ та запитів ефективного діапазону |
| Ідентифікатор уніфікованої активності   | Унікальний ідентифікатор | Внутрішній ідентифікатор справи клієнта (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

У цій таблиці містяться вихідні дані про показники, що залежать від атрибутів клієнта.

| Column             | Ввести             | Опис                 |
|--------------------|------------------|-----------------------------|
| Ідентифікатор клієнта         | SMS           | Ідентифікатор профілю клієнта        |
| Вимірювання           | SMS      | Містить список пар ключ-значення із іменами показників та значеннями для певного клієнта |
| Identifier | SMS           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Унікальний ідентифікатор     | Ідентифікатор профілю клієнта |

### <a name="enrichment"></a>Збагачення

У цій таблиці містяться результати процесу збагачення.

| Column               | Ввести             |  Опис                                          |
|----------------------|------------------|------------------------------------------------------|
| Ідентифікатор клієнта           | SMS           | Ідентифікатор профілю клієнта                                 |
| EnrichmentProvider   | SMS           | Ім’я постачальника збагачення                                  |
| EnrichmentType       | SMS           | Тип збагачення                                      |
| Значення               | SMS      | Список атрибутів, створених під час процесу збагачення |
| Збагачення | Унікальний ідентифікатор            | Детермінований GUID, створений з`Identifier` |
| Identifier   | SMS           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Прогноз

У цій таблиці містяться результати прогнозів моделі.

| Column               | Ввести        | Опис                                          |
|----------------------|-------------|------------------------------------------------------|
| Ідентифікатор клієнта           | SMS      | Ідентифікатор профілю клієнта                                  |
| ModelProvider        | SMS      | Ім’я постачальника моделі                                      |
| Модель                | SMS      | Ім’я моделі                                                |
| Значення               | SMS | Список атрибутів, створених моделлю |
| ПрогнозуванняId | Унікальний ідентифікатор       | Детермінований GUID, створений з`Identifier` |
| Identifier   | SMS      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Членство в сегменті

Ця таблиця містить відомості про членство в сегментах профілів клієнтів.

| Column        | Ввести | Опис                        |
|--------------------|--------------|-----------------------------|
| Ідентифікатор клієнта        | SMS       | Ідентифікатор профілю клієнта        |
| СегментПровайдер      | SMS       | Програма, яка публікує сегменти.      |
| СегментТип членства | SMS       | Тип клієнта для запису про членство в цьому сегменті. Підтримує кілька типів, таких як Клієнт, Контакт або Обліковий запис. За замовчуванням: Клієнт  |
| Сегменти       | SMS  | Перелік унікальних сегментів, до складу яких входить профіль клієнта      |
| Identifier  | SMS   | Унікальний ідентифікатор запису про членство в сегменті. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Унікальний ідентифікатор      | Детермінований GUID, створений з`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
