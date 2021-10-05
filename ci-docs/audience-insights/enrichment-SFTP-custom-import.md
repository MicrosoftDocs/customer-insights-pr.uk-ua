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
ms.openlocfilehash: b67aa7477033222b0bc9512a962a1580edd973b4882ce925620ff5ec14f83fe3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032737"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Збагачення профілів клієнтів з настроюваними даними (попередній перегляд)

Настроюваний імпорт за допомогою протоколу SFTP дозволяє імпортувати дані збагачення, які не мають обов’язково проходити процес уніфікації даних. Це гнучкий, безпечний і простий спосіб залучити дані. Настроюваний імпорт SFTP можна використовувати в поєднанні з [експортом SFTP](export-sftp.md), що дозволяє експортувати дані профілю клієнта, необхідні для збагачення. Потім дані можна обробляти та збагачувати, при цьому можна використовувати настроюваний імпорт SFTP, щоб повернути збагачені дані й зробити їх доступними для аналітичних оглядів за допомогою функції Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Вимоги

Для настроювання настроюваного імпорту SFTP необхідно виконати зазначені нижче передумови.

- Для імпорту вузла SFTP у вас є ім’я та розташування (шлях) файлу.
- Є файл *model.json* у якому є [схема Common Data Model](/common-data-model/) для даних, які підлягають імпортуванню. Цей файл має бути в тому самому каталозі, що й файл для імпорту.
- Підключення SFTP вже налаштоване адміністратором *або* у вас є права [адміністратора](permissions.md#administrator). Для розташування SFTP, з якого потрібно імпортувати дані, вам буде потрібно отримати потрібні облікові дані користувача, URL-адресу й номер порту для розташування SFTP, із якого ви бажаєте імпортувати дані.


## <a name="configure-the-import"></a>Налаштуйте імпорт

1. Перейдіть в меню **Дані** > **Збагачення** і виберіть вкладку **Виявлення**.

1. У розділі **Настроюваний імпорт через SFTP** виберіть **Збагатити мої дані**, потім виберіть пункт **Почати**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Настроюваний імпорт через SFTP.":::

1. Виберіть [підключення](connections.md) з розкривного списку. Якщо жодне підключення недоступне, зверніться до адміністратора. Якщо ви є адміністратором, ви можете створити підключення способом вибору пункту **Додати підключення**, потім вибору з розкривного списку пункту **Настроюваний імпорт через SFTP**.

1. Виберіть **Підключитися до настроюваного імпорту**, щоб підтвердити вибране підключення.

1.  Виберіть пункт **Далі**, потім введіть **Шлях** та **Ім’я файлу** даних, який ви бажаєте імпортувати.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Знімок екрану введення розташування даних.":::

1. Виберіть **Далі**, потім введіть ім’я збагачення та ім'я вихідної сутності. 

1. Виберіть пункт **Зберегти збагачення** після того, як переглянете доступні вам варіанти вибору.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Налаштуйте підключення для настроюваного імпорту через SFTP 

Щоб налаштувати підключення ви маєте бути адміністратором. Виберіть **Додати підключення** під час налаштування збагачення *або* перейдіть до розділу **Адміністратор** > **Підключення** й виберіть пункт **Налаштувати** на плитці настроюваного імпорту.

1. Введіть ім'я підключення в полі **Коротке ім’я**.

1. Введіть дійсне ім’я користувача, пароль, URL-адресу хоста для сервера SFTP, на якому зберігаються дані, що підлягають імпортуванню.

1. Перегляньте та прийміть умови **конфіденційності й відповідності даних**, установивши прапорець **Приймаю**.

1. Виберіть **Підтвердити**, щоб підтвердити конфігурацію.

1. Після завершення перевірки підключення можна зберегти, вибравши пункт **Зберегти**.

   > [!div class="mx-imgBorder"]
   > ![Сторінка налаштування підключення Experian.](media/enrichment-SFTP-connection.png "Сторінка налаштування підключення Experian")


## <a name="defining-field-mappings"></a>Визначення зіставлень полів 

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

Створюйте на основі збагачених даних клієнтів. Створюйте [сегменти](segments.md) й [міри](measures.md), а також [експортуйте дані](export-destinations.md) задля забезпечення індивідуальної взаємодії для своїх клієнтів.

[!INCLUDE[footer-include](../includes/footer-banner.md)]