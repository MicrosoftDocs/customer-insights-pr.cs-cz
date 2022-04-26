---
title: Pochopení a správa měr
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
ms.openlocfilehash: ef10f480086ccac4fa5c6c58818e35ecae67532c
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529669"
---
# <a name="measures-overview"></a>Přehled měr

Míry vám pomohou lépe porozumět chování zákazníků a výkonnosti podniku. Zaměřují se na relevantní hodnoty ze [sjednocených profilů](data-unification.md). Například firma chce vidět *celkové výdaje na zákazníka*, aby rozuměla historii nebo míře nákupu jednotlivého zákazníka nebo změřila *celkový prodej společnosti*, aby porozuměla agregovaným výnosům v celém podniku.  

Míry jsou vytvářeny [pomocí nástroje pro tvorbu měr](measure-builder.md), což je platforma pro dotazování dat s různými operátory a možnostmi jednoduchého mapování. Umožňuje filtrovat data, seskupovat výsledky, detekovat [cesty vztahů mezi entitami](relationships.md) a zobrazovat náhledy výstupu. Můžete [používat předdefinované šablony](measure-templates.md) pro efektivní konfiguraci běžně používaných měr.

Pomocí nástroje pro tvorbu měr můžete plánovat obchodní aktivity dotazováním zákaznických dat a extrahováním přehledů. Například vytvoření míry *celkové výdaje na zákazníka* a *celková návratnost na zákazníka* pomáhá identifikovat skupinu zákazníků s vysokými výdaji, ale s vysokou návratností. Můžete [vytvořit segment](segments.md) na základě těchto měr a řídit další nejlepší akce.

## <a name="manage-your-measures"></a>Správa opatření

Seznam měr naleznete na stránce **Míry**.

Najdete informace o typu, tvůrci, datu vytvoření, statusu a stavu míry. Když vyberete míru ze seznamu, můžete zobrazit náhled výstupu a stáhnout soubor CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Akce ke správě jednotlivých opatření."lightbox="media/measures-actions.png":::

Po výběru míry jsou k dispozici následující akce:

- **Upravte** konfiguraci míry.
- Na míru použijte možnost **Duplikovat**. Můžete se rozhodnout upravit její vlastnosti hned nebo duplicitu jednoduše uložit.
- **Aktualizujte** míru na základě nejnovějších údajů. Chcete-li aktualizovat všechny míry najednou, vyberte všechny míry a poté zvolte možnost **Aktualizovat**.
- **Přejmenujte** míru.
- **Aktivujte** nebo **deaktivujte**. Neaktivní míry se během [plánované aktualizace](system.md#schedule-tab) neaktualizují.
- Volbou **Značka** můžete [spravovat značky](work-with-tags-columns.md#manage-tags) pro segment.
- **Odstraňte** míry.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Další krok

K vytváření můžete použít stávající míry [zákaznický segment](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
