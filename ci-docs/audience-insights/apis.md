---
title: Робота з API
description: Використання API пояснення обмежень.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689155"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="eaa82-103">Робота з Customer Insights APIs</span><span class="sxs-lookup"><span data-stu-id="eaa82-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="eaa82-104">Dynamics 365 Customer Insights забезпечує API для створення власних програм на основі даних у Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eaa82-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eaa82-105">Відомості про ці API наведено в [Довіднику Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="eaa82-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="eaa82-106">Вони містять додаткові відомості про операції, параметри та відповіді.</span><span class="sxs-lookup"><span data-stu-id="eaa82-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="eaa82-107">У цій статті наведено відомості про доступ до Customer Insights API, створення реєстрації програми Azure та надання допомоги для початку роботи з наявними клієнтськими бібліотеками.</span><span class="sxs-lookup"><span data-stu-id="eaa82-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="eaa82-108">Почати роботу з Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="eaa82-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="eaa82-109">[Увійдіть](https://home.ci.ai.dynamics.com) до Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eaa82-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="eaa82-110">Якщо ще немає передплати, [підпишіться на ознайомлювальну версію Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="eaa82-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="eaa82-111">Щоб увімкнути API в Customer Insights, виберіть **Адміністратор** > **Дозволи**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="eaa82-112">Для цього потрібно мати дозвіл адміністратора.</span><span class="sxs-lookup"><span data-stu-id="eaa82-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="eaa82-113">Перейдіть на вкладку **API** та натисніть кнопку **Ввімкнути**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="eaa82-114">Ввімкнення API створює первинний та вторинний ключ передплати для вашої інсталяції, які буд використано у запитах API.</span><span class="sxs-lookup"><span data-stu-id="eaa82-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="eaa82-115">Ключі можна створити повторно, вибравши **Повторно створити первинний ключ** або **Повторно створити вторинний ключ** у меню **Адміністратор** > **Дозволи** > **API**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Ввімкнути Customer Insights APIs":::

1. <span data-ttu-id="eaa82-117">Виберіть **Ознайомтеся з нашими API**, щоб випробувати API.</span><span class="sxs-lookup"><span data-stu-id="eaa82-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="eaa82-118">Виберіть операцію API та натисніть кнопку **Спробувати**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="eaa82-119">У бічній області установіть для параметру в розкривному меню **Авторизація** значення **Неявна**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="eaa82-120">Верхній колонтитул `Authorization` отримає доданий маркер на пред’явника.</span><span class="sxs-lookup"><span data-stu-id="eaa82-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="eaa82-121">Ключ передплати буде автоматично заповнено.</span><span class="sxs-lookup"><span data-stu-id="eaa82-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="eaa82-122">Крім того, можна додати всі необхідні параметри запиту.</span><span class="sxs-lookup"><span data-stu-id="eaa82-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="eaa82-123">Перейдіть до нижньої частини бічної області й натисніть **Надіслати**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="eaa82-124">Відповідь HTTP скоро з'явиться нижче.</span><span class="sxs-lookup"><span data-stu-id="eaa82-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="eaa82-125">Створення нової програми для реєстрації на порталі Azure</span><span class="sxs-lookup"><span data-stu-id="eaa82-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="eaa82-126">Ці кроки допоможуть розпочати використання Customer Insights API у програмі Azure, використовуючи делеговані дозволи.</span><span class="sxs-lookup"><span data-stu-id="eaa82-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="eaa82-127">Перевірте, щоб спочатку був заповнений [розділ «Початок роботи»](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="eaa82-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="eaa82-128">Увійдіть до [порталу Azure](https://portal.azure.com) з обліковим записом, який може отримати доступ до даних Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eaa82-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="eaa82-129">На лівій панелі виберіть пункт **Реєстрації програми**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="eaa82-130">Виберіть пункт **Нова реєстрація**, надайте ім'я програми та виберіть тип бізнес-партнера.</span><span class="sxs-lookup"><span data-stu-id="eaa82-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="eaa82-131">Крім того, можна додати URL для переспрямування.</span><span class="sxs-lookup"><span data-stu-id="eaa82-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="eaa82-132">http://localhost є достатнім для розробки програми на локальному комп'ютері.</span><span class="sxs-lookup"><span data-stu-id="eaa82-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="eaa82-133">У новій реєстрації програми виберіть **дозволи API**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="eaa82-134">Виберіть **Додати дозвіл** та виберіть **Customer Insights** в бічній області.</span><span class="sxs-lookup"><span data-stu-id="eaa82-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="eaa82-135">Для **Типу дозволів** виберіть параметр **Делеговані дозволи** й виберіть досвід **Уособлення користувача**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="eaa82-136">Виберіть **Додати дозволи**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-136">Select **Add permissions**.</span></span> <span data-ttu-id="eaa82-137">Якщо потрібно отримати доступ до API без входу користувача, перегляньте розділ [Міжсерверні дозволи програм](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="eaa82-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="eaa82-138">Виберіть **Згода адміністратора для…**, щоб заповнити реєстрацію програми.</span><span class="sxs-lookup"><span data-stu-id="eaa82-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="eaa82-139">Для реєстрації цієї програми з Microsoft Authentication Library (MSAL) можна використати ідентифікатор програми/клієнта для отримання маркера на пред’явника, щоб надіслати з вашим запитом до API.</span><span class="sxs-lookup"><span data-stu-id="eaa82-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="eaa82-140">Для отримання додаткових відомостей про MSAL див. [Огляд бібліотеки автентифікації Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="eaa82-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="eaa82-141">Для отримання додаткових відомостей про реєстрацію програми в Azure див. [Реєстрація нової програми на порталі Azure](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="eaa82-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="eaa82-142">Для отримання інформації про використання бібліотек наших клієнтів API див. [Бібліотеки клієнтів Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="eaa82-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="eaa82-143">Міжсерверні дозволи програм</span><span class="sxs-lookup"><span data-stu-id="eaa82-143">Server-to-server application permissions</span></span>

