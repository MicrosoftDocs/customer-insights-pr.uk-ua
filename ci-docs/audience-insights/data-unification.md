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
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407240"
---
# <a name="data-unification"></a>Уніфікація даних

Після [налаштування джерела даних](data-sources.md) можна уніфікувати дані. Уніфікація даних складається з трьох кроків: **Зіставлення**, **Знаходження відповідностей** та **Злиття**.

Процес уніфікації даних дає змогу уніфікувати колись різнорідні джерела даних в один основний набір даних, який забезпечує уніфіковане подання клієнтів. Етапи уніфікації є обов’язковими, і виконуються в такому порядку:

1. [Зіставити](map-entities.md)
2. [Match](match-entities.md)
3. [Злиття](merge-entities.md)

Після завершення уніфікації даних можна додатково

- [налаштувати зв’язки між сутностями](relationships.md), щоб створити складні сегменти
- [збагатити дані](enrichment-hub.md), щоб отримувати ширший діапазон аналітичних оглядів про своїх клієнтів
- [визначити справи](activities.md) з деяких переданих атрибутів
