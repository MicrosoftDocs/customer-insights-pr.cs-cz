---
title: Entity a datové sady
description: Zobrazení data na stránce Entity.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269368"
---
# <a name="entities-in-audience-insights"></a>Entity v přehledech cílové skupiny

Po [konfigurace zdrojů dat](data-sources.md) přejděte na stránku **Entity** pro vyhodnocení kvality přijímaných dat. Entity jsou považovány za datové sady. Kolem těchto entit jsou postaveny některé funkce Dynamics 365 Customer Insights. Jejich pečlivá kontrola vám pomůže ověřit výstup těchto funkcí.

Stránka **Entity** uvádí entity a zahrnuje několik sloupců:

- **Název**: Název vaší datové entity. Pokud se vedle názvu entity zobrazí varovný symbol, znamená to, že se data pro tuto entitu nenačítala úspěšně.
- **Zdroj**: Typ zdroje dat, který přijal entitu
- **Vytvořil/a**: Jméno osoby, která entitu vytvořila
- **Vytvořeno**: Datum a čas, kdy byla entita vytvořena
- **Aktualizoval/a**: Jméno osoby, která entitu aktualizovala
- **Naposledy aktualizováno**: Datum a čas poslední aktualizace entity
- **Poslední aktualizace**: Datum a čas poslední aktualizace dat

## <a name="exploring-a-specific-entitys-data"></a>Zkoumání dat konkrétní entity

Vyberte entitu a prozkoumejte různá pole a záznamy obsažené v této entitě.

> [!div class="mx-imgBorder"]
> ![Výběr entity](media/data-manager-entities-data.png "Vyberte entitu.")

- Karta **Data** je ve výchozím nastavení vybrána a zobrazuje tabulku s podrobnostmi o jednotlivých záznamech entity.

> [!div class="mx-imgBorder"]
> ![Tabulka polí](media/data-manager-entities-fields.PNG "Tabulka polí")

- Karta **Pole** zobrazuje tabulku pro kontrolu podrobností o vybrané entitě, jako jsou názvy polí, datové typy a typy. Sloupec **Typ** zobrazuje typy přidružené k Common Data Model, které jsou systémem automaticky identifikovány nebo [ručně mapovány](map-entities.md) uživateli. Jedná se o sémantické typy, které se mohou lišit od datových typů atributů - například pole *E-mail* níže je datový typ *Text*, ale jeho (sémantický) typ Common Data Model může být *E-mail* nebo *Emailová adresa*.

> [!NOTE]
> Obě tabulky ukazují pouze ukázku dat vaší entity. Chcete-li zobrazit celou datovou sadu, přejděte na stránku **Zdroje dat**, vyberte entitu, vyberte **Upravit** a poté si prohlédněte data této entity pomocí editoru Power Query, jak je vysvětleno v části [Zdroje dat](data-sources.md).

Chcete-li se dozvědět více o údajích přijímaných v entitě, sloupec **Souhrn** poskytuje některé důležité vlastnosti dat, jako jsou nuly, chybějící hodnoty, jedinečné hodnoty, počty a distribuce, které se vztahují na vaše data.

Klepnutím na ikonu grafu zobrazíte souhrn dat.

> [!div class="mx-imgBorder"]
> ![Souhrnný symbol](media/data-manager-entities-summary.png "Souhrnná tabulka dat")

### <a name="next-step"></a>Další krok

V tématu [Sjednotit](data-unification.md) se dozvíte, jak na to *mapovat*, *přiřadit* a *sloučit* přijatá data.


[!INCLUDE[footer-include](../includes/footer-banner.md)]