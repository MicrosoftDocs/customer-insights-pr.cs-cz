---
title: Rozšíření zdroje dat
description: Před procesem sjednocení dat rozšiřte zdroje dat.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: d1e14d2d4e718d71ccbd2afd259a350ad5c9e69a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755678"
---
# <a name="enrichment-for-data-sources-preview"></a>Rozšíření zdrojů dat (Preview)

Použijte data ze zdrojů, jako je Microsoft a další partneři, abyste rozšířili svá zákaznická data před jejich sjednocením. Rozšíření zdrojů dat pomáhají vytvářet vyšší úplnost a kvalitu dat, která může pomoci dosáhnout lepších výsledků, jakmile svá data sjednotíte. Například použití normalizovaného a standardizovaného formátu pro adresy zvyšuje kvalitu výsledků shody. Seznam podporovaných rozšíření najdete v části [Podporované možnosti rozšíření zdroje dat](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Rozšíření zdroje dat

K vytváření nebo úpravě rozšíření musíte mít roli Přispěvatel nebo Správce. Další informace naleznete v části [Oprávnění](permissions.md).  

1. Přejděte na **Data** > **Sjednotit**. Vyberte entitu, kterou chcete rozšířit, a vyberte jeden atribut jako primární klíč pro entitu. Více informací viz část [Výběr primárního klíče](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Přejděte na **Data** > **Zdroje dat**.

1. Vyberte svislý výpustek vedle zdroje dat, který chcete rozšířit, a vyberte příkaz **Rozšířit**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Stránka Rozšíření zdroje dat.":::

   Karta **Zjistit** zobrazuje [podporované možnosti rozšíření zdroje dat](#supported-data-source-enrichments).

1. Vyberte příkaz **Rozšířit moje data** a zahajte tak konfiguraci rozšíření zdroje dat. Název výstupní entity je automaticky vyplněn.

## <a name="supported-data-source-enrichments"></a>Podporovaná rozšíření zdroje dat

Pro datové zdroje jsou momentálně dostupné následující rozšíření. Přečtěte si podrobné kroky postupu rozšíření, abyste se naučili, jak jej nakonfigurovat.

- [Rozšířené adresy](enrichment-enhanced-addresses.md)
- [Vylepšená data společnosti](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Správa stávajících rozšíření zdrojů dat

Jděte na kartu **Moje rozšíření**, kde zobrazíte všechna nakonfigurovaná rozšíření.

Výběrem rozšíření zobrazíte dostupné možnosti. Můžete také vybrat tři tečky (...) na položce seznamu a zobrazit možnosti. Pokud jste nakonfigurovali několik rozšíření, můžete je rychle najít pomocí vyhledávacího pole.

Rozšíření zdrojů dat můžete zobrazit, upravit, spustit nebo odstranit. Další informace naleznete v tématu [Správa existujících rozšíření](enrichment-hub.md).
