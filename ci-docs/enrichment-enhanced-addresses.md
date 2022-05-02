---
title: Rozšíření vylepšení adresy (obsahuje video)
description: Rozšiřte a normalizujte informace o adresách profilů zákazníků s modely společnosti Microsoft.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: b4fef3b5e30e1cac4e5cb4401498f2f0981a409e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645719"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Rozšíření profilů zákazníků o vylepšené adresy

Adresy ve vašich datech mohou být nestrukturované, neúplné nebo nesprávné. Použijte modely společnosti Microsoft k normalizaci a rozšíření vašich adres do [formátu Common Data Model](/common-data-model/schema/core/applicationcommon/address) pro lepší přesnost a přehledy.

Můžete také [rozšířit zdroje dat o adresy](data-sources-enrichment.md) a zlepšit přesnost shody v procesu sjednocování dat. 

## <a name="how-we-enhance-addresses"></a>Jak vylepšujeme adresy

Náš model prochází vylepšením adresy ve dvou krocích. Nejprve analyzuje adresu, aby identifikovala její komponenty, a umístí je do strukturovaného formátu. Poté pomocí AI opravíme, doplníme a standardizujeme hodnoty v adrese.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Příklad

Informace o adrese mohou být v nestandardním formátu a mohou obsahovat pravopisné chyby. Model může tyto problémy vyřešit a vytvořit konzistentní adresy v jednotných zákaznických profilech.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Omezení

Vylepšené adresy pracují pouze s hodnotami, které již existují v přijatých datech adres. Model nikoliv: 

1. Ověřte, zda je adresa platná.
2. Ověřte, zda jsou některé z hodnot, například PSČ nebo názvy ulic, platné.
3. Změňte hodnoty, které nerozpozná.

Model používá techniky založené na strojovém učení k vylepšení adres. I když použijeme vysokou prahovou hodnotu spolehlivosti, když model změní vstupní hodnotu, stejně jako u jakéhokoli modelu založeného na strojovém učení, není zaručena 100% přesnost.

## <a name="supported-countries-or-regions"></a>Podporované země nebo regiony

V současné době podporujeme rozšiřující adresy v těchto zemích nebo regionech: 

- Austrálie
- Kanada
- Francie
- Německo
- Itálie
- Japonsko
- Spojené království
- USA

Adresy musí obsahovat hodnotu země / oblasti. Nezpracováváme adresy pro země nebo oblasti, které nejsou podporovány, a adresy, které nemají zadanou zemi nebo oblast.

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření**.

1. Vyberte **Rozšířit moje data** v dlaždici **Vylepšené adresy**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Screenshot dlaždice Vylepšené adresy.":::

1. Vyberte **Datová sada zákazníka** a vyberte entitu obsahující adresy, které chcete rozšířit. Můžete vybrat entitu *Zákazník* k rozšíření adres ve všech vašich zákaznických profilech nebo entitu segmentu k rozšíření adres pouze v zákaznických profilech obsažených v tomto segmentu.

1. Vyberte způsob formátování adres v datové sadě. Pokud adresy ve vašich datech používají jedno pole, zvolte **Adresa s jedním atributem**. Pokud adresy ve vašich datech používají více než jedno datové pole, zvolte **Adresa s více atributy**.

   > [!NOTE]
   > Země / oblast je povinná u adres s jedním atributem i u více atributů. Adresy, které neobsahují platné nebo podporované hodnoty země / oblasti, nebudou rozšířeny.

1.  Mapujte pole adresy z vaší sjednocené entity zákazníka.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Vylepšená stránka pro mapování polí adresy.":::

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Zadejte název rozšíření a název výstupní entity.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

## <a name="enrichment-results"></a>Výsledky rozšíření

Chcete-li zahájit proces rozšíření, vyberte **Spustit** z panelu příkazů. Můžete také nechat systém automaticky spustit rozšíření jako součást [plánované aktualizace](system.md#schedule-tab). Doba zpracování závisí na velikosti vašich zákaznických dat.

Po dokončení procesu rozšíření můžete zkontrolovat nově rozšířené údaje o zákaznických profilech v **Moje rozšíření**. Dále najdete čas poslední aktualizace a počet rozšířených profilů.

Ukázku rozšířených dat můžete vidět v dlaždici **Náhled rozšířených zákazníků**. Vyberte možnost **Další informace** a vyberte kartu **Data** , na které najdete podrobné zobrazení každého rozšířeného profilu.

### <a name="overview-card"></a>Karta Přehled

Karta Přehled zobrazuje podrobnosti o pokrytí rozšíření. 

* **Zpracované a změněné adresy**: Počet zákaznických profilů s adresami, které byly úspěšně rozšířeny.

* **Zpracované a nezměněné adresy**: Počet zákaznických profilů s adresami, které byly rozpoznány, ale nebyly změněny. To se obvykle stane, když jsou vstupní data platná a nelze je zlepšit rozšířením.

* **Nezpracované a nezměněné adresy**: Počet zákaznických profilů s adresami, které nebyly rozpoznány. Obvykle se to děje u vstupních dat, která jsou neplatná nebo je rozšíření nepodporuje.

## <a name="next-steps"></a>Další kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
