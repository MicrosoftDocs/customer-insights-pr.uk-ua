---
title: Збагачення за допомогою настроюваного імпорту SFTP
description: Загальні відомості про збагачення настроюваного імпорту SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568519"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="f499b-103">Збагачення профілів клієнтів з настроюваними даними (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="f499b-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="f499b-104">Настроюваний імпорт за допомогою протоколу SFTP дозволяє імпортувати дані збагачення, які не мають обов’язково проходити процес уніфікації даних.</span><span class="sxs-lookup"><span data-stu-id="f499b-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="f499b-105">Це гнучкий, безпечний і простий спосіб залучити дані.</span><span class="sxs-lookup"><span data-stu-id="f499b-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="f499b-106">Настроюваний імпорт SFTP можна використовувати в поєднанні з [експортом SFTP](export-sftp.md), що дозволяє експортувати дані профілю клієнта, необхідні для збагачення.</span><span class="sxs-lookup"><span data-stu-id="f499b-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="f499b-107">Потім дані можуть бути оброблені, збагачені і настроюваний імпорт SFTP можна використовувати, щоб повертати збагачені дані до можливості аналізу аудиторії Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f499b-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f499b-108">Вимоги</span><span class="sxs-lookup"><span data-stu-id="f499b-108">Prerequisites</span></span>

<span data-ttu-id="f499b-109">Для настроювання настроюваного імпорту SFTP необхідно виконати зазначені нижче передумови.</span><span class="sxs-lookup"><span data-stu-id="f499b-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f499b-110">У вас є облікові дані користувача (ім'я користувача та пароль) для SFTP-розташування, з якого буде імпортовано дані.</span><span class="sxs-lookup"><span data-stu-id="f499b-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="f499b-111">У вас є URL-адреса та номер порту (зазвичай 22) для хоста STFP.</span><span class="sxs-lookup"><span data-stu-id="f499b-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="f499b-112">У вас є ім'я файлу та розташування файлу для імпортування на хості SFTP.</span><span class="sxs-lookup"><span data-stu-id="f499b-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="f499b-113">У файлі *model.json* визначено схему для даних, які потрібно імпортувати.</span><span class="sxs-lookup"><span data-stu-id="f499b-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="f499b-114">Цей файл має бути в тому самому каталозі, що й файл для імпорту.</span><span class="sxs-lookup"><span data-stu-id="f499b-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="f499b-115">Ви маєте дозвіл [Адміністратор](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="f499b-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="f499b-116">Конфігурація</span><span class="sxs-lookup"><span data-stu-id="f499b-116">Configuration</span></span>

1. <span data-ttu-id="f499b-117">Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.</span><span class="sxs-lookup"><span data-stu-id="f499b-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f499b-118">На **плитці «Настроюваний імпорт SFTP»** виберіть **Збагатити дані**.</span><span class="sxs-lookup"><span data-stu-id="f499b-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f499b-119">![Плитка «Настроюваний імпорт SFTP»](media/SFTP_Custom_Import_tile.png "Плитка «Настроюваний імпорт SFTP»")</span><span class="sxs-lookup"><span data-stu-id="f499b-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="f499b-120">Виберіть **Почати** та надайте облікові дані та адресу сервера SFTP.</span><span class="sxs-lookup"><span data-stu-id="f499b-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="f499b-121">Наприклад, sftp://mysftpserver.com: 22.</span><span class="sxs-lookup"><span data-stu-id="f499b-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="f499b-122">Введіть ім'я файлу, який містить дані та шлях до файлу на сервері SFTP, якщо він відсутній у кореневій папці.</span><span class="sxs-lookup"><span data-stu-id="f499b-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="f499b-123">Підтвердьте всі входи, вибравши **З'єднати з настроюваним імпортом**.</span><span class="sxs-lookup"><span data-stu-id="f499b-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f499b-124">![Спливаюче меню «Налаштування настроюваного імпорту SFTP»](media/SFTP_Custom_Import_Configuration_flyout.png "Спливаюче меню «Налаштування настроюваного імпорту SFTP»")</span><span class="sxs-lookup"><span data-stu-id="f499b-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="f499b-125">Визначення зіставлень полів</span><span class="sxs-lookup"><span data-stu-id="f499b-125">Defining field mappings</span></span> 

<span data-ttu-id="f499b-126">Каталог, який містить файл для імпортування на сервері SFTP, також має містити файл *model.json*.</span><span class="sxs-lookup"><span data-stu-id="f499b-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="f499b-127">У цьому файлі буде визначено схему, яка використовуватиметься для імпортування даних.</span><span class="sxs-lookup"><span data-stu-id="f499b-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="f499b-128">Схема має використовувати [Common Data Model](https://docs.microsoft.com/common-data-model/) для визначення зіставлення поля.</span><span class="sxs-lookup"><span data-stu-id="f499b-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="f499b-129">Простий приклад файлу model.json має такий вигляд:</span><span class="sxs-lookup"><span data-stu-id="f499b-129">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="f499b-130">Результати збагачення</span><span class="sxs-lookup"><span data-stu-id="f499b-130">Enrichment results</span></span>

<span data-ttu-id="f499b-131">Щоб почати процес збагачення, натисніть **Виконати** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="f499b-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f499b-132">Також можна дозволити системі автоматично запустити збагачення в рамках [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f499b-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f499b-133">Час обробки буде залежати від розміру даних, які необхідно імпортувати, а також підключення до сервера SFTP.</span><span class="sxs-lookup"><span data-stu-id="f499b-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="f499b-134">Після завершення процесу збагачення, ви можете переглянути нові імпортовані настроювані дані збагачення у розділі **Мої збагачення**.</span><span class="sxs-lookup"><span data-stu-id="f499b-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="f499b-135">Крім того, можна знайти час останнього оновлення та кількість збагачених профілів.</span><span class="sxs-lookup"><span data-stu-id="f499b-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f499b-136">Можна отримати доступ до докладного подання кожного збагаченого профілю, вибравши елемент **Переглянути збагачені дані**.</span><span class="sxs-lookup"><span data-stu-id="f499b-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f499b-137">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="f499b-137">Next steps</span></span>

<span data-ttu-id="f499b-138">Створюйте на основі збагачених даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="f499b-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f499b-139">Створюйте [сегменти](segments.md), [показники](measures.md) та [експорт даних](export-destinations.md) для надання персонального досвіду для клієнтів.</span><span class="sxs-lookup"><span data-stu-id="f499b-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


