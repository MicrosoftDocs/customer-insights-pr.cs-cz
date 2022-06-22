---
title: Limity služeb v Customer Insights
description: Seznamte se s limity a omezeními ve službě Customer Insights SaaS.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940660"
---
# <a name="service-limits-in-customer-insights"></a>Limity služeb v Customer Insights

Tento článek popisuje vestavěné limity služby Customer Insights, které jsou navrženy tak, aby zajistily spolehlivost a stabilitu služby. Jakékoli žádosti o změny lze podat prostřednictvím [Fórum nápadů](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Plocha  | Limity  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, míry a predikce | 300  | Celkový počet [segmentů](segments.md), [měr](measures.md) a [predíkcí](predictions.md) dohromady nesmí přesáhnout 300.  |
| Relace | 20 úrovní hloubky vztahů v cestách entit. | Při vytváření [segmentů](segments.md) nebo [měření](measures.md) pomocí rozhraní Builderu mohou mít cesty entit až 20 skokových relací mezi počáteční entitou a cílovou entitou.  |

## <a name="fair-scheduling-of-jobs"></a>Spravedlivé plánování pracovních míst

Customer Insights je služba SaaS, která využívá sdílené prostředky Azure. Zákazníci mívají pracovní zátěž různé intenzity a různé rozvrhy. Abychom zajistili spravedlivý přístup k základním zdrojům, zajišťujeme, aby byly systémové procesy prováděny ve spravedlivém pořadí. Příkladem systémových procesů jsou úlohy související se sjednocením dat, aktualizacemi segmentů nebo výpočtem měření. Spravedlivé plánování vás ochrání před zařazováním zdrojů do fronty, pokud dojde k nárůstu požadovaných úloh. Customer Insights zároveň nezaručuje, že všechny úlohy, které zařadíte do fronty, budou zpracovány paralelně.

[!INCLUDE [footer-include](includes/footer-banner.md)]
