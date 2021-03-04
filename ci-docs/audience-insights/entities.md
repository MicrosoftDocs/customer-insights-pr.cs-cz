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
# <a name="entities-in-audience-insights"></a><span data-ttu-id="e894c-103">Entity v přehledech cílové skupiny</span><span class="sxs-lookup"><span data-stu-id="e894c-103">Entities in audience insights</span></span>

<span data-ttu-id="e894c-104">Po [konfigurace zdrojů dat](data-sources.md) přejděte na stránku **Entity** pro vyhodnocení kvality přijímaných dat.</span><span class="sxs-lookup"><span data-stu-id="e894c-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="e894c-105">Entity jsou považovány za datové sady.</span><span class="sxs-lookup"><span data-stu-id="e894c-105">Entities are considered datasets.</span></span> <span data-ttu-id="e894c-106">Kolem těchto entit jsou postaveny některé funkce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e894c-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="e894c-107">Jejich pečlivá kontrola vám pomůže ověřit výstup těchto funkcí.</span><span class="sxs-lookup"><span data-stu-id="e894c-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="e894c-108">Stránka **Entity** uvádí entity a zahrnuje několik sloupců:</span><span class="sxs-lookup"><span data-stu-id="e894c-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="e894c-109">**Název**: Název vaší datové entity.</span><span class="sxs-lookup"><span data-stu-id="e894c-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="e894c-110">Pokud se vedle názvu entity zobrazí varovný symbol, znamená to, že se data pro tuto entitu nenačítala úspěšně.</span><span class="sxs-lookup"><span data-stu-id="e894c-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="e894c-111">**Zdroj**: Typ zdroje dat, který přijal entitu</span><span class="sxs-lookup"><span data-stu-id="e894c-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="e894c-112">**Vytvořil/a**: Jméno osoby, která entitu vytvořila</span><span class="sxs-lookup"><span data-stu-id="e894c-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="e894c-113">**Vytvořeno**: Datum a čas, kdy byla entita vytvořena</span><span class="sxs-lookup"><span data-stu-id="e894c-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="e894c-114">**Aktualizoval/a**: Jméno osoby, která entitu aktualizovala</span><span class="sxs-lookup"><span data-stu-id="e894c-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="e894c-115">**Naposledy aktualizováno**: Datum a čas poslední aktualizace entity</span><span class="sxs-lookup"><span data-stu-id="e894c-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="e894c-116">**Poslední aktualizace**: Datum a čas poslední aktualizace dat</span><span class="sxs-lookup"><span data-stu-id="e894c-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="e894c-117">Zkoumání dat konkrétní entity</span><span class="sxs-lookup"><span data-stu-id="e894c-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="e894c-118">Vyberte entitu a prozkoumejte různá pole a záznamy obsažené v této entitě.</span><span class="sxs-lookup"><span data-stu-id="e894c-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e894c-119">![Výběr entity](media/data-manager-entities-data.png "Vyberte entitu.")</span><span class="sxs-lookup"><span data-stu-id="e894c-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="e894c-120">Karta **Data** je ve výchozím nastavení vybrána a zobrazuje tabulku s podrobnostmi o jednotlivých záznamech entity.</span><span class="sxs-lookup"><span data-stu-id="e894c-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e894c-121">![Tabulka polí](media/data-manager-entities-fields.PNG "Tabulka polí")</span><span class="sxs-lookup"><span data-stu-id="e894c-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="e894c-122">Karta **Pole** zobrazuje tabulku pro kontrolu podrobností o vybrané entitě, jako jsou názvy polí, datové typy a typy.</span><span class="sxs-lookup"><span data-stu-id="e894c-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="e894c-123">Sloupec **Typ** zobrazuje typy přidružené k Common Data Model, které jsou systémem automaticky identifikovány nebo [ručně mapovány](map-entities.md) uživateli.</span><span class="sxs-lookup"><span data-stu-id="e894c-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="e894c-124">Jedná se o sémantické typy, které se mohou lišit od datových typů atributů - například pole *E-mail* níže je datový typ *Text*, ale jeho (sémantický) typ Common Data Model může být *E-mail* nebo *Emailová adresa*.</span><span class="sxs-lookup"><span data-stu-id="e894c-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="e894c-125">Obě tabulky ukazují pouze ukázku dat vaší entity.</span><span class="sxs-lookup"><span data-stu-id="e894c-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="e894c-126">Chcete-li zobrazit celou datovou sadu, přejděte na stránku **Zdroje dat**, vyberte entitu, vyberte **Upravit** a poté si prohlédněte data této entity pomocí editoru Power Query, jak je vysvětleno v části [Zdroje dat](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="e894c-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="e894c-127">Chcete-li se dozvědět více o údajích přijímaných v entitě, sloupec **Souhrn** poskytuje některé důležité vlastnosti dat, jako jsou nuly, chybějící hodnoty, jedinečné hodnoty, počty a distribuce, které se vztahují na vaše data.</span><span class="sxs-lookup"><span data-stu-id="e894c-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="e894c-128">Klepnutím na ikonu grafu zobrazíte souhrn dat.</span><span class="sxs-lookup"><span data-stu-id="e894c-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e894c-129">![Souhrnný symbol](media/data-manager-entities-summary.png "Souhrnná tabulka dat")</span><span class="sxs-lookup"><span data-stu-id="e894c-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="e894c-130">Další krok</span><span class="sxs-lookup"><span data-stu-id="e894c-130">Next step</span></span>

<span data-ttu-id="e894c-131">V tématu [Sjednotit](data-unification.md) se dozvíte, jak na to *mapovat*, *přiřadit* a *sloučit* přijatá data.</span><span class="sxs-lookup"><span data-stu-id="e894c-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]