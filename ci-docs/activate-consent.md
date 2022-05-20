---
title: Aktivace pravidel souhlasu pro segmenty
description: Postupujte podle následujících kroků k propojení dat souhlasu a aktivaci kontrol souhlasu v Dynamics 365 Customer Insights. Správce může také zakázat kontroly souhlasu.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755162"
---
# <a name="activate-consent-rules"></a>Aktivace pravidel obsahu

[Centrum souhlasu (Preview)](consent-management/overview.md) vám pomůže harmonizovat data souhlasu z různých zdrojů. Pro použití výchozích kontrol souhlasu použijte sjednocenou entitu *Souhlas*. Po importování dat souhlasu a konfiguraci pravidel mapy pro data je entita *Souhlas* automaticky synchronizována s Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Povolit kontroly souhlasu

Po importu dat souhlasu do Centra souhlasu (Preview) a nastavení pravidel můžete povolit kontroly souhlasu. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Karta Souhlas v nastavení Customer Insights s aktivovanými daty souhlasu.":::

1. V části Customer Insights přejděte na **Správcet** > **Systém**.

1. Vyberte kartu **Souhlas (Preview)**.

1. V sekci **Povolení kontrol souhlasu** nastavte přepínač na **Zapnuto** pro všechny oblasti, které chcete povolit.

1. Výběrem zaškrtávacího políčka **Povolit přepsání výchozích pravidel souhlasu** odeberete výchozí kontroly souhlasu vynucené pro určitý segment. 

1. V rozevírací nabídce vyberte, kde chcete povolit přepsání.     

1. V sekci **Propojit souhlas s profily zákazníků** vyberte atribut, který slouží jako identifikátor k propojení dat souhlasu se zákaznickými daty. Budet to pravděpodobně telefonní číslo nebo e-mailová adresa. 

1. Výběrem možnosti **Uložit** použijte nastavení.

## <a name="disable-consent-checks"></a>Zákaz kontroly souhlasu

Pokud chcete používat data souhlasu v Customer Insights, správce musí odpovídajícím způsobem aktualizovat nastavení systému.

1. V části Customer Insights přejděte na **Správcet** > **Systém**.

1. Vyberte kartu **Souhlas (Preview)**.

1. V sekci **Povolit kontroly souhlasu** nastavte přepínač do polohy **Vypnuto**.

> [!TIP]
> Chcete-li přestat používat funkci správy souhlasu, viz [Nastavení systému v Centru souhlasu (Preview)](consent-management/system-settings.md).
