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
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483653"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limity služeb ve funkcích aplikace Customer Insights

Tento článek popisuje vestavěné limity služby Customer Insights, které jsou navrženy tak, aby zajistily spolehlivost a stabilitu služby. Jakékoli žádosti o změny lze podat prostřednictvím [Fórum nápadů](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Přehledy pro cílovou skupinu

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Omezení funkce přehledů cílové skupiny v Dynamics 365 Customer Insights

| Plocha  | Limity  | Poznámky |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty a míry | 100 segmentů nebo měr. | Celkový počet aktivních [segmentů](audience-insights/segments.md) a [měr](audience-insights/measures.md) dohromady nesmí překročit 100.  |
| Relace | 20 úrovní hloubky vztahů v cestách entit. | Při vytváření [segmentů](audience-insights/segments.md) nebo [měření](audience-insights/measures.md) pomocí rozhraní Builderu mohou mít cesty entit až 20 skokových relací mezi počáteční entitou a cílovou entitou.  |


## <a name="engagement-insights"></a>Přehledy zapojení

### <a name="workspace-and-event-quotas"></a>Pracovní prostor a kvóty událostí

Přehledy zapojení je vysoce škálovatelná aplikace, která může podporovat miliony událostí za sekundu. Během Public Preview mají události prahovou hodnotu objemu. Existuje také omezení počtu pracovních prostorů v organizaci.

### <a name="engagement-insights-limits"></a>Omezení přehledů zapojení

- Maximální objem událostí na pracovní prostor = 100 událostí za sekundu

- Maximální počet pracovních prostorů na organizaci = 100

Když události překročí prahovou hodnotu, může to vést ke ztrátě dat v sestavách na základě těchto událostí. Můžete [kontaktovat podporu](https://go.microsoft.com/fwlink/?linkid=2145734) a požádat o zvýšení objemu, než překročíte limity. Společně s vámi určíme, zda potřebujete zvýšit objem, a podpoříme váš požadavek.


[!INCLUDE[footer-include](includes/footer-banner.md)]