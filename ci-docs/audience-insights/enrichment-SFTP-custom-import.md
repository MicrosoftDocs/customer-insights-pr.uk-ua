---
title: Збагачення за допомогою настроюваного імпорту SFTP
description: Загальні відомості про збагачення настроюваного імпорту SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896306"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="dc90b-103">Збагачення профілів клієнтів з настроюваними даними (попередній перегляд)</span><span class="sxs-lookup"><span data-stu-id="dc90b-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="dc90b-104">Настроюваний імпорт за протоколом безпечної передачі даних (SFTP) дозволяє імпортувати дані, при цьому немає необхідності проходити процес уніфікації даних.</span><span class="sxs-lookup"><span data-stu-id="dc90b-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="dc90b-105">Це гнучкий, безпечний і простий спосіб залучити дані.</span><span class="sxs-lookup"><span data-stu-id="dc90b-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="dc90b-106">Настроюваний імпорт SFTP можна використовувати в поєднанні з [експортом SFTP](export-sftp.md), що дозволяє експортувати дані профілю клієнта, необхідні для збагачення.</span><span class="sxs-lookup"><span data-stu-id="dc90b-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="dc90b-107">Потім дані можуть бути оброблені, збагачені і настроюваний імпорт SFTP можна використовувати, щоб повертати збагачені дані до можливості аналізу аудиторії Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dc90b-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dc90b-108">Вимоги</span><span class="sxs-lookup"><span data-stu-id="dc90b-108">Prerequisites</span></span>

