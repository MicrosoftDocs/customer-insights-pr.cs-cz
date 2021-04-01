---
title: Rozšíření profilů zákazníků pomocí Microsoft Graphu
description: Použijte proprietární data z Microsoft Graph k obohacení svých zákaznických údajů o značky a zájmové afinity.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: aa46dac4f9c0d27881371877b14a92a6725710da
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596445"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Obohaťte si zákaznické profily značkami a zájmovými skupinami (preview)

Použijte proprietární data z Microsoft Graph k obohacení svých zákaznických údajů o značky a zájmové afinity. Tato náklonnost je určována na základě údajů od osob z podobné demografické skupiny jako vaši zákazníci. Tyto informace vám pomohou lépe porozumět a rozdělit zákazníky podle jejich náklonnosti ke konkrétním značkám a zájmům.

V přehledech cílové skupiny přejděte na **Data** > **Rozšíření**, kde můžete [nakonfigurovat a zobrazit rozšíření](enrichment-hub.md).

Chcete-li nakonfigurovat rozšíření o náklonnost ke značkám, přejděte na kartu **Zjistit** a vyberte **Rozšířit moje data** na dlaždici **Značky**.

Chcete-li nakonfigurovat rozšíření o náklonnost k zájmům, přejděte na kartu **Zjistit** a vyberte **Rozšířit moje data** na dlaždici **Zájmy**.

   > [!div class="mx-imgBorder"]
   > ![Dlaždice Značky a zájmy](media/BrandsInterest-tile-Hub.png "Dlaždice Značky a zájmy")

## <a name="about-microsoft-graph"></a>O Microsoft Graphu

Data z vyhledávání online z programu Microsoft Graph používáme k vyhledání afinity ke značkám a zájmům v různých demografických segmentech (definovaných věkem, pohlavím nebo místem). Objem online vyhledávání pro určitou značku nebo zájem určuje, jak velkou afinitu má demografický segment ve srovnání s jinými segmenty k této značce nebo zájmu.

[Další informace o Microsoft Graphu](/graph/overview).

## <a name="affinity-level-and-score"></a>Úroveň a skóre afinity

U každého rozšířeného zákaznického profilu poskytujeme dvě související hodnoty -–úroveň afinity a skóre afinity. Tyto hodnoty vám pomohou určit, jak silná je afinita k demografickému segmentu daného profilu, ke značce nebo zájmu ve srovnání s jinými demografickými segmenty.

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

Chcete-li vybrat zemi, otevřete **Rozšíření značek** nebo **Rozšíření zájmů** a vyberte **Změnit** vedle **Země/oblasti**. V podokně **Nastavení země/oblasti** vyberte požadovanou možnost a vyberte **Použít**.

### <a name="implications-related-to-country-selection"></a>Důsledky výběru země

- Při [výběru vlastních značek](#define-your-brands-or-interests) systém poskytne návrhy na základě vybrané země nebo oblasti.

- Při [výběru odvětví](#define-your-brands-or-interests) se vám zobrazí nejrelevantnější značky nebo zájmy na základě vybrané země nebo oblasti.

- Při [rozšiřování profilů](#refresh-enrichment) dojde k rozšíření profilů zákazníků, pro které získáme údaje o vybraných značkách a zájmech. Včetně profilů, které nejsou ve vybrané zemi nebo oblasti. Pokud jste například vybrali Německo, rozšíříme profily umístěné ve Spojených státech, pokud máme k dispozici data Microsoft Graphu pro vybrané značky a zájmy v USA.

## <a name="configure-enrichment"></a>Konfigurace rozšíření

### <a name="define-your-brands-or-interests"></a>Uveďte své značky nebo zájmy

Vyberte jednu z následujících možností:

- **Odvětví**: Systém identifikuje top značky nebo zájmy relevantní pro váš obor a obohacuje o ně vaše zákaznická data.
- **Vyberte vlastní**: Ze seznamu značek nebo zájmů, které jsou pro vaši organizaci nejvhodnější, vyberte až pět položek.

Chcete-li přidat značku nebo zájem, zadejte je do vstupní oblasti a získejte návrhy na základě odpovídajících podmínek. Pokud neuvedeme značku nebo zájem, který hledáte, pošlete nám zpětnou vazbu pomocí odkazu **Navrhnout**.

### <a name="review-enrichment-preferences"></a>Kontrola předvoleb rozšíření

Zkontrolujte své výchozí předvolby rozšíření a podle potřeby je aktualizujte.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Screenshot okna předvoleb rozšíření.":::

### <a name="select-entity-to-enrich"></a>Vyberte entitu, kterou chcete rozšířit.

Vyberte **Rozšířená entita** a zvolte datovou sadu, kterou chcete rozšířit o firemní data z Microsoft Graph. Můžete vybrat entitu Zákazník k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.

### <a name="map-your-fields"></a>Mapování polí

Namapujte pole z vaší sjednocené entity zákazníka a definujte demografický segment, který má systém použít k rozšíření vašich zákaznických dat. Namapujte zemi/oblast a alespoň atributy Datum narození nebo Pohlaví. Kromě toho je nutné namapovat alespoň jedno z měst (a kraj) nebo PSČ. Volbou **Upravit** definujete mapování polí a když máte hotovo, vyberte **Použít**. Vyberte **Uložit** pro dokončení mapování pole.

Jsou podporovány následující formáty a hodnoty, hodnoty nerozlišují velká a malá písmena:

- **Datum narození**: Během příjmu dat doporučujeme převést datum narození na typ Datum a čas. Alternativně to může být řetězec ve formátu [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) „rrrr-MM-dd“ nebo „rrrr-MM-ddTHH: mm: ssZ“.
- **Pohlaví**: Muž, žena, neznámý
- **PSČ**: Pětimístné PSČ pro USA, standardní PSČ všude jinde
- **Město**: Název města v angličtině
- **Kraj**: Dvoupísmenná zkratka pro USA a Kanadu. Dvou- nebo třípísmenná zkratka pro Austrálii. Nelze použít ve Francii, Německu nebo Velké Británii.
- **Země/oblast**:

  - US: Spojené státy americké, Spojené státy, USA, US, Amerika
  - CA: Kanada, CA
  - GB: Spojené království, UK, Velká Británie, GB, Spojené království Velké Británie a Severního Irska, Spojené království Velké Británie
  - AU: Austrálie, AU, Australské společenství
  - FR: Francie, FR, Francouzská republika
  - DE: Německo, němčina, Deutschland, Allemagne, DE, Spolková republika Německo, Německo

## <a name="refresh-enrichment"></a>Aktualizace rozšíření

Spusťte obohacení po konfiguraci značek, zájmů a mapování terénu pro demografii. Chcete-li zahájit proces, vyberte **Spustit** na stránce konfigurace značek nebo zájmů. Kromě toho můžete nechat systém spustit rozšíření automaticky jako součást plánované aktualizace.
V závislosti na velikosti vašich zákaznických dat může dokončení obohacování trvat několik minut.

> [!TIP]
> Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy. Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies). Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy. Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.

## <a name="enrichment-results"></a>Výsledky rozšíření

Po spuštění procesu rozšíření přejděte na **Moje rozšíření**, kde zkontrolujte celkový počet rozšířených zákazníků a rozpis značek nebo zájmů v rozšířených profilech zákazníků.

:::image type="content" source="media/my-enrichments.png" alt-text="Náhled výsledků po spuštění procesu rozšíření":::

Prohlédněte si obohacená data výběrem **Zobrazit obohacená data** v grafu. Obohatená data pro značky obsahuje entita **BrandAffinityFromMicrosoft**. Data pro zájmy jsou v entitě **InterestAffinityFromMicrosoft**. Tyto entity najdete také ve skupině **Rozšíření** v umístění **Data** > **Entity**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Zobrazení rozšíření dat na kartě zákazníka

Náklonnost ke značkám a zájmům lze zobrazit také na jednotlivých kartách zákazníka. Jděte na **Zákazníci** a vyberte profil zákazníka. Na kartě zákazníka najdete grafy značek nebo zájmů, ke kterým mají lidé v demografickém profilu zákazníka náklonnost.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta zákazníka s rozšířenými daty":::

## <a name="next-steps"></a>Další kroky

Stavte na svých obohacených zákaznických údajích. Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.


[!INCLUDE[footer-include](../includes/footer-banner.md)]