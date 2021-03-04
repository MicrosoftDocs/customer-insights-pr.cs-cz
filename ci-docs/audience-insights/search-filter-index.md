---
title: Hledání a filtrování profilů zákazníků
description: Rychle vyhledejte informace o sjednocených profilech zákazníků a filtrujte zadané atributy.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270058"
---
# <a name="customer-profiles-search--filter-index"></a>Profily zákazníků: Prohledávání a filtrování indexu

Výsledkem sjednocení údajů o zákaznících je entita profilu zákazníka, která poskytuje jednotný pohled na vaši celkovou zákaznickou základnu. Chcete-li rychle [najít informace o konkrétním zákazníkovi nebo skupině zákazníků](customer-profiles.md), můžete nakonfigurovat funkce **Vyhledávání** a **Filtr** na stránce **Zákazníci**. Čtěte dále a dozvíte se, jak mohou správci upravovat atributy na stránce **Prohledávání a filtrování rejstříku**, které jsou uživatelům k dispozici pro vyhledávání a filtrování.

> [!div class="mx-imgBorder"]
> ![Filtr hledání](media/search-filter.png "Filtr hledání")

## <a name="add-fields-and-specify-attributes"></a>Přidejte pole a zadejte atributy

Pokud poprvé definujete prohledatelné atributy jako správce, musíte nejprve definovat indexovaná pole. Doporučujeme, abyste si vybrali všechny atributy, podle kterých mohou uživatelé na internetu vyhledávat a filtrovat zákazníky na stránce **Zákazníci**. Můžete určit pouze atributy, které existují v entitě profilu zákazníka, kterou jste vytvořili během procesu sjednocení dat.

1. Otevřete stránku **Zákazníci** a vyberte **Index hledání a filtrování**.

2. Volbou **+ Přidat** určete indexovaná pole.

3. V seznamu vyberte atributy, které chcete přidat jako indexovaná pole. Výběrem **Přidat** můžete vždy přidat další atributy. Jakékoli vybrané atributy můžete také odstranit výběrem symbolu **Odstranit**.

## <a name="explore-the-indexed-customer-fields-table"></a>Prozkoumejte tabulku Pole indexovaných zákazníků

Tabulka obsahuje následující informace.

- **Název**: Představuje název atributu, jak je uveden v entitě profilu zákazníka.
- **Datový typ**: Určuje, zda je typ dat řetězec, číslo nebo datum.
- **Zahrnuto do vyhledávání**: Určuje, zda lze tento atribut použít pro vyhledávání zákazníků na stránce **Zákazníci** pomocí pole **Vyhledávání**.
- **Přidat filtr**: Ovládací prvek, který definuje, jak lze tento atribut použít pro filtrování na stránce **Zákazníci**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Úpravy možností filtrování pro daný atribut

Nabídka **Filtr** na stránce **Zákazníci** může zahrnovat různý počet úrovní atributů (například různé věkové skupiny, podle kterých lze filtrovat zákazníky).

1. Vyberte **Přidat filtr** pro daný atribut na stránce **Hledat a filtrovat rejstřík**. Můžete definovat počet výsledků a pořadí, ve kterém budou uspořádány. V závislosti na datovém typu atributu se objeví jedno z následujících podoken.

- Atributy typu řetězec: Zadejte počet požadovaných výsledků v podokně **Možnosti filtrování řetězců** a zásady řazení, podle kterých budou uspořádány.

- Atributy typu číslo: Zadejte intervaly z podokna **Možnosti filtrování čísel** a zásady řazení, podle kterých budou uspořádány.

- Atributy typu datum: Zadejte intervaly z podokna **Možnosti filtrování kalendářních dat** a zásady řazení, podle kterých budou uspořádány.

2. Výběrem možnosti **Uložit** se vaše změny uplatní.

3. Vyberte **Spustit**, jakmile budete připraveni použít svá nastavení.

## <a name="next-steps"></a>Další kroky

Přejděte na stránku **Zákazníci** pro vyhledání profilů zákazníků nebo pomocí indexovaného pole zobrazte podmnožinu všech profilů zákazníků.


[!INCLUDE[footer-include](../includes/footer-banner.md)]