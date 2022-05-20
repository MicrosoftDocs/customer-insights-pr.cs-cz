---
title: Správa výchozích pravidel souhlasu pro segmenty
description: Pomocí funkce správy souhlasu můžete zakázat nebo změnit výchozí pravidla souhlasu, pokud jsou povolena přepsání.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755208"
---
# <a name="disable-or-change-default-consent-rules"></a>Zákaz nebo změna výchozích pravidel souhlasu

Pokud vaše organizace používá [funkci správy souhlasu](consent-management/overview.md) s Dynamics 365 Customer Insights, [správci mohou vynutit pravidla souhlasu](activate-consent.md) pro segmenty. 

Díky vynuceným pravidlům souhlasu v oblasti segmentu každý segment informuje o stavu kontroly a pravidlech souhlasu. Pokud jsou povolena přepsání, výchozí pravidla souhlasu jsou pro konkrétní segmenty vypnuta. Každý tvůrce segmentu může nad rámec výchozích pravidel segmentu přidat další pravidla souhlasu. 

## <a name="for-administrators"></a>Pro správce

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Nástroj pro tvorbu segmentů s možnostmi pravidla souhlasu.":::

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
1. [Vytvořte segment](segments.md) v Customer Insights a uložte jej. 

1. Sdílejte název segmentu se svým správcem a požádejte ho o [povolení přepsání pro váš segment](activate-consent.md). 

1. Znovu otevřete své segmenty. V oznámení **Pravidla souhlasu** vyberte **Zobrazit podrobnosti** a přidejte pravidla souhlasu, která chcete použít. Poté **Uložte** a **Spusťte** svůj segment.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
