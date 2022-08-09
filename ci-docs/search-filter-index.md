---
title: Správa indexu vyhledávání a filtrování pro profily zákazníků
description: Rychle vyhledejte informace o sjednocených profilech zákazníků a filtrujte zadané atributy.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187901"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Správa indexu vyhledávání a filtrování pro profily zákazníků

Výsledkem sjednocení údajů o zákaznících je entita *Zákazník*, která poskytuje jednotný pohled na vaši celkovou zákaznickou základnu. Aby mohli uživatelé rychle [vyhledat informace o konkrétním zákazníkovi nebo skupině zákazníků](customer-profiles.md), správce musí nakonfigurovat funkce **Vyhledávání** a **Filtr** na stránce **Zákazníci**.

   :::image type="content" source="media/search-filter.png" alt-text="Filtr hledání":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definování vyhledatelných atributů a indexovaných polí

Pokud poprvé definujete vyhledatelné atributy jako správce, nejprve definujte indexovaná pole. Doporučujeme, abyste si vybrali všechny atributy, podle kterých mohou uživatelé na internetu vyhledávat a filtrovat zákazníky na stránce **Zákazníci**. Můžete zadat pouze atributy, které existují v entitě *Zákazník*, kterou jste vytvořili během procesu sjednocení dat.

1. Jděte na stránku **Zákazníci** a vyberte **Index hledání a filtrování**.

1. Vyberte **+ Přidat**.

1. V seznamu vyberte atributy, které chcete přidat jako indexovaná pole, a klikněte na možnost **Použít**.

1. Chcete-li přidat další atributy, vyberte **Přidat**. Chcete-li odebrat vybraný atribut, vyberte jej a poté vyberte možnost **Odstranit**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Stránka Index hledání a filtrování.":::

1. Vyberte **Spustit**, jakmile budete připraveni použít nastavení hledání a filtrování. Jakmile jsou změny zpracovány, zobrazíte je v [zákaznických kartách na stránce Zákazníka](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Definování možností filtrování pro daný atribut

Nastavte pole, která lze použít pro filtrování zákazníků, na stránce **Zákazníci**.

1. Jděte na stránku **Zákazníci** a vyberte **Index hledání a filtrování**.

1. Vyberte atribut a **Přidejte filtr**. Definujte počet výsledků a pořadí, ve kterém budou uspořádány. V závislosti na datovém typu atributu se objeví jedno z následujících podoken.

   - Atributy typu řetězec: Zadejte počet požadovaných výsledků v podokně **Filtrování řetězců** a zásady řazení, podle kterých budou uspořádány.

   - Atributy typu číslo: Zadejte intervaly z podokna **Filtrování čísel** a zásady řazení, podle kterých budou uspořádány.

   - Atributy typu datum: Zadejte intervaly z podokna **Filtrování kalendářních dat** a zásady řazení, podle kterých budou uspořádány.

1. Vyberte položku **OK**. Opakujte pro všechny atributy, podle kterých chcete filtrovat.

1. Vyberte **Spustit**, jakmile budete připraveni použít nastavení hledání a filtrování. Jakmile jsou změny zpracovány, zobrazíte je v [zákaznických kartách na stránce Zákazníka](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Zobrazení indexovaných polí zákazníka

Stránka **Index hledání a filtrování** obsahuje následující informace:

- **Název**: Představuje název atributu, jak je uveden v entitě *Zákazník*.
- **Datový typ**: Určuje, zda je typ dat řetězec, číslo nebo datum.
- **Zahrnuto do vyhledávání**: Určuje, zda lze tento atribut použít pro vyhledávání zákazníků na stránce **Zákazníci** pomocí pole **Vyhledávání**.
- **Přidat filtr**: Ovládací prvek, který definuje, jak lze tento atribut použít pro filtrování na stránce **Zákazníci**.

## <a name="next-steps"></a>Další kroky

Zkontrolujte [stránka jednotných profilů](customer-profiles.md) a vyhledejte profily nebo pomocí indexovaných polí zobrazte podmnožinu všech sjednocených profilů.

[!INCLUDE [footer-include](includes/footer-banner.md)]
