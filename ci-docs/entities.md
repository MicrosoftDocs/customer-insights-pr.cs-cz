---
title: Entity v Customer Insights
description: Zobrazení data na stránce Entity.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610090"
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

[!INCLUDE [footer-include](includes/footer-banner.md)]
