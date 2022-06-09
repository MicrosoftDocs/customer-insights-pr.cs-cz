---
title: Vytvoření sjednoceného zobrazení zákazníků
description: Projděte proces sjednocení dat se svými daty a vytvořte jedinou datovou sadu sjednocených zákaznických profilů.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755726"
---
# <a name="data-unification-overview"></a>Přehled sjednocení dat

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Po [nastavení zdrojů dat](data-sources.md) můžete data sjednotit. Sjednocení dat vám umožňuje sjednotit kdysi nesourodé zdroje dat do jediné hlavní datové sady, která poskytuje jednotný pohled na tato data. Pro jednotlivé spotřebitele (B-to-C), kde jsou data soustředěna kolem jednotlivců, poskytuje sjednocení jednotný pohled na vaše zákazníky. Pro obchodní účty (B-to-B), kde jsou data soustředěna kolem zákaznických účtů, poskytuje sjednocení jednotný pohled na vaše zákaznické účty.

Data mohou být sjednocena na jedné entitě nebo více entitách. Sjednocení se provádí v následujícím pořadí:

1. [Zdrojová pole](map-entities.md) (dříve nazývaná Mapa): V kroku zdrojových polí vyberte entity a pole, která chcete zahrnout do procesu sjednocení. Mapujte pole na společný sémantický typ, který popisuje účel pole.

1. [Duplicitní záznamy](remove-duplicates.md) (dříve součást Shody): V kroku duplicitních záznamů volitelně definujte pravidla pro odstranění duplicitních záznamů zákazníků z každé entity.

1. [Odpovídající podmínky](match-entities.md) (dříve nazývané Shoda): V kroku párovacích podmínek definujte pravidla, která přiřazují záznamy zákazníků mezi entitami. Když je zákazník nalezen ve dvou nebo více entitách, vytvoří se jeden konsolidovaný záznam se všemi sloupci a daty z každé entity.

1. [Sjednocená zákaznická pole](merge-entities.md) (dříve nazývané Sloučit): V kroku sjednocených polí zákazníka určete, která zdrojová pole by měla být zahrnuta, vyloučena nebo sloučena do jednotného profilu zákazníka.  

1. [Posouzení](review-unification.md) a vytvořte jednotný profil.

Po dokončení sjednocení dat můžete volitelně:

- [Nastavení vztahů mezi entitami](relationships.md), abyste mohli vytvářet sofistikované segmenty.
- [Obohacení vašich dat](enrichment-hub.md), abyste získali širší přehled o svých zákaznících.
- [Definování aktivity](activities.md) z některých ingestovaných atributů.
- [Budování opatření](measures.md) pro lepší pochopení chování zákazníků a obchodní výkonnost.

[!INCLUDE [footer-include](includes/footer-banner.md)]