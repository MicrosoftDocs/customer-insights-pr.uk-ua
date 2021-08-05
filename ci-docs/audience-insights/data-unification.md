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
ms.custom: intro-internal
ms.openlocfilehash: cb96763d4b5b67b5110db757eb7d160c294d6fc3
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539094"
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