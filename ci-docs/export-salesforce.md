---
title: Експорт даних у маркетингову хмару Salesforce (попередній перегляд)
description: Дізнайтеся про те, як налаштувати підключення та експортувати дані до хмари Salesforce Marketing.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082628"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Експорт даних у маркетингову хмару Salesforce (попередній перегляд)

Використовуйте дані клієнтів у хмарі Salesforce Marketing способом експорту через розташування Secure File Transfer Protocol (SFTP).

## <a name="prerequisites-for-connection"></a>Попередні вимоги для підключення

- Доступність хост-комп’ютера SFTP і відповідних облікових даних адміністратора. [Як налаштувати розташування SFTP для хмари Salesforce Marketing](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Налаштуйте підключення до хмари Salesforce Marketing

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть пункт **Додати підключення**, потім виберіть розділ **Хмара Salesforce Marketing**, щоб налаштувати підключення.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. Якщо не вжити жодних дій, за замовчуванням це будуть Адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Укажіть **Ім'я користувача**, **Пароль**, **Ім'я хосту** та **Папку експорту** для вашого облікового запису SFTP.

1. Виберіть **Перевірити**, щоб перевірити підключення.

1. Виберіть **Приймаю**, щоб підтвердити **Відповідність вимогам і конфіденційність даних**.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

Ви можете налаштувати цей експорт, якщо у вас є доступ до підключень такого типу. Додаткові відомості: [Дозволи, необхідні для налаштування експорту](export-destinations.md#set-up-a-new-export).

1. Відкрийте **Дані** > **Експорти**.

1. Щоб створити новий експорт, виберіть **Додати призначення**.

1. У полі **Підключення для експорту** виберіть підключення з розділу SFTP. Якщо ім'я цього розділу не відображається, це означає, що для вас немає жодного доступного підключення цього типу.

1. Виберіть, чи бажаєте ви експортувати дані **стиснутими за допомогою Gzip** або **без стискання**, а також вкажіть **роздільник полів** для експортованих файлів.

1. Виберіть сутності, наприклад, сегменти, які необхідно експортувати.

   > [!NOTE]
   > Кожна вибрана сутність буде розділена на щонайбільше п'ять вихідних файлів під час експорту. 

1. Виберіть **Зберегти**.

При збереженні експорт не запуститься негайно.

Експорт виконується під час кожного [запланованого оновлення](system.md#schedule-tab). Також можна [експортувати дані неавтоматично](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Імпортуйте дані Customer Insights із розташування SFTP до хмари Salesforce Marketing

1. Створіть [розширення даних у хмарі Salesforce Marketing](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), щоб імпортувати файл даних Customer Insights із розташування SFTP.

2. [Імпортуйте дані з розташування SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) до розширення даних хмари Salesforce Marketing. 

3. Налаштуйте автоматизацію, щоб імпортувати дані до розширень даних. Дізнайтеся докладніше про [автоматизацію перенесення файлів і заплановану автоматизацію](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Визначте [автоматизацію перенесення файлів](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) або [заплановану автоматизацію](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Далі наведено приклад [автоматизації за допомогою SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Конфіденційність і відповідність даних

Під час увімкнення Dynamics 365 Customer Insights для передавання даних до SFTP Technologies можна перенести дані за межі нормативного регіону до Dynamics 365 Customer Insights, включно з потенційно конфіденційними даними, наприклад особистими даними. Корпорація Microsoft передаватиме ці дані відповідно до ваших указівок, але всю відповідальність за те, щоб напрям експорту відповідав будь-яким вашим вимогам щодо конфіденційності або безпеки, покладено на вас. Для отримання додаткових відомостей див. розділ [Декларація про конфіденційність Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Ваш адміністратор Dynamics 365 Customer Insights може будь-коли видалити це призначення експорту, щоб припинити користуватися цією функцією.

[!INCLUDE [footer-include](includes/footer-banner.md)]
