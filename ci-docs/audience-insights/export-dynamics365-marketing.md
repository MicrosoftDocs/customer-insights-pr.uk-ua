---
title: Експорт даних Customer Insights до Dynamics 365 Marketing
description: Дізнайтесь, як налаштувати підключення до Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643798"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="0f869-103">З'єднувач для Dynamics 365 Marketing (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="0f869-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0f869-104">Використовуйте [сегменти](segments.md), щоб формувати кампанії та специфічні групи клієнтів за допомогою Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="0f869-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="0f869-105">Для отримання додаткових відомостей див. [Використання сегментів з Dynamics 365 Customer Insights у Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="0f869-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="0f869-106">Передумова</span><span class="sxs-lookup"><span data-stu-id="0f869-106">Prerequisite</span></span>

<span data-ttu-id="0f869-107">Записи контактів [з прийнятого Dynamics 365 Marketing Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="0f869-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="0f869-108">Налаштування з'єднувача для Marketing</span><span class="sxs-lookup"><span data-stu-id="0f869-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="0f869-109">У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.</span><span class="sxs-lookup"><span data-stu-id="0f869-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0f869-110">В області **Dynamics 365 Marketing** виберіть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="0f869-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="0f869-111">Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="0f869-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0f869-112">Введіть URL-адресу Marketing вашої організації в полі **Адреса сервера**.</span><span class="sxs-lookup"><span data-stu-id="0f869-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="0f869-113">У розділі **Обліковий запис адміністратора сервера** виберіть **Увійти** і оберіть обліковий запис Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="0f869-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="0f869-114">Зіставте поле ІДЕНТИФІКАТОРА клієнта з ІДЕНТИФІКАТОРОМ контакту Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0f869-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="0f869-115">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="0f869-115">Select **Next**.</span></span>

1. <span data-ttu-id="0f869-116">Виберіть один або кілька сегментів.</span><span class="sxs-lookup"><span data-stu-id="0f869-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="0f869-117">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="0f869-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0f869-118">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="0f869-118">Export the data</span></span>

<span data-ttu-id="0f869-119">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0f869-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0f869-120">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0f869-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
