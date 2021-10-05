---
title: Використання демографічних вимірів для розділення поведінкових даних (відібрані виміри)
description: Скористайтеся відібраними вимірами єдиних профілів, щоб увімкнути властивості клієнтських профілів аналітичних оглядів аудиторії.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a3d7f9276330a6daacbe9428d84a371b81bbefe
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: uk-UA
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466373"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Використання демографічних вимірів для розділення поведінкових даних

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Використовуючи демографічні виміри єдиних профілів, користувачі аналітичних оглядів взаємодії матимуть доступ до властивостей профілю аналітичних оглядів аудиторії. Ці властивості можна використовувати в інтерактивному аналізі поведінкових даних, в тому числі даних, записаних аналітичними оглядами взаємодії на вашому веб-сайті або програмі для мобільних пристроїв.

>[!NOTE]
> Аналітичні висновки щодо взаємодії включають готові виміри для властивостей подій. Додаткові відомості: [Перегляд та створення вимірів](dimensions.md)

## <a name="prerequisite"></a>Передумова

- Середовище аналітичних оглядів взаємодії, в якому є дані профілю клієнта, зв'язані з середовищем аналітичних оглядів аудиторії, де створюються профілі клієнтів. Додаткові відомості: [Створення зв'язку між аналітичними оглядами аудиторії та аналітичними оглядами взаємодії](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Після створення зв'язку між аналітичними оглядами аудиторії та середовищами аналітичних оглядів взаємодії, можливо вам будуть потрібні лише дані, що стосуються властивостей профілю клієнта, та можуть служити вимірами в аналітичних оглядах взаємодії. Для отримання додаткових відомостей, перейдіть до розділу [Увімкнення атрибутів та сегментів єдиних профілів аналітичних оглядів аудиторії](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Створення нового настроюваного звіту

1. В області ліворуч натисніть **Настроюваний** > **Новий звіт** та виберіть потрібний показник. (У цьому прикладі ми вибрали **Перегляди сторінки по годинам**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Виберіть показник.":::

2. У редакторі графічних відображень натисніть **Виміри** та виберіть **Демографічні** у розкривному меню **Тип виміру**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Виберіть демографічні виміри.":::

3. Виберіть вимір **Signal.Customer.*xxx***. (У цьому прикладі показано Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Виберіть вимір.":::
  
## <a name="limitations"></a>Обмеження

На даний момент для розділення поведінкових даних можна використовувати лише демографічні виміри.


[!INCLUDE[footer-include](../includes/footer-banner.md)]