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
# <a name="data-unification-overview"></a><span data-ttu-id="deb58-103">Загальні відомості про уніфікацію даних</span><span class="sxs-lookup"><span data-stu-id="deb58-103">Data unification overview</span></span>

<span data-ttu-id="deb58-104">Після [налаштування джерела даних](data-sources.md) можна уніфікувати дані.</span><span class="sxs-lookup"><span data-stu-id="deb58-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="deb58-105">Уніфікація даних складається з трьох кроків: **Зіставлення**, **Знаходження відповідностей** та **Злиття**.</span><span class="sxs-lookup"><span data-stu-id="deb58-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="deb58-106">Процес уніфікації даних дає змогу уніфікувати колись різнорідні джерела даних в один основний набір даних, який забезпечує уніфіковане подання клієнтів.</span><span class="sxs-lookup"><span data-stu-id="deb58-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="deb58-107">Етапи уніфікації є обов’язковими, і виконуються в такому порядку:</span><span class="sxs-lookup"><span data-stu-id="deb58-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="deb58-108">Зіставити</span><span class="sxs-lookup"><span data-stu-id="deb58-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="deb58-109">Match</span><span class="sxs-lookup"><span data-stu-id="deb58-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="deb58-110">Злиття</span><span class="sxs-lookup"><span data-stu-id="deb58-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="deb58-111">Після завершення уніфікації даних можна додатково</span><span class="sxs-lookup"><span data-stu-id="deb58-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="deb58-112">[налаштувати зв’язки між сутностями](relationships.md), щоб створити складні сегменти</span><span class="sxs-lookup"><span data-stu-id="deb58-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="deb58-113">[збагатити дані](enrichment-hub.md), щоб отримувати ширший діапазон аналітичних оглядів про своїх клієнтів</span><span class="sxs-lookup"><span data-stu-id="deb58-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="deb58-114">[визначити справи](activities.md) з деяких переданих атрибутів</span><span class="sxs-lookup"><span data-stu-id="deb58-114">[define activities](activities.md) from some of the ingested attributes</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]