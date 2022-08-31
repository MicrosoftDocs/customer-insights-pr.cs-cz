---
title: Vytvoření sjednoceného zobrazení zákazníků
description: Projděte proces sjednocení dat se svými daty a vytvořte jedinou hlavní datovou sadu účtu nebo zákaznických profilů.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304419"
---
# <a name="data-unification-overview"></a>Přehled sjednocení dat

Po [nastavení zdrojů dat](data-sources.md) můžete data sjednotit. Sjednocení dat vám umožňuje sjednotit kdysi nesourodé zdroje dat do jediné hlavní datové sady, která poskytuje jednotný pohled na tato data.

Pro jednotlivé spotřebitele (B-to-C), kde jsou data soustředěna kolem jednotlivců, poskytuje sjednocení jednotný pohled na vaše zákazníky. Pro obchodní účty (B-to-B), kde jsou data soustředěna kolem zákaznických účtů, poskytuje sjednocení jednotný pohled na vaše zákaznické účty. [Sjednocení kontaktů (Preview)](data-unification-contacts.md) umožňuje, aby kontakty pro tyto účty byly samostatně sjednoceny a přidruženy k účtům.

Data mohou být sjednocena na jedné entitě nebo více entitách.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

Proces sjednocení mapuje zákaznická data z vašich zdrojů dat, odstraňuje duplikáty, porovnává data napříč entitami a vytvoří sjednocený profil. Sjednocení se provádí v následujícím pořadí:

1. [Zdrojová pole](map-entities.md) (dříve nazývaná Mapa): V kroku zdrojových polí vyberte entity a pole, která chcete zahrnout do procesu sjednocení. Mapujte pole na společný sémantický typ, který popisuje účel pole.

1. [Duplicitní záznamy](remove-duplicates.md) (dříve součást Shody): V kroku duplicitních záznamů volitelně definujte pravidla pro odstranění duplicitních záznamů zákazníků z každé entity.

1. [Odpovídající podmínky](match-entities.md) (dříve nazývané Shoda): V kroku párovacích podmínek definujte pravidla, která přiřazují záznamy zákazníků mezi entitami. Když je zákazník nalezen ve dvou nebo více entitách, vytvoří se jeden konsolidovaný záznam se všemi sloupci a daty z každé entity.

1. [Sjednocená zákaznická pole](merge-entities.md) (dříve nazývané Sloučit): V kroku sjednocených polí zákazníka určete, která zdrojová pole by měla být zahrnuta, vyloučena nebo sloučena do jednotného profilu zákazníka.  

1. [Posouzení](review-unification.md) a vytvořte jednotný profil.

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

Proces sjednocení mapuje data účtu z vašich zdrojů dat, odstraňuje duplikáty, porovnává data napříč entitami a vytvoří sjednocený profil. Sjednocení se provádí v následujícím pořadí:

1. [Zdrojová pole](map-entities.md) (dříve nazývaná Mapa): V kroku zdrojových polí vyberte entity a pole, která chcete zahrnout do procesu sjednocení účtu. Mapujte pole na společný sémantický typ, který popisuje účel pole.

1. [Duplicitní záznamy](remove-duplicates.md) (dříve součást Shody): V kroku duplicitních záznamů volitelně definujte pravidla pro odstranění duplicitních záznamů účtu z každé entity.

1. [Odpovídající podmínky](match-entities.md) (dříve nazývané Shoda): V kroku párovacích podmínek definujte pravidla, která přiřazují záznamy účtu mezi entitami. Když je účet nalezen ve dvou nebo více entitách, vytvoří se jeden konsolidovaný záznam se všemi sloupci a daty z každé entity.

1. [Sjednocená zákaznická pole](merge-entities.md) (dříve nazývané Sloučit): V kroku sjednocených polí zákazníka určete, která zdrojová pole by měla být zahrnuta, vyloučena nebo sloučena do jednotného profilu zákazníka.  

1. [Posouzení](review-unification.md) a vytvořte jednotný profil.

Po sjednocení účtů můžete volitelně [sjednotit kontakty (Preview)](data-unification-contacts.md) pro tyto účty a propojit sjednocené kontakty se sjednocenými účty.

---

Po dokončení sjednocení dat můžete volitelně:

- [Nastavení vztahů mezi entitami](relationships.md), abyste mohli vytvářet sofistikované segmenty.
- [Obohacení vašich dat](enrichment-hub.md), abyste získali širší přehled o svých zákaznících.
- [Definování aktivity](activities.md) z některých ingestovaných atributů.
- [Budování opatření](measures.md) pro lepší pochopení chování zákazníků a obchodní výkonnost.

[!INCLUDE [footer-include](includes/footer-banner.md)]
