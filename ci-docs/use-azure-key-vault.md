---
title: Робота з власним сховищем ключів Azure (підготовча версія)
description: Дізнайтеся, як настроїти Customer Insights на використання власного сховища ключів Azure для керування секретами.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 8fdb131de35c7d936d2921265f03faa5682db6f6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082649"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Робота з власним сховищем ключів Azure (підготовча версія)

Зв'язування спеціального [сховища](/azure/key-vault/general/basic-concepts) ключів Azure із середовищем Customer Insights допомагає організаціям відповідати вимогам відповідності.
Спеціалізоване сховище ключів можна використовувати для розміщення та використання секретів у межах відповідності організації. Customer Insights може використовувати секрети в Сховищі ключів Azure для [налаштування з'єднань](connections.md) зі сторонніми системами.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Зв'яжіть ключове сховище з середовищем Customer Insights

### <a name="prerequisites"></a>вимоги

Щоб налаштувати сховище ключів в Customer Insights, необхідно виконати наступні передумови:

- Ви повинні мати активну передплату на Azure.

- Ви виконуєте [роль адміністратора](permissions.md#admin) в Customer Insights. Дізнайтеся більше про [дозволи користувачів у розділі "Статистика клієнтів"](permissions.md#assign-roles-and-permissions).

- Ви маєте ролі [Співавтор](/azure/role-based-access-control/built-in-roles#contributor) і [Адміністратор доступу користувачів](/azure/role-based-access-control/built-in-roles#user-access-administrator) до сховища ключів або групи ресурсів, до якої належить сховище ключів. Для отримання додаткових відомостей перейдіть до пункту [Додавання або видалення призначень ролей Azure за допомогою порталу Azure](/azure/role-based-access-control/role-assignments-portal). Якщо у сховищі ключів немає ролі адміністратора доступу користувачів, слід окремо налаштувати дозволи керування доступом на основі ролей для принципала служби Azure для Dynamics 365 Customer Insights. Виконайте кроки, щоб [використовувати принципала служби Azure](connect-service-principal.md) для сховища ключів, яке потрібно зв’язати.

- Для сховища ключів має бути **вимкнуто** брандмауер сховища ключів.

- Ключове сховище знаходиться в тому ж [розташуванні](https://azure.microsoft.com/global-infrastructure/geographies/#overview) Azure, що і середовище Customer Insights. Регіон навколишнього середовища в Customer Insights наведено в розділі **Система** > **адміністрування** > **про** > **регіон**.

### <a name="link-a-key-vault-to-the-environment"></a>Зв'язування сховища ключів із середовищем

1. Перейдіть до **розділу Безпека** > **адміністратора**, а потім перейдіть на вкладку **Сховище ключів**.
1. На плитці **Сховище ключів** виберіть **«Настроювання»**.
1. Виберіть **Передплата**.
1. Виберіть сховище ключів у розкривному списку **«Сховище ключів»**. Якщо відображається забагато сховищ ключів, виберіть групу ресурсів, щоб обмежити результати пошуку.
1. Прийміть положення про **Конфіденційність та відповідність даних**.
1. Виберіть **Зберегти**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Кроки для налаштування зв'язаного ключового сховища в Customer Insights.":::

Плитка **«Сховище ключів»** тепер містить ім'я зв'язаного сховища ключів, групу ресурсів і передплату. Його можна використати в настройці з'єднання.
Щоб отримати докладнішу інформацію про те, які дозволи щодо сховища ключів надаються Customer Insights, перейдіть до [розділу Дозволи, надані в сховищі](#permissions-granted-on-the-key-vault) ключів, далі в цій статті.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Використання сховища ключів у настройках з'єднання

Під час [настроювання підключень](connections.md) до систем стороннього виробника секрети зв'язаного сховища ключів можна використовувати для настроювання підключень.

1. Відкрийте **Адміністрування** > **Підключення**.
1. Виберіть **«Додати підключення»**.
1. Для підтримуваних типів з'єднання доступний перемикач **«Використовувати сховище ключів»**, якщо ви зв'язали сховище ключів.
1. Замість того, щоб вводити секрет вручну, можна вибрати ім'я секрету, яке вказує на секретне значення в сховищі ключів.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Область підключення зі з'єднанням SFTP, де використовується секрет сховища ключів.":::

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

## <a name="permissions-granted-on-the-key-vault"></a>Дозволи, надані на сховище ключів

Наведені нижче дозволи надаються Customer Insights у сховищі зв'язаних ключів, якщо [ввімкнуто політику доступу до Сховища ключів](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) або [елемент керування доступом](/azure/key-vault/general/rbac-guide?tabs=azure-cli) на основі ролей Azure.

### <a name="key-vault-access-policy"></a>Політика доступу до сховища ключів

| Ввести        | Дозволи          |
| ----------- | -------------------- |
| Клавіша         | [Отримати ключі](/rest/api/keyvault/keys/get-keys/get-keys), [Отримати ключ](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Секрет      | [Отримати секрети](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Отримати секрет](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Сертифікат | [Отримати сертифікати](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Отримати сертифікат](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Попередні значення — це мінімальне значення для списку та читання під час виконання.

### <a name="azure-role-based-access-control"></a>Керування доступом на основі ролей Azure

Для аналізу клієнтів будуть додані ролі користувача "Зчитувач ключових сховищ" і "Секрети ключових сховищ". Щоб отримати відомості про ці ролі, перейдіть до розділу [Вбудовані ролі Azure для операцій із площиною даних сховища ключів](/azure/key-vault/general/rbac-guide?tabs=azure-cli)

## <a name="recommendations"></a>Рекомендації

- Використовуйте окреме або виділене сховище ключів, яке містить лише секрети, необхідні для Customer Insights. Читайте докладніше про те, чому [рекомендується використовувати окремі сховища ключів](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Дотримуйтеся [рекомендацій з використання сховища ключів](/azure/key-vault/general/best-practices#turn-on-logging), щоб керувати доступом, резервним копіюванням, відстеженням і перевіркою параметрів.

## <a name="frequently-asked-questions"></a>Запитання й відповіді

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Чи може Customer Insights вписати секрети або перезаписати секрети в ключове сховище?

Ні. Лише дозволи на читання та список, описані в [розділі наданих дозволів](#permissions-granted-on-the-key-vault), наведених вище в цій статті, надаються Програмі Customer Insights. У сховищі ключів система не може додавати, видаляти або перезаписувати секрети. Це також пояснює, чому не можна вводити облікові дані, коли підключення використовує сховище ключів.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Чи можна змінити підключення за допомогою секретів сховища ключів на автентифікацію за замовчуванням?

Ні. Ви не можете повернутися до підключення за замовчуванням після його налаштування за допомогою використання секрету зв'язаного сховища ключів. Створіть окреме підключення та видаліть старе, якщо воно більше не потрібне.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Як я можу відкликати доступ до сховища ключів для Customer Insights?

Залежно від того, чи увімкнуто [політику доступу до сховища ключів](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) або [керування доступом на основі ролей Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli), потрібно видалити дозволи для принципала служби `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` з іменем `Dynamics 365 AI for Customer Insights`. Усі підключення, що використовують сховище ключів, припинять роботу.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Секрет, який використовується в підключенні, видалений зі сховища ключів. Що можна зробити?

У Customer Insights з'являється сповіщення, коли настроєний секрет зі сховища ключів більше не доступний. Увімкніть [м'яке видалення](/azure/key-vault/general/soft-delete-overview) у сховищі ключів, щоб відновити секрети, якщо їх було випадково видалено.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Підключення не працює, але мій секрет у сховищі ключів. Яка причина?

У Customer Insights з'являється сповіщення, коли він не може отримати доступ до сховища ключів. Можлива причина

- Дозволи для директора служби Customer Insights було видалено. Їх потрібно відновити вручну.

- Брандмауер увімкнено у сховищі ключів. Брандмауер потрібно вимкнути, щоб знову зробити сховище ключів доступним для Customer Insights.
