---
title: Створення та настроювання платної ліцензії Customer Insights
description: Кроки, які треба виконати для отримання ліцензованої передплати на Dynamics 365 Customer Insights та налаштувати її.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034477"
---
# <a name="get-started-with-a-paid-subscription"></a>Початок роботи з оплаченою передплатою

У цій статті пояснюється, як створити нове середовище після придбання передплати на Dynamics 365 Customer Insights в організації. Якщо ви хочете придбати Customer Insights, наші контактні особи перелічені на [веб-сайті Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Якщо вам потрібна ознайомлювальна послуга та функції, див. [Настроювання ознайомлювального середовища](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Створення середовища в наявній організації

Після придбання ліцензії на передплату для Customer Insights глобальний адміністратор клієнта Microsoft 365 отримує повідомлення електронної пошти, яке запрошує їх створити середовище. Щоб почати, перейдіть до [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start). 

Customer Insights не ліцензовано для кожного користувача, тому він не відображатимуться в області «Ліцензії». Якщо вам потрібна ліцензія у центрі адміністрування Microsoft 365, перейдіть до розділу **Ваші продукти**. 

> [!NOTE]
> Організації можуть створити *два* середовища для кожної ліцензії Customer Insights. Якщо ваша організація придбала ліцензію більше одного разу, [зверніться до нашої робочої групи служби підтримки клієнтів](https://go.microsoft.com/fwlink/?linkid=2079641), щоб збільшити кількість доступних середовищ. Для отримання додаткових відомостей про виробничу спроможність і виробничу спроможність надбудови, завантажте [посібник із ліцензування Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Щоб створити середовище, виконайте наведені нижче кроки.

1. У діалоговому вікні **Створення середовища** виберіть пункт **Нове середовище**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Діалог для створення нового середовища Customer Insights.":::

   Радимо почати настроювання середовища з нуля. Проте, якщо ви адміністратор або учасник ознайомлювального середовища, можна [копіювати дані з іншого середовища](manage-environments.md#copy-the-environment-configuration), вибравши параметр **Копіювати з наявного середовища**. Відобразиться список усіх наявних середовищ в організації, з яких можна скопіювати дані.

1. Вкажіть нижчезазначені відомості.
   - **Ім'я**: ім'я цього середовища. Це поле буде вже заповнено, якщо ви копіювали з наявного середовища, але ці значення можна змінити.
   - **Регіон**: розташування, в якому розгорнуто та розміщено службу.
   - **Тип**: виберіть тип середовища, яке потрібно створити: виробниче або ізольоване. У ізольованому середовищі не можна планувати заплановане оновлення даних і їх призначено для попередньої реалізації та тестування.
   
1. Також можна вибрати **Додаткові параметри**.

   - **Зберегти всі дані до**: указує місце, в якому потрібно зберігати вихідні дані, створені з Customer Insights. У вас буде два параметри: **Сховище Customer Insights** (це Azure Data Lake під керуванням робочої групи Customer Insights) і **Azure Data Lake Storage** (ваше власне сховище Azure Data Lake Storage). За замовчуванням вибрано сховище Customer Insights.

     > [!NOTE]
     > При збереженні даних у Azure Data Lake Storage ви погоджуєтеся з тим, що дані будуть передаватися до відповідного географічного розташування для облікового запису сховища Azure та зберігатися в ньому. Це географічне розташування може відрізнятися від розташування, в якому зберігаються дані, передані до Dynamics 365 Customer Insights. [Дізнайтеся докладніше в центрі безпеки та конфіденційності Microsoft.](https://www.microsoft.com/trust-center)
     >
     > Наразі оброблені сутності з потоків даних Power BI зберігаються у керованому Microsoft Dataverse Data Lake. 
     > 
     > Ми підтримуємо облікові записи Azure Data Lake Storage із одного й того самого регіону Azure, який ви вибрали при створенні середовища. 
     > 
     > Ми підтримуємо лише облікові записи Azure Data Lake Storage, у яких увімкнений ієрархічний простір імен.


   - Автентифікацію для Azure Data Lake Storage можна вибирати з двох різних параметрів: параметра на основі ресурсу й параметра на основі передплати. Для отримання додаткових відомостей див. розділ [Підключення аналізу аудиторії до облікового запису Azure Data Lake Storage Gen2 за допомогою принципала служби Azure](connect-service-principal.md). Ім'я **Контейнера** змінити не можна, і воно буде `customerinsights`.
   
   - Якщо потрібно використовувати [готові моделі](predictions-overview.md#out-of-box-models), налаштуйте спільне використання даних з Microsoft Dataverse або ввімкніть передавання даних з локальних джерел даних, надайте URL-адресу середовища Microsoft Dataverse у розділі **налаштування спільного використання даних із Microsoft Dataverse і вмикання додаткових можливостей**. Виберіть **Увімкнути спільний доступ до даних**, щоб надати спільний доступ до вихідних даних Customer Insights, використовуючи службу керованого Data Lake Microsoft Dataverse.

     > [!NOTE]
     > - Спільний доступ до даних за допомогою служби керованого Data Lake Microsoft Dataverse наразі не підтримується, якщо ви зберігаєте усі дані у власному Azure Data Lake Storage.
     > - [Прогнозування відсутніх значень у сутності](predictions.md) наразі не підтримується, якщо увімкнуто спільний доступ до даних за допомогою керованого Data Lake Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Параметри конфігурації для ввімкнення спільного доступу до даних за допомогою Microsoft Dataverse.":::

   Коли системні процеси, як-от передавання даних, завершені, система створює відповідні папки в обліковому записі вказаного сховища. Файли даних і файли model.json створюються та додаються до папок залежно від імені процесу.

   У разі створення кількох середовищ Customer Insights і вибору збереження вихідних сутностей з цих середовищ у вашому обліковому записі сховища, окремі папки створюватимуться для кожного середовища з ci_ <environmentid> в контейнері.

1. Натисніть **Створити**, щоб налаштувати середовище. 

## <a name="configure-an-environment"></a>Налаштування середовища

Перегляньте наведені нижче статті, які допоможуть почати настроювання Customer Insights. 

- [Додайте інших користувачів і призначте дозволи](permissions.md).
- [Обробіть джерела даних](data-sources.md) і запустіть ї через [процес уніфікації даних](data-unification.md), щоб отримати [уніфіковані профілі клієнтів](customer-profiles.md).
- [Збагатіть уніфіковані профілі клієнтів](enrichment-hub.md) або [запустіть прогнозні моделі](predictions-overview.md).
- Створіть [сегменти](segments.md) для групування клієнтів і KPI оглядів [вимірювань](measures.md).
- Настройте [підключення](connections.md) та [експорти](export-destinations.md) для обробки вкладених наборів даних у інших програмах.