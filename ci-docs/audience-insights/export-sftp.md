---
title: Експорт даних Customer Insights до SFTP hosts
description: Дізнайтесь, як настроїти підключення до хоста SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643528"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="4900d-103">З’єднувач для SFTP (підготовча версія)</span><span class="sxs-lookup"><span data-stu-id="4900d-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="4900d-104">Використовуйте дані клієнтів у програмах сторонніх виробників, експортувавши їх до хосту протоколу SFTP.</span><span class="sxs-lookup"><span data-stu-id="4900d-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4900d-105">Вимоги</span><span class="sxs-lookup"><span data-stu-id="4900d-105">Prerequisites</span></span>

- <span data-ttu-id="4900d-106">Доступність хоста SFTP та відповідних облікових даних.</span><span class="sxs-lookup"><span data-stu-id="4900d-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="4900d-107">Підключення до SFTP</span><span class="sxs-lookup"><span data-stu-id="4900d-107">Connect to SFTP</span></span>

1. <span data-ttu-id="4900d-108">Відкрийте **Адміністрування** > **Призначення експорту**.</span><span class="sxs-lookup"><span data-stu-id="4900d-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4900d-109">У розділі **SFTP** виберіть **Настроювання**.</span><span class="sxs-lookup"><span data-stu-id="4900d-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="4900d-110">Дайте своєму призначенню ім’я, яке легко впізнати, в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="4900d-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="4900d-111">Надайте **Ім'я користувача**, **Пароль** і **Ім'я хосту** для вашого облікового запису SFTP.</span><span class="sxs-lookup"><span data-stu-id="4900d-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="4900d-112">Приклад. Якщо кореневу папку SFTP-сервера є /root/folder, а також потрібно експортувати дані в/root/Folder/ci_export_destination_folder, то хост має бути SFTP://< server_address >/ci_export_destination_folder.</span><span class="sxs-lookup"><span data-stu-id="4900d-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="4900d-113">Виберіть **Перевірити**, щоб перевірити підключення.</span><span class="sxs-lookup"><span data-stu-id="4900d-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="4900d-114">Після успішного підтвердження виберіть, чи потрібно експортувати дані як **Стиснуті** або **Розпаковані** і виберіть **Роздільник полів** для експортованих файлів.</span><span class="sxs-lookup"><span data-stu-id="4900d-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="4900d-115">Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.</span><span class="sxs-lookup"><span data-stu-id="4900d-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4900d-116">Натисніть **Далі**, щоб почати настроювання експорту.</span><span class="sxs-lookup"><span data-stu-id="4900d-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="4900d-117">Налаштування підключення</span><span class="sxs-lookup"><span data-stu-id="4900d-117">Configure the connection</span></span>

1. <span data-ttu-id="4900d-118">Виберіть **Атрибути користувача**, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="4900d-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="4900d-119">Можна експортувати один або кілька атрибутів.</span><span class="sxs-lookup"><span data-stu-id="4900d-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="4900d-120">Виберіть **Далі**.</span><span class="sxs-lookup"><span data-stu-id="4900d-120">Select **Next**.</span></span>

1. <span data-ttu-id="4900d-121">Виберіть сегменти, які потрібно експортувати.</span><span class="sxs-lookup"><span data-stu-id="4900d-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="4900d-122">Виберіть **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="4900d-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="4900d-123">Експорт даних</span><span class="sxs-lookup"><span data-stu-id="4900d-123">Export the data</span></span>

<span data-ttu-id="4900d-124">Ви можете [експортувати дані вручну](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4900d-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="4900d-125">Експорт також запускатиметься під час кожного [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4900d-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4900d-126">Конфіденційність і відповідність даних</span><span class="sxs-lookup"><span data-stu-id="4900d-126">Data privacy and compliance</span></span>

<span data-ttu-id="4900d-127">Під час увімкнення Dynamics 365 Customer Insights для передавання даних до SFTP Technologies можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними.</span><span class="sxs-lookup"><span data-stu-id="4900d-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4900d-128">Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб напрям експорту відповідав будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас.</span><span class="sxs-lookup"><span data-stu-id="4900d-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4900d-129">Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4900d-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4900d-130">Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити цей напрям експорту, щоб припинити користуватися цією функцією.</span><span class="sxs-lookup"><span data-stu-id="4900d-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
