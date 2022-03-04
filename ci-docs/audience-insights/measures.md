---
title: Pochopení a správa měr
description: Zjistěte, jak míry pomáhají analyzovat a odrážet výkon vašeho podnikání.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359765"
---
# <a name="measures-overview"></a>Přehled měr

Míry vám pomohou lépe porozumět chování zákazníků a výkonnosti podniku. Zaměřují se na relevantní hodnoty ze [sjednocených profilů](data-unification.md). Například firma chce vidět *celkové výdaje na zákazníka*, aby rozuměla historii nebo míře nákupu jednotlivého zákazníka nebo změřila *celkový prodej společnosti*, aby porozuměla agregovaným výnosům v celém podniku.  

Míry jsou vytvářeny [pomocí nástroje pro tvorbu měr](measure-builder.md), což je platforma pro dotazování dat s různými operátory a možnostmi jednoduchého mapování. Umožňuje filtrovat data, seskupovat výsledky, detekovat [cesty vztahů mezi entitami](relationships.md) a zobrazovat náhledy výstupu. Můžete [používat předdefinované šablony](measure-templates.md) pro efektivní konfiguraci běžně používaných měr.

Pomocí nástroje pro tvorbu měr můžete plánovat obchodní aktivity dotazováním zákaznických dat a extrahováním přehledů. Například vytvoření míry *celkové výdaje na zákazníka* a *celková návratnost na zákazníka* pomáhá identifikovat skupinu zákazníků s vysokými výdaji, ale s vysokou návratností. Můžete [vytvořit segment](segments.md) na základě těchto měr a řídit další nejlepší akce. 

## <a name="manage-your-measures"></a>Správa opatření

Seznam měr naleznete na stránce **Míry**.

Najdete informace o typu, tvůrci, datu vytvoření, statusu a stavu míry. Když vyberete míru ze seznamu, můžete zobrazit náhled výstupu a stáhnout soubor CSV.

Chcete-li obnovit všechna vaše opatření současně, vyberte **Aktualizovat vše** bez výběru konkrétního opatření.

:::image type="content" source="media/measure-actions.png" alt-text="Akce ke správě jednotlivých opatření.":::

Vyberte míru ze seznamu a použijte některou z následujících voleb:

- Chcete-li zobrazit podrobnosti, vyberte název míry.
- **Upravte** konfiguraci míry.
- **Aktualizujte** míru na základě nejnovějších údajů.
- **Přejmenujte** míru.
- **Odstraňte** míry.
- **Aktivujte** nebo **deaktivujte**. Neaktivní míry se během [plánované aktualizace](system.md#schedule-tab) neaktualizují.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Další krok

K vytváření můžete použít stávající míry [zákaznický segment](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
