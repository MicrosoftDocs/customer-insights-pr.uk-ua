---
title: Увімкнення готових звітів про профілі
description: Як створювати готові звіти про профілі, згруповані за статтю, віком і країною або регіоном походження.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486145"
---
# <a name="out-of-box-profile-reports"></a>Готові звіти про профілі

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Звіт — це колекція графічних відображень даних, який допомагає проаналізувати поведінку користувачів. Після підключення до аналізу аудиторії Customer Insights аналітичні висновки щодо взаємодії можуть показати звіт з інформацією про уніфіковані профілі клієнтів. Цей звіт включає наявну у вас кількість профілів, згрупованих за статтю, віком і географічним положенням.

## <a name="prerequisites"></a>Вимоги

Середовище аналізу аудиторії має зберігати дані в обліковому записі Azure Data Lake Storage, керованому клієнтом.

Якщо ви використовуєте ознайомлювальну версію засобу аналізу аудиторії або середовище в озері даних, керованому Customer Insights, [зверніться до нас](https://go.microsoft.com/fwlink/?linkid=2145734) по допомогу.  


## <a name="enable-the-customer-profile-report"></a>Увімкнення звіту про профіль клієнта

Адміністратор середовища повинен [зв'язати аналітику взаємодії та аналіз аудиторії](integrate-audience-insights-engagement-insights.md).

Після внесення відомостей про підключення адміністратор може надати доступ іншим користувачам в організації, щоб вони могли переглянути звіт. Адміністратор середовища, який налаштовує підключення, автоматично отримує доступ до звіту. 

Після завершення підключення функція **Профілі** буде доступна на панелі переходів ліворуч. 

- Перейдіть до розділу **Виявити** > **Профілі**, щоб переглянути звіт.

Звіт **Профілі** містить графічні відображення даних щодо статі, віку та географічного положення підключених профілів клієнтів.

:::image type="content" source="media/customer-profiles.png" alt-text="Звіт про профіль клієнта.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]