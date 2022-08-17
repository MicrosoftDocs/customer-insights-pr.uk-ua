---
title: Робота з власним сховищем ключів Azure (підготовча версія)
description: Дізнайтеся, як налаштувати Customer Insights на використання власного сховища ключів Azure для керування секретами.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246180"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Робота з власним сховищем ключів Azure (підготовча версія)

Зв’язування спеціального [сховища](/azure/key-vault/general/basic-concepts) ключів Azure із середовищем Customer Insights допомагає організаціям відповідати вимогам відповідності.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Зв’яжіть ключове сховище з середовищем Customer Insights

Налаштуйте спеціальне сховище ключів, щоб інсценувати та використовувати секрети на межі відповідності організації.

### <a name="prerequisites"></a>вимоги

- Активна передплата Azure.

- Роль [адміністратора,](permissions.md#admin)[призначена](permissions.md#add-users) в customer Insights.

- [Ролі постачальника](/azure/role-based-access-control/built-in-roles#contributor) та [адміністратора](/azure/role-based-access-control/built-in-roles#user-access-administrator) доступу користувачів у сховищі ключа або групі ресурсів, до якої належить сховище ключів. Для отримання додаткових відомостей перейдіть до пункту [Додавання або видалення призначень ролей Azure за допомогою порталу Azure](/azure/role-based-access-control/role-assignments-portal). Якщо у ключовому сховищі немає ролі адміністратора доступу користувачів, настройте дозволи на керування доступом на основі ролей для принципала Dynamics 365 Customer Insights служби Azure окремо. Виконайте кроки, щоб [використовувати принципала служби Azure](connect-service-principal.md) для сховища ключів, яке потрібно зв’язати.

- У сховищі ключів повинен бути відключений **брандмауер** Key Vault.

- Ключове сховище знаходиться в тому ж [місці](https://azure.microsoft.com/global-infrastructure/geographies/#overview) Azure, що й середовище Customer Insights. У розділі Customer Insights перейдіть на **вкладку** > **Адміністратор** системи **та Про програму**, щоб переглянути регіон середовища.

### <a name="recommendations"></a>Рекомендації

- [Використовуйте окреме або спеціальне сховище](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) ключів, яке містить лише секрети, необхідні для Customer Insights.

- Дотримуйтеся [рекомендацій з використання сховища ключів](/azure/key-vault/general/best-practices#turn-on-logging), щоб керувати доступом, резервним копіюванням, відстеженням і перевіркою параметрів.

### <a name="link-a-key-vault-to-the-environment"></a>Зв'язування сховища ключів із середовищем

1. Перейдіть до **Безпека** > **адміністратора**, а потім виберіть вкладку **Сховище** ключів.
1. На плитці **Сховище ключів** виберіть **«Настроювання»**.
1. Виберіть **Передплата**.
1. Виберіть сховище ключів у розкривному списку **«Сховище ключів»**. Якщо доступно забагато ключових сховищ, виберіть групу ресурсів, щоб обмежити результати пошуку.
1. Перегляньте декларацію про [Конфіденційність і відповідність даних](connections.md#data-privacy-and-compliance) і виберіть **Приймаю**.
1. Виберіть **Зберегти**.

Плитка " **Сховище** ключів" відображає зв’язане ім’я сховища ключів, передплату та групу ресурсів. Його можна використати в настройці з'єднання.
Щоб дізнатися більше про те, які дозволи на ключове сховище надаються Customer Insights, перейдіть до [розділу Дозволи, надані в сховищі ключів](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Використання сховища ключів у настройках з'єднання

При [налаштуванні підключень](connections.md) до [підтримуваних сторонніх](#supported-connection-types) систем використовуйте секрети з прив’язаного Key Vault для настройки з’єднань.

1. Відкрийте **Адміністрування** > **Підключення**.
1. Виберіть **«Додати підключення»**.
1. Для підтримуваних типів з'єднання доступний перемикач **«Використовувати сховище ключів»**, якщо ви зв'язали сховище ключів.
1. Замість того, щоб вводити секрет вручну, виберіть ім’я секрету, яке вказує на секретне значення в ключовому сховищі.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Область підключення зі з'єднанням SFTP, де використовується секрет сховища ключів.":::

1. Натисніть кнопку **Зберегти**, щоб створити підключення.

## <a name="supported-connection-types"></a>Підтримувані типи підключень

Підтримуються такі підключення для [експорту](export-destinations.md):

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Хмара Salesforce Marketing](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Дозволи, надані на ключовому сховищі

Наведені нижче дозволи надаються Customer Insights на зв’язане сховище ключів, [якщо ввімкнуто політику](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) доступу до Сховища ключів або [керування доступом](/azure/key-vault/general/rbac-guide?tabs=azure-cli) на основі ролей Azure.

### <a name="key-vault-access-policy"></a>Політика доступу до сховища ключів

| Ввести        | Дозволи          |
| ----------- | -------------------- |
| Клавіша         | [Отримати ключі](/rest/api/keyvault/keys/get-keys/get-keys), [Отримати ключ](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Секрет      | [Отримати секрети](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Отримати секрет](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Сертифікат | [Отримати сертифікати](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Отримати сертифікат](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Попередні значення — це мінімальне значення для списку та читання під час виконання.

### <a name="azure-role-based-access-control"></a>Керування доступом на основі ролей Azure

Для customer Insights будуть додані [ролі](/azure/key-vault/general/rbac-guide?tabs=azure-cli) користувача Key Vault Reader і Key Vault Secrets.

## <a name="frequently-asked-questions"></a>Запитання й відповіді

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Чи може Customer Insights писати секрети або перезаписувати секрети в ключове сховище?

Ні. Лише дозволи для читання та переліку, описані в [наданих дозволах](#permissions-granted-on-the-key-vault), надаються Customer Insights. У сховищі ключів система не може додавати, видаляти або перезаписувати секрети. Це також пояснює, чому не можна вводити облікові дані, коли підключення використовує сховище ключів.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Чи можна змінити підключення за допомогою секретів сховища ключів на автентифікацію за замовчуванням?

Ні. Ви не можете повернутися до підключення за замовчуванням після його налаштування за допомогою використання секрету зв'язаного сховища ключів. Створіть окреме підключення та видаліть старе, якщо воно більше не потрібне.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Як відкликати доступ до ключового сховища для Customer Insights?

Якщо ввімкнуто [політику](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) доступу до сховища ключів або [елементний контроль](/azure/key-vault/general/rbac-guide?tabs=azure-cli) доступу Azure, видаліть дозволи для принципала `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` служби з іменем `Dynamics 365 AI for Customer Insights`. Усі підключення, що використовують сховище ключів, припинять роботу.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Секрет, який використовується в підключенні, видалений зі сховища ключів. Що можна зробити?

Сповіщення з’являється в Customer Insights, коли налаштований секрет зі сховища ключів більше не доступний. Увімкніть [м'яке видалення](/azure/key-vault/general/soft-delete-overview) у сховищі ключів, щоб відновити секрети, якщо їх було випадково видалено.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Підключення не працює, але мій секрет у сховищі ключів. Яка причина?

У Customer Insights з’являється сповіщення, коли він не може отримати доступ до сховища ключів. Можлива причина

- Дозволи для директора служби Customer Insights було видалено. Їх потрібно відновити вручну.

- Брандмауер увімкнено у сховищі ключів. Брандмауер потрібно вимкнути, щоб зробити сховище ключів знову доступним для Customer Insights.
