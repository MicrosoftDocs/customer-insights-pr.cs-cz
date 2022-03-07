---
title: Schéma entit Customer Insights v definici Common Data Model
description: Práce s entitami v Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 66d846c3e9404ca7993cae742ea6e16833233fba
ms.sourcegitcommit: 205f931ec671a0ab1850f2c1c94df3307ffb62c9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/13/2021
ms.locfileid: "7380735"
---
# <a name="entity-schemas-in-common-data-model"></a>Schémata entit v Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](/common-data-model/) je deklarativní specifikace a definice standardních entit, která představuje běžně používané koncepce a aktivity v různých obchodních a produktivních aplikacích. Tento model se rozšiřuje také na pozorovací a analytická data. Common Data Model poskytuje jasně definované, modulární a rozšiřitelné obchodní entity (například Účet, Obchodní jednotka, Případ, Kontakt, Zájemce, Příležitost a Produkt) a také interakce a vztahy mezi dodavateli, pracovníky a zákazníky, například aktivity a smlouvy o úrovni služeb. Kdokoli může stavět a rozšiřovat definice Common Data Model, aby zahrnul další podnikatelské nápady.

Tento sdílený datový model umožňuje aplikacím a datovým integrátorům snadnější spolupráci tím, že poskytuje jednotnou definici dat. Common Data Model zahrnuje bohatý systém metadat se standardními entitami, vztahy, hierarchiemi, zvláštnostmi a další. Pochází z aplikací Dynamics 365 a jeho veřejný zdrojový kód je k dispozici na GitHubu s více než 260 standardními entitami. Rozsáhlý systém interních a externích partnerů přispívá koncepty Common Data Model pro jednotlivá odvětví.

Common Data Model dnes implementuje více systémů a platforem, včetně datových toků Power BI a Azure Data Services. Už je podporováno v Microsoft Dataverse, Dynamics 365, Power Apps, Power BI a nadcházející datové služby Azure, přímo zvyšující hodnotu vůči [Otevřené datové iniciativě](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Schémata entit Customer Insights

Pro vytvoření 360stupňového pohledu na zákazníka a zpřístupnění modelů Customer Insights v Common Data Model pro rozšiřitelnost jsme publikovali následující schémata entit:

| Entita | Popis |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Aktivita prováděná uživatelem, která má pro podnik pozorovací hodnotu. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Osoba nebo organizace, která buď vykonávala obchodní aktivity, nebo k nim má potenciál. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definice ukazatelů KPI rozdělených podle žádných nebo více dimenzí (např. Měsíční aktivní uživatelé, Celkové výdaje podle zákazníka, Průměrné náklady na získání zákazníka) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definuje skupinu členů se společnými rysy. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Členové pro daný segment. |

Další informace naleznete v dokumentaci [Schémata entit Customer Insights v definici Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Zobrazení entit pomocí navigátoru entit Common Data Model

Entity si můžete prohlédnout v [navigátoru entit Common Data Model](https://microsoft.github.io/CDM/). Vyberte entitu z části aplikace přehledů a získáte seznam entit Customer Insights a jejich definice.
> [!div class="mx-imgBorder"]
> ![Navigátor entit CDM zobrazující entitu CustomerActivity.](media/CDM-entity-navigator.png "Navigátor entit CDM zobrazující entitu CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]
