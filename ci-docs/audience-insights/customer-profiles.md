---
title: Zobrazení profilů zákazníků
description: Získejte kombinované zobrazení sjednocených údajů o zákaznících.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a5d928ae518f3cb1afbf8e2b197e51b27665f6e0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269736"
---
# <a name="customer-profiles"></a>Profily zákazníků

Stránka **Zákazníci** obsahuje kombinované zobrazení vašich zákazníků na základě dat profilů získaných ze [všech zdrojů dat](data-sources.md). Profily zákazníků jsou k dispozici, jakmile [vytvoříte sjednocenou entitu zákazníka](data-unification.md). Ujistěte se, že jste dokončili proces sjednocení dat, abyste získali lepší přehled o svých zákaznících. Tato stránka také umožňuje vyhledávat zákazníky.

Zákazníci mohou být jednotlivci nebo organizace (náhled). Každý profil zákazníka nebo organizace je reprezentován dlaždicí. Výběrem dlaždice zobrazíte další informace o konkrétním zákazníkovi nebo organizaci. Chcete-li zobrazit další záznamy, použijte ovládací prvky stránkování ve spodní části stránky.

> [!div class="mx-imgBorder"] 
> ![Zákaznické profily B2C](media/profiles-customers.png "Zákaznické profily B2C")

Organizace (Náhled)
> [!div class="mx-imgBorder"] 
> ![Zákaznické profily B2B](media/profile-customers-b2b.png "Zákaznické profily B2B")

> [!NOTE]
> Pokud nevidíte dlaždice, když vyberete **Zákazníci** v navigaci, musí váš správce [definovat alespoň jeden prohledávatelný atribut](search-filter-index.md) v **Hledat a filtrovat index**.

## <a name="search-for-customers"></a>Hledat zákazníky

Vyhledejte zákazníky zadáním jména nebo jiného atributu do vyhledávacího pole. Hledání funguje pouze v rámci entity Profil zákazníka vytvořené během procesu sjednocení dat.

Jako správce můžete konfigurovat prohledávatelné atributy pomocí stránky **Hledat a filtrovat rejstřík**. Další informace získáte v tématu [Správa vyhledávání a filtrování rejstříku](search-filter-index.md).

## <a name="filter-customers"></a>Filtrování zákazníků

Zákazníky můžete filtrovat podle polí entity Zákaznický profil. Podobně jako při vyhledávání bude muset správce nejprve definovat pole jako filtrovatelná pomocí stránky **Hledat a filtrovat rejstřík**.

1. Vyberte **Filtr** na stránce **Zákazníci**.

2. Zaškrtněte políčka vedle atributů, podle kterých chcete zákazníky filtrovat.

   > [!div class="mx-imgBorder"] 
   > ![Profily zákazníků](media/profiles-customers3.png "Profily zákazníků")

3. Odeberte filtry volbou **Vymazat filtry** na stránce **Zákazníci**.

##  <a name="customer-details-page"></a>Stránka podrobností zákazníka

Vyberte některou z dlaždic zákazníků a otevřete **stránku podrobností zákazníka**. Toto zobrazení obsahuje jednotné informace o vybraném zákazníkovi.

Podrobnosti o zákazníkovi zahrnují následující:

-   **Dlaždice profilu zákazníka:** Tato dlaždice zobrazuje různé hodnoty z entity sjednoceného profilu zákazníka. Tyto podrobnosti mohou zahrnovat e-mailovou adresu, jméno, město atd. 

-   **Potenciální zájmy, potenciální značky:** Ukazuje, zda jste nakonfigurovali rozšíření první strany. Představuje potenciální zájmy a oblíbenost značek, které může mít zákazník s profilem podobným tomuto zákazníkovi. Další informace viz [Rozšíření profilů zákazníků afinitami značky a zájmů](enrichment-microsoft-graph.md)

-   **Míry:** Ukazuje, zda jste nakonfigurovali jednu nebo více měr atributů zákazníka. Zahrnují vypočítané klíčové ukazatele výkonu ohledně vašich zákazníků na úrovni jednotlivých zákazníků. Další informace viz [Definování a správa měr](measures.md).

-   **Časová osa aktivit:** Ukazuje, zda máte konfigurovány aktivity. Zobrazení časové osy obsahuje chronologicky seřazené aktivity tohoto zákazníka, počínaje nejnovější aktivitou. Další informace najdete v tématu [Aktivity zákazníka](activities.md).

Volbou **Zpět k zákazníkům** se vrátíte na stránku pro vyhledávání zákazníků.

## <a name="next-steps"></a>Další kroky

[Přidejte další zdroje dat](data-sources.md) nebo [vytvořte segmenty zákazníků](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]