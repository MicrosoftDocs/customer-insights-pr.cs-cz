---
title: Přehledy pro segmenty (Preview)
description: Získejte přehled o existujících segmentech a podívejte se na rozdíly a společné rysy.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170995"
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

1. Po dokončení analýzy vyhledejte podrobnosti o tomto přehledu v části **Segmenty** > **Přehledy (Preview)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Podrobnosti přehledu překrytí segmentů.":::

1. Chcete-li zobrazit výsledky analýzy, vyberte příslušný přehled:

   - Počet překrývajících se členů v segmentech vybraných pro analýzu.
   - Počet členů zahrnutých v jednom ze segmentů, ale nikoli ve zbývajících segmentech.
   - Pokud jste při konfiguraci analýzy překryté vybrali některá pole, najdete je na příslušných kartách. Pomocí rozevíracího seznamu filtru můžete vybrat libovolnou požadovanou úroveň atributu a tabulka v dolní části zobrazí odpovídající data.

## <a name="segment-differentiators"></a>Diferenciátory segmentů

Diferenciátory segmentů vám pomohou zjistit, co odlišuje segment od ostatních vašich zákazníků nebo od jiného segmentu. Vyberte segment a systém identifikuje atributy a míry profilu, které odlišují vybraný segment.

### <a name="run-a-differentiator-analysis"></a>Spuštění analýzy diferenciátoru

1. Přejděte na **Segmenty** a vyberte kartu **Přehledy (Preview)**.

1. Vyberte **Nový** a zvolte možnost **Diferenciátory** v panelu **Zvolte typ přehledu**.

1. Vyberte segment, který chcete analyzovat, jako **Primární segment** a vyberte **Další**.

1. Vyberte **Všichni zákazníci** nebo **Sekundární segment**, abyste porovnali svůj primární segment a vyberte **Další**.

1. Volitelně vyberte jedno nebo více oblastí zájmu, aby se analýza zaměřila na konkrétní atributy, a vyberte **Další**.

1. Zadejte název analýzy diferenciátoru, volitelný zobrazovaný název a popis.

1. Volbou **Uložit** spusťe analýzu. Analýza diferenciátoru je připravena, když se stav změní z Aktualizace na Úspěšné.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Zobrazení a optimalizace analýzy diferenciatorů

1. Po dokončení analýzy přejděte do části **Segmenty** > **Přehledy (Preview)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Podrobnosti přehledu diferenciátoru segmentů.":::

1. Chcete-li zobrazit výsledky analýzy, vyberte příslušný přehled. Analýza diferenciátoru zahrnuje dvě karty. Karta **Atributy** uvádí atributy profilu, které jsou považovány za diferenciátory. Karta **Míry** obsahuje diferenciátory. Každá karta obsahuje následující podrobnosti:

   - Hodnocený seznam diferenciátorů seřazený podle skóre rozdílnosti.
   - **Skóre rozdílnosti** pro každý diferenciátor. Skóre rozdílu představuje stupeň rozdílnosti atributu mezi dvěma segmenty. Čím vyšší je skóre rozdílnosti, tím více atributů se liší mezi těmito dvěma segmenty. Výběrem skóre otevřete podokno **Skóre rozdílnosti** s rozdělením hodnot pro tento atribut.

## <a name="manage-segment-insights"></a>Správa přehledů segmentů

Jděte na **Segmenty** > **Přehledy (Preview)** k zobrazení přehledů segmentů a jejich správě. Vyberte přehled segmentu pro zobrazení dostupných akcí.

- **Zobrazte** analýzu přehledu
- **Úpravou** přehledu změňte jeho vlastnosti
- **Aktualizujte** přehled pro opětovné spuštění analýzy
- **Přejmenujte** přehled
- **Odstraňte** přehled

[!INCLUDE [footer-include](includes/footer-banner.md)]
