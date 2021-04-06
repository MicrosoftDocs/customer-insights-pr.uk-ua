---
title: Уніфікація даних
description: Дізнайтеся, як уніфікувати передані дані.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 73d8006c670268420f8cd6a2b37cb214ba1bbd6c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597904"
---
# <a name="data-unification-overview"></a>Загальні відомості про уніфікацію даних

Після [налаштування джерела даних](data-sources.md) можна уніфікувати дані. Уніфікація даних складається з трьох кроків: **Зіставлення**, **Знаходження відповідностей** та **Злиття**.

Процес уніфікації даних дає змогу уніфікувати колись різнорідні джерела даних в один основний набір даних, який забезпечує уніфіковане подання клієнтів. Етапи уніфікації є обов’язковими, і виконуються в такому порядку:

1. [Зіставити](map-entities.md)
2. [Match](match-entities.md)
3. [Злиття](merge-entities.md)

Після завершення уніфікації даних можна додатково

- [налаштувати зв’язки між сутностями](relationships.md), щоб створити складні сегменти
- [збагатити дані](enrichment-hub.md), щоб отримувати ширший діапазон аналітичних оглядів про своїх клієнтів
- [визначити справи](activities.md) з деяких переданих атрибутів


[!INCLUDE[footer-include](../includes/footer-banner.md)]