---
title: Rozšíření zdroje dat
description: Před procesem sjednocení dat rozšiřte zdroje dat.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: b34b83d7a73dbdf21984f626174524188f0f1dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011465"
---
# <a name="enrichment-for-data-sources-preview"></a>Rozšíření zdrojů dat (Preview)

Použijte data ze zdrojů, jako je Microsoft a další partneři, abyste rozšířili svá zákaznická data před jejich sjednocením. Rozšíření zdrojů dat pomáhají vytvářet vyšší úplnost a kvalitu dat, která může pomoci dosáhnout lepších výsledků, jakmile svá data sjednotíte. Například použití normalizovaného a standardizovaného formátu pro adresy zvyšuje kvalitu výsledků shody. Seznam podporovaných rozšíření najdete v části [Podporované možnosti rozšíření zdroje dat](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Rozšíření zdroje dat

K vytváření nebo úpravě rozšíření musíte mít roli Přispěvatel nebo Správce. Další informace naleznete v části [Oprávnění](permissions.md).  

1. Přejděte na **Data** > **Sjednotit**. Vyberte entitu, kterou chcete rozšířit, a vyberte jeden atribut jako primární klíč pro entitu. Více informací viz část [Výběr primárního klíče](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Přejděte na **Data** > **Zdroje dat**.

1. Vyberte vertikální tři tečky (&vellip;) vedle zdroje dat, který chcete rozšířit, a vyberte příkaz **Rozšířit**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Stránka Zdroje dat se zvýrazněným rozšiřováním":::

   Karta **Zjistit** zobrazuje [podporované možnosti rozšíření zdroje dat](#supported-data-source-enrichments).

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Stránka Rozšíření zdroje dat.":::

1. Vyberte příkaz **Rozšířit moje data** a zahajte tak konfiguraci rozšíření zdroje dat. Název výstupní entity je automaticky vyplněn.

## <a name="supported-data-source-enrichments"></a>Podporovaná rozšíření zdroje dat

Pro datové zdroje jsou momentálně dostupné následující rozšíření. Přečtěte si podrobné kroky postupu rozšíření, abyste se naučili, jak jej nakonfigurovat.

- [Rozšířené adresy](enrichment-enhanced-addresses.md)
- [Vylepšená data společnosti](enrichment-enhanced-company-data.md)
- [Data identity ze služby LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Správa stávajících rozšíření zdrojů dat

Jděte na kartu **Moje rozšíření**, kde zobrazíte všechna nakonfigurovaná rozšíření.

Výběrem rozšíření zobrazíte dostupné možnosti. Můžete také vybrat vertikální tři tečky (&vellip;) na položce seznamu, abyste viděli možnosti. Pokud jste nakonfigurovali několik rozšíření, můžete je rychle najít pomocí vyhledávacího pole.

Rozšíření zdrojů dat můžete zobrazit, upravit, spustit nebo odstranit. Další informace naleznete v tématu [Správa existujících rozšíření](enrichment-hub.md).
