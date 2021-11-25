---
title: Vylepšení dat společnosti
description: Rozšiřte a normalizujte data společnosti pomocí modelů společnosti Microsoft.
ms.date: 11/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: d11700c87f31cedc40d32b201251d8a9e2e2c312
ms.sourcegitcommit: dfc4843cc78857f1e3ca49d7b938e3ba77969169
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2021
ms.locfileid: "7813910"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Rozšíření profilů společnosti o vylepšená data společnosti

K opravě, doplnění a standardizování profilů vaší společnosti použijte modely a kompilovaná firemní data společnosti Microsoft. Pro lepší přesnost a přehledy použijeme [formát Common Data Model](/common-data-model/schema/core/applicationcommon/account).

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

Vylepšená data mají několik omezení. Položky v seznamu níže nejsou modelem podporovány.

1.  Potvrzení identity společnosti. Neověřujeme, zda je vstupem existující organizace nebo zda společnost používá výstup jako svůj standardní název.
2.  Komplexně pokrývá společnosti po celém světě. Data společnosti kompilovaná společností Microsoft mají globální pokrytí, ale většinu pokrytí nabízejí v Austrálii, Kanadě, Spojeném království a Spojených státech.
3.  Globálně standardizujte firemní adresy. V současné době podporujeme standardizaci adres v těchto zemích nebo oblastech: Austrálie, Kanada, Francie, Německo, Itálie, Japonsko, Spojené království a Spojené státy americké.
4.  Garance správnosti nebo aktuálnosti dat. Vzhledem k tomu, že obchodní informace se často mění, nemůžeme zaručit, že poskytovaná vylepšená data společnosti jsou vždy přesná nebo aktuální.

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření**.

1. Vyberte **Rozšířit moje data** na dlaždici **Vylepšená data společnosti**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Dlaždice rozšíření v centru pro rozšíření dat společnosti.":::

1. Vyberte **Datová sada zákazníka** a vyberte entitu obsahující adresy, které chcete rozšířit. Můžete vybrat entitu *Zákazník* k obohacení adres ve všech vašich zákaznických profilech nebo entitu segmentu k obohacení adres pouze v zákaznických profilech obsažených v tomto segmentu.

1. Vyberte, který typ polí z profilů vaší společnosti se má použít pro porovnání s daty společnosti zkompilovanými společností Microsoft. Tento výběr ovlivní mapovací pole, ke kterým máte přístup v dalším kroku.

1.  Namapujte pole společnosti z vaší sjednocené entity zákazníka. Čím více identifikátorů a polí klíče mapujete, tím větší je pravděpodobnost vyšší míry shody.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Krok mapování dat při konfiguraci rozšíření společnosti.":::

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Zadejte název obohacení a název výstupní entity.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

## <a name="enrichment-results"></a>Výsledky rozšíření

Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů. Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab). Doba zpracování závisí na velikosti vašich zákaznických dat.

Po dokončení procesu obohacení můžete zkontrolovat nově obohacené údaje o zákaznických profilech v **Moje rozšíření**. Dále najdete čas poslední aktualizace a počet obohacených profilů.

Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.

## <a name="next-steps"></a>Další kroky

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
