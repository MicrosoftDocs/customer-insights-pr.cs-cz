---
title: Ingestování data prostřednictvím konektoru Power Query
description: Konektory pro zdroje dat založené na Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405375"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="ce69e-103">Připojte se k Power Query zdroji dat</span><span class="sxs-lookup"><span data-stu-id="ce69e-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="ce69e-104">Power Query nabízí širokou sadu konektorů pro příjem dat.</span><span class="sxs-lookup"><span data-stu-id="ce69e-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="ce69e-105">Většina z těchto konektorů je podporována Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ce69e-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="ce69e-106">Přidání zdrojů dat na základě Power Query konektorů obecně postupuje podle kroků uvedených v následující části.</span><span class="sxs-lookup"><span data-stu-id="ce69e-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="ce69e-107">V závislosti na použitém konektoru jsou však vyžadovány různé informace.</span><span class="sxs-lookup"><span data-stu-id="ce69e-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="ce69e-108">Další informace najdete v dokumentaci o jednotlivých konektorech v [Odkazu na konektory Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="ce69e-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="ce69e-109">Vytvořit nový zdroj dat</span><span class="sxs-lookup"><span data-stu-id="ce69e-109">Create a new data source</span></span>

1. <span data-ttu-id="ce69e-110">V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="ce69e-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="ce69e-111">Vyberte **Přidat zdroj dat**.</span><span class="sxs-lookup"><span data-stu-id="ce69e-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="ce69e-112">Vyberte metodu **Import dat** a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="ce69e-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="ce69e-113">Uveďte **Název** pro zdroj dat a vyberte **Další** k vytvoření zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="ce69e-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="ce69e-114">Vyberte jeden z [dostupných konektorů](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="ce69e-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="ce69e-115">V tomto příkladu vybereme konektor **Text / CSV**.</span><span class="sxs-lookup"><span data-stu-id="ce69e-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="ce69e-116">Zadejte požadované podrobnosti do **Nastavení připojení** pro vybraný konektor a vyberte **Další** pro zobrazení náhledu dat.</span><span class="sxs-lookup"><span data-stu-id="ce69e-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="ce69e-117">Vyberte **Transformovat data**.</span><span class="sxs-lookup"><span data-stu-id="ce69e-117">Select **Transform data**.</span></span> <span data-ttu-id="ce69e-118">V tomto kroku přidáte entity do zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="ce69e-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="ce69e-119">Entity jsou datové sady.</span><span class="sxs-lookup"><span data-stu-id="ce69e-119">Entities are datasets.</span></span> <span data-ttu-id="ce69e-120">Pokud máte databázi, která obsahuje více datových sad, je každá datová sada vlastní entitou.</span><span class="sxs-lookup"><span data-stu-id="ce69e-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="ce69e-121">Dialogové okno **Power Query - Upravit dotazy** umožňuje zkontrolovat a upřesnit data.</span><span class="sxs-lookup"><span data-stu-id="ce69e-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="ce69e-122">V levém podokně se zobrazí entity, které systémy identifikované ve vybraném zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="ce69e-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ce69e-123">![Dialog Upravit dotazy](media/data-manager-configure-edit-queries.png "Dialog Upravit dotazy")</span><span class="sxs-lookup"><span data-stu-id="ce69e-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="ce69e-124">Data lze rovněž transformovat.</span><span class="sxs-lookup"><span data-stu-id="ce69e-124">You can also transform your data.</span></span> <span data-ttu-id="ce69e-125">Vyberte entitu, kterou chcete upravit nebo transformovat.</span><span class="sxs-lookup"><span data-stu-id="ce69e-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="ce69e-126">K použití transformací použijte možnosti v okně Power Query.</span><span class="sxs-lookup"><span data-stu-id="ce69e-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="ce69e-127">Každá transformace bude uvedena v **Použité kroky**.</span><span class="sxs-lookup"><span data-stu-id="ce69e-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="ce69e-128">Power Query poskytuje řadu předem připravených možností transformace.</span><span class="sxs-lookup"><span data-stu-id="ce69e-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="ce69e-129">Další informace najdete v tématu [Transormace Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="ce69e-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="ce69e-130">Výběrem **Získejte data** v dialogu **Upravit dotazy** můžete do svého zdroje dat přidat další entity.</span><span class="sxs-lookup"><span data-stu-id="ce69e-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="ce69e-131">Tyto transformace jsou vysoce doporučeny:</span><span class="sxs-lookup"><span data-stu-id="ce69e-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="ce69e-132">Pokud přijímáte data ze souboru CSV, první řádek často obsahuje záhlaví.</span><span class="sxs-lookup"><span data-stu-id="ce69e-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="ce69e-133">Přejděte na **Transformační tabulka** a vyberte **Jako první řádek použijte záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="ce69e-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="ce69e-134">Zajistěte, aby byl datový typ nastaven správně.</span><span class="sxs-lookup"><span data-stu-id="ce69e-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="ce69e-135">Výběrem tlačítka **Uložit** ve spodní části Power Query uložte transformace.</span><span class="sxs-lookup"><span data-stu-id="ce69e-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="ce69e-136">Po uložení najdete svůj zdroj dat v **Data** > **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="ce69e-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="ce69e-137">Na stránce **Zdroje dat** si všimnete, že nový zdroj dat je ve stavu **Aktualizace**.</span><span class="sxs-lookup"><span data-stu-id="ce69e-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="ce69e-138">Dostupné Power Query zdroje dat</span><span class="sxs-lookup"><span data-stu-id="ce69e-138">Available Power Query data sources</span></span>

<span data-ttu-id="ce69e-139">Viz [Odkaz na konektory Power Query](https://docs.microsoft.com/power-query/connectors/) pro aktuální seznam konektorů, které můžete vybrat k importu dat do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ce69e-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="ce69e-140">Konektory se zaškrtnutím ve sloupci **Customer Insights (toky dat)** slouží k vytvoření nových zdrojů dat založených na Power Query.</span><span class="sxs-lookup"><span data-stu-id="ce69e-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="ce69e-141">Projděte si dokumentaci konkrétního konektoru a dozvíte se více o jeho požadavcích, omezeních a dalších podrobnostech.</span><span class="sxs-lookup"><span data-stu-id="ce69e-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="ce69e-142">Upravit zdroje dat Power Query</span><span class="sxs-lookup"><span data-stu-id="ce69e-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="ce69e-143">Pravděpodobně nebude možné provést změny ve zdrojích dat, které se aktuálně používají v jednom z procesů aplikace (např. *segmentace*, *shoda* nebo *sloučit*).</span><span class="sxs-lookup"><span data-stu-id="ce69e-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="ce69e-144">Za použití stránky **Nastavení** můžete sledovat průběh každého z aktivních procesů.</span><span class="sxs-lookup"><span data-stu-id="ce69e-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="ce69e-145">Po dokončení procesu se můžete vrátit na stránku **Zdroje dat** stránku a provést změny.</span><span class="sxs-lookup"><span data-stu-id="ce69e-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="ce69e-146">V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="ce69e-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="ce69e-147">Vyberte vertikální tři tečky vedle zdroje dat, který chcete změnit, a vyberte **Upravit** z rozbalovací nabídky.</span><span class="sxs-lookup"><span data-stu-id="ce69e-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ce69e-148">![Upravit možnost](media/edit-option-data-sources.png "Upravit možnost")</span><span class="sxs-lookup"><span data-stu-id="ce69e-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="ce69e-149">Aplikujte své změny a transformace v dialogovém okně **Power Query - Upravit dotazy**, jak je popsáno v sekci [Vytvořte nový zdroj dat](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="ce69e-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="ce69e-150">Vyberte **Uložit** po dokončení úprav a uložte změny v Power Query.</span><span class="sxs-lookup"><span data-stu-id="ce69e-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
