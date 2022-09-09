---
title: Робота із даними Customer Insights у Microsoft Dataverse
description: Дізнайтеся, як підключити Customer Insights і Microsoft Dataverse зрозуміти вихідні об’єкти, які експортуються в Dataverse.
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
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424334"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Робота із даними Customer Insights у Microsoft Dataverse

Customer Insights дозволяє зробити вихідні сутності доступними в [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ця інтеграція забезпечує легкий обмін даними та індивідуальну розробку за допомогою підходу з низьким кодом /без коду. Вихідні [сутності](#output-entities) доступні у вигляді таблиць у середовищі Dataverse. Ви можете використовувати дані для будь-якого іншого додатка на Dataverse основі таблиць. Ці таблиці вмикають такі сценарії, як автоматизовані робочі процеси через Power Automate або створення програм за допомогою Power Apps.

Підключення до середовища Dataverse також дає змогу [отримувати дані з локальний джерел даних за допомогою Power Platform потоків даних і шлюзів](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>вимоги

- Статистику клієнтів і Dataverse середовища потрібно розміщувати в одному регіоні.
- Глобальна роль адміністратора, створена в навколишньому Dataverse середовищі. Перевірте, чи пов’язано це [Dataverse середовище з](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) певними групами безпеки, і переконайтеся, що вас додано до цих груп безпеки.
- Жодне інше середовище Customer Insights вже не пов’язане з середовищем, Dataverse яке ви хочете підключити. Дізнайтеся, як [видалити наявне підключення до Dataverse середовища](#remove-an-existing-connection-to-a-dataverse-environment).
- Середовище Microsoft Dataverse, підключене до одного облікового запису сховища, якщо ви налаштували середовище на [використання вашого Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse право на ємність сховища

Передплата Customer Insights дає право на додаткові можливості для наявного [Dataverse обсягу](/power-platform/admin/capacity-storage) сховища вашої організації. Додаткова ємність залежить від кількості профілів, які використовує ваша підписка.

**Приклад:**

Припускаючи, що ви отримуєте 15 ГБ пам’яті бази даних і 20 ГБ файлової пам’яті на 100 000 профілів клієнтів. Якщо ваша передплата включає 300 000 профілів клієнтів, загальний обсяг сховища становить 45 ГБ (3 x 15 ГБ) пам’яті бази даних і 60 ГБ простору для зберігання файлів (3 x 20 ГБ). Аналогічно, якщо у вас є підписка на B-to-B з обліковими записами 30K, загальний обсяг сховища становить 45 ГБ (3 x 15 ГБ) сховища бази даних і 60 ГБ пам’яті (3 x 20 ГБ).

Лог-ємність не є додатковою та фіксованою для вашої організації.

Докладні відомості про докладні права на пропускну здатність наведено в [Посібнику з](https://go.microsoft.com/fwlink/?LinkId=866544) ліцензування Dynamics 365.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Dataverse Підключення середовища до Customer Insights

Цей **Microsoft Dataverse** крок дозволяє зв’язати Customer Insights зі своїм Dataverse середовищем, створюючи [середовище](create-environment.md) Customer Insights.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="обмін даними з Microsoft Dataverse автоматичним увімкненням для нових середовищ.":::

1. Надайте URL-адресу своєму Dataverse середовищу або залиште порожньою, щоб вона була створена для вас.

   > [!NOTE]
   > Після встановлення зв’язку між Customer Insights і Dataverse, не змінюйте назву організації для навколишнього Dataverse середовища. Назва організації використовується в URL-адресі Dataverse, а змінене ім’я розриває зв’язок із Customer Insights.

   [Power Platform адміністратори можуть контролювати, хто може створювати нове Dataverse середовище](/power-platform/admin/control-environment-creation). Якщо ви намагаєтеся налаштувати нове середовище Customer Insights, але не можете, можливо, адміністратор вимкнув створення Dataverse середовища для всіх, крім адміністраторів.

1. Якщо ви використовуєте власний обліковий запис Data Lake Storage:
   1. Виберіть **Увімкнути спільний доступ до** даних за допомогою Dataverse.
   1. **Введіть ідентифікатор дозволів**. Щоб отримати ідентифікатор дозволу, [увімкніть спільний доступ до даних зі Dataverse свого власного Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Увімкнення спільного доступу до даних за допомогою Dataverse власного Azure Data Lake Storage (попередній перегляд)

У [власному Azure Data Lake Storage обліковому записі](own-data-lake-storage.md) переконайтеся, що користувач, який настроює середовище Customer Insights, має принаймні **дозволи зчитувача** даних BLOB-сховища на `customerinsights` контейнері в обліковому записі сховища.

### <a name="limitations"></a>Обмеження

- Лише індивідуальне зіставлення між організацією Dataverse та обліковим записом Azure Data Lake Storage. Dataverse Після підключення організації до облікового запису сховища вона не може підключитися до іншого облікового запису сховища. Це обмеження запобігає Dataverse заповненню кількох облікових записів сховища.
- Обмін даними не працюватиме, якщо для доступу до вашого Azure Data Lake Storage облікового запису знадобиться настройка Azure Private Link, оскільки вона знаходиться за брандмауером. Dataverse в даний час не підтримує з’єднання з приватними кінцевими точками через Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Самостійне настроювання груп безпеки Azure Data Lake Storage

1. Створіть дві групи безпеки за передплатою Azure – одну **групу безпеки Reader** і одну **групу безпеки співавтора** та встановіть Microsoft Dataverse службу як власника для обох груп безпеки.

1. Керуйте списком контролю доступу (ACL) на `customerinsights` контейнері в обліковому записі сховища за допомогою цих груп безпеки.
   1. Додайте службу Microsoft Dataverse та будь-які Dataverse бізнес-програми на основі, як-от Dynamics 365 Marketing, до **групи безпеки Reader** з **дозволами лише для** читання.
   1. Додайте *лише* програму Customer Insights до **групи безпеки співавторів,** щоб надавати дозволи на **читання та записування** профілів та аналітичних даних.

### <a name="set-up-powershell"></a>Настроювання powershell

Налаштуйте PowerShell для виконання сценаріїв PowerShell.

1. Встановіть останню версію [Azure Active Directory PowerShell для Graph](/powershell/azure/active-directory/install-adv2).
   1. На комп'ютері натисніть клавішу Windows на клавіатурі, знайдіть **Windows PowerShell** і виберіть **Запуск від імені адміністратора**.
   1. У вікні PowerShell, що відкриється, введіть `Install-Module AzureAD`.

1. Імпортуйте три модулі.
   1. У вікні PowerShell введіть `Install-Module -Name Az.Accounts` і виконайте вказівки.
   1. Повторіть для `Install-Module -Name Az.Resources` і `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Виконуйте сценарії PowerShell та отримуйте ідентифікатор дозволів

1. Завантажте два сценарії PowerShell, які вам потрібно запустити, з репо [GitHub нашого інженера](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Потрібні дозволи адміністратора клієнта.
   - `ByolSetup.ps1`: Потрібні дозволи власника даних BLOB сховища на рівні облікового запису/контейнера сховища. Цей сценарій створить для вас дозвіл. Призначення ролей можна видалити вручну після успішного запуску сценарію.

1. Виконайте `CreateSecurityGroups.ps1` в Windows PowerShell, надавши ідентифікатор передплати Azure, що містить ваш Azure Data Lake Storage. Відкрийте скрипт PowerShell в редакторі, щоб переглянути додаткову інформацію і реалізовану логіку.

   За допомогою цього сценарію буде створено дві групи безпеки в передплаті Azure: одна для групи Reader, а інша для групи співавторів. Microsoft Dataverse сервіс є власником для обох цих груп безпеки.

1. Збережіть обидва значення ідентифікатора групи безпеки, створені цим сценарієм, для використання в `ByolSetup.ps1` сценарії.

   > [!NOTE]
   > У клієнті можна вимкнути створення групи безпеки. У цьому випадку знадобиться ручне налаштування, і ваш Azure AD адміністратор повинен [буде ввімкнути створення](/azure/active-directory/enterprise-users/groups-self-service-management) групи безпеки.

1. Виконайте `ByolSetup.ps1` у Windows PowerShell, надавши ідентифікатор передплати Azure, який містить Azure Data Lake Storage ім’я облікового запису сховища, ім’я групи ресурсів, а також значення ідентифікатора групи безпеки переглядача та співавтора. Відкрийте скрипт PowerShell в редакторі, щоб переглянути додаткову інформацію і реалізовану логіку.

   Цей сценарій додає необхідний рольовий контроль доступу для Microsoft Dataverse служби та будь-яких Dataverse бізнес-додатків. Він також оновлює список контролю доступу (ACL) у контейнері `customerinsights` для груп безпеки, створених за допомогою сценарію `CreateSecurityGroups.ps1`. Групі співавторів надається *дозвіл rwx,* а групі читачів надається *лише дозвіл r-x*.

1. Скопіюйте рядок виводу, який виглядає так: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Введіть скопійований рядок виводу **в поле Ідентифікатор дозволів** кроку конфігурації середовища для Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Параметри конфігурації для можливості обміну даними з вашого власного Azure Data Lake Storage за допомогою Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Видалення наявного підключення до Dataverse середовища

Під час Dataverse підключення до середовища повідомлення **про помилку Ця організація CDS уже додається до іншого екземпляра** Customer Insights означає, що Dataverse середовище вже використовується в середовищі Customer Insights. Можна видалити наявне підключення від імені глобального адміністратора в середовищі Dataverse. Заповнення змін може зайняти пару годин.

1. Перейти до [Power Apps](https://make.powerapps.com).
1. Виберіть середовище з засобу вибору середовища.
1. Перейдіть до розділу **Рішення**.
1. Видаліть або видаліть рішення з іменем **Dynamics 365 Customer Insights «Додаткова версія картки клієнта» (Попередній перегляд).**.

АБО

1. Відкрийте своє Dataverse оточення.
1. Перейдіть до **додаткових рішень налаштувань** > **·**.
1. **Видаліть рішення CustomerInsightsCustomerCard**.

Якщо видалення підключення не вдається через залежності, потрібно також видалити залежності. Для отримання додаткової інформації дивіться [Видалення залежностей](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Вихідні сутності

Деякі вихідні об’єкти з Customer Insights доступні у вигляді таблиць у Dataverse. У розділах нижче описано очікувану схему таких таблиць.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Збагачення](#enrichment)
- [Прогноз](#prediction)
- [Членство в сегменті](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Ця таблиця містить уніфікований профіль клієнта з Customer Insights. Схема для уніфікованого профілю клієнта залежить від сутностей та атрибутів, що використовуються в процесі уніфікації даних. Схема профілю клієнта зазвичай містить підмножину атрибутів із [визначення CustomerProfile в Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Для сценарію B-to-B профіль клієнта містить уніфіковані облікові записи, а схема зазвичай містить підмножину атрибутів із [визначення загальної моделі даних облікового запису](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

Файл ContactProfile містить уніфіковану інформацію про контакт. Контакти – це [особи, які зіставляються з обліковим записом](data-unification-contacts.md) у сценарії B-to-B.

| Column                       | Ввести                | Опис     |
| ---------------------------- | ------------------- | --------------- |
|  Дата народження            | DateTime       |  Дата народження контакту               |
|  Місто                 | SMS |  Місто контактної адреси               |
|  Ідентифікатор контакту            | SMS |  Ідентифікатор профілю контакту               |
|  КонтактПрофілеІд     | Унікальний ідентифікатор   |  Ідентифікатор GUID для контакту               |
|  КраїнаОррегіон      | SMS |  Країна/регіон контактної адреси               |
|  Ідентифікатор клієнта           | SMS |  Ідентифікатор облікового запису, з яким контакт зіставлено               |
|  EntityName           | SMS |  Сутність, з якої надходять дані                |
|  FirstName            | SMS |  ім’я контакту               |
|  Стать               | SMS |  Стать контакту               |
|  Ідентифікатор                   | SMS |  Детермінований GUID на основі`Identifier`               |
|  Identifier           | SMS |  Внутрішній ідентифікатор профілю контакту: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | SMS |  Посада контактної особи               |
|  LastName             | SMS |  прізвище контакту               |
|  PostalCode           | SMS |  ПОШТОВИЙ ІНДЕКС контактної адреси               |
|  PrimaryEmail         | SMS |  Адреса електронної пошти контакту               |
|  Основний телефон         | SMS |  Номер телефону контакту               |
|  Область або республіка      | SMS |  Штат або провінція контактної адреси               |
|  Вуличнаадреса        | SMS |  Вулиця контактної адреси               |

### <a name="alternatekey"></a>AlternateKey

У таблиці AlternateKey містяться ключі сутностей, які брали участь в процесі уніфікації.

|Column  |Ввести  |Опис  |
|---------|---------|---------|
|DataSourceName    |SMS         | Ім'я джерела даних. Наприклад: `datasource5`        |
|EntityName        | SMS        | Назва юридичної особи в Customer Insights. Наприклад: `contact1`        |
|AlternateValue    |SMS         |Альтернативний ідентифікатор, зіставлений з ідентифікатором клієнта. Приклад: `cntid_1078`         |
|KeyRing           | SMS        | Значення JSON  </br> Зразок: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|Ідентифікатор клієнта         | SMS        | Ідентифікатор уніфікованого профілю клієнта.         |
|AlternateKeyId     | Унікальний ідентифікатор        |  Альтернативний детермінований GUID на основі`Identifier`      |
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
| UnifiedActivityId   | Унікальний ідентифікатор | Внутрішній ідентифікатор справи клієнта (ActivityId) |

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
| ЗбагаченняІд | Унікальний ідентифікатор            | Детермінований GUID, створений на основі`Identifier` |
| Identifier   | SMS           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Прогноз

У цій таблиці містяться результати прогнозів моделі.

| Column               | Ввести        | Опис                                          |
|----------------------|-------------|------------------------------------------------------|
| Ідентифікатор клієнта           | SMS      | Ідентифікатор профілю клієнта                                  |
| ModelProvider        | SMS      | Ім’я постачальника моделі                                      |
| Модель                | SMS      | Ім’я моделі                                                |
| Значення               | SMS | Список атрибутів, створених моделлю |
| ПередбаченняІд | Унікальний ідентифікатор       | Детермінований GUID, створений на основі`Identifier` |
| Identifier   | SMS      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Членство в сегменті

Ця таблиця містить інформацію про членство в сегментах профілів клієнтів.

| Column        | Ввести | Опис                        |
|--------------------|--------------|-----------------------------|
| Ідентифікатор клієнта        | SMS       | Ідентифікатор профілю клієнта        |
| СегментПровидер      | SMS       | Додаток, який публікує сегменти.      |
| СегментЧленствоТип | SMS       | Тип клієнта для запису про членство в цьому сегменті. Підтримує кілька типів, таких як Клієнт, Контакт або Обліковий запис. За замовчуванням: клієнт  |
| Сегменти       | SMS  | Список унікальних сегментів, учасниками яких є профіль клієнта      |
| Identifier  | SMS   | Унікальний ідентифікатор запису про членство в сегменті. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| СегментЧленствоІд | Унікальний ідентифікатор      | Детермінований GUID, створений на основі`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
