---
title: Запуск зразка SDK для вебу
description: Дізнайтеся, як персоналізувати та запустити зразок SDK для вебу.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606288"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Запуск зразка SDK для вебу для засобу аналітичних висновків щодо взаємодії Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Бібліотекою SDK для вебу засобу аналітичних висновків щодо взаємодії є бібліотека JavaScript зі зразком коду, який ви можете використовувати на своєму веб-сайті.

## <a name="prerequisites"></a>Вимоги

- Інсталюйте [код Visual Studio](https://code.visualstudio.com/).
- [Інсталюйте розширення Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) у код Visual Studio та ознайомтеся з тим, як запустити Live Server.
- Потрібно мати [робочу область «Статистика взаємодії»](create-workspace.md)

## <a name="run-sample"></a>Запуск зразку

1. [Завантаження зразка SDK для вебу](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Розпакуйте стиснутий файл `ei_websdk_sample.zip`.

1. Відкрийте розпаковану папку в коді Visual Studio.

1. Перейдіть на портал «Аналітика взаємодії» для робочої області. Виберіть **Адміністратор** > **Робоча область** і потім натисніть **Посібник із установлення**. Дотримуйтеся першого параметра та виберіть **«Копіювати код»** для копіювання фрагменту коду JavaScript.

1. У цьому файлі `ei_websdk_sample.html` вставте фрагмент коду, щойно скопійований у цьому рядку.

   - < – ВСТАВТЕ ФРАГМЕНТ КОДУ JAVASCRIPT З ПОРТАЛУ АНАЛІТИКИ ВЗАЄМОДІЇ НИЖЧЕ ЦЬОГО РЯДКА – >

1. Відкрийте файл `ei_websdk_sample.html` за допомогою Live Server у коді Visual Studio, вибравши елемент **Активувати** з рядку стану.

1. Під час відкриття сторінки має бути автоматично надіслана подія перегляду. Натискання на будь-яку з кнопок на сторінці надсилатиме події дії. Кнопка **Відстежувати події** також надсилатиме настроювані події. Якщо натиснути кнопку **Перейти до Bing**, буде надіслано подію дії, перш ніж перейти до веб-сайту Bing.

1. Погляньте на події, що передаються, коли ви переходите до своєї робочої області. Ця робоча область пов’язана з ключем прийому, введеному на Кроці 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
