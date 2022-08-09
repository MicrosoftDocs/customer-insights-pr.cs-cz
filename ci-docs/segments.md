---
title: Přehled segmentů
description: Vytvořte přehled segmentů a způsob jejich vytváření a správy.
ms.date: 05/20/2022
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
ms.openlocfilehash: 4bcfbb50b893ca7e6ec4607d3c156a3c6979f775
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170673"
---
# <a name="segments-overview"></a>Přehled segmentů

Segmenty umožňují seskupit zákazníky na základě demografických, transakčních nebo behaviorálních atributů. Segmenty můžete použít k cílení propagačních kampaní, prodejních aktivit a akcí podpory zákazníků k dosažení vašich obchodních cílů.

Profily zákazníků, které odpovídají filtrům definice segmentu, se označují jako *členy* segmentu. Použijí se některé [servisní limity](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Vytvořit segment

Vyberte, jak vytvořit segment na základě vaší cílové skupiny.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

- Složité segmenty s nástrojem pro tvorbu segmentů: [Sestavte si vlastní](segment-builder.md)
- Jednoduché segmenty s jedním operátorem: [Rychlý segment](segment-quick.md)
- Způsob vyhledání podobných zákazníků pomocí technologie AI: [Podobní zákazníci](find-similar-customer-segments.md)
- Návrhy využívající AI založené na mírách nebo atributech: [Navrhované segmenty na základě měr](suggested-segments.md)
- Návrhy založené na činnostech: [Navrhované segmenty na základě aktivity zákazníků](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

- Jednoduché nebo složité segmenty s nástrojem pro tvorbu segmentů: [Sestavte si vlastní](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Správa existujících segmentů

Jděte na stránku **Segmenty**, kde uvidíte vámi vytvořené segment s jejich stavem, počtu členů a časem poslední aktualizace dat. Seznam segmentů můžete seřadit podle libovolného sloupce nebo pomocí vyhledávacího pole najít segment, který chcete spravovat.

Výběrem segmentu zobrazíte dostupné akce.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Vybraný segment s rozevíracím seznamem možností a dostupnými možnostmi." lightbox="media/segments-selected-segment.png":::

- [**Zobrazte**](#view-segment-details) podrobnosti o segmentu, včetně trendu počtu členů a náhledu členů segmentu.
- **Stáhnout** seznam členů jako soubor .CSV.
- **Upravit** segment změnit jeho vlastnosti.
- **Vytvořit duplicitu** segmentu. Můžete se rozhodnout upravit jeho vlastnosti okamžitě nebo uložit duplicitu.
- [**Aktualizujte**](#refresh-segments) segment a zahrňte nejnovější data.
- **Aktivace** nebo **deaktivace** segmentu. Neaktivní segmenty se neaktualizují během [plánované aktualizace](system.md#schedule-tab) a mají **Stav** uveden jako **Přeskočeno**, což označuje, že u nich neproběhl ani pokus o aktualizaci. Aktivní segmenty se aktualizují na základě jejich typu: statické nebo dynamické.
- Volbami **Nastavit jako statický** nebo **Nastavit jako statický** nastavte typ segmentu. Statické segmenty musí být aktualizovány ručně. Dynamické segmenty jsou automaticky aktualizovány během aktualizací systému.
- [**Vyhledat podobné zákazníky**](find-similar-customer-segments.md) ze segmentu.
- **Přejmenovat** segment.
- Volbou **Značka** můžete [spravovat značky](work-with-tags-columns.md#manage-tags) pro segment.
- Možnost [**Spravovat exporty**](#export-segments) zobrazí segmenty související s exportem a umožní jejich správu. [Další informace o exportech.](export-destinations.md)
- **Odstranit** segment.
- **Sloupce** pro [přizpůsobení sloupců](work-with-tags-columns.md#customize-columns), které se zobrazí.
- **Filtrovat** pro [filtrování podle značek](work-with-tags-columns.md#filter-on-tags).
- **Hledat název** pro vyhledání podle názvu segmentu.

## <a name="view-segment-details"></a>Zobrazení podrobností segmentu

Na stránce **Segmenty** vyberte segment pro zobrazení historie zpracování a členů segmentu.

Horní část stránky obsahuje graf trendů, který vizualizuje změny v počtu členů. Najeďte na datové body, abyste viděli počet členů k určitému datu. Změna časového rámce vizualizace.

:::image type="content" source="media/segment-time-range.png" alt-text="Časový rozsah segmentu.":::

Spodní část obsahuje seznam členů segmentu.

> [!NOTE]
> Pole, která se zobrazí v tomto seznamu, jsou založena na atributech entit segmentu.
>
>Seznam je náhledem odpovídajících členů segmentu a zobrazuje prvních 100 záznamů segmentu, takže jej můžete rychle vyhodnotit a v případě potřeby zkontrolovat jeho definice. Chcete-li zobrazit všechny odpovídající záznamy, [exportujte segment](export-destinations.md).

## <a name="refresh-segments"></a>Aktualizovat segmenty

Segmenty lze aktualizovat podle automatického plánu nebo ručně na vyžádání. Chcete-li ručně aktualizovat jeden nebo více segmentů, vyberte je a zvolte **Aktualizovat**.

Na záložce [naplánovat automatické obnovení](system.md#schedule-tab) jděte na **Správce** > **Systém** > **Plán**. Platí následující pravidla:

- Všechny segmenty s typem **Dynamický** nebo **Rozšíření** se automaticky aktualizují podle nastavené kadence. Po dokončení aktualizace **Stav** označuje, zda při aktualizaci segmentu došlo k nějakým problémům. **Poslední aktualizace** zobrazuje časové razítko poslední úspěšné aktualizace. Pokud dojde k chybě, výběrem chyby zobrazíte podrobnosti o tom, co se stalo.
- Segmenty s typem **Statický** *nebudou* automaticky aktualizovány. **Poslední aktualizace** zobrazuje časové razítko posledního spuštění nebo ruční aktualizace statických segmentů.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Export segmentů

Chcete-li data dále používat, exportujte segmenty do jiných aplikací. Exportujte segment ze stránky segmentů nebo ze [stránky exportů](export-destinations.md).

1. Jděte na stránku **Segmenty** a vyberte segment, který chcete exportovat.

1. Vyberte **Spravovat exporty**. Otevře se stránka **Exporty (preview) pro segment**. Zobrazte všechny nakonfigurované exporty seskupené podle toho, zda obsahují aktuální segment, nebo ne.

   1. Chcete -li přidat vybraný segment do exportu, **upravte** příslušný export pro výběr odpovídajících segmentů a poté uložte. V prostředích pro jednotlivé zákazníky vyberte export v seznamu a vyberte **Přidat segment**, abyste dosáhli stejného výsledku.

   1. Chcete-li vytvořit nový export s vybraným segmentem, vyberte **Přidat export**. Další informace o vytváření exportů najdete v části [Nastavení nového exportu](export-destinations.md#set-up-a-new-export).

1. Výběrem možnosti **Zpět** se vraťte na hlavní stránku pro segmenty.

## <a name="track-usage-of-a-segment"></a>Sledování využití segmentu

Pokud v aplikacích používáte segmenty, které jsou založeny na stejné organizaci Microsoft Dataverse, která je propojena s Customer Insights, můžete sledovat využití segmentu. U [segmentů Customer Insights používané v cestách zákazníků Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile) vás systém informuje o využití daného segmentu.

Při úpravě segmentu, který se používá v prostředí Customer Insights nebo v cestě zákazníka v aplikaci Marketing, vás banner v [tvůrci segmentů](segment-builder.md) informuje o závislostech. Podrobnosti o závislosti zkontrolujete přímo z banneru nebo výběrem možnosti **Využití** v tvůrci segmentů.

Podokno **Využití segmentu** zobrazuje podrobnosti o využití tohoto segmentu v aplikacích založených na Dataverse. U segmentů používaných v cestách zákazníků najdete odkaz na kontrolu cesty v Marketingu, kde se tento segment používá. Pokud máte oprávnění pro přístup k aplikaci Marketing, zobrazíte tam další podrobnosti.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Boční panel s podrobnostmi o využití segmentu v tvůrci segmentů.":::

Systém vás informuje o využití sledovaného segmentu, když se jej pokusíte odstranit. Pokud je segment, který se chystáte odstranit, použit v cestě zákazníka v aplikaci Marketing, tato cesta se zastaví pro všechny uživatele v segmentu. Pokud je cesta součástí marketingové kampaně, odstranění ovlivní samotnou kampaň. Segment však můžete odstranit i přes varování.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialogové okno pro potvrzení odstranění segmentu, když je segment použit v aplikaci Dataverse.":::

### <a name="supported-apps"></a>Podporované aplikace

Využití je aktuálně sledováno v následujících aplikacích založených na Dataverse:

- [Cesty zákazníků v Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
