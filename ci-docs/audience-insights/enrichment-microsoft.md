---
title: Rozšíření profilů zákazníků daty od společnosti Microsoft
description: Použijte proprietární data od společnosti Microsoft k obohacení vašich zákaznických údajů o afinitách a podílu na sledovanosti.
ms.date: 11/11/2021
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
ms.openlocfilehash: 77972475c9a448186cee3b1b62eeda7b1996edfc
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355311"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Obohaťte profily zákazníků o afinity a podíl na sledovanosti (Preview)

Použijte proprietární data Microsoftu k obohacení vašich zákaznických dat o afinity značky, afinity zájmu a podílu na sledovanosti. Tyto afinity a podíl na sledovanosti jsou založeny na datech od lidí s demografickými údaji podobnými vašim zákazníkům. Tyto informace vám pomohou lépe porozumět a segmentovat vaše zákazníky na základě jejich afinity nebo podílu sledovanosti vzhledem ke konkrétním značkám a zájmům.

V přehledech cílové skupiny přejděte na **Data** > **Rozšíření**, kde můžete [nakonfigurovat a zobrazit rozšíření](enrichment-hub.md).

Chcete-li nakonfigurovat obohacení o afinity značky a podílu na sledovanosti, přejděte na kartu **Objevit** a vyberte **Obohatit moje data** na dlaždici **Značky**.

Chcete-li nakonfigurovat obohacení o afinity zájmu a podílu na sledovanosti, přejděte na kartu **Objevit** a vyberte **Obohatit moje data** na dlaždici **Zájmy**.

   > [!div class="mx-imgBorder"]
   > ![Dlaždice Značky a zájmy.](media/BrandsInterest-tile-Hub.png "Dlaždice Značky a zájmy")

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

Podíl na sledovanosti počítáme na 100bodové škále. Celkový podíl na sledovanosti napříč všemi značkami nebo zájmy pro každý obohacený zákaznický profil se rovná 100. Na rozdíl od afinity je podíl na sledovanosti relativní ke značkám a zájmům, které vyberete. Například hodnoty podíli na sledovanosti pro Microsoft se mohou lišit, pokud jsou vybrané značky (Microsoft, GitHub) a (Microsoft, LinkedIn).

## <a name="supported-countriesregions"></a>Podporované země/oblasti

V současné době podporujeme následující země/oblasti: Austrálie, Kanada (angličtina), Francie, Německo, Spojené království nebo Spojené státy americké (angličtina).

Chcete-li vybrat zemi nebo region, otevřete **Obohacování značek** nebo **Obohacování zájmů** a vyberte **Změna** vedle **Země/Region**. V podokně **Nastavení země/oblasti** vyberte požadovanou možnost a vyberte **Použít**.

### <a name="implications-related-to-country-selection"></a>Důsledky výběru země

- Při [výběru vlastních značek](#define-your-brands-or-interests) systém poskytne návrhy na základě vybrané země nebo oblasti.

- Při [výběru odvětví](#define-your-brands-or-interests) se vám zobrazí nejrelevantnější značky nebo zájmy na základě vybrané země nebo oblasti.

- Při [obohacování profilů](#refresh-enrichment) obohatíme všechny profily zákazníků, pro které získáváme data pro vybrané značky a zájmy, včetně profilů, které nejsou ve vybrané zemi nebo oblasti. Pokud jste například vybrali Německo, rozšíříme profily nacházející se ve Spojených státech, pokud máme k dispozici údaje o vybraných značkách a zájmech v USA.

## <a name="configure-enrichment"></a>Konfigurace rozšíření

Asistované prostředí vám pomůže s konfigurací obohacení. 

### <a name="define-your-brands-or-interests"></a>Uveďte své značky nebo zájmy

Vyberte až pět značek nebo zájmů pomocí jedné nebo obou z těchto možností:

- **Odvětví**: Vyberte své odvětví z rozevíracího seznamu a poté vyberte z nejlepších značek nebo zájmů pro toto odvětví.
- **Zvolte své vlastní** : Zadejte značku nebo zájem, který je relevantní pro vaši organizaci, a poté vyberte z odpovídajících návrhů. Pokud neuvedeme značku nebo zájem, který hledáte, pošlete nám zpětnou vazbu pomocí odkazu **Navrhnout**.

### <a name="review-enrichment-preferences"></a>Kontrola předvoleb rozšíření

Zkontrolujte své výchozí předvolby rozšíření a podle potřeby je aktualizujte.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Screenshot okna předvoleb rozšíření.":::

### <a name="select-entity-to-enrich"></a>Vyberte entitu, kterou chcete rozšířit.

Vyberte **Obohacená entita** a vyberte datovou sadu, kterou chcete obohatit o data od společnosti Microsoft. Můžete vybrat entitu Zákazník k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.

### <a name="map-your-fields"></a>Mapování polí

Namapujte pole z vaší sjednocené entity zákazníka a definujte demografický segment, který má systém použít k rozšíření vašich zákaznických dat. Namapujte zemi/oblast a alespoň atributy Datum narození nebo Pohlaví. Kromě toho je nutné namapovat alespoň jedno z měst (a kraj) nebo PSČ. Volbou **Upravit** definujete mapování polí a když máte hotovo, vyberte **Použít**. Vyberte **Uložit** pro dokončení mapování pole.

Jsou podporovány následující formáty a hodnoty (hodnoty nerozlišují velká a malá písmena):

- **Datum narození**: Během příjmu dat doporučujeme převést datum narození na typ Datum a čas. Alternativně to může být řetězec v [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formát „rrrr-MM-dd“ nebo „rrrr-MM-ddTHH: mm: ss“.
- **Pohlaví**: Muž, žena, neznámé.
- **Poštovní směrovací číslo**: Pětimístné PSČ pro Spojené státy, standardní PSČ všude jinde.
- **Město**: Název města v angličtině.
- **Kraj**: Dvoupísmenná zkratka pro USA a Kanadu. Dvou nebo třípísmenná zkratka pro Austrálii. Nelze použít ve Francii, Německu nebo Velké Británii.
- **Země/oblast**:

  - US: Spojené státy americké, Spojené státy, USA, US, Amerika
  - CA: Kanada, CA
  - GB: Spojené království, UK, Velká Británie, GB, Spojené království Velké Británie a Severního Irska, Spojené království Velké Británie
  - AU: Austrálie, AU, Australské království
  - FR: Francie, FR, Francouzská republika
  - DE: Německo, němčina, Deutschland, Allemagne, DE, Spolková republika Německo, Německo

## <a name="review-and-name-the-enrichment"></a>Kontrola a pojmenování rozšíření

Nakonec si přečtěte informace a uveďte název rozšíření.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stránka kontroly zájmů a pojmenování.":::

## <a name="refresh-enrichment"></a>Aktualizace rozšíření

Spusťte obohacení po konfiguraci značek, zájmů a mapování terénu pro demografii. Chcete-li zahájit proces, vyberte **Spustit** na stránce konfigurace značek nebo zájmů. Kromě toho můžete nechat systém spustit rozšíření automaticky jako součást plánované aktualizace.

V závislosti na velikosti vašich zákaznických dat může dokončení obohacování trvat několik minut.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Výsledky rozšíření

Po spuštění procesu rozšíření přejděte na **Moje rozšíření**, kde zkontrolujte celkový počet rozšířených zákazníků a rozpis značek nebo zájmů v rozšířených profilech zákazníků.

:::image type="content" source="media/my-enrichments.png" alt-text="Náhled výsledků po spuštění procesu rozšíření.":::

Najdete zde graf s počtem obohacených zákaznických profilů v průběhu času a náhledy obohacených entit. Prohlédněte si obohacená data výběrem možnosti **Další informace** v grafech **Úroveň afinity** nebo **Podíl na sledovanosti** grafy. Obohacená data pro značky přechízí do entit **BrandAffinityFromMicrosoft** a **BrandShareOfVoiceFromMicrosoft**. Údaje pro zájmy jsou v entitách **InterestAffinityFromMicrosoft** a **InterestShareOfVoiceFromMicrosoft**. Tyto entity najdete také ve skupině **Rozšíření** v umístění **Data** > **Entity**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Zobrazení rozšíření dat na kartě zákazníka

Podíl na sledovanosti značky a zájmu lze zobrazit i na jednotlivých zákaznických kartách. Jděte na **Zákazníci** a vyberte profil zákazníka. V zákaznické kartě najdete grafy pro podíl na sledovanosti značky nebo zájmu založené na lidech v demografickém profilu daného zákazníka.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta zákazníka s rozšířenými daty.":::

## <a name="next-steps"></a>Další kroky

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
