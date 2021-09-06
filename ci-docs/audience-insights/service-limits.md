---
title: Omezení služby
description: Pochopte limity a omezení.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034856"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Omezení funkce přehledů cílové skupiny v Dynamics 365 Customer Insights

Tento článek popisuje vestavěné limity služby Customer Insights, které jsou navrženy tak, aby zajistily spolehlivost a stabilitu služby. Jakékoli žádosti o změny lze podat prostřednictvím [Fórum nápadů](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Plocha  | Limity  | Poznámky |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty a míry | 100 segmentů nebo měr. | Celkový počet aktivních [segmentů](segments.md) a [měr](measures.md) dohromady nesmí překročit 100.  |
| Relace | 20 úrovní hloubky vztahů v cestách entit. | Při vytváření [segmentů](segments.md) nebo [měření](measures.md) pomocí rozhraní Builderu mohou mít cesty entit až 20 skokových relací mezi počáteční entitou a cílovou entitou.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]