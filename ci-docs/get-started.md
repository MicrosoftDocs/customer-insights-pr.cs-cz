---
title: Seznámení s aplikací Dynamics 365 Customer Insights
description: Přehled zdrojů nápovědy Customer Insights, abyste mohli rychle začít.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 68c26eb0ad0da787a9f594b4aebe679588b0d6bf
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833531"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Seznámení s aplikací Dynamics 365 Customer Insights

Customer Insights vám může pomoci lépe porozumět vašim zákazníkům. Propojte data z různých transakčních, behaviorálních a observačních zdrojů a vytvořte kompletní pohled na zákazníka. Pomocí těchto statistik budete moci zkušenosti a procesy zaměřit na zákazníka. Sjednocení a pochopení zákaznických dat a jejich využití pro inteligentní přehledy a akce.

## <a name="step-1-create-an-environment"></a>Krok 1: Vytvoření prostředí

Nejprve vytvořte prostředí pro práci. Pokud si vaše organizace již zakoupila licenci, viz [Vytvoření prostředí](create-environment.md). Chcete-li zahájit zkušební verzi Customer Insights, viz [Nastavte zkušební prostředí](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Krok 2: Prozkoumejte Customer Insights

Při prvním přihlášení do Customer Insights nakonfigurujte nastavení a prozkoumejte produkt.

1. [Přihlaste se do Customer Insights](https://home.ci.ai.dynamics.com) pomocí vašeho uživatelského účtu Microsoft Azure Active Directory (AAD).

1. Změňte prostředí, chcete-li zobrazit ukázková data a [prozkoumejte Customer Insights.](home.md)

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Krok 3: Ingestujte, sjednoťte a nastavte vztahy pro svá data

Sjednocené profily jsou základem pro získávání přehledů a přijímání opatření v souvislosti s daty. Přineste data z různých zdrojů a spusťte proces sjednocení dat, abyste mohli kombinovat sjednocené profily. Mezi přijatými entitami určete vztahy a použijte funkce obohacení k přidání informací do profilů.

1. Ingestujte data vytvářením zdrojů dat z více možností. Vyberte mezi [konektory Power Query](connect-power-query.md) a [složkou Common Data Model](connect-common-data-model.md), nebo [Microsoft Dataverse](connect-dataverse-managed-lake.md).

1. Spusťte [proces sjednocení dat](data-unification.md) identifikací [zdrojových polí](map-entities.md), odstraněním [duplicit](remove-duplicates.md), [odpovídající podmínky](match-entities.md) a [sjednocující pole](merge-entities.md).

1. Seznamte se s [entitami, které systém vytváří](entities.md), a vytvořte [vztahy mezi ingestovanými entitami](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Krok 4: Vylepšete sjednocené profily pomocí předpovědí, aktivit a měr

S nastavením sjednocených profilů vylepšete svá data a dále rozšiřte informace, které poskytují.

1. Vybírejte z rozšiřující se knihovny poskytovatelů obohacení a [obohaťe své zákaznické údaje](enrichment-hub.md).

1. Použijte [integrované modely](predictions-overview.md) a předpovídejte pravděpodobnost ztráty nebo očekávané výnosy.

1. [Konfigurujte aktivity](activities.md) na základě ingestovaných dat a vizualizujte interakce se svými zákazníky v chronologické časové ose.

1. [Vytvářejte míry](measures.md), abyste změřili své obchodní cíle a KPI.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Krok 5: Vytvořte segmenty a aktivujte data pomocí různých možností exportu

Nyní, když jsou vaše data kompletní a obsahují širokou škálu informací o vašich zákaznících, hledejte způsoby, jak s těmito daty naložit.

1. [Vytvářejte segmenty](segments.md), podmnožiny vaší zákaznické základny, abyste zajistili, že vaše akce jsou relevantní pro cílové zákazníky.

1. Procházet rozšiřující se katalog [možností exportu](export-destinations.md), kde můžete použít zákaznická data. Data můžete například použít ke správě propagačních akcí a kontaktu s digitálním marketingem.

1. Zkontrolujte možnosti integrace, například do jiných aplikací Dynamics 365 s [Doplňkem Zákaznické karty](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]