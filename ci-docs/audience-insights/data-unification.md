---
title: Уніфікація даних
description: Дізнайтеся, як уніфікувати передані дані.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 44f97696ec91dc488dd6a7528e186abb99c8288b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269677"
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