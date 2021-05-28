---
title: Obohacení vylepšením adresy
description: Obohaťte a normalizujte informace o adresách profilů zákazníků s modely společnosti Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965570"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Obohacení profilů zákazníků o vylepšené adresy

Adresy ve vašich datech mohou být nestrukturované, neúplné nebo nesprávné. Použijte modely společnosti Microsoft k normalizaci a obohacení vašich adres do [formátu Common Data Model](/common-data-model/schema/core/applicationcommon/address) pro lepší přesnost a přehledy.

## <a name="how-we-enhance-addresses"></a>Jak vylepšujeme adresy

Náš model prochází vylepšením adresy ve dvou krocích. Nejprve analyzuje adresu, aby identifikovala její komponenty, a umístí je do strukturovaného formátu. Poté pomocí umělé inteligence opravíme, doplníme a standardizujeme hodnoty v adrese.

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

Model používá techniky založené na strojovém učení k vylepšení adres. I když použijeme vysokou mezní hodnotu spolehlivosti, platí, že když model změní vstupní hodnotu, stejně jako u jakéhokoli modelu založeného na ML není zaručena 100% přesnost.

## <a name="supported-countries-or-regions"></a>Podporované země nebo regiony

V současné době podporujeme obohacující adresy v těchto zemích nebo regionech: 

- Austrálie
- Kanada
- Spojené království
- USA

Adresy musí obsahovat hodnotu země / oblasti. Nezpracováváme adresy pro země nebo oblasti, které nejsou podporovány, a adresy, které nemají zadanou zemi nebo oblast.

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření**.

1. Vyberte **Obohatit moje data** v dlaždici **Vylepšené adresy**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Screenshot dlaždice Vylepšené adresy.":::

1. Vyberte **Datová sada zákazníka** a vyberte entitu obsahující adresy, které chcete rozšířit. Můžete vybrat entitu *Zákazník* k obohacení adres ve všech vašich zákaznických profilech nebo entitu segmentu k obohacení adres pouze v zákaznických profilech obsažených v tomto segmentu.

1. Vyberte způsob formátování adres v datové sadě. Pokud adresy ve vašich datech používají jedno pole, zvolte **Adresa s jedním atributem**. Pokud adresy ve vašich datech používají více než jedno datové pole, zvolte **Adresa s více atributy**.

   > [!NOTE]
   > Země / oblast je povinná u adresy s jedním i více atributy. Adresy, které neobsahují platné nebo podporované hodnoty země / oblasti, nebudou obohaceny

1.  Mapujte pole adresy z vaší sjednocené entity zákazníka.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Vylepšená stránka pro mapování polí adresy.":::

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Zadejte název obohacení a název výstupní entity.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

## <a name="enrichment-results"></a>Výsledky rozšíření

Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů. Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab). Doba zpracování závisí na velikosti vašich zákaznických dat.

Po dokončení procesu obohacení můžete zkontrolovat nově obohacené údaje o zákaznických profilech v **Moje rozšíření**. Dále najdete čas poslední aktualizace a počet obohacených profilů.

Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.

## <a name="next-steps"></a>Další kroky

Stavte na svých obohacených zákaznických údajích. Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
