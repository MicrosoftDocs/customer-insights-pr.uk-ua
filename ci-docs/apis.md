---
title: Робота з Customer Insights APIs
description: Використання API пояснення обмежень.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387365"
---
# <a name="work-with-customer-insights-apis"></a>Робота з Customer Insights APIs

Програма Dynamics 365 Customer Insights забезпечує API для розробки власних програм на основі даних у Customer Insights.

> [!IMPORTANT]
> Відомості про ці API наведено в [Довіднику Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Вони містять додаткові відомості про операції, параметри та відповіді.

Спробуйте API Customer Insights, створіть реєстрацію програми Azure і почніть роботу з клієнтськими бібліотеками.

## <a name="get-started-trying-the-customer-insights-apis"></a>Почати роботу з Customer Insights API

Увімкніть API Customer Insights і спробуйте їх. Адміністратор Customer Insights повинен увімкнути доступ API до Customer Insights. Після ввімкнення доступу будь-який користувач може використовувати API з ключем підписки.

1. [Увійдіть](https://home.ci.ai.dynamics.com) до Customer Insights. Якщо ще немає передплати, [підпишіться на ознайомлювальну версію Customer Insights](https://aka.ms/tryci).

1. Перейдіть до **Безпека** > **адміністратора** та виберіть вкладку **API**.

1. Якщо доступ API до середовища не був налаштований, виберіть **Увімкнути**.

   Ввімкнення API створює первинний та вторинний ключ передплати для вашої інсталяції, які буд використано у запитах API. Щоб повторно створити клавіші, виберіть " **Відновити первинний** " або **"Відновити додатковий** " на **вкладці API**.

1. Виберіть [**Вивчити наші API**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances), щоб випробувати API.

1. Знайдіть і виберіть операцію API і виберіть **Спробувати**.

   :::image type="content" source="media/try-api.png" alt-text="Як тестувати API.":::

1. На бічній панелі в розкривному меню **Авторизація** задайте значення **неявна**. У заголовку `Authorization` додається маркер на пред’явника. Ключ передплати заповнюється автоматично.
  
1. Крім того, можна додати всі необхідні параметри запиту.

1. Перейдіть до нижньої частини бічної області й натисніть **Надіслати**.

   Відповідь HTTP відображається в нижній частині області.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Створення нової програми для реєстрації на порталі Azure

Створіть нову [реєстрацію](/graph/auth-register-app-v2) програми, щоб використовувати API Customer Insights у програмі Azure, використовуючи делеговані дозволи.

1. [Заповніть розділ](#get-started-trying-the-customer-insights-apis) Початок роботи.

1. Увійдіть до [порталу Azure](https://portal.azure.com) з обліковим записом, який може отримати доступ до даних Customer Insights.

1. Знайдіть і виберіть **Реєстрація** програми.

1. Виберіть пункт **Нова реєстрація**, зазначте ім’я програми та виберіть тип бізнес-партнера.

   Крім того, можна додати URL для переспрямування. http://localhost є достатнім для розробки програми на локальному комп'ютері.

1. Виберіть **Реєстрація**.

1. У новій реєстрації програми виберіть **дозволи API**.

1. Виберіть елемент **Додати дозвіл** і виберіть динамічний **365 AI for Customer Insights** на бічній панелі.

1. Для параметра **Тип дозволу** виберіть **Делеговані дозволи**, потім виберіть дозвіл **user_impersonation**.

1. Виберіть **Додати дозволи**.

1. Виберіть **Згода адміністратора для…**, щоб заповнити реєстрацію програми.

1. Щоб отримати доступ до API без входу користувача, перейдіть до [дозволів](#server-to-server-application-permissions) програми server-to-server.

Ви можете використовувати ідентифікатор програми/клієнта для реєстрації цієї програми в [Бібліотеці автентифікації Microsoft (MSAL),](/azure/active-directory/develop/msal-overview) щоб отримати токен пред’явника для надсилання запиту до API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Відомості про використання API у клієнтських бібліотеках див. у розділі [«Клієнтські бібліотеки Customer Insights»](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Міжсерверні дозволи програм

Створіть реєстрацію програми, яка не потребує взаємодії з користувачем і може бути запущена на сервері.

1. У реєстрації програми на порталі Azure виберіть **Дозволи API**.

1. Виберіть **Додати дозвіл**.

1. Виберіть вкладку **API, які використовує моя організація**, і виберіть **ШІ Dynamics 365 для Customer Insights** у списку.

1. Для параметра **Тип дозволу** виберіть **Дозволи програм**, потім виберіть дозвіл **CustomerInsights.Api.All**.

1. Виберіть **Додати дозволи**.

1. Поверніться до **Дозволів API** для реєстрації вашої програми.

1. Виберіть **Згода адміністратора для…**, щоб заповнити реєстрацію програми.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Додайте ім’я реєстрації програми як користувача в Customer Insights.

   1. Відкрийте Customer Insights, перейдіть до **розділу Безпека** > **адміністратора** та виберіть **Додати користувачів**.

   1. Знайдіть ім'я реєстрації програми, виберіть його в результатах пошуку, а потім натисніть **Зберегти**.

## <a name="sample-queries"></a>Приклади запитів

Короткий список зразків запитів OData для роботи з API наведено в прикладах [запитів](odata-examples.md) OData.

## <a name="customer-insights-client-libraries"></a>Бібліотеки клієнтів Customer Insights

Почніть використовувати клієнтські бібліотеки, доступні для API Customer Insights. Усі вихідні коди бібліотек і зразки програм можна знайти на сторінці [Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Використовуйте клієнтські бібліотеки C# від NuGet.org. В даний час пакет націлений на фреймворки netstandard2.0 і netcoreapp2.0. Докладнішу інформацію про пакет можна знайти на NuGet сторінці [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Додавання клієнтської бібліотеки C# до проекту C#

1. У програмі Visual Studio відкрийте **Диспетчер пакетів NuGet** для вашого проекту.

1. Знайдіть **Microsoft.Dynamics.CustomerInsights.Api**.

1. Виберіть **Інсталювати**, щоб додати пакет до проекту.

   Також цю команду можна виконати в **Консолі менеджера пакетів NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Використання клієнтської бібліотеки C#

1. Використовуйте [бібліотеку автентифікації Microsoft (MSAL)](/azure/active-directory/develop/msal-overview), щоб отримати `AccessToken` з використанням [реєстрації наявної програми Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Після успішної аутентифікації та придбання токена створіть новий або використовуйте існуючий `HttpClient` за допомогою **defaultRequestHeaders "Авторизація"**, встановленого на **"токен доступу"** на пред’явника та **Ocp-Apim-Subscription-Key, встановлений** для [**ключа** підписки з вашого середовища](#get-started-trying-the-customer-insights-apis) Customer Insights.   

   У разі потреби можна скинути заголовок **Авторизація**. Наприклад, коли термін дії маркера минув.

1. Передайте цей `HttpClient` в конструкцію клієнта `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Наприклад, можна дзвонити з клієнтом в «методах розширення» `GetAllInstancesAsync`. Якщо доступ до базового `Microsoft.Rest.HttpOperationResponse` є кращим, використовуйте "методи повідомлення http", наприклад,`GetAllInstancesWithHttpMessagesAsync`.

1. Відповідь, швидше за все, `object` тип, оскільки метод може повертати кілька типів (наприклад, `IList<InstanceInfo>` і `ApiErrorResult`). Щоб перевірити тип повернення, використовуйте об’єкти в типах відповідей, указаних на [сторінці](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) відомостей про API для цієї операції.

   Якщо потрібно отримати більше інформації про запит, скористайтеся **методами http message** для доступу до об'єкта відповіді на запит.

### <a name="nodejs-package"></a>Пакет NodeJS

Скористайтеся клієнтськими бібліотеками NodeJS, доступними в NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Пакет Python

Скористайтеся клієнтськими бібліотеками Python, доступними в PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
