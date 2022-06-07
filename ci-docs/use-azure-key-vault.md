---
title: Робота з власним сховищем ключів Azure для керування секретами
description: Дізнайтесь, як настроїти Customer Insights для використання власного сховища ключів Azure.
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
ms.openlocfilehash: d4f2d5ebc828053c40e22065f4915c4d0f84153f
ms.sourcegitcommit: 6ec4626a185892dfb781d3c7af4384f9c13f3723
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 05/17/2022
ms.locfileid: "8763604"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Робота з власним сховищем ключів Azure (підготовча версія)

Зв'язування виділеного [сховища](/azure/key-vault/general/basic-concepts) ключів Azure з середовищем статистики клієнтів допомагає організаціям відповідати вимогам відповідності.
Спеціалізоване сховище ключів можна використовувати для розміщення та використання секретів у межах відповідності організації. Customer Insights може використовувати секрети в Azure Key Vault для [налаштування підключень](connections.md) до сторонніх систем.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Зв'язування сховища ключів із середовищем статистики клієнтів

### <a name="prerequisites"></a>вимоги

Щоб налаштувати сховище ключів у службі статистики клієнтів, необхідно виконати такі передумови:

- Ви повинні мати активну передплату на Azure.

- У вас є [роль адміністратора](permissions.md#admin) в інсайтах клієнтів. Докладніше про [дозволи користувачів можна дізнатися в розділі "Статистика клієнтів"](permissions.md#assign-roles-and-permissions).

- Ви маєте ролі [Співавтор](/azure/role-based-access-control/built-in-roles#contributor) і [Адміністратор доступу користувачів](/azure/role-based-access-control/built-in-roles#user-access-administrator) до сховища ключів або групи ресурсів, до якої належить сховище ключів. Для отримання додаткових відомостей перейдіть до пункту [Додавання або видалення призначень ролей Azure за допомогою порталу Azure](/azure/role-based-access-control/role-assignments-portal). Якщо у сховищі ключів немає ролі адміністратора доступу користувачів, слід окремо налаштувати дозволи керування доступом на основі ролей для принципала служби Azure для Dynamics 365 Customer Insights. Виконайте кроки, щоб [використовувати принципала служби Azure](connect-service-principal.md) для сховища ключів, яке потрібно зв’язати.

- Для сховища ключів має бути **вимкнуто** брандмауер сховища ключів.

- Сховище ключів знаходиться в тому ж [розташуванні](https://azure.microsoft.com/global-infrastructure/geographies/#overview) Azure, що й середовище статистики клієнтів. Регіон середовища в "Статистика клієнтів" відображається в розділі **"Система** > **адміністрування** > **про** > **регіон"**.

### <a name="link-a-key-vault-to-the-environment"></a>Зв'язування сховища ключів із середовищем

1. Перейдіть до **розділу Безпека** > **адміністратора** та перейдіть на **вкладку Сховище ключів**.
1. На плитці **Сховище ключів** виберіть **«Настроювання»**.
1. Виберіть **Передплата**.
1. Виберіть сховище ключів у розкривному списку **«Сховище ключів»**. Якщо відображається забагато сховищ ключів, виберіть групу ресурсів, щоб обмежити результати пошуку.
1. Прийміть положення про **Конфіденційність та відповідність даних**.
1. Виберіть **Зберегти**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Кроки для настроювання зв'язаного сховища ключів у службі &quot;Статистика клієнтів&quot;.":::

Плитка **«Сховище ключів»** тепер містить ім'я зв'язаного сховища ключів, групу ресурсів і передплату. Його можна використати в настройці з'єднання.
Щоб отримати додаткові відомості про те, які дозволи на сховищі ключів надаються Customer Insights, перейдіть до [розділу Дозволи, надані в сховищі](#permissions-granted-on-the-key-vault) ключів, пізніше в цій статті.

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

## <a name="permissions-granted-on-the-key-vault"></a>Дозволи, надані для сховища ключів

Наведені нижче дозволи надаються customer insights на пов'язаному сховищі ключів, [якщо ввімкнуто політику](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) доступу до сховища ключів або [керування доступом](/azure/key-vault/general/rbac-guide?tabs=azure-cli) azure на основі ролей.

### <a name="key-vault-access-policy"></a>Політика доступу до сховища ключів

| Ввести        | Дозволи          |
| ----------- | -------------------- |
| Клавіша         | [Отримати ключі](/rest/api/keyvault/keys/get-keys/get-keys), [Отримати ключ](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Секрет      | [Отримати секрети](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Отримати секрет](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Сертифікат | [Отримати сертифікати](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Отримати сертифікат](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Попередні значення — це мінімальне значення для списку та читання під час виконання.

### <a name="azure-role-based-access-control"></a>Керування доступом на основі ролей Azure

Для статистики клієнтів буде додано зчитувач ключових сховищ і ключові секрети vault. Щоб отримати відомості про ці ролі, перейдіть до розділу [Вбудовані ролі Azure для операцій із площиною даних сховища ключів](/azure/key-vault/general/rbac-guide?tabs=azure-cli)

## <a name="recommendations"></a>Рекомендації

- Використовуйте окреме або виділене сховище ключів, яке містить лише секрети, необхідні для статистики клієнтів. Читайте докладніше про те, чому [рекомендується використовувати окремі сховища ключів](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Дотримуйтеся [рекомендацій з використання сховища ключів](/azure/key-vault/general/best-practices#turn-on-logging), щоб керувати доступом, резервним копіюванням, відстеженням і перевіркою параметрів.

## <a name="frequently-asked-questions"></a>Запитання й відповіді

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Чи може Customer Insights написати секрети або перезаписати секрети в сховище ключів?

Ні. Лише дозволи для читання та списку, описані в розділі "Надані дозволи ["](#permissions-granted-on-the-key-vault) раніше в цій статті, надаються "Статистика клієнтів". У сховищі ключів система не може додавати, видаляти або перезаписувати секрети. Це також пояснює, чому не можна вводити облікові дані, коли підключення використовує сховище ключів.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Чи можна змінити підключення за допомогою секретів сховища ключів на автентифікацію за замовчуванням?

Ні. Ви не можете повернутися до підключення за замовчуванням після його налаштування за допомогою використання секрету зв'язаного сховища ключів. Створіть окреме підключення та видаліть старе, якщо воно більше не потрібне.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Як я можу відкликати доступ до сховища ключів для статистики клієнтів?

Залежно від того, чи увімкнуто [політику доступу до сховища ключів](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) або [керування доступом на основі ролей Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli), потрібно видалити дозволи для принципала служби `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` з іменем `Dynamics 365 AI for Customer Insights`. Усі підключення, що використовують сховище ключів, припинять роботу.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Секрет, який використовується в підключенні, видалений зі сховища ключів. Що можна зробити?

У Службі підтримки клієнтів з'являється сповіщення, коли налаштований секрет зі сховища ключів більше не доступний. Увімкніть [м'яке видалення](/azure/key-vault/general/soft-delete-overview) у сховищі ключів, щоб відновити секрети, якщо їх було випадково видалено.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Підключення не працює, але мій секрет у сховищі ключів. Яка причина?

Сповіщення з'являється в Службі статистики клієнтів, коли він не може отримати доступ до сховища ключів. Можлива причина

- Дозволи для принципала служби "Статистика клієнтів" видалено. Їх потрібно відновити вручну.

- Брандмауер увімкнено у сховищі ключів. Брандмауер потрібно вимкнути, щоб зробити сховище ключів доступним для статистики клієнтів знову.
