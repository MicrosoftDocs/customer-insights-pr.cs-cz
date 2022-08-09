---
title: Entity v Customer Insights
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
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183535"
---
# <a name="entities-in-customer-insights"></a>Entity v Customer Insights

Po [konfigurace zdrojů dat](data-sources.md) přejděte na stránku **Entity** pro vyhodnocení kvality přijímaných dat. Entity jsou považovány za datové sady. Kolem těchto entit jsou postaveny některé funkce Dynamics 365 Customer Insights. Jejich pečlivá kontrola vám pomůže ověřit výstup těchto funkcí.

Když pracujete v Customer Insights, rozšiřujete svá data nebo vytváříte segmenty, míry a aktivity, entity vytvořené z těchto akcí se zobrazují na stránce **Entity**.

## <a name="view-a-list-of-entities"></a>Zobrazení seznamu entit

Jděte na **Data** > **Entity**, čímž zobrazíte seznam entit. Pro každou entitu se zobrazí následující informace.

- **Název**: Název datové entity. Pokud se vedle názvu entity zobrazí varovný symbol, znamená to, že se data pro tuto entitu nenačítala úspěšně.
- **Zdroj**: Typ zdroje dat přijatého entitou.
- **Aktualizováno**: Čas poslední aktualizace entity.
- **Stav**: Podrobnosti o poslední aktualizaci entity.

## <a name="explore-a-specific-entitys-data"></a>Prozkoumání dat konkrétní entity

1. Přejděte na **Data** > **Entity**.
1. Výběrem entity otevřete stránku s podrobnostmi.  
1. Prozkoumejte různá pole a záznamy obsažené v této entitě.

- Ve výchozím nastavení je vybrána karta **Atributy**, která zobrazuje podrobnosti vybrané entity, jako jsou názvy polí, datové typy a typy. Sloupec **Typ** zobrazuje typy přidružené k Common Data Model, které jsou systémem automaticky identifikovány nebo [ručně mapovány](map-entities.md) uživateli. Tyto typy jsou sémantické typy, které se mohou lišit od datových typů atributů. Níže uvedené pole *E-mail* má například datový typ *Řetězec*, ale jeho (sémantický typ) Common Data Model může být *Email*, *EmailAddress* nebo *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabulka polí.":::

   > [!NOTE]
   > Tato stránka zobrazuje pouze ukázku dat entity. Chcete-li zobrazit celou datovou sadu, přejděte na stránku **Zdroje dat**, vyberte entitu, vyberte **Upravit** a poté si prohlédněte data této entity pomocí editoru Power Query, jak je vysvětleno v části [Zdroje dat](data-sources.md).

   Chcete-li se dozvědět více o údajích přijímaných v entitě, sloupec **Souhrn** poskytuje některé důležité vlastnosti dat, jako jsou nuly, chybějící hodnoty, jedinečné hodnoty, počty, distribuce, cokoli, co se vztahuje na vaše data. Klepnutím na ikonu grafu zobrazíte souhrn dat.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Souhrnná tabulka dat.":::

- Karta **Data** záložka zobrazuje podrobnosti o jednotlivých záznamech entity. Uvedené podrobnosti závisí na datovém typu entity.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Zvolte entitu.":::

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

   :::image type="content" source="media/corruption-reason.png" alt-text="Důvod poškození.":::

Customer Insights stále zpracovává poškozené záznamy. Při práci se sjednocenými daty však mohou způsobit problémy.

Následující kontroly běží na přijatých datech, aby odhalily poškozené záznamy:

- Hodnota pole se neshoduje s datovým typem jeho sloupce.
- Pole obsahují znaky, které způsobují, že sloupce neodpovídají očekávanému schématu. Například: nesprávně formátované uvozovky, neuzavřené uvozovky nebo znaky nového řádku.
- Pokud existují sloupce datetime/date/datetimeoffset, je třeba jejich formát zadat v modelu, pokud se neřídí standardním formátem ISO.

[!INCLUDE [footer-include](includes/footer-banner.md)]
