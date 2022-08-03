---
title: Експорт сегментів у маркетинг Dynamics 365 (попередній перегляд)
description: Дізнайтеся, як налаштувати підключення та експорт до Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: uk-UA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196649"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Експорт сегментів у маркетинг Dynamics 365 (попередній перегляд)

Використовуйте [сегменти](segments.md) для створення кампаній і зв'язку з певними групами клієнтів за допомогою [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Якщо ви використовуєте нові можливості Dynamics 365 Marketing для оркестрації шляху клієнта в реальному часі в організації Dataverse, то створювати стандартний експорт до Dynamics 365 Marketing не потрібно. Контакти та сегменти з Customer Insights доступні безпосередньо в Dynamics 365 Marketing після підключення Marketing і Customer Insights. Перш ніж видаляти наявні експорти, перегляньте документацію про [підключення Customer Insights і Dynamics 365 Marketing шлях клієнта оркестрування](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Передумова

Записи контактних осіб мають бути присутніми в Dynamics 365 Marketing, щоб ви змогли експортувати сегмент з Customer Insights до Marketing. Дізнайтеся більше про те, як прийняти контактних осіб у [Dynamics 365 Marketing, використовуючи Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Експорт сегментів із Customer Insights до marketing не призведе до створення нових записів контактів у екземплярах Marketing. Контактні записи з Marketing повинні потрапляти в Customer Insights і використовуватися як джерело даних. Їх також потрібно включити в уніфіковану сутність «Клієнт», щоб зіставити ідентифікатори клієнтів із ідентифікаторами контактних осіб, перш ніж можна буде експортувати сегменти.

## <a name="set-up-connection-to-marketing"></a>Налаштування підключення до Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Відкрийте **Адміністрування** > **Підключення**.

1. Виберіть Додати **підключення** та виберіть **Dynamics 365 Marketing**.

1. Надайте у полі **Коротке ім’я** для свого підключення змістовне ім'я, яке легко впізнати. Ім’я та тип підключення описують це підключення. Ми рекомендуємо вибирати ім’я, яке роз'яснює ціль і мету даного підключення.

1. Виберіть користувачів, які зможуть використовувати це підключення. За промовчанням це можуть робити лише адміністратори. Докладніші відомості див. у розділі [Дозвольте співавторам використовувати підключення для експортів](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Введіть URL-адресу Marketing вашої організації в полі **Адреса сервера**.

1. У розділі **Обліковий запис адміністратора сервера** виберіть **Увійти** і оберіть обліковий запис Dynamics 365 Marketing.

1. Зіставте поле «Ідентифікатор контакту» в організації клієнта з ідентифікатором контакту Dynamics 365.

1. Перегляньте конфіденційність [і відповідність](connections.md#data-privacy-and-compliance) даних і виберіть пункт **Я погоджуюся**.

1. Щоб завершити створення підключення, виберіть **Зберегти**.

## <a name="configure-an-export"></a>Налаштування експорту

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Відкрийте **Дані** > **Експорти**.

1. Виберіть Додати **експорт**.

1. У полі **Підключення для експорту** виберіть підключення з розділу Dynamics 365 Marketing. Якщо жодне підключення недоступне, зверніться до адміністратора.

1. Введіть ім'я експорту.

1. Виберіть поле Ідентифікатор контакту в організації клієнта, яке відповідає ідентифікатору контакту Dynamics 365.

1. Виберіть сегменти, які потрібно експортувати.

1. Виберіть **Зберегти**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
