---
title: Rozšíření zdrojů dat (Preview)
description: Před procesem sjednocení dat rozšiřte zdroje dat.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207175"
---
# <a name="enrichment-for-data-sources-preview"></a>Rozšíření zdrojů dat (Preview)

Použijte data ze zdrojů, jako je Microsoft a další partneři, abyste rozšířili svá zákaznická data před jejich sjednocením. Rozšíření zdrojů dat pomáhají vytvářet vyšší úplnost a kvalitu dat, která může pomoci dosáhnout lepších výsledků, jakmile svá data sjednotíte. Například použití normalizovaného a standardizovaného formátu pro adresy zvyšuje kvalitu výsledků shody. Seznam podporovaných rozšíření najdete v části [Podporované možnosti rozšíření zdroje dat](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Rozšíření zdroje dat

K vytváření nebo úpravě rozšíření musíte mít [oprávnění](permissions.md) Přispěvatel nebo Správce.  

1. Přejděte na **Data** > **Sjednotit**. Vyberte entitu, kterou chcete rozšířit, a vyberte jeden atribut jako [primární klíč](map-entities.md#select-primary-key-and-semantic-type-for-attributes) pro entitu.

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

Přejděte na **Data** > **Rozšíření**. Na záložce **Moje rozšíření** zobrazte nakonfigurovaná rozšíření, jejich stav, počet rozšířených zákazníků a čas poslední aktualizace dat. Seznam rozšiřování můžete seřadit podle libovolného sloupce nebo pomocí vyhledávacího pole najít rozšiřování, které chcete spravovat.

Výběrem rozšíření zobrazíte dostupné možnosti. Můžete také vybrat vertikální tři tečky (&vellip;) na položce seznamu, abyste viděli možnosti.

Rozšíření zdrojů dat můžete zobrazit, upravit, spustit nebo odstranit. Další informace naleznete v tématu [Správa existujících rozšíření](enrichment-hub.md#manage-existing-enrichments).
