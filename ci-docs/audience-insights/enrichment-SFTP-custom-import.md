---
title: Збагачення за допомогою настроюваного імпорту SFTP
description: Загальні відомості про збагачення настроюваного імпорту SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269631"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Збагачення профілів клієнтів з настроюваними даними (попередній перегляд)

Настроюваний імпорт за допомогою протоколу SFTP дозволяє імпортувати дані збагачення, які не мають обов’язково проходити процес уніфікації даних. Це гнучкий, безпечний і простий спосіб залучити дані. Настроюваний імпорт SFTP можна використовувати в поєднанні з [експортом SFTP](export-sftp.md), що дозволяє експортувати дані профілю клієнта, необхідні для збагачення. Потім дані можуть бути оброблені, збагачені і настроюваний імпорт SFTP можна використовувати, щоб повертати збагачені дані до можливості аналізу аудиторії Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Вимоги

Для настроювання настроюваного імпорту SFTP необхідно виконати зазначені нижче передумови.

- У вас є облікові дані користувача (ім'я користувача та пароль) для SFTP-розташування, з якого буде імпортовано дані.
- У вас є URL-адреса та номер порту (зазвичай 22) для хоста STFP.
- У вас є ім'я файлу та розташування файлу для імпортування на хості SFTP.
- У файлі *model.json* визначено схему для даних, які потрібно імпортувати. Цей файл має бути в тому самому каталозі, що й файл для імпорту.
- Ви маєте дозвіл [Адміністратор](permissions.md#administrator).

## <a name="configuration"></a>Конфігурація

1. Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.

1. На **плитці «Настроюваний імпорт SFTP»** виберіть **Збагатити дані**.

   > [!div class="mx-imgBorder"]
   > ![Плитка «Настроюваний імпорт SFTP»](media/SFTP_Custom_Import_tile.png "Плитка «Настроюваний імпорт SFTP»")

1. Виберіть **Почати** та надайте облікові дані та адресу сервера SFTP. Наприклад, sftp://mysftpserver.com: 22.

1. Введіть ім'я файлу, який містить дані та шлях до файлу на сервері SFTP, якщо він відсутній у кореневій папці.

1. Підтвердьте всі входи, вибравши **З'єднати з настроюваним імпортом**.

   > [!div class="mx-imgBorder"]
   > ![Спливаюче меню «Налаштування настроюваного імпорту SFTP»](media/SFTP_Custom_Import_Configuration_flyout.png "Спливаюче меню «Налаштування настроюваного імпорту SFTP»")

## <a name="defining-field-mappings"></a>Визначення зіставлень полів 

Каталог, який містить файл для імпортування на сервері SFTP, також має містити файл *model.json*. У цьому файлі буде визначено схему, яка використовуватиметься для імпортування даних. Схема має використовувати [Common Data Model](https://docs.microsoft.com/common-data-model/) для визначення зіставлення поля. Простий приклад файлу model.json має такий вигляд:

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

## <a name="enrichment-results"></a>Результати збагачення

Щоб почати процес збагачення, натисніть **Виконати** на панелі команд. Також можна дозволити системі автоматично запустити збагачення в рамках [запланованого оновлення](system.md#schedule-tab). Час обробки буде залежати від розміру даних, які необхідно імпортувати, а також підключення до сервера SFTP.

Після завершення процесу збагачення, ви можете переглянути нові імпортовані настроювані дані збагачення у розділі **Мої збагачення**. Крім того, можна знайти час останнього оновлення та кількість збагачених профілів.

Можна отримати доступ до докладного подання кожного збагаченого профілю, вибравши елемент **Переглянути збагачені дані**.

## <a name="next-steps"></a>Наступні кроки

Створюйте на основі збагачених даних клієнтів. Створюйте [сегменти](segments.md), [показники](measures.md) та [експорт даних](export-destinations.md) для надання персонального досвіду для клієнтів.




[!INCLUDE[footer-include](../includes/footer-banner.md)]