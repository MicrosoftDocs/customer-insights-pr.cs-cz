---
title: Přehled měr
description: Zjistěte, jak míry pomáhají analyzovat a odrážet výkon vašeho podnikání.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245365"
---
# <a name="measures-overview"></a>Přehled měr

Míry vám pomohou lépe porozumět chování zákazníků a výkonnosti podniku. Zaměřují se na relevantní hodnoty ze [sjednocených profilů](data-unification.md). Například firma chce vidět *celkové výdaje na zákazníka*, aby rozuměla historii nebo míře nákupu jednotlivého zákazníka nebo změřila *celkový prodej společnosti*, aby porozuměla agregovaným výnosům v celém podniku.

Vytváření měr umožňuje plánovat obchodní aktivity dotazováním zákaznických dat a extrahováním přehledů. Například vytvoření míry *celkové výdaje na zákazníka* a *celková návratnost na zákazníka* pomáhá identifikovat skupinu zákazníků s vysokými výdaji, ale s vysokou návratností. Poté můžete [vytvořit segment](segments.md) na základě těchto měr a řídit další nejlepší akce.

## <a name="create-a-measure"></a>Vytvořit nové opatření

Vyberte, jak vytvořit míru na základě vaší cílové skupiny.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

- Od začátku v tvůrci měr: [Sestavte si vlastní](measure-builder.md).
- Z běžně používaných měr: [Použití předdefinovaných šablon](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

Od začátku v tvůrci měr: [Sestavte si vlastní](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Správa existujících měr

Jděte na stránku **Míry**, kde uvidíte vámi vytvořené míry s jejich stavem, typem a časem poslední aktualizace dat. Seznam měr můžete seřadit podle libovolného sloupce nebo pomocí vyhledávacího pole najít míry, které chcete spravovat.

Výběrem vedle míry zobrazíte dostupné akce. Výběrem názvu míry zobrazíte náhled výstupu a můžete si stáhnout soubor CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Akce ke správě jednotlivých opatření."lightbox="media/measures-actions.png":::

- Volbou **Upravit** změníte vlastnosti míry.
- Volbou **Aktualizovat** do míry zahrnete nejnovější data.
- **Přejmenujte** míru.
- **Aktivujte** nebo **deaktivujte** míru. Neaktivní míry se neaktualizují během [plánované aktualizace](schedule-refresh.md) a mají **Stav** uveden jako **Přeskočeno**, což označuje, že u nich neproběhl ani pokus o aktualizaci.
- Volbou **Značka** můžete [spravovat značky](work-with-tags-columns.md#manage-tags) pro míru.
- **Odstraňte** míry.
- **Sloupce** pro [přizpůsobení sloupců](work-with-tags-columns.md#customize-columns), které se zobrazí.
- **Filtrovat** pro [filtrování podle značek](work-with-tags-columns.md#filter-on-tags).
- **Hledat název** pro vyhledání podle názvu míry.

## <a name="refresh-measures"></a>Aktualizace měr

Míry lze aktualizovat podle automatického plánu nebo ručně na vyžádání. Chcete-li ručně obnovit jednu nebo více měr, vyberte ji a vyberte **Aktualizovat**. Na záložce [naplánovat automatické obnovení](schedule-refresh.md) jděte na **Správce** > **Systém** > **Plán**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
