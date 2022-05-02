---
title: Limity služeb v Dynamics 365 Customer Insights
description: Pochopte limity a omezení.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641754"
---
# <a name="service-limits-in-customer-insights"></a>Limity služeb v Customer Insights

Tento článek popisuje vestavěné limity služby Customer Insights, které jsou navrženy tak, aby zajistily spolehlivost a stabilitu služby. Jakékoli žádosti o změny lze podat prostřednictvím [Fórum nápadů](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Plocha  | Limity  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, míry a predikce | 300  | Celkový počet [segmentů](segments.md), [měr](measures.md) a [predíkcí](predictions.md) dohromady nesmí přesáhnout 300.  |
| Relace | 20 úrovní hloubky vztahů v cestách entit. | Při vytváření [segmentů](segments.md) nebo [měření](measures.md) pomocí rozhraní Builderu mohou mít cesty entit až 20 skokových relací mezi počáteční entitou a cílovou entitou.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
