---
title: Експорт даних Customer Insights до Dynamics 365 Marketing
description: Дізнайтесь, як налаштувати підключення до Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597628"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="c62f9-103">З'єднувач для Dynamics 365 Marketing (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="c62f9-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c62f9-104">Використовуйте [сегменти](segments.md), щоб формувати кампанії та специфічні групи клієнтів за допомогою Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="c62f9-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="c62f9-105">Для отримання додаткових відомостей див. [Використання сегментів з Dynamics 365 Customer Insights у Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="c62f9-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="c62f9-106">Передумова</span><span class="sxs-lookup"><span data-stu-id="c62f9-106">Prerequisite</span></span>

- <span data-ttu-id="c62f9-107">Записи контактних осіб мають бути присутніми в Dynamics 365 Marketing, щоб ви змогли експортувати сегмент з Customer Insights до Marketing.</span><span class="sxs-lookup"><span data-stu-id="c62f9-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="c62f9-108">Дізнайтеся більше про те, як прийняти контактних осіб у [Dynamics 365 Marketing, використовуючи Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c62f9-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="c62f9-109">Експортування сегментів з аналізу аудиторії до Marketing не призведе до створення нових записів контактних осіб в інсталяціях Marketing.</span><span class="sxs-lookup"><span data-stu-id="c62f9-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="c62f9-110">Записи контактних осіб з Marketing повинні бути прийняті в аналізі аудиторії та мають використовуватися, як джерело даних.</span><span class="sxs-lookup"><span data-stu-id="c62f9-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="c62f9-111">Їх також потрібно включити в уніфіковану сутність «Клієнт», щоб зіставити ідентифікатори клієнтів із ідентифікаторами контактних осіб, перш ніж можна буде експортувати сегменти.</span><span class="sxs-lookup"><span data-stu-id="c62f9-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="c62f9-112">Налаштування з'єднувача для Marketing</span><span class="sxs-lookup"><span data-stu-id="c62f9-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="c62f9-113">У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.</span><span class="sxs-lookup"><span data-stu-id="c62f9-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c62f9-114">В області **Dynamics 365 Marketing** виберіть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="c62f9-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="c62f9-115">Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="c62f9-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c62f9-116">Введіть URL-адресу Marketing вашої організації в полі **Адреса сервера**.</span><span class="sxs-lookup"><span data-stu-id="c62f9-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="c62f9-117">У розділі **Обліковий запис адміністратора сервера** виберіть **Увійти** і оберіть обліковий запис Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="c62f9-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="c62f9-118">Зіставте поле ІДЕНТИФІКАТОРА клієнта з ІДЕНТИФІКАТОРОМ контакту Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c62f9-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="c62f9-119">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="c62f9-119">Select **Next**.</span></span>

1. <span data-ttu-id="c62f9-120">Виберіть один або кілька сегментів.</span><span class="sxs-lookup"><span data-stu-id="c62f9-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="c62f9-121">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="c62f9-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c62f9-122">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="c62f9-122">Export the data</span></span>

<span data-ttu-id="c62f9-123">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c62f9-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c62f9-124">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c62f9-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]