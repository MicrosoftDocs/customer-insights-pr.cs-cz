---
title: Přehledy existujících segmentů
description: Získejte přehled o existujících segmentech a podívejte se na rozdíly a společné rysy.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1f90b0d18331584fce306da38bd31faea93ef97e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732304"
---
# <a name="segment-insights-preview"></a>Přehledy pro segmenty (Preview)

Získejte další informace a přehledy o vašich stávajících segmentech. Zjistěte, co odlišuje dva segmenty nebo co mají společné.

## <a name="segment-overlap"></a>Překrytí segmentů

Analýza překrytí segmentů ukazuje, kolik a které zákazníky sdílejí dva nebo více segmentů. Například jak se segment častých zákazníků překrývá se segmentem, který obsahuje zákazníky, kteří jsou spokojeni s vaší službou nebo produktem.
Můžete také analyzovat, jak se překrývání mění u konkrétních atributů.

### <a name="run-an-overlap-analysis"></a>Spuštění analýzy překrytí

1. Přejděte na **Segmenty** a vyberte kartu **Přehledy (Preview)**.

1. Vyberte **Nový** a zvolte možnost **Překrytí** v panelu **Zvolte typ přehledu**.

1. Vyberte požadované segmenty a vyberte **Další**.

1. Volitelně vyberte jedno nebo více požadovaných polí, chcete-li analyzovat překrytí pro každou možnou hodnotu pole, a vyberte **Další**.

1. Zadejte název analýzy překrytí, volitelný zobrazovaný název a popis.

1. Volbou **Uložit** spusťe analýzu. Analýza překrytí je připravena, když se stav změní z Aktualizace na Úspěšné.

### <a name="view-and-optimize-an-overlap-analysis"></a>Zobrazení a optimalizace analýzy překrytí

Po dokončení analýzy vyhledejte podrobnosti o tomto přehledu v části **Segmenty** > **Přehledy (Preview)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Podrobnosti přehledu překrytí segmentů.":::

Chcete-li zobrazit výsledky analýzy, vyberte příslušný přehled:

- Počet překrývajících se členů v segmentech vybraných pro analýzu.
- Počet členů zahrnutých v jednom ze segmentů, ale nikoli ve zbývajících segmentech.
- Pokud jste při konfiguraci analýzy překryté vybrali některá pole, najdete je na příslušných kartách. Pomocí rozevíracího seznamu filtru můžete vybrat libovolnou požadovanou úroveň atributu a tabulka v dolní části zobrazí odpovídající data.

## <a name="segment-differentiators"></a>Diferenciátory segmentů

Diferenciátory segmentů vám pomohou zjistit, co odlišuje segment od ostatních vašich zákazníků nebo od jiného segmentu. Musíte pouze vybrat segment a systém identifikuje atributy a míry profilu, které odlišují vybraný segment.

### <a name="run-a-differentiator-analysis"></a>Spuštění analýzy diferenciátoru

1. Přejděte na **Segmenty** a vyberte kartu **Přehledy (Preview)**.

1. Vyberte **Nový** a zvolte možnost **Překrytí** v panelu **Zvolte typ přehledu**.

1. Vyberte segment, který chcete analyzovat, jako **Primární segment** a vyberte **Další**.

1. Vyberte **Všichni zákazníci** nebo **Sekundární segment**, abyste porovnali svůj primární segment a vyberte **Další**.

1. Volitelně vyberte jedno nebo více oblastí zájmu, aby se analýza zaměřila na konkrétní atributy, a vyberte **Další**.

1. Zadejte název analýzy překrytí, volitelný zobrazovaný název a popis.

1. Volbou **Uložit** spusťe analýzu. Analýza překrytí je připravena, když se stav změní z Aktualizace na Úspěšné.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Zobrazení a optimalizace analýzy diferenciatorů

Po dokončení analýzy vyhledejte podrobnosti o tomto přehledu v části **Segmenty** > **Přehledy (Preview)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Podrobnosti přehledu diferenciátoru segmentů.":::

Chcete-li zobrazit výsledky analýzy, vyberte příslušný přehled. Analýza diferenciátoru zahrnuje dvě karty. Karta **Atributy** uvádí atributy profilu, které jsou považovány za diferenciátory. Karta **Míry** obsahuje diferenciátory. Každá karta obsahuje následující podrobnosti:

- Hodnocený seznam diferenciátorů seřazený podle skóre rozdílnosti.
- **Skóre rozdílnosti** pro každý diferenciátor. Skóre rozdílu představuje stupeň rozdílnosti atributu mezi dvěma segmenty. Čím vyšší je skóre rozdílnosti, tím více atributů se liší mezi těmito dvěma segmenty. Výběrem skóre otevřete podokno **Skóre rozdílnosti** s rozdělením hodnot pro tento atribut.

## <a name="manage-segment-insights"></a>Správa přehledů segmentů

V přehledech můžete použít následující možnosti z panelu příkazů:

- **Zpět** pro návrat na seznam přehledů
- **Aktualizovat** pro opětovné spuštění analýzy
- **Odstranit** pro odstranění tohoto přehledu


[!INCLUDE[footer-include](../includes/footer-banner.md)]
