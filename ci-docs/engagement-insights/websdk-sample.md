---
title: Запуск зразка SDK для вебу
description: Дізнайтеся, як персоналізувати та запустити зразок SDK для вебу.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036628"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Запуск зразка SDK для вебу для засобу аналітичних висновків щодо взаємодії Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Бібліотекою SDK для вебу засобу аналітичних висновків щодо взаємодії є бібліотека JavaScript зі зразком коду, який ви можете використовувати на своєму веб-сайті.

## <a name="prerequisites"></a>Вимоги

- Інсталюйте [код Visual Studio](https://code.visualstudio.com/).
- [Інсталюйте розширення Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) у код Visual Studio та ознайомтеся з тим, як запустити Live Server.
- Ви повинні мати [ключ прийому](instrument-website.md).

## <a name="run-sample"></a>Запуск зразку

1. [Завантаження зразка SDK для вебу](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Розпакуйте стиснутий файл `ei_websdk_sample.zip`.

1. Відкрийте розпаковану папку в коді Visual Studio.

1. У файлі `ei_websdk_sample.html` замініть рядок “INGESTION_KEY” своїм ключем прийому з порталу засобу аналітичних висновків щодо взаємодії і рядок “NAME” з глобальним іменем, з яким потрібно створити SDK. Переконайтеся, що ви замінили всі входження.

1. Відкрийте файл `ei_websdk_sample.html` за допомогою Live Server у коді Visual Studio, вибравши елемент **Активувати** з рядку стану.

1. Під час відкриття сторінки має бути автоматично надіслана подія перегляду. Натискання на будь-яку з кнопок на сторінці надсилатиме події дії. Кнопка **Відстежувати події** також надсилатиме настроювані події. Якщо натиснути кнопку **Перейти до Bing**, буде надіслано подію дії, перш ніж перейти до веб-сайту Bing.

1. Погляньте на події, що передаються, коли ви переходите до своєї робочої області. Ця робоча область пов’язана з ключем прийому, введеному на Кроці 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]