---
title: Rozšíření profilů zákazníků daty od společnosti Microsoft
description: Použijte vlastnická data od společnosti Microsoft k rozšíření svých zákaznických dat o afinitu ke značce a zájmem.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 3b10fb23cca03ed918aa7fd46478b568d5ebbf1a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555483"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Obohaťte si zákaznické profily značkami a zájmovými skupinami (preview)

Použijte vlastnická data společnosti Microsoft k rozšíření svých zákaznických dat o afinitu ke značce a zájmem. Tyt afinity jsou založeny na datech od lidí v podobné demografické skupině, jako jsou vaši zákazníci. Tyto informace vám pomohou lépe porozumět a rozdělit zákazníky podle jejich náklonnosti ke konkrétním značkám a zájmům.

V přehledech cílové skupiny přejděte na **Data** > **Rozšíření**, kde můžete [nakonfigurovat a zobrazit rozšíření](enrichment-hub.md).

Chcete-li nakonfigurovat rozšíření o náklonnost ke značkám, přejděte na kartu **Zjistit** a vyberte **Rozšířit moje data** na dlaždici **Značky**.

Chcete-li nakonfigurovat rozšíření o náklonnost k zájmům, přejděte na kartu **Zjistit** a vyberte **Rozšířit moje data** na dlaždici **Zájmy**.

   > [!div class="mx-imgBorder"]
   > ![Dlaždice Značky a zájmy.](media/BrandsInterest-tile-Hub.png "Dlaždice Značky a zájmy")

## <a name="how-we-determine-affinities"></a>Jak určujeme afinity

Údaje online vyhledávání společnosti Microsoft používáme k vyhledání afinity ke značkám a zájmy v různých demografických segmentech (definovaných podle věku, pohlaví nebo polohy). Objem online vyhledávání pro určitou značku nebo zájem určuje, jak velkou afinitu má demografický segment ve srovnání s jinými segmenty k této značce nebo zájmu.

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

Vyberte **Rozšířená entita** a vyberte datovou sadu, kterou chcete rozšířit o firemní data od společnosti Microsoft. Můžete vybrat entitu Zákazník k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.

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

> [!TIP]
> Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy. Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies). Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy. Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.

## <a name="enrichment-results"></a>Výsledky rozšíření

Po spuštění procesu rozšíření přejděte na **Moje rozšíření**, kde zkontrolujte celkový počet rozšířených zákazníků a rozpis značek nebo zájmů v rozšířených profilech zákazníků.

:::image type="content" source="media/my-enrichments.png" alt-text="Náhled výsledků po spuštění procesu rozšíření.":::

Prohlédněte si obohacená data výběrem **Zobrazit obohacená data** v grafu. Obohatená data pro značky obsahuje entita **BrandAffinityFromMicrosoft**. Data pro zájmy jsou v entitě **InterestAffinityFromMicrosoft**. Tyto entity najdete také ve skupině **Rozšíření** v umístění **Data** > **Entity**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Zobrazení rozšíření dat na kartě zákazníka

Náklonnost ke značkám a zájmům lze zobrazit také na jednotlivých kartách zákazníka. Jděte na **Zákazníci** a vyberte profil zákazníka. Na kartě zákazníka najdete grafy značek nebo zájmů, ke kterým mají lidé v demografickém profilu zákazníka náklonnost.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta zákazníka s rozšířenými daty.":::

## <a name="next-steps"></a>Další kroky

Stavte na svých obohacených zákaznických údajích. Vytvořte [segmenty](segments.md) a [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům poskytli přizpůsobené prostředí.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