<span data-ttu-id="eaa82-144">У [розділі «Реєстрація програм»](#create-a-new-app-registration-in-the-azure-portal) описано, як зареєструвати програму, яка вимагає від користувача увійти до системи для автентифікації.</span><span class="sxs-lookup"><span data-stu-id="eaa82-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="eaa82-145">Дізнайтесь, як створити реєстрацію програми, яка не потребує взаємодії з користувачем і може виконуватись на сервері.</span><span class="sxs-lookup"><span data-stu-id="eaa82-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="eaa82-146">У реєстрації програми на порталі Azure виберіть **Дозволи API**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="eaa82-147">Виберіть **Додати дозвіл** та виберіть **Customer Insights** в бічній області.</span><span class="sxs-lookup"><span data-stu-id="eaa82-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="eaa82-148">Для **Типу дозволів** натисніть **Дозволи програми** й виберіть дозвіл **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="eaa82-149">Виберіть **Додати дозволи**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="eaa82-150">Щоб надати адміністратору згоду на дозвіл для цієї програми, необхідно додати основну послугу.</span><span class="sxs-lookup"><span data-stu-id="eaa82-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="eaa82-151">Інсталяція модуля Azure Active Directory (AD) PowerShell `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="eaa82-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="eaa82-152">Підключення до облікового запису AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="eaa82-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="eaa82-153">Ідентифікатор клієнта можна знайти в розділі **Огляд** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="eaa82-154">Щоб додати основну послугу Azure AD, виконайте таку команду: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` параметр AppID відповідний до програми Customer Insights API.</span><span class="sxs-lookup"><span data-stu-id="eaa82-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Приклад основної служби":::

1. <span data-ttu-id="eaa82-156">Поверніться до **Дозволів API** для реєстрації вашої програми.</span><span class="sxs-lookup"><span data-stu-id="eaa82-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="eaa82-157">Виберіть **Згода адміністратора для…**, щоб заповнити реєстрацію програми.</span><span class="sxs-lookup"><span data-stu-id="eaa82-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="eaa82-158">Щоб завершити, необхідно додати назву реєстрації програми як користувача в Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eaa82-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="eaa82-159">Відкрийте Customer Insights, перейдіть до меню **Адміністратор** > **Дозволи** і натисніть **Додати користувача**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="eaa82-160">Знайдіть ім'я реєстрації програми, виберіть його в результатах пошуку, а потім натисніть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="eaa82-161">Бібліотеки клієнтів Customer Insights</span><span class="sxs-lookup"><span data-stu-id="eaa82-161">Customer Insights client libraries</span></span>

<span data-ttu-id="eaa82-162">Інформація цього розділу допоможе почати роботу з використанням клієнтських бібліотек, доступних для Customer Insights API.</span><span class="sxs-lookup"><span data-stu-id="eaa82-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="eaa82-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="eaa82-163">C# NuGet</span></span>

<span data-ttu-id="eaa82-164">Дізнайтесь, як почати роботу з використанням клієнтської бібліотеки C# із програми NuGet.org. Для отримання додаткових відомостей про пакет NuGet див. розділ [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="eaa82-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="eaa82-165">На даний момент цей пакунок націлений на структури netstandard2.0 і netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="eaa82-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="eaa82-166">Додавання клієнтської бібліотеки C# до проекту C#</span><span class="sxs-lookup"><span data-stu-id="eaa82-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="eaa82-167">У програмі Visual Studio відкрийте **Диспетчер пакетів NuGet** для вашого проекту.</span><span class="sxs-lookup"><span data-stu-id="eaa82-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="eaa82-168">Знайдіть **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="eaa82-169">Виберіть **Інсталювати**, щоб додати пакет до проекту.</span><span class="sxs-lookup"><span data-stu-id="eaa82-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="eaa82-170">Також цю команду можна виконати в **Консолі менеджера пакетів NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="eaa82-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Додати пакет NuGet до проекту Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="eaa82-172">Використання клієнтської бібліотеки C#</span><span class="sxs-lookup"><span data-stu-id="eaa82-172">Use the C# client library</span></span>

1. <span data-ttu-id="eaa82-173">Використовуйте [бібліотеку автентифікації Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview), щоб отримати `AccessToken` з використанням [реєстрації наявної програми Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="eaa82-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="eaa82-174">Після успішної автентифікації і отримання маркера, створіть новий або використайте наявний `HttpClient` з додатковим **DefaultRequestHeaders "Authorization"** встановлено на **Пред’явник<access token>** і **Ocp-Apim-Subscription-Key** встановленим на [**Ключ передплати** з вашого середовища Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="eaa82-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="eaa82-175">У разі потреби можна скинути заголовок **Авторизація**.</span><span class="sxs-lookup"><span data-stu-id="eaa82-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="eaa82-176">Наприклад, коли термін дії маркера минув.</span><span class="sxs-lookup"><span data-stu-id="eaa82-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="eaa82-177">Передайте цей `HttpClient` в конструкцію клієнта `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="eaa82-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Приклад httpclient":::

1. <span data-ttu-id="eaa82-179">Наприклад, можна дзвонити з клієнтом в «методах розширення» `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="eaa82-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="eaa82-180">Якщо перевага надається доступу до основної `Microsoft.Rest.HttpOperationResponse`, слід використовувати «методи http-повідомлення» `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="eaa82-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="eaa82-181">Ймовірно, відповідь буде типом `object`, оскільки метод може повертати кілька типів (наприклад, `IList<InstanceInfo>` і `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="eaa82-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="eaa82-182">Щоб перевірити тип повернення, можна спокійно перетворювати об'єкти до типів відповідей, указаних на [сторінці відомостей API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) для цієї операції.</span><span class="sxs-lookup"><span data-stu-id="eaa82-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="eaa82-183">Якщо потрібно отримати більше інформації про запит, скористайтеся **методами http message** для доступу до об'єкта відповіді на запит.</span><span class="sxs-lookup"><span data-stu-id="eaa82-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>
