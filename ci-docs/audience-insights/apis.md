---
title: Робота з API
description: Використання API пояснення обмежень.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 8404515a20529c00708d84813f3a022ad98c45362a2f1e68d7aa890d085071a9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033610"
---
# <a name="work-with-customer-insights-apis"></a>Робота з Customer Insights APIs

Програма Dynamics 365 Customer Insights забезпечує API для розробки власних програм на основі даних у Customer Insights.

> [!IMPORTANT]
> Відомості про ці API наведено в [Довіднику Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Вони містять додаткові відомості про операції, параметри та відповіді.

У цій статті описано API Customer Insights, створення реєстрації в програмі Azure та початок із використанням доступних клієнтських бібліотек.

## <a name="get-started-trying-the-customer-insights-apis"></a>Почати роботу з Customer Insights API

1. [Увійдіть](https://home.ci.ai.dynamics.com) до Customer Insights. Якщо ще немає передплати, [підпишіться на ознайомлювальну версію Customer Insights](https://aka.ms/tryci).

1. Щоб увімкнути API в Customer Insights, виберіть **Адміністратор** > **Дозволи**. Для цього потрібно мати дозвіл адміністратора.

1. Перейдіть на вкладку **API** та натисніть кнопку **Ввімкнути**.    
 
   Ввімкнення API створює первинний та вторинний ключ передплати для вашої інсталяції, які буд використано у запитах API. Ключі можна створити повторно, вибравши **Повторно створити первинний ключ** або **Повторно створити вторинний ключ** у меню **Адміністратор** > **Дозволи** > **API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Ввімкнути Customer Insights APIs.":::

1. Виберіть **Ознайомтеся щ нашими API**, щоб [випробувати API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Виберіть операцію API та натисніть кнопку **Спробувати**.

1. На бічній панелі в розкривному меню **Авторизація** задайте значення **неявна**. У заголовку `Authorization` додається маркер на пред’явника. Ключ передплати буде автоматично заповнено.
  
1. Крім того, можна додати всі необхідні параметри запиту.

1. Перейдіть до нижньої частини бічної області й натисніть **Надіслати**.

Відповідь HTTP скоро з'явиться нижче.

   :::image type="content" source="media/try-apis.gif" alt-text="Як тестувати API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Створення нової програми для реєстрації на порталі Azure

Ці кроки допоможуть почати користуватися API Customer Insights у програмі Azure з використанням делегованих дозволів. Спочатку обов’язково заповніть розділ [Почати](#get-started-trying-the-customer-insights-apis).

1. Увійдіть до [порталу Azure](https://portal.azure.com) з обліковим записом, який може отримати доступ до даних Customer Insights.

1. На лівій панелі виберіть пункт **Реєстрації програми**.

1. Виберіть пункт **Нова реєстрація**, зазначте ім’я програми та виберіть тип бізнес-партнера.
 
   Крім того, можна додати URL для переспрямування. http://localhost є достатнім для розробки програми на локальному комп'ютері.

1. У новій реєстрації програми виберіть **дозволи API**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Як задати дозволи API при реєстрації програми.":::

1. Виберіть **Додати дозвіл** та виберіть **Customer Insights** в бічній області.

1. Для параметра **Тип дозволу** виберіть **Делеговані дозволи**, потім виберіть дозвіл **user_impersonation**.

1. Виберіть **Додати дозволи**. Якщо потрібно отримати доступ до API без входу користувача, перегляньте розділ [Міжсерверні дозволи програм](#server-to-server-application-permissions).

1. Виберіть **Згода адміністратора для…**, щоб заповнити реєстрацію програми.

Для реєстрації цієї програми з Microsoft Authentication Library (MSAL) можна використати ідентифікатор програми/клієнта для отримання маркера на пред’явника, щоб надіслати з вашим запитом до API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Як надати згоду адміністратора.":::

Для отримання додаткових відомостей про MSAL див. [Огляд бібліотеки автентифікації Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Докладніше про реєстрацію програми в Azure див. у розділі [Реєстрація програми](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Відомості про використання API у клієнтських бібліотеках див. у розділі [«Клієнтські бібліотеки Customer Insights»](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Міжсерверні дозволи програм

У [розділі «Реєстрація програм»](#create-a-new-app-registration-in-the-azure-portal) описано, як зареєструвати програму, яка вимагає від користувача увійти до системи для автентифікації. Дізнайтесь, як створити реєстрацію програми, яка не потребує взаємодії з користувачем і може виконуватись на сервері.

1. У реєстрації програми на порталі Azure виберіть **Дозволи API**.

1. Виберіть **Додати дозвіл**. 

1. Виберіть вкладку **API, які використовує моя організація**, і виберіть **ШІ Dynamics 365 для Customer Insights** у списку. 

1. Для параметра **Тип дозволу** виберіть **Дозволи програм**, потім виберіть дозвіл **CustomerInsights.Api.All**.

1. Виберіть **Додати дозволи**.

1. Поверніться до **Дозволів API** для реєстрації вашої програми.

1. Виберіть **Згода адміністратора для…**, щоб заповнити реєстрацію програми.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Як надати згоду адміністратора.":::

1. Щоб завершити, необхідно додати назву реєстрації програми як користувача в Customer Insights.  
   
   Відкрийте Customer Insights, перейдіть до меню **Адміністратор** > **Дозволи** і натисніть **Додати користувача**.

1. Знайдіть ім'я реєстрації програми, виберіть його в результатах пошуку, а потім натисніть **Зберегти**.

## <a name="customer-insights-client-libraries"></a>Бібліотеки клієнтів Customer Insights

Інформація цього розділу допоможе почати роботу з використанням клієнтських бібліотек, доступних для Customer Insights API. Усі вихідні коди бібліотек і зразки програм можна знайти на сторінці [Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Дізнайтесь, як почати роботу з використанням клієнтської бібліотеки C# із програми NuGet.org. Для отримання додаткових відомостей про пакет NuGet див. розділ [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). На даний момент цей пакунок націлений на структури netstandard2.0 і netcoreapp2.0

#### <a name="add-the-c-client-library-to-a-c-project"></a>Додавання клієнтської бібліотеки C# до проекту C#

1. У програмі Visual Studio відкрийте **Диспетчер пакетів NuGet** для вашого проекту.

1. Знайдіть **Microsoft.Dynamics.CustomerInsights.Api**.

1. Виберіть **Інсталювати**, щоб додати пакет до проекту.
 
   Також цю команду можна виконати в **Консолі менеджера пакетів NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Додати пакет NuGet до проекту Visual Studio.":::

#### <a name="use-the-c-client-library"></a>Використання клієнтської бібліотеки C#

1. Використовуйте [бібліотеку автентифікації Microsoft (MSAL)](/azure/active-directory/develop/msal-overview), щоб отримати `AccessToken` з використанням [реєстрації наявної програми Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Після успішної автентифікації і отримання маркера, створіть новий або використайте наявний `HttpClient` з додатковим **DefaultRequestHeaders "Authorization"** встановлено на **Пред’явник<access token>** і **Ocp-Apim-Subscription-Key** встановленим на [**Ключ передплати** з вашого середовища Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   У разі потреби можна скинути заголовок **Авторизація**. Наприклад, коли термін дії маркера минув.

1. Передайте цей `HttpClient` в конструкцію клієнта `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Приклад httpclient.":::

1. Наприклад, можна робити виклики клієнта в «методах розширення» – наприклад, `GetAllInstancesAsync`. Якщо перевага надається основному `Microsoft.Rest.HttpOperationResponse`, використовуйте «http message methods» – наприклад, `GetAllInstancesWithHttpMessagesAsync`.

1. Ймовірно, відповідь буде типом `object`, оскільки метод може повертати кілька типів (наприклад, `IList<InstanceInfo>` і `ApiErrorResult`). Щоб перевірити тип повернення, можна спокійно перетворювати об'єкти до типів відповідей, указаних на [сторінці відомостей API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) для цієї операції.    
   
   Якщо потрібно отримати більше інформації про запит, скористайтеся **методами http message** для доступу до об'єкта відповіді на запит.

### <a name="nodejs-package"></a>Пакет NodeJS

Скористайтеся клієнтськими бібліотеками NodeJS, доступними в NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Пакет Python

Скористайтеся клієнтськими бібліотеками Python, доступними в PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]