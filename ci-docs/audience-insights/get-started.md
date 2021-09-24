---
title: Začínáme s funkcí přehledů cílových skupin v aplikaci Dynamics 365 Customer Insights
description: Informace o přehledech cílových skupin pomáhají zdrojům rychle začít.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: aaaf1848df175469d8af07754ac153b777781ffb
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466569"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Začínáme s funkcí přehledů cílových skupin v aplikaci Dynamics 365 Customer Insights

Přehledy cílových skupin vám pomohou vybudovat hlubší porozumění vašim zákazníkům. Propojte data z různých transakčních, behaviorálních a observačních zdrojů a vytvořte kompletní pohled na zákazníka. Pomocí těchto statistik budete moci zkušenosti a procesy zaměřit na zákazníka. Sjednocení a pochopení zákaznických dat a jejich využití pro inteligentní přehledy a akce.

## <a name="step-1-create-an-environment"></a>Krok 1: Vytvoření prostředí

Chcete -li začít, musíte nejprve vytvořit prostředí, ve kterém budete pracovat. Pokud si vaše organizace již zakoupila licenci, postupujte podle části [Začínáme s placeným předplatným](get-started-paid.md). Chcete -li spustit zkušební verzi přehledů cílových skupin, postupujte podle části [Nastavení zkušebního prostředí](get-started-trial.md). 

## <a name="step-2-explore-audience-insights"></a>Krok 2: Prozkoumání přehledů cílových skupin

Při první návštěvě se přihlaste k přehledům cílových skupin a můžete nakonfigurovat nastavení a prozkoumat produkt.

1. [Přihlaste se k přehledům cílových skupin](https://home.ci.ai.dynamics.com) pomocí vašeho uživatelského účtu Microsoft Azure Active Directory (AAD).

1. [Změňte prostředí](manage-environments.md#switch-environments) pro zobrazení ukázkových dat a [prozkoumejte přehledy cílových skupin](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Krok 3: Ingestujte, sjednoťte a nastavte vztahy pro svá data

Sjednocené profily jsou základem pro získávání přehledů a přijímání opatření v souvislosti s daty. Přineste data z různých zdrojů a spusťte proces sjednocení dat, abyste mohli kombinovat sjednocené profily. Určete vztahy mezi ingestovanými entitami pomocí funkcí obohacení pro přidání informací do profilů. 

1. Ingestujte data vytvářením zdrojů dat z více možností. Vyberte si mezi [konektory Power Query](connect-power-query.md), [složkou Common Data Model](connect-common-data-model.md), nebo [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. Spusťte [proces sjednocení dat](data-unification.md) procházením fází [mapování](map-entities.md), [párování](match-entities.md) a [sloučení](merge-entities.md).

1. Seznamte se s [entitami, které systém vytváří](entities.md), a vytvořte [vztahy mezi ingestovanými entitami](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Krok 4: Vylepšete sjednocené profily pomocí předpovědí, aktivit a měr

Díky nastavení sjednocených profilů můžete svá data vylepšit a dále navýšit informace, které poskytují.

1. Vybírejte z rozšiřující se knihovny poskytovatelů obohacení a [obohaťe své zákaznické údaje](enrichment-hub.md).

1. Použijte [integrované modely](predictions-overview.md) a předpovídejte pravděpodobnost ztráty nebo očekávané výnosy.

1. [Konfigurujte aktivity](activities.md) na základě ingestovaných dat a vizualizujte interakce se svými zákazníky v chronologické časové ose. 

1. [Vytvářejte míry](measures.md), abyste změřili své obchodní cíle a KPI.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Krok 5: Vytvořte segmenty a aktivujte data pomocí různých možností exportu

Nyní, když jsou vaše data kompletní a obsahují širokou škálu informací o vašich zákaznících, je na čase hledat způsoby, jak s těmito daty nakládat. 

1. [Vytvářejte segmenty](segments.md), podmnožiny vaší zákaznické základny, abyste zajistili, že vaše akce jsou relevantní pro cílové zákazníky.

1. Procházet rozšiřující se katalog [možností exportu](export-destinations.md), kde můžete použít zákaznická data. Data můžete například použít ke správě propagačních akcí a kontaktu s digitálním marketingem.

1. Zkontrolujte možnosti integrace, například pomocí [přímé připojení k přehledům zapojení](../engagement-insights/integrate-audience-insights-engagement-insights.md) nebo k jiným aplikacím Dynamics 365 díky [doplňku zákaznické karty](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
