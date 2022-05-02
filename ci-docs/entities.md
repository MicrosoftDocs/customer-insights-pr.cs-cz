---
title: Entity a datové sady
description: Zobrazení data na stránce Entity.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: c1094bc2f6d137087b317ed20d0615289d6f1187
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645822"
---
# <a name="entities-in-customer-insights"></a>Entity v Customer Insights

Po [konfigurace zdrojů dat](data-sources.md) přejděte na stránku **Entity** pro vyhodnocení kvality přijímaných dat. Entity jsou považovány za datové sady. Kolem těchto entit jsou postaveny některé funkce Dynamics 365 Customer Insights. Jejich pečlivá kontrola vám pomůže ověřit výstup těchto funkcí.

Stránka **Entity** uvádí entity a obsahuje tyto sloupce:

- **Název**: Název datové entity. Pokud se vedle názvu entity zobrazí varovný symbol, znamená to, že se data pro tuto entitu nenačítala úspěšně.
- **Zdroj**: Typ zdroje dat přijatého entitou.
- **Aktualizováno**: Čas poslední aktualizace entity.
- **Stav**: Podrobnosti o poslední aktualizaci entity.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Prozkoumání dat konkrétní entity

1. Přejděte na **Data** > **Entity**.
1. Na stránce **Entity** vyberte entitu a otevřete stránku podrobností.  
1. Prozkoumejte různá pole a záznamy obsažené v této entitě.

- Ve výchozím nastavení je vybrána karta **Atributy**, která zobrazuje tabulku pro kontrolu podrobností vybrané entity, jako jsou názvy polí, datové typy a typy. Sloupec **Typ** zobrazuje typy přidružené k Common Data Model, které jsou systémem automaticky identifikovány nebo [ručně mapovány](map-entities.md) uživateli. Tyto typy jsou sémantické typy, které se mohou lišit od datových typů atributů. Níže uvedené pole *E-mail* má například datový typ *Text*, ale jeho (sémantický typ) Common Data Model může být *Email* nebo *EmailAddress*.

> [!div class="mx-imgBorder"]
> ![Tabulka polí.](media/data-manager-entities-fields.PNG "Tabulka polí")

> [!NOTE]
> Tato stránka zobrazuje pouze ukázku dat entity. Chcete-li zobrazit celou datovou sadu, přejděte na stránku **Zdroje dat**, vyberte entitu, vyberte **Upravit** a poté si prohlédněte data této entity pomocí editoru Power Query, jak je vysvětleno v části [Zdroje dat](data-sources.md).

Chcete-li se dozvědět více o údajích přijímaných v entitě, sloupec **Souhrn** poskytuje některé důležité vlastnosti dat, jako jsou nuly, chybějící hodnoty, jedinečné hodnoty, počty a distribuce, které se vztahují na vaše data. Klepnutím na ikonu grafu zobrazíte souhrn dat.

> [!div class="mx-imgBorder"]
> ![Souhrnný symbol.](media/data-manager-entities-summary.png "Souhrnná tabulka dat")

- Karta **Data** záložka zobrazuje tabulku s podrobnostmi o jednotlivých záznamech entity. Uvedené podrobnosti závisí na datovém typu entity.

> [!div class="mx-imgBorder"]
> ![Zvolte entitu.](media/data-manager-entities-data.png "Zvolte entitu")

- Karta **Sestavy** (dostupná pro některé entity) umožňuje vizualizovat data vytvořením sestavy a obsahuje tyto sloupce:

  - **Název sestavy**: Název sestavy.
  - **Vytvořil/a**: Jméno osoby, která entitu vytvořila.
  - **Vytvořeno**: Datum a čas, kdy byla entita vytvořena.
  - **Upravil/a**: Jméno osoby, která entitu upravila.
  - **Upraveno**: Datum a čas, kdy byla entita změněna. 

## <a name="entity-specific-information"></a>Informace specifické pro entitu

Následující část poskytuje informace o některých systémově vytvořených entitách.

### <a name="corrupted-data-sources"></a>Poškozené zdroje dat

Pole z přijatého zdroje dat mohou obsahovat poškozená data. Záznamy s poškozenými poli jsou vystaveny v systémově vytvořených entitách. Když víte o poškozených záznamech, můžete určit, která data je třeba zkontrolovat a aktualizovat ve zdrojovém systému. Po dalším obnovení zdroje dat budou opravené záznamy přijaty do Customer Insights a předány do navazujících procesů. 

Sloupec „narozeniny“ má například datový typ nastavený jako „datum“. Záznam zákazníka má jeho narozeniny zadané jako '01/01/19777'. Systém označí tento záznam jako poškozený. Někdo teď může změnit narozeniny ve zdrojovém systému na '1977'. Po automatickém obnovení zdrojů dat má pole nyní platný formát a záznam bude odebrán z poškozené entity. 

Jděte na **Data** > **Subjekty** a vyhledejte poškozené entity v sekci **Systém**. Schéma pojmenování poškozených entit: 'DataSourceName_EntityName_corrupt'. Vyberte poškozenou entitu a identifikujte všechna poškozená pole a důvod na úrovni jednotlivých záznamů.
> [!div class="mx-imgBorder"]
> ![Důvod poškození.](media/corruption-reason.png "Důvod poškození")

Customer Insights stále zpracovává poškozené záznamy. Při práci se sjednocenými daty však mohou způsobit problémy.

Následující kontroly běží na přijatých datech, aby odhalily poškozené záznamy: 

- Hodnota pole se neshoduje s datovým typem jeho sloupce.
- Pole obsahují znaky, které způsobují, že sloupce neodpovídají očekávanému schématu. Například: nesprávně formátované uvozovky, neuzavřené uvozovky nebo znaky nového řádku.
- Pokud existují sloupce datetime/date/datetimeoffset, je třeba jejich formát zadat v modelu, pokud se neřídí standardním formátem ISO.


[!INCLUDE [footer-include](includes/footer-banner.md)]
