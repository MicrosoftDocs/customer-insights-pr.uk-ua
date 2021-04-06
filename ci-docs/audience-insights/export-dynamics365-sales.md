---
title: Експорт даних Customer Insights до Dynamics 365 Sales
description: Дізнайтесь, як налаштувати підключення до Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598134"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="ecd34-103">З'єднувач для Dynamics 365 Sales (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="ecd34-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ecd34-104">Використовуйте дані клієнта для створення маркетингових списків, подальших робочих циклів і надсилання промо-акцій з даними Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ecd34-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="ecd34-105">Передумова</span><span class="sxs-lookup"><span data-stu-id="ecd34-105">Prerequisite</span></span>

1. <span data-ttu-id="ecd34-106">Записи контактних осіб мають бути присутніми в Dynamics 365 Sales, щоб ви змогли експортувати сегмент з Customer Insights до Sales.</span><span class="sxs-lookup"><span data-stu-id="ecd34-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="ecd34-107">Дізнайтеся більше про те, як прийняти контактних осіб у [Dynamics 365 Sales, використовуючи Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ecd34-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="ecd34-108">Експортування сегментів з аналізу аудиторії до Sales не призведе до створення нових записів контактних осіб в інсталяціях Sales.</span><span class="sxs-lookup"><span data-stu-id="ecd34-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="ecd34-109">Записи контактних осіб з Sales повинні бути прийняті в аналізі аудиторії та мають використовуватися, як джерело даних.</span><span class="sxs-lookup"><span data-stu-id="ecd34-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="ecd34-110">Їх також потрібно включити в уніфіковану сутність «Клієнт», щоб зіставити ідентифікатори клієнтів із ідентифікаторами контактних осіб, перш ніж можна буде експортувати сегменти.</span><span class="sxs-lookup"><span data-stu-id="ecd34-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="ecd34-111">Налаштування з'єднувача для Sales</span><span class="sxs-lookup"><span data-stu-id="ecd34-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="ecd34-112">У розділі «Аналіз аудиторії» виберіть **Адміністратор** > **Напрямки експорту**.</span><span class="sxs-lookup"><span data-stu-id="ecd34-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ecd34-113">В області **Dynamics 365 Sales** виберіть **Налаштувати**.</span><span class="sxs-lookup"><span data-stu-id="ecd34-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="ecd34-114">Задайте для свого призначення експорту ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="ecd34-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ecd34-115">Введіть URL-адресу Sales вашої організації в полі **Адреса сервера**.</span><span class="sxs-lookup"><span data-stu-id="ecd34-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="ecd34-116">У розділі **Обліковий запис адміністратора сервера** виберіть **Увійти** і оберіть обліковий запис Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ecd34-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="ecd34-117">Зіставте поле ІДЕНТИФІКАТОРА клієнта з ІДЕНТИФІКАТОРОМ контакту Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ecd34-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="ecd34-118">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="ecd34-118">Select **Next**.</span></span>

1. <span data-ttu-id="ecd34-119">Виберіть один або кілька сегментів.</span><span class="sxs-lookup"><span data-stu-id="ecd34-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="ecd34-120">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="ecd34-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ecd34-121">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="ecd34-121">Export the data</span></span>

<span data-ttu-id="ecd34-122">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ecd34-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ecd34-123">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ecd34-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]