---
title: Obohaťte profily zákazníků o údaje o značkách a zájmech od společnosti Microsoft (Preview)
description: Použijte proprietární data od společnosti Microsoft k rozšíření vašich zákaznických údajů o afinitách a podílu na sledovanosti.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: e1827adca10a3b193c02a20c4abccacf73194a77
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080913"
---
# <a name="enrich-customer-profiles-with-brands-and-interests-data-from-microsoft-preview"></a>Obohaťte profily zákazníků o údaje o značkách a zájmech od společnosti Microsoft (Preview)

Použijte proprietární data Microsoftu k rozšíření vašich zákaznických dat o afinity značky, afinity zájmu a podílu na sledovanosti. Tyto afinity a podíl na sledovanosti jsou založeny na datech od lidí s demografickými údaji podobnými vašim zákazníkům. Tyto informace vám pomohou lépe porozumět a segmentovat vaše zákazníky na základě jejich afinity nebo podílu sledovanosti vzhledem ke konkrétním značkám a zájmům.

## <a name="how-we-determine-affinities-and-sov"></a>Jak určujeme afinity a podíl na sledovanosti

Údaje o online vyhledávání společnosti Microsoft používáme k nalezení afinit a podílu na sledovanosti pro značky a zájmy v různých demografických segmentech (definovaných podle věku, pohlaví nebo místa). Objem online vyhledávání pro značku nebo zájem tvoří základ pro určení afinity nebo podílu na sledovanosti. Každý však poskytuje jinou perspektivu pochopení vašich zákazníků.

- Afinita je srovnávací faktor napříč demografickými segmenty. Tyto informace můžete použít k identifikaci demografických segmentů, které mají nejvyšší afinitu k dané značce nebo zájmu ve srovnání s ostatními segmenty.

- Podíl na sledovanosti je srovnávací faktor mezi vámi vybranými značkami nebo zájmy. Tyto informace můžete použít ke zjištění, která značka nebo zájem má nejvyšší podíl sledovanosti pro daný demografický segment ve srovnání s jinými značkami nebo zájmy, které jste vybrali.

## <a name="affinity-level-and-score"></a>Úroveň a skóre afinity

U každého rozšířeného zákaznického profilu poskytujeme dvě související hodnoty: úroveň afinity a skóre afinity. Tyto hodnoty vám pomohou určit, jak silná je afinita k demografickému segmentu daného profilu, ke značce nebo zájmu ve srovnání s jinými demografickými segmenty.

*Úroveň afinity* se skládá ze čtyř úrovní a *skóre afinity* se počítá na 100bodové stupnici, která se mapuje na úrovně afinity.

|Úroveň afinity |Skóre příbuznosti  |
|---------|---------|
|Velmi vysoká     | 85–100       |
|vysokou     | 70–84        |
|střední     | 35–69        |
|nízkou     | 1–34        |

V závislosti na granularitě, kterou chcete pro měření afinity, můžete použít buď úroveň nebo skóre afinity. Skóre afinity vám dává přesnější kontrolu.

## <a name="share-of-voice-sov"></a>Podíl na sledovanosti

Podíl na sledovanosti počítáme na 100bodové škále. Celkový podíl na sledovanosti napříč všemi značkami nebo zájmy pro každý rozšířený zákaznický profil se rovná 100. Na rozdíl od afinity je podíl na sledovanosti relativní ke značkám a zájmům, které vyberete. Například hodnoty podíli na sledovanosti pro Microsoft se mohou lišit, pokud jsou vybrané značky (Microsoft, GitHub) a (Microsoft, LinkedIn).

## <a name="supported-countriesregions"></a>Podporované země/oblasti

V současné době podporujeme následující země/oblasti: Austrálie, Kanada (angličtina), Francie, Německo, Spojené království nebo Spojené státy americké (angličtina).

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření** a vyberte kartu **Objevit**.

   - Pokud chcete nakonfigurovat afinity značek a rozšíření SoV, vyberte **Rozšířit moje data** na dlaždici **Značky**.

   - Pokud chcete nakonfigurovat afinity zájmů a rozšíření SoV, vyberte **Rozšířit moje data** na dlaždici **Zájmy**.

   > [!div class="mx-imgBorder"]
   > ![Dlaždice Značky a zájmy.](media/BrandsInterest-tile-Hub.png "Dlaždice Značky a zájmy")

