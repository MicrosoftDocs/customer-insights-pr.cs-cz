---
title: Limity služeb v Customer Insights
description: Seznamte se s limity a omezeními ve službě Customer Insights SaaS.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f38b7d9985368fc38107f1f360f0603a7fcc8e6
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411732"
---
# <a name="service-limits-in-customer-insights"></a>Limity služeb v Customer Insights

 Služba Customer Insights má vestavěné limity, které jsou navrženy tak, aby zajistily spolehlivost a stabilitu služby. Jakékoli žádosti o změny lze podat prostřednictvím [Fórum nápadů](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Plocha  | Limity  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, míry a predikce | 300  | Celkový počet [segmentů](segments.md), [měr](measures.md) a [predíkcí](predictions-overview.md) dohromady nesmí přesáhnout 300.  |
| Relace | 20 úrovní hloubky vztahů v cestách entit. | Při vytváření [segmentů](segments.md) nebo [měření](measures.md) pomocí rozhraní Builderu mohou mít cesty entit až 20 skokových relací mezi počáteční entitou a cílovou entitou.  |

## <a name="fair-scheduling-of-jobs"></a>Spravedlivé plánování pracovních míst

Customer Insights je služba SaaS, která využívá sdílené prostředky Azure. Zákazníci mívají pracovní zátěž různé intenzity a různé rozvrhy. Abychom zajistili spravedlivý přístup k základním zdrojům, zajišťujeme, aby byly systémové procesy prováděny ve spravedlivém pořadí. Příkladem systémových procesů jsou úlohy související se sjednocením dat, aktualizacemi segmentů nebo výpočtem měření. Spravedlivé plánování vás ochrání před zařazováním zdrojů do fronty, pokud dojde k nárůstu požadovaných úloh. Customer Insights zároveň nezaručuje, že všechny úlohy, které zařadíte do fronty, budou zpracovány paralelně.

[!INCLUDE [footer-include](includes/footer-banner.md)]
