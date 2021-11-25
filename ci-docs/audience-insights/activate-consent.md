---
title: Aktivace pravidel obsahu pro segmenty v přehledech cílových skupin
description: Kroky k propojení dat souhlasu a aktivaci kontrol souhlasu v přehledech cílových skupin.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 33ec3a684c2ca47badb4e5461f069d1b2e4a4f3d
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753053"
---
# <a name="activate-consent-rules"></a>Aktivace pravidel obsahu

[Centrum souhlasu (Preview)](../consent-management/overview.md) vám pomůže harmonizovat data souhlasu z různých zdrojů. Pro použití výchozích kontrol souhlasu použijte sjednocenou entitu *Souhlas*. Po importování dat souhlasu v Centru souhlasu a konfiguraci pravidel pro importovaná data souhlasu je entita *Souhlas* automaticky synchronizována s přehledy cílových skupin.

## <a name="enable-consent-checks"></a>Povolit kontroly souhlasu

Po importu dat souhlasu do Centra souhlasu (Preview) a nastavení pravidel můžete povolit kontroly souhlasu v přehledech cílových skupin. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Karta Souhlas v nastavení přehledů cílových skupin s aktivovanými daty souhlasu.":::

1. V přehledech cílové skupiny přejděte na **Správa** > **Systém**.

1. Vyberte kartu **Souhlas (Preview)**.

1. V sekci **Povolení kontrol souhlasu** nastavte přepínač pro oblast, kterou chcete povolit, do polohy **Zapnuto**.

1. Výběrem zaškrtávacího políčka **Povolit přepsání výchozích pravidel souhlasu** odeberete výchozí kontroly souhlasu vynucené pro určitý segment. 

1. V rozevírací nabídce vyberte, kde chcete povolit přepsání.     

1. V sekci **Propojit souhlas s profily zákazníků** vyberte atribut, který slouží jako identifikátor k propojení dat souhlasu se zákaznickými daty. Je to pravděpodobně telefonní číslo nebo e-mailová adresa. 

1. Výběrem možnosti **Uložit** použijte nastavení.

## <a name="disable-consent-checks"></a>Zákaz kontroly souhlasu

Pokud chcete používat data souhlasu v přehledech cílových skupin, správce musí odpovídajícím způsobem aktualizovat nastavení systému.

1. V přehledech cílové skupiny přejděte na **Správa** > **Systém**.

1. Vyberte kartu **Souhlas (Preview)**.

1. V sekci **Povolit kontroly souhlasu** nastavte přepínač do polohy **Vypnuto**.
