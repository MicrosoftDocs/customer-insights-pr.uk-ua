---
title: Експорт даних у маркетингову хмару Salesforce (попередній перегляд)
description: Дізнайтеся про те, як налаштувати підключення та експортувати дані до хмари Salesforce Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197063"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Експорт даних у маркетингову хмару Salesforce (попередній перегляд)

Використовуйте дані клієнтів у хмарі Salesforce Marketing способом експорту через розташування Secure File Transfer Protocol (SFTP).

## <a name="prerequisites"></a>вимоги

- Хост [SFTP для Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) і відповідні облікові дані адміністратора.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Налаштуйте підключення до маркетингової хмари Salesforce

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть **Додати з'єднання** та виберіть **Маркетингова хмара Salesforce**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Укажіть **Ім'я користувача**, **Пароль**, **Ім'я хосту** та **Папку експорту** для вашого облікового запису SFTP.

1. Виберіть **Перевірити**, щоб перевірити підключення.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть Додати **експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу SFTP. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім'я експорту.

1. Виберіть, чи бажаєте ви експортувати дані **стиснутими за допомогою Gzip** або **без стискання**, а також вкажіть **роздільник полів** для експортованих файлів.

1. Виберіть об'єкти, наприклад сегменти, які потрібно експортувати.

   > [!NOTE]
   > Кожна виділена сутність буде розділена максимум на п'ять вихідних файлів під час експорту.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Імпортуйте дані Customer Insights із розташування SFTP до хмари Salesforce Marketing

1. Створіть [розширення даних у хмарі Salesforce Marketing](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), щоб імпортувати файл даних Customer Insights із розташування SFTP.

2. [Імпортуйте дані з розташування SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) до розширення даних хмари Salesforce Marketing.

3. Налаштуйте автоматизацію, щоб імпортувати дані до розширень даних. Дізнайтеся докладніше про [автоматизацію перенесення файлів і заплановану автоматизацію](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Визначте [автоматизацію перенесення файлів](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) або [заплановану автоматизацію](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Далі наведено приклад [автоматизації за допомогою SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
