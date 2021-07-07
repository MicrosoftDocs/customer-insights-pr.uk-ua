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
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304767"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="9a16b-103">Робота з Customer Insights APIs</span><span class="sxs-lookup"><span data-stu-id="9a16b-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="9a16b-104">Програма Dynamics 365 Customer Insights забезпечує API для розробки власних програм на основі даних у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9a16b-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a16b-105">Відомості про ці API наведено в [Довіднику Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="9a16b-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="9a16b-106">Вони містять додаткові відомості про операції, параметри та відповіді.</span><span class="sxs-lookup"><span data-stu-id="9a16b-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="9a16b-107">У цій статті описано API Customer Insights, створення реєстрації в програмі Azure та початок із використанням доступних клієнтських бібліотек.</span><span class="sxs-lookup"><span data-stu-id="9a16b-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="9a16b-108">Почати роботу з Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="9a16b-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="9a16b-109">[Увійдіть](https://home.ci.ai.dynamics.com) до Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9a16b-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="9a16b-110">Якщо ще немає передплати, [підпишіться на ознайомлювальну версію Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="9a16b-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="9a16b-111">Щоб увімкнути API в Customer Insights, виберіть **Адміністратор** > **Дозволи**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="9a16b-112">Для цього потрібно мати дозвіл адміністратора.</span><span class="sxs-lookup"><span data-stu-id="9a16b-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="9a16b-113">Перейдіть на вкладку **API** та натисніть кнопку **Ввімкнути**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="9a16b-114">Ввімкнення API створює первинний та вторинний ключ передплати для вашої інсталяції, які буд використано у запитах API.</span><span class="sxs-lookup"><span data-stu-id="9a16b-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="9a16b-115">Ключі можна створити повторно, вибравши **Повторно створити первинний ключ** або **Повторно створити вторинний ключ** у меню **Адміністратор** > **Дозволи** > **API**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Ввімкнути Customer Insights APIs":::

