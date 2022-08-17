---
title: Збагачуйте профілі клієнтів за допомогою спеціального імпорту SFTP (попередній перегляд)
description: Загальні відомості про збагачення настроюваного імпорту SFTP.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237791"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Збагачуйте профілі клієнтів за допомогою спеціального імпорту SFTP (попередній перегляд)

Настроюваний імпорт за допомогою протоколу SFTP дозволяє імпортувати дані збагачення, які не мають обов’язково проходити процес уніфікації даних. Це гнучкий, безпечний і простий спосіб залучити дані. Настроюваний імпорт SFTP можна використовувати в поєднанні з [експортом SFTP](export-sftp.md), що дозволяє експортувати дані профілю клієнта, необхідні для збагачення. Потім дані можуть бути оброблені та збагачені, а спеціальний імпорт SFTP може бути використаний для повернення збагачених даних до Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>вимоги

- Відомо ім’я файлу та місцезнаходження (шлях) файлу, що імпортується на хості SFTP.

- Файл *model.json*, який визначає схему загальної моделі даних для імпортованих даних, доступний. Цей файл має бути в тому самому каталозі, що й файл для імпорту.

- Налаштовано SFTP-з’єднання [...](connections.md)[...](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Приклад схеми файлу

Каталог, який містить файл для імпортування на сервері SFTP, також має містити файл *model.json*. У цьому файлі буде визначено схему, яка використовуватиметься для імпортування даних. Щоб вказати зіставлення полів, ця схема має використовувати [Common Data Model](/common-data-model/). Простий приклад файлу model.json має такий вигляд:

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Налаштуйте підключення для настроюваного імпорту через SFTP

Ви повинні бути адміністратором [Customer](permissions.md#admin) Insights і мати облікові дані користувача, URL-адресу та номер порту для розташування SFTP, звідки потрібно імпортувати дані.

1. Виберіть елемент **Додати підключення** під час настроювання збагачення або перейдіть до **розділу Підключення** > **адміністратора** та натисніть кнопку **Настроїти** на плитці Імпорт.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Настроювана сторінка конфігурації підключення імпорту.":::

1. Введіть ім’я підключення.

1. Введіть дійсне ім’я користувача, пароль, URL-адресу хоста для сервера SFTP, на якому зберігаються дані, що підлягають імпортуванню.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Натисніть кнопку **Перевірити**, щоб перевірити конфігурацію, а потім натисніть кнопку **Зберегти**.

## <a name="configure-the-import"></a>Налаштуйте імпорт

1. Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.

1. Виберіть елемент **Збагатити мої дані** на користувацькій імпортній **плитці** SFTP.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Настроюваний імпорт через SFTP.":::

1. Перегляньте огляд і натисніть кнопку **Далі**.

1. Виберіть підключення. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. **Виберіть набір** даних клієнта та виберіть профіль або сегмент, який потрібно збагатити. Організація *клієнта* збагачує всі ваші профілі клієнтів, тоді як сегмент збагачує лише профілі клієнтів, що містяться в цьому сегменті.

1. Виберіть **Далі**.

1. **Введіть шлях** та **ім’я** файлу даних, який потрібно імпортувати.

1. Виберіть **Далі**.

1. Вкажіть ім’я **для** збагачення та ім’я **сутності виводу**.

1. Виберіть пункт **Зберегти збагачення** після того, як переглянете доступні вам варіанти вибору.

1. Натисніть кнопку **Виконати**, щоб розпочати процес збагачення, або близько, щоб повернутися на сторінку **Збагачення**.

## <a name="view-enrichment-results"></a>Переглянути результати збагачення

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Наступні кроки

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
