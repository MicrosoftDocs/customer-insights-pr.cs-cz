---
title: Segmenty v přehledech cílové skupiny
description: Vytvořte přehled segmentů a způsob jejich vytváření a správy.
ms.date: 03/30/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 68e71df3853470af47228c7365f25db3a71d15b0
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529531"
---
# <a name="segments-overview"></a>Přehled segmentů

Segmenty umožňují seskupit zákazníky na základě demografických, transakčních nebo behaviorálních atributů. Segmenty můžete použít k cílení propagačních kampaní, prodejních aktivit a akcí podpory zákazníků k dosažení vašich obchodních cílů.

Profily zákazníků, které odpovídají filtrům definice segmentu, se označují jako *prvky* segmentu. Použijí se některé [servisní limity](/dynamics365/customer-insights/service-limits).

## <a name="create-a-new-segment"></a>Vytvořit nový segment

Existuje několik způsobů, jak vytvořit nový segment: 

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

- Složitý segment s nástrojem pro tvorbu segmentů: [Vybudujte si vlastní](segment-builder.md#create-a-new-segment) 
- Jednoduché segmenty s jedním operátorem: [Rychlý segment](segment-builder.md#quick-segments) 
- Způsob vyhledání podobných zákazníků pomocí technologie AI: [Podobní zákazníci](find-similar-customer-segments.md) 
- Návrhy využívající AI založené na mírách nebo atributech: [Navrhované segmenty ke zlepšení měr](suggested-segments.md) 
- Návrhy založené na činnostech: [Navrhované segmenty na základě aktivity zákazníků](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

- Složitý segment s nástrojem pro tvorbu segmentů: [Vybudujte si vlastní](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Správa existujících segmentů

Jděte na stránku **Segmenty**, kde můžete zobrazit všechny uložené segmenty a spravovat je.

Každý segment je reprezentován řádkem, která obsahuje další informace o segmentu.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Vybraný segment s rozevíracím seznamem možností a dostupnými možnostmi." lightbox="media/segments-selected-segment.png":::

Po výběru segmentu jsou k dispozici následující akce:

- **Zobrazit** podrobnosti o segmentu, včetně trendu počtu členů, náhledu členů segmentu.
- **Stáhnout** seznam členů jako soubor .CSV.
- **Upravit** segment změnit jeho vlastnosti.
- **Vytvořit duplicitu** segmentu. Můžete se rozhodnout upravit její vlastnosti hned nebo duplicitu jednoduše uložit.
- **Obnovit** segment a zahrnout nejnovější data.
- **Aktivace** nebo **deaktivace** segmentu. Pro neaktivní segmenty existuje jejich definice, ale zatím neobsahuje žádné zákazníky. Aktivní segment hledá zákazníky, kteří odpovídají definici segmentu. Pokud je konfigurována [plánovaná aktualizace](system.md#schedule-tab), neaktivní segmenty mají **Stav** uveden jako **Přeskočeno**, což označuje, že u nich neproběhl ani pokus o aktualizaci. Když je neaktivní segment aktivován, aktualizuje se a bude součástí plánovaných aktualizací.
  Případně můžete použít funkci **Plánovat později** v rozevíracím seznamu **Aktivovat/deaktivovat** pro určení budoucího data a času aktivace a deaktivace konkrétního segmentu.
- **[Vyhledat podobné zákazníky](find-similar-customer-segments.md)** ze segmentu.
- **Přejmenovat** segment.
- Volbou **Značka** můžete [spravovat značky](work-with-tags-columns.md#manage-tags) pro segment.
- **Stáhnout** seznam členů jako soubor .CSV.
- Možnost **Spravovat exporty** zobrazí segment související s exportem a umožní jeho správu. [Další informace o exportech.](export-destinations.md)
- **Odstranit** segment.
- **Sloupce** pro [přizpůsobení sloupců](work-with-tags-columns.md#customize-columns), které se zobrazí.
- **Filtrovat** pro [filtrování podle značek](work-with-tags-columns.md#filter-on-tags).
- **Hledat název** pro vyhledání podle názvu segmentu.

## <a name="refresh-segments"></a>Aktualizovat segmenty

Můžete aktualizovat všechny segmenty najednou výběrem **Aktualizovat vše** na stránce **Segmenty** nebo můžete aktualizovat jeden nebo více segmentů, když je vyberete a z možností vyberete volbu **Aktualizovat**. Případně můžete nakonfigurovat opakovanou aktualizaci **Správce** > **Systém** > **Plán**. Při konfiguraci opakované aktualizace platí následující pravidla:
- Všechny segmenty s typem **Dynamický** nebo **Rozšíření** se automaticky aktualizují podle nastavené kadence. Po dokončení obnovy **Stav** označuje, zda při aktualizaci segmentu došlo k nějakým problémům. **Poslední aktualizace** zobrazuje časové razítko poslední úspěšné aktualizace. Pokud dojde k chybě, výběrem chyby zobrazíte podrobnosti o tom, co se stalo.
- Segmenty s typem **Statický** *nebudou* automaticky aktualizovány. **Poslední aktualizace** zobrazuje časové razítko posledního spuštění nebo ruční aktualizace statických segmentů.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Export segmentů

Segment můžete exportovat ze stránky segmentů nebo ze [stránky exportů](export-destinations.md). 

1. Přejde na stránku **Segmenty**.

1. Vyberte možnost **Zobrazit další [...]** pro segment, který chcete exportovat.

1. V rozevíracím seznamu akcí vyberte **Spravovat exporty**.

1. Otevře se stránka **Exporty (preview) pro segment**. Všechny nakonfigurované exporty můžete vidět seskupené podle toho, zda obsahují aktuální segment nebo ne.

   1. Chcete -li přidat vybraný segment do exportu, **upravte** příslušný export pro výběr odpovídajících segmentů a poté uložte. V prostředích pro jednotlivé zákazníky můžete místo toho vybrat export v seznamu a vybrat **Přidat segment**, abyste dosáhli stejného výsledku.

   1. Chcete-li vytvořit nový export s vybraným segmentem, vyberte **Přidat export**. Další informace o vytváření exportů najdete v části [Nastavení nového exportu](export-destinations.md#set-up-a-new-export).

1. Výběrem možnosti **Zpět** se vraťte na hlavní stránku pro segmenty.

## <a name="view-processing-history-and-segment-members"></a>Zobrazit historii zpracování a členy segmentu

Konsolidovaná data o segmentu můžete zobrazit kontrolou jeho podrobností.

Na stránce **Segmenty** vyberte segment, který chcete zkontrolovat.

Horní část stránky obsahuje graf trendů, který vizualizuje změny v počtu členů. Najeďte na datové body, abyste viděli počet členů k určitému datu.

Můžete aktualizovat časový rámec vizualizace.

> [!div class="mx-imgBorder"]
> ![Časový rozsah segmentu.](media/segment-time-range.png "Časový rozsah segmentu")

Spodní část obsahuje seznam členů segmentu.

> [!NOTE]
> Pole, která se zobrazí v tomto seznamu, jsou založena na atributech entit segmentu.
>
>Seznam je náhledem odpovídajících členů segmentu a zobrazuje prvních 100 záznamů segmentu, takže jej můžete rychle vyhodnotit a v případě potřeby zkontrolovat jeho definice. Chcete-li zobrazit všechny odpovídající záznamy, je třeba [segment exportovat](export-destinations.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
