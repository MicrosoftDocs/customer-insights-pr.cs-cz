---
title: Rozšíření profilů zákazníků o vylepšené adresy (obsahuje video)
description: Rozšiřte a normalizujte informace o adresách profilů zákazníků s modely společnosti Microsoft.
ms.date: 06/10/2022
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
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080840"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Rozšíření profilů zákazníků o vylepšené adresy

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

Rozšířené adresy fungují pouze s hodnotami, které již existují ve vašich zpracovaných datech adresy. Model nikoliv:

1. Ověřte, zda je adresa platná.
2. Ověřte, zda jsou některé z hodnot, například PSČ nebo názvy ulic, platné.
3. Změňte hodnoty, které nerozpozná.

Model používá techniky založené na strojovém učení k vylepšení adres. Stejně jako u jakéhokoli modelu založeného na strojovém učení není zaručena 100procentní přesnost.

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

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření** a vyberte kartu **Objevit**.

1. Vyberte **Rozšířit moje data** v dlaždici **Vylepšené adresy**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Screenshot dlaždice Vylepšené adresy.":::

1. Zkontrolujte přehled a poté vyberte **Další**.

1. Vyberte **Sada údajů o zákazníkovi** a zvolte profil nebo segment, které chcete rozšířit. Entita *Zákazník* rozšíří všechny profily vašich zákazníků zatímco segment rozšíří pouze profily zákazníků obsažené v tomto segmentu.

1. Vyberte způsob formátování adres v datové sadě. Pokud adresy ve vašich datech používají jedno pole, zvolte **Adresa s jedním atributem**. Pokud adresy ve vašich datech používají více než jedno datové pole, zvolte **Adresa s více atributy**.

1. Vyberte **Další** a namapujte pole adresy z vaší jednotné zákaznické entity.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Vylepšená stránka pro mapování polí adresy.":::

   > [!NOTE]
   > Země / oblast je povinná u adres s jedním atributem i u více atributů. Adresy, které neobsahují platné nebo podporované hodnoty země / oblasti, nebudou rozšířeny.

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Zadejte **Název** rozšíření a **Výstupní entitu**.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

## <a name="view-enrichment-results"></a>Zobrazení výsledků rozšiřování

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Pokud je k dispozici možnost **Počet zákazníků obohacených o pole**, můžete procházet k podrobnostem pokrytí každého rozšířeného pole.

### <a name="overview-card"></a>Karta Přehled

Karta **Přehled změn zákazníků** zobrazuje podrobnosti o pokrytí rozšíření:

- **Zpracované a změněné adresy**: Počet zákaznických profilů s adresami, které byly úspěšně rozšířeny.
- **Zpracované a nezměněné adresy**: Počet zákaznických profilů s adresami, které byly rozpoznány, ale nebyly změněny. To se obvykle stane, když jsou vstupní data platná a nelze je zlepšit rozšířením.
- **Nezpracované a nezměněné adresy**: Počet zákaznických profilů s adresami, které nebyly rozpoznány. Obvykle se to děje u vstupních dat, která jsou neplatná nebo je rozšíření nepodporuje.

## <a name="next-steps"></a>Další kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
