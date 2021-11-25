---
title: Limity služeb v Dynamics 365 Customer Insights
description: Pochopte limity a omezení.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791973"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limity služeb ve funkcích aplikace Customer Insights

Tento článek popisuje vestavěné limity služby Customer Insights, které jsou navrženy tak, aby zajistily spolehlivost a stabilitu služby. Jakékoli žádosti o změny lze podat prostřednictvím [Fórum nápadů](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Přehledy pro cílovou skupinu

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Omezení funkce přehledů cílové skupiny v Dynamics 365 Customer Insights

| Plocha  | Limity  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, míry a predikce | 300  | Celkový počet [segmentů](audience-insights/segments.md), [měr](audience-insights/measures.md) a [predíkcí](audience-insights/predictions.md) dohromady nesmí přesáhnout 300.  |
| Relace | 20 úrovní hloubky vztahů v cestách entit. | Při vytváření [segmentů](audience-insights/segments.md) nebo [měření](audience-insights/measures.md) pomocí rozhraní Builderu mohou mít cesty entit až 20 skokových relací mezi počáteční entitou a cílovou entitou.  |


## <a name="engagement-insights"></a>Přehledy zapojení

### <a name="workspace-and-event-quotas"></a>Pracovní prostor a kvóty událostí

Přehledy zapojení je vysoce škálovatelná aplikace, která může podporovat miliony událostí za sekundu. Během Public Preview mají události prahovou hodnotu objemu. Existuje také omezení počtu pracovních prostorů v organizaci.

### <a name="engagement-insights-limits"></a>Omezení přehledů zapojení

- Maximální objem událostí na pracovní prostor = 100 událostí za sekundu

- Maximální počet pracovních prostorů na organizaci = 100

Když události překročí prahovou hodnotu, může to vést ke ztrátě dat v sestavách na základě těchto událostí. Můžete [kontaktovat podporu](https://go.microsoft.com/fwlink/?linkid=2145734) a požádat o zvýšení objemu, než překročíte limity. Společně s vámi určíme, zda potřebujete zvýšit objem, a podpoříme váš požadavek.


[!INCLUDE[footer-include](includes/footer-banner.md)]