1. <span data-ttu-id="9a16b-117">Виберіть **Ознайомтеся щ нашими API**, щоб [випробувати API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="9a16b-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="9a16b-118">Виберіть операцію API та натисніть кнопку **Спробувати**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="9a16b-119">На бічній панелі в розкривному меню **Авторизація** задайте значення **неявна**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="9a16b-120">У заголовку `Authorization` додається маркер на пред’явника.</span><span class="sxs-lookup"><span data-stu-id="9a16b-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="9a16b-121">Ключ передплати буде автоматично заповнено.</span><span class="sxs-lookup"><span data-stu-id="9a16b-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="9a16b-122">Крім того, можна додати всі необхідні параметри запиту.</span><span class="sxs-lookup"><span data-stu-id="9a16b-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="9a16b-123">Перейдіть до нижньої частини бічної області й натисніть **Надіслати**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="9a16b-124">Відповідь HTTP скоро з'явиться нижче.</span><span class="sxs-lookup"><span data-stu-id="9a16b-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Як тестувати API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="9a16b-126">Створення нової програми для реєстрації на порталі Azure</span><span class="sxs-lookup"><span data-stu-id="9a16b-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="9a16b-127">Ці кроки допоможуть почати користуватися API Customer Insights у програмі Azure з використанням делегованих дозволів.</span><span class="sxs-lookup"><span data-stu-id="9a16b-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="9a16b-128">Спочатку обов’язково заповніть розділ [Почати](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="9a16b-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="9a16b-129">Увійдіть до [порталу Azure](https://portal.azure.com) з обліковим записом, який може отримати доступ до даних Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9a16b-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="9a16b-130">На лівій панелі виберіть пункт **Реєстрації програми**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="9a16b-131">Виберіть пункт **Нова реєстрація**, зазначте ім’я програми та виберіть тип бізнес-партнера.</span><span class="sxs-lookup"><span data-stu-id="9a16b-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="9a16b-132">Крім того, можна додати URL для переспрямування.</span><span class="sxs-lookup"><span data-stu-id="9a16b-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="9a16b-133">http://localhost є достатнім для розробки програми на локальному комп'ютері.</span><span class="sxs-lookup"><span data-stu-id="9a16b-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="9a16b-134">У новій реєстрації програми виберіть **дозволи API**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Як задати дозволи API при реєстрації програми.":::

1. <span data-ttu-id="9a16b-136">Виберіть **Додати дозвіл** та виберіть **Customer Insights** в бічній області.</span><span class="sxs-lookup"><span data-stu-id="9a16b-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="9a16b-137">Для параметра **Тип дозволу** виберіть **Делеговані дозволи**, потім виберіть дозвіл **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="9a16b-138">Виберіть **Додати дозволи**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-138">Select **Add permissions**.</span></span> <span data-ttu-id="9a16b-139">Якщо потрібно отримати доступ до API без входу користувача, перегляньте розділ [Міжсерверні дозволи програм](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="9a16b-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="9a16b-140">Виберіть **Згода адміністратора для…**, щоб заповнити реєстрацію програми.</span><span class="sxs-lookup"><span data-stu-id="9a16b-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="9a16b-141">Для реєстрації цієї програми з Microsoft Authentication Library (MSAL) можна використати ідентифікатор програми/клієнта для отримання маркера на пред’явника, щоб надіслати з вашим запитом до API.</span><span class="sxs-lookup"><span data-stu-id="9a16b-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Як надати згоду адміністратора.":::

<span data-ttu-id="9a16b-143">Для отримання додаткових відомостей про MSAL див. [Огляд бібліотеки автентифікації Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="9a16b-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="9a16b-144">Докладніше про реєстрацію програми в Azure див. у розділі [Реєстрація програми](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="9a16b-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="9a16b-145">Відомості про використання API у клієнтських бібліотеках див. у розділі [«Клієнтські бібліотеки Customer Insights»](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="9a16b-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="9a16b-146">Міжсерверні дозволи програм</span><span class="sxs-lookup"><span data-stu-id="9a16b-146">Server-to-server application permissions</span></span>

<span data-ttu-id="9a16b-147">У [розділі «Реєстрація програм»](#create-a-new-app-registration-in-the-azure-portal) описано, як зареєструвати програму, яка вимагає від користувача увійти до системи для автентифікації.</span><span class="sxs-lookup"><span data-stu-id="9a16b-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="9a16b-148">Дізнайтесь, як створити реєстрацію програми, яка не потребує взаємодії з користувачем і може виконуватись на сервері.</span><span class="sxs-lookup"><span data-stu-id="9a16b-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="9a16b-149">У реєстрації програми на порталі Azure виберіть **Дозволи API**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="9a16b-150">Виберіть **Додати дозвіл**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="9a16b-151">Виберіть вкладку **API, які використовує моя організація**, і виберіть **ШІ Dynamics 365 для Customer Insights** у списку.</span><span class="sxs-lookup"><span data-stu-id="9a16b-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="9a16b-152">Для параметра **Тип дозволу** виберіть **Дозволи програм**, потім виберіть дозвіл **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="9a16b-153">Виберіть **Додати дозволи**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="9a16b-154">Поверніться до **Дозволів API** для реєстрації вашої програми.</span><span class="sxs-lookup"><span data-stu-id="9a16b-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="9a16b-155">Виберіть **Згода адміністратора для…**, щоб заповнити реєстрацію програми.</span><span class="sxs-lookup"><span data-stu-id="9a16b-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Як надати згоду адміністратора.":::

1. <span data-ttu-id="9a16b-157">Щоб завершити, необхідно додати назву реєстрації програми як користувача в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9a16b-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="9a16b-158">Відкрийте Customer Insights, перейдіть до меню **Адміністратор** > **Дозволи** і натисніть **Додати користувача**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="9a16b-159">Знайдіть ім'я реєстрації програми, виберіть його в результатах пошуку, а потім натисніть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="9a16b-160">Бібліотеки клієнтів Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9a16b-160">Customer Insights client libraries</span></span>

<span data-ttu-id="9a16b-161">Інформація цього розділу допоможе почати роботу з використанням клієнтських бібліотек, доступних для Customer Insights API.</span><span class="sxs-lookup"><span data-stu-id="9a16b-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="9a16b-162">Усі вихідні коди бібліотек і зразки програм можна знайти на сторінці [Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="9a16b-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="9a16b-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="9a16b-163">C# NuGet</span></span>

<span data-ttu-id="9a16b-164">Дізнайтесь, як почати роботу з використанням клієнтської бібліотеки C# із програми NuGet.org. Для отримання додаткових відомостей про пакет NuGet див. розділ [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="9a16b-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="9a16b-165">На даний момент цей пакунок націлений на структури netstandard2.0 і netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="9a16b-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="9a16b-166">Додавання клієнтської бібліотеки C# до проекту C#</span><span class="sxs-lookup"><span data-stu-id="9a16b-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="9a16b-167">У програмі Visual Studio відкрийте **Диспетчер пакетів NuGet** для вашого проекту.</span><span class="sxs-lookup"><span data-stu-id="9a16b-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="9a16b-168">Знайдіть **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="9a16b-169">Виберіть **Інсталювати**, щоб додати пакет до проекту.</span><span class="sxs-lookup"><span data-stu-id="9a16b-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="9a16b-170">Також цю команду можна виконати в **Консолі менеджера пакетів NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="9a16b-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Додати пакет NuGet до проекту Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="9a16b-172">Використання клієнтської бібліотеки C#</span><span class="sxs-lookup"><span data-stu-id="9a16b-172">Use the C# client library</span></span>

1. <span data-ttu-id="9a16b-173">Використовуйте [бібліотеку автентифікації Microsoft (MSAL)](/azure/active-directory/develop/msal-overview), щоб отримати `AccessToken` з використанням [реєстрації наявної програми Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="9a16b-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="9a16b-174">Після успішної автентифікації і отримання маркера, створіть новий або використайте наявний `HttpClient` з додатковим **DefaultRequestHeaders "Authorization"** встановлено на **Пред’явник<access token>** і **Ocp-Apim-Subscription-Key** встановленим на [**Ключ передплати** з вашого середовища Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="9a16b-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="9a16b-175">У разі потреби можна скинути заголовок **Авторизація**.</span><span class="sxs-lookup"><span data-stu-id="9a16b-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="9a16b-176">Наприклад, коли термін дії маркера минув.</span><span class="sxs-lookup"><span data-stu-id="9a16b-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="9a16b-177">Передайте цей `HttpClient` в конструкцію клієнта `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="9a16b-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Приклад httpclient":::

1. <span data-ttu-id="9a16b-179">Наприклад, можна робити виклики клієнта в «методах розширення» – наприклад, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="9a16b-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="9a16b-180">Якщо перевага надається основному `Microsoft.Rest.HttpOperationResponse`, використовуйте «http message methods» – наприклад, `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="9a16b-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="9a16b-181">Ймовірно, відповідь буде типом `object`, оскільки метод може повертати кілька типів (наприклад, `IList<InstanceInfo>` і `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="9a16b-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="9a16b-182">Щоб перевірити тип повернення, можна спокійно перетворювати об'єкти до типів відповідей, указаних на [сторінці відомостей API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) для цієї операції.</span><span class="sxs-lookup"><span data-stu-id="9a16b-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="9a16b-183">Якщо потрібно отримати більше інформації про запит, скористайтеся **методами http message** для доступу до об'єкта відповіді на запит.</span><span class="sxs-lookup"><span data-stu-id="9a16b-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="9a16b-184">Пакет NodeJS</span><span class="sxs-lookup"><span data-stu-id="9a16b-184">NodeJS package</span></span>

<span data-ttu-id="9a16b-185">Скористайтеся клієнтськими бібліотеками NodeJS, доступними в NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="9a16b-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="9a16b-186">Пакет Python</span><span class="sxs-lookup"><span data-stu-id="9a16b-186">Python package</span></span>

<span data-ttu-id="9a16b-187">Скористайтеся клієнтськими бібліотеками Python, доступними в PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="9a16b-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
