---
title: Vylepšení dat společnosti
description: Rozšiřte a normalizujte data společnosti pomocí modelů společnosti Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953941"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Rozšíření profilů společnosti o vylepšená data společnosti

K opravě, doplnění a standardizování profilů vaší společnosti použijte modely a kompilovaná firemní data společnosti Microsoft. Pro lepší přesnost a přehledy použijeme [formát Common Data Model](/common-data-model/schema/core/applicationcommon/account).

Můžete také [rozšířit podniková data ve zdrojích dat](data-sources-enrichment.md) a zlepšit přesnost shody v procesu sjednocování dat.

Pro veřejné společnosti ve Spojených státech jsou k dispozici informace, jako jsou příjmy, burzovní burza, průmysl a další.  

## <a name="how-we-enhance-company-data"></a>Jak vylepšíme data společnosti

Při vylepšování profilu společnosti prochází náš model dvoufázovým procesem. Nejprve normalizuje název společnosti. Například *Microsoft Corp* bude opraven a standardizován na *Microsoft Corporation*. Snaží se najít shodu v datech společnosti kompilovaných společností Microsoft. Pokud je nalezena shoda, rozšíříme profil společnosti o informace z našich kompilovaných dat společnosti, včetně názvu společnosti.

### <a name="example"></a>Příklad

Informace o vaší společnosti nemusí mít standardizovaný formát a mohou obsahovat pravopisné chyby. Model se snaží tyto problémy opravit a vytvořit konzistentní informace.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Omezení

Model nikoliv:

- Potvrzení identity společnosti. Neověřujeme, zda je vstupem existující organizace nebo zda společnost používá výstup jako svůj standardní název.
- Komplexně pokrývá společnosti po celém světě. Data společnosti kompilovaná společností Microsoft mají globální pokrytí, ale většinu pokrytí nabízejí v Austrálii, Kanadě, Spojeném království a Spojených státech.
- Globálně standardizujte firemní adresy. V současné době podporujeme standardizaci adres v těchto zemích nebo oblastech: Austrálie, Kanada, Francie, Německo, Itálie, Japonsko, Spojené království a Spojené státy americké.
- Garance správnosti nebo aktuálnosti dat. Vzhledem k tomu, že obchodní informace se často mění, nemůžeme zaručit, že poskytovaná vylepšená data společnosti jsou vždy přesná nebo aktuální.

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření** a vyberte kartu **Objevit**.

1. Vyberte **Rozšířit moje data** na dlaždici **Vylepšená data společnosti**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Dlaždice rozšíření v centru pro rozšíření dat společnosti.":::

1. Zkontrolujte přehled a poté vyberte **Další**.

1. Vyberte **Sada údajů o zákazníkovi** a zvolte profil nebo segment, které chcete rozšířit. Entita *Zákazník* rozšíří všechny profily vašich zákazníků zatímco segment rozšíří pouze profily zákazníků obsažené v tomto segmentu.

1. Vyberte, který typ polí z profilů vaší společnosti se má použít pro porovnání s daty společnosti zkompilovanými společností Microsoft. Tento výběr ovlivní mapovací pole, ke kterým máte přístup v dalším kroku.

1. Vyberte **Další**.

1. Namapujte pole vaší společnosti na firemní data od společnosti Microsoft. Pro vyšší přesnost shody přidejte další pole.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Krok mapování dat při konfiguraci rozšíření společnosti.":::

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Zadejte **Název** rozšíření a **Výstupní entitu**.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

1. Vyberte **Spustit** k zahájení procesu obohacování nebo blízko k návratu na stránku **Rozšíření**.

## <a name="enrichment-results"></a>Výsledky rozšíření

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Karta Přehled

Dlaždice **Přehled změn zákazníků** zobrazuje podrobnosti o pokrytí rozšíření

- **Zpracované a změněné společnosti**: Počet profilů společností zákazníků, které byly úspěšně rozšířeny.
- **Zpracované a nezměněné společnosti**: Počet profilů společností zákazníků, které byly rozpoznány, ale nebyly změněny. To se obvykle stane, když jsou vstupní data platná a nelze je zlepšit rozšířením.
- **Nezpracované a nezměněné společnosti**: Počet profilů společností zákazníků, které nebyly rozpoznány. Obvykle se to děje u vstupních dat, která jsou neplatná nebo je rozšíření nepodporuje.

## <a name="next-steps"></a>Další kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