<span data-ttu-id="dc90b-109">Для настроювання настроюваного імпорту SFTP необхідно виконати зазначені нижче передумови.</span><span class="sxs-lookup"><span data-stu-id="dc90b-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="dc90b-110">Для імпортування на вузол SFTP у вас є ім’я та розташування (шлях) файлу, який підлягає імпортуванню.</span><span class="sxs-lookup"><span data-stu-id="dc90b-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="dc90b-111">Є файл *model.json* у якому є [схема Common Data Model](/common-data-model/) для даних, які підлягають імпортуванню.</span><span class="sxs-lookup"><span data-stu-id="dc90b-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="dc90b-112">Цей файл має бути в тому самому каталозі, що й файл для імпорту.</span><span class="sxs-lookup"><span data-stu-id="dc90b-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="dc90b-113">Підключення SFTP вже налаштоване адміністратором *або* у вас є права [адміністратора](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="dc90b-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="dc90b-114">Для розташування SFTP, з якого потрібно імпортувати дані, вам буде потрібно отримати потрібні облікові дані користувача, URL-адресу й номер порту для розташування SFTP, із якого ви бажаєте імпортувати дані.</span><span class="sxs-lookup"><span data-stu-id="dc90b-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="dc90b-115">Налаштуйте імпорт</span><span class="sxs-lookup"><span data-stu-id="dc90b-115">Configure the import</span></span>

1. <span data-ttu-id="dc90b-116">Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.</span><span class="sxs-lookup"><span data-stu-id="dc90b-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="dc90b-117">У розділі **Настроюваний імпорт через SFTP** виберіть **Збагатити мої дані**, потім виберіть пункт **Почати**.</span><span class="sxs-lookup"><span data-stu-id="dc90b-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Настроюваний імпорт через SFTP.":::

1. <span data-ttu-id="dc90b-119">Виберіть [підключення](connections.md) з розкривного списку.</span><span class="sxs-lookup"><span data-stu-id="dc90b-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="dc90b-120">Якщо жодне підключення недоступне, зверніться до адміністратора.</span><span class="sxs-lookup"><span data-stu-id="dc90b-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="dc90b-121">Якщо ви є адміністратором, ви можете створити підключення способом вибору пункту **Додати підключення**, потім у розкривному списку виберіть пункт **Настроюваний імпорт через SFTP**.</span><span class="sxs-lookup"><span data-stu-id="dc90b-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="dc90b-122">Виберіть **Підключитися до настроюваного імпорту**, щоб підтвердити вибране підключення.</span><span class="sxs-lookup"><span data-stu-id="dc90b-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="dc90b-123">Виберіть **Далі**, введіть **Ім’я файлу** та **Шлях** файлу даних, який ви бажаєте імпортувати.</span><span class="sxs-lookup"><span data-stu-id="dc90b-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Знімок екрану введення розташування даних.":::

1. <span data-ttu-id="dc90b-125">Виберіть **Далі**, потім введіть ім’я збагачення та ім'я вихідної сутності.</span><span class="sxs-lookup"><span data-stu-id="dc90b-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="dc90b-126">Виберіть пункт **Зберегти збагачення** після того, як переглянете доступні вам варіанти вибору.</span><span class="sxs-lookup"><span data-stu-id="dc90b-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="dc90b-127">Налаштуйте підключення для настроюваного імпорту через SFTP</span><span class="sxs-lookup"><span data-stu-id="dc90b-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="dc90b-128">Щоб налаштувати підключення ви маєте бути адміністратором.</span><span class="sxs-lookup"><span data-stu-id="dc90b-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="dc90b-129">Виберіть **Додати підключення** під час налаштування збагачення *або* перейдіть до розділу **Адміністратор** > **Підключення** й виберіть пункт **Налаштувати** на плитці настроюваного імпорту.</span><span class="sxs-lookup"><span data-stu-id="dc90b-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="dc90b-130">Введіть ім'я підключення в полі **Коротке ім’я**.</span><span class="sxs-lookup"><span data-stu-id="dc90b-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="dc90b-131">Введіть дійсне ім'я користувача, пароль і URL-адресу сервера STFP, на якому перебувають дані, що підлягають імпортуванню.</span><span class="sxs-lookup"><span data-stu-id="dc90b-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="dc90b-132">Перегляньте та прийміть умови **конфіденційності й відповідності даних**, установивши прапорець **Приймаю**.</span><span class="sxs-lookup"><span data-stu-id="dc90b-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="dc90b-133">Виберіть **Підтвердити**, щоб підтвердити конфігурацію.</span><span class="sxs-lookup"><span data-stu-id="dc90b-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="dc90b-134">Після завершення перевірки підключення можна зберегти, натиснувши **Зберегти**.</span><span class="sxs-lookup"><span data-stu-id="dc90b-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="dc90b-135">![Сторінка налаштування підключення Experian.](media/enrichment-SFTP-connection.png "Сторінка налаштування підключення Experian")</span><span class="sxs-lookup"><span data-stu-id="dc90b-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="dc90b-136">Визначення зіставлень полів</span><span class="sxs-lookup"><span data-stu-id="dc90b-136">Defining field mappings</span></span> 

<span data-ttu-id="dc90b-137">Каталог, який містить файл для імпортування на сервері SFTP, також має містити файл *model.json*.</span><span class="sxs-lookup"><span data-stu-id="dc90b-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="dc90b-138">У цьому файлі буде визначено схему, яка використовуватиметься для імпортування даних.</span><span class="sxs-lookup"><span data-stu-id="dc90b-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="dc90b-139">Схема має використовувати [Common Data Model](/common-data-model/) для визначення зіставлення поля.</span><span class="sxs-lookup"><span data-stu-id="dc90b-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="dc90b-140">Простий приклад файлу model.json має такий вигляд:</span><span class="sxs-lookup"><span data-stu-id="dc90b-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="dc90b-141">Результати збагачення</span><span class="sxs-lookup"><span data-stu-id="dc90b-141">Enrichment results</span></span>

<span data-ttu-id="dc90b-142">Щоб почати процес збагачення, натисніть **Виконати** на панелі команд.</span><span class="sxs-lookup"><span data-stu-id="dc90b-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="dc90b-143">Також можна дозволити системі автоматично запустити збагачення в рамках [запланованого оновлення](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dc90b-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dc90b-144">Час обробки буде залежати від розміру даних, які необхідно імпортувати, а також підключення до сервера SFTP.</span><span class="sxs-lookup"><span data-stu-id="dc90b-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="dc90b-145">Після завершення процесу збагачення, ви можете переглянути нові імпортовані настроювані дані збагачення у розділі **Мої збагачення**.</span><span class="sxs-lookup"><span data-stu-id="dc90b-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="dc90b-146">Крім того, можна знайти час останнього оновлення та кількість збагачених профілів.</span><span class="sxs-lookup"><span data-stu-id="dc90b-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="dc90b-147">Можна отримати доступ до докладного подання кожного збагаченого профілю, вибравши елемент **Переглянути збагачені дані**.</span><span class="sxs-lookup"><span data-stu-id="dc90b-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dc90b-148">Наступні кроки</span><span class="sxs-lookup"><span data-stu-id="dc90b-148">Next steps</span></span>

<span data-ttu-id="dc90b-149">Створюйте на основі збагачених даних клієнтів.</span><span class="sxs-lookup"><span data-stu-id="dc90b-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dc90b-150">Створюйте [сегменти](segments.md), [показники](measures.md) та [експорт даних](export-destinations.md) для надання персонального досвіду для клієнтів.</span><span class="sxs-lookup"><span data-stu-id="dc90b-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
