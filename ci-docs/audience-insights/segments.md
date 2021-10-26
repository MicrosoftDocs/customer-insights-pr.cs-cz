---
title: Segmenty v přehledech cílové skupiny
description: Vytvořte přehled segmentů a způsob jejich vytváření a správy.
ms.date: 09/30/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6840f4bc345b0821fb2349666130b39d542878e7
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617331"
---
# <a name="segments-overview"></a>Přehled segmentů

Segmenty umožňují seskupit zákazníky na základě demografických, transakčních nebo behaviorálních atributů. Segmenty můžete použít k cílení propagačních kampaní, prodejních aktivit a akcí podpory zákazníků k dosažení vašich obchodních cílů.

Profily zákazníků, které odpovídají filtrům definice segmentu, se označují jako *prvky* segmentu. Použijí se některé [servisní limity](service-limits.md).

## <a name="create-a-new-segment"></a>Vytvořit nový segment

Existuje několik způsobů, jak vytvořit nový segment: 

# <a name="individual-customers-b2c"></a>[Jednotliví zákazníci (B2C)](#tab/b2c)

- Složitý segment s nástrojem pro tvorbu segmentů: [Vybudujte si vlastní](segment-builder.md#create-a-new-segment) 
- Jednoduché segmenty s jedním operátorem: [Rychlý segment](segment-builder.md#quick-segments) 
- Způsob vyhledání podobných zákazníků pomocí technologie AI: [Podobní zákazníci](find-similar-customer-segments.md) 
- Návrhy využívající AI založené na mírách nebo atributech: [Navrhované segmenty ke zlepšení měr](suggested-segments.md) 
- Návrhy založené na činnostech: [Navrhované segmenty na základě aktivity zákazníků](suggested-segments-activity.md) 

# <a name="business-accounts-b2b"></a>[Obchodní účty (B2C)](#tab/b2b)

- Složitý segment s nástrojem pro tvorbu segmentů: [Vybudujte si vlastní](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Správa existujících segmentů

Jděte na stránku **segmenty**, kde můžete zobrazit všechny uložené segmenty a spravovat je.

Každý segment je reprezentován řádkem, která obsahuje další informace o segmentu.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Vybraný segment s rozevíracím seznamem možností a dostupnými možnostmi.":::

Když vyberete segment, jsou k dispozici následující akce:

- **Zobrazit** podrobnosti o segmentu, včetně trendu počtu členů, náhledu členů segmentu.
- **Upravit** segment změnit jeho vlastnosti.
- **Vytvořit duplicitu** segmentu. Můžete se rozhodnout upravit její vlastnosti hned nebo duplicitu jednoduše uložit.
- **Obnovit** segment a zahrnout nejnovější data.
- **Aktivace** nebo **deaktivace** segmentu. Segmenty mají dva možné stavy – aktivní nebo neaktivní. Tyto stavy jsou užitečné při úpravách segmentu. Pro neaktivní segmenty existuje jejich definice, ale zatím neobsahuje žádné zákazníky. Když aktivujete segment, jeho stav se změní z „neaktivní“ na „aktivní“ a začne hledat zákazníky, kteří odpovídají definici segmentu. Pokud je konfigurována [plánovaná aktualizace](system.md#schedule-tab), neaktivní segmenty mají **Stav** uveden jako **Přeskočeno**, což označuje, že u nich neproběhl ani pokus o aktualizaci. Když je neaktivní segment aktivován, aktualizuje se a bude součástí plánovaných aktualizací.
  Případně můžete použít funkci **Plánovat později** v rozevíracím seznamu **Aktivovat/deaktivovat** pro určení budoucího data a času aktivace a deaktivace konkrétního segmentu.
- **Přejmenovat** segment.
- **Stáhnout** seznam členů jako soubor .CSV.
- Možnost **Spravovat exporty** zobrazí segment související s exportem a umožní jeho správu. [Další informace o exportech.](export-destinations.md)
- **Odstranit** segment.

## <a name="refresh-segments"></a>Aktualizovat segmenty

Můžete aktualizovat všechny segmenty najednou výběrem **Aktualizovat vše** na stránce **Segmenty** nebo můžete aktualizovat jeden nebo více segmentů, když je vyberete a z možností vyberete volbu **Aktualizovat**. Případně můžete nakonfigurovat opakovanou aktualizaci **Správce** > **Systém** > **Plán**.

> [!TIP]
> Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy. Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies). Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy. Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.

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
