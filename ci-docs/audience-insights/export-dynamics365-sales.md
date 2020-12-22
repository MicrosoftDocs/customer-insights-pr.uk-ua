---
title: Експорт даних Customer Insights до Dynamics 365 Sales
description: Дізнайтесь, як налаштувати підключення до Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643843"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="2f25a-103">З'єднувач для Dynamics 365 Sales (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="2f25a-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="2f25a-104">Використовуйте дані клієнта для створення маркетингових списків, подальших робочих циклів і надсилання промо-акцій з даними Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="2f25a-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="2f25a-105">Передумова</span><span class="sxs-lookup"><span data-stu-id="2f25a-105">Prerequisite</span></span>

<span data-ttu-id="2f25a-106">Записи контактів [з переданого Dynamics 365 Sales за допомогою Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="2f25a-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="2f25a-107">Налаштування з'єднувача для Sales</span><span class="sxs-lookup"><span data-stu-id="2f25a-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="2f25a-108">У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.</span><span class="sxs-lookup"><span data-stu-id="2f25a-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2f25a-109">В області **Dynamics 365 Sales** виберіть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="2f25a-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="2f25a-110">Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="2f25a-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="2f25a-111">Введіть URL-адресу Sales вашої організації в полі **Адреса сервера**.</span><span class="sxs-lookup"><span data-stu-id="2f25a-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="2f25a-112">У розділі **Обліковий запис адміністратора сервера** виберіть **Увійти** і оберіть обліковий запис Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="2f25a-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="2f25a-113">Зіставте поле ІДЕНТИФІКАТОРА клієнта з ІДЕНТИФІКАТОРОМ контакту Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="2f25a-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="2f25a-114">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="2f25a-114">Select **Next**.</span></span>

1. <span data-ttu-id="2f25a-115">Виберіть один або кілька сегментів.</span><span class="sxs-lookup"><span data-stu-id="2f25a-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="2f25a-116">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="2f25a-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2f25a-117">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="2f25a-117">Export the data</span></span>

<span data-ttu-id="2f25a-118">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2f25a-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2f25a-119">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2f25a-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