1. Zkontrolujte přehled a poté vyberte **Další**.

1. Chcete-li změnit zemi nebo region, vyberte **Změnit** vedle **Země/oblast**. V podokně **Nastavení země/oblasti** vyberte [podporovaná země/oblast](#supported-countriesregions) a vyberte **Použít**.

   > [!NOTE]
   > Při výběru vlastních značek systém poskytne návrhy na základě vybrané země nebo oblasti. Při výběru odvětví se vám zobrazí nejrelevantnější značky nebo zájmy na základě vybrané země nebo oblasti.

1. Vyberte až pět značek nebo zájmů pomocí jedné nebo obou z těchto možností:

   - **Odvětví**: Vyberte své odvětví z rozevíracího seznamu a poté vyberte z nejlepších značek nebo zájmů pro toto odvětví.
   - **Zvolte své vlastní** : Zadejte značku nebo zájem, který je relevantní pro vaši organizaci, a poté vyberte z odpovídajících návrhů. Pokud neuvedeme značku nebo zájem, který hledáte, pošlete nám zpětnou vazbu pomocí odkazu **Navrhnout**.

1. Vyberte **Další** a zkontrolujte své výchozí předvolby rozšíření a podle potřeby je aktualizujte.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Screenshot okna předvoleb rozšíření.":::

1. Vyberte **Další**.

1. Vyberte **Sada údajů o zákazníkovi** a zvolte profil nebo segment, které chcete obohatit o demografické údaje od Microsoft. Entita *Zákazník* rozšíří všechny profily vašich zákazníků zatímco segment rozšíří pouze profily zákazníků obsažené v tomto segmentu.

1. Vyberte **Další**.

1. Namapujte pole z jednotné entity zákazníka na data společnosti Microsoft.

   > [!NOTE]
   > Jsou vyžadovány alespoň atributy Datum narození nebo Pohlaví. Je vyžadována země/oblast a alespoň město (a stát/provincie) nebo PSČ. Při příjmu dat doporučujeme převést datum narození na typ DateTime. Alternativně to může být řetězec v [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formát „rrrr-MM-dd“ nebo „rrrr-MM-ddTHH: mm: ss“.

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Zadejte jméno rozšíření. **Název výstupní entity** je automaticky vybrán.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stránka kontroly zájmů a pojmenování.":::

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

1. Vyberte **Spustit** k zahájení procesu obohacování nebo blízko k návratu na stránku **Rozšíření**.

   Při rozšíření profilů rozšíříme všechny profily zákazníků, pro které získáváme data pro vybrané značky a zájmy, včetně profilů, které nejsou ve vybrané zemi nebo oblasti. Pokud jste například vybrali Německo, rozšíříme profily nacházející se ve Spojených státech, pokud máme k dispozici údaje o vybraných značkách a zájmech v USA.

## <a name="view-enrichment-results"></a>Zobrazení výsledků rozšiřování

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Náhled výsledků po spuštění procesu rozšíření.":::

Výsledky zahrnují grafy **Úroveň afinity** nebo **Podíl na sledovanosti**.

Subjekty vytvořené z rozšiřování jsou uvedeny pod skupinou **rozšiřování** v okně **Data** > **Entity**. Rozšířená data pro značky přechízí do entit **BrandAffinityFromMicrosoft** a **BrandShareOfVoiceFromMicrosoft**. Údaje pro zájmy jsou v entitách **InterestAffinityFromMicrosoft** a **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Zobrazení rozšíření dat na kartě zákazníka

Podíl na sledovanosti značky a zájmu lze zobrazit i na jednotlivých zákaznických kartách. Jděte na **Zákazníci** a vyberte profil zákazníka. V zákaznické kartě najdete grafy pro podíl na sledovanosti značky nebo zájmu založené na lidech v demografickém profilu daného zákazníka.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta zákazníka s rozšířenými daty.":::

## <a name="next-steps"></a>Další kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
