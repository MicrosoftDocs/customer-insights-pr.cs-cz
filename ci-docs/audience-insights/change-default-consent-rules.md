---
title: Správa výchozích pravidel souhlasu pro segmenty
description: Pomocí funkce správy souhlasu můžete zakázat nebo změnit výchozí pravidla souhlasu, pokud jsou povolena přepsání.
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884162"
---
# <a name="disable-or-change-default-consent-rules"></a>Zákaz nebo změna výchozích pravidel souhlasu

Pokud vaše organizace používá [funkci správy souhlasu](../consent-management/overview.md) v kombinaci s přehledy cílových skupin, [správci mohou vynutit pravidla souhlasu](activate-consent.md) pro segmenty. 

Díky vynuceným pravidlům souhlasu v oblasti segmentu každý segment informuje o stavu kontroly a pravidlech souhlasu. Pokud jsou povolena přepsání, výchozí pravidla souhlasu jsou pro konkrétní segmenty vypnuta. Každý tvůrce segmentu může nad rámec výchozích pravidel segmentu přidat další pravidla souhlasu. 

## <a name="for-administrators"></a>Pro správce

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Nástroj pro tvorbu segmentů s možnostmi pravidla souhlasu.":::

**Chcete-li deaktivovat výchozí pravidla souhlasu:**

1. V oznámení **Pravidla souhlasu** vyberte **Zobrazit podrobnosti**. 

1. Nastavte přepínač **Výchozí pravidla souhlasu** do polohy **Vypnuto**.

**Chcete-li přidat pravidla souhlasu:**

1. V oznámení **Pravidla souhlasu** vyberte **Zobrazit podrobnosti**. 

1. Vyberte **Přidat pravidla souhlasu** a vyberte pravidlo souhlasu z rozevíracího seznamu **Vyberte datový typ souhlasu**.

1. Volbou **Uložit** použijete nové pravidlo na segment.

## <a name="for-contributors"></a>Pro přispěvatele

Chcete-li vytvořit segment bez vynucených pravidel souhlasu, musíte je deaktivovat v daném segmentu ve spolupráci se svým správcem. Do segmentů, které vlastníte a spravujete, však můžete přidat vlastní pravidla souhlasu.

Jedná se o třístupňový proces: 
1. [Vytvořte segment](segments.md) v přehledech cílových skupin a uložte jej. 

1. Sdílejte název segmentu se svým správcem a požádejte ho o [povolení přepsání pro váš segment](activate-consent.md). 

1. Znovu otevřete své segmenty. V oznámení **Pravidla souhlasu** vyberte **Zobrazit podrobnosti** a přidejte pravidla souhlasu, která chcete použít. Poté **Uložte** a **Spusťte** svůj segment.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
