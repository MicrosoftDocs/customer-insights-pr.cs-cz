---
title: Přehledy existujících segmentů
description: Získejte přehled o existujících segmentech a podívejte se na rozdíly a společné rysy.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 92e1b05dd08588a5da446af5b17b2d6ce57490ce
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405396"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="bf3d7-103">Přehledy pro segmenty (Preview)</span><span class="sxs-lookup"><span data-stu-id="bf3d7-103">Segment insights (preview)</span></span>

<span data-ttu-id="bf3d7-104">Získejte další informace a přehledy o vašich stávajících segmentech.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="bf3d7-105">Zjistěte, co odlišuje dva segmenty nebo co mají společné.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="bf3d7-106">Překrytí segmentů</span><span class="sxs-lookup"><span data-stu-id="bf3d7-106">Segment overlap</span></span>

<span data-ttu-id="bf3d7-107">Analýza překrytí segmentů ukazuje, kolik a které zákazníky sdílejí dva nebo více segmentů.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="bf3d7-108">Například jak se segment častých zákazníků překrývá se segmentem, který obsahuje zákazníky, kteří jsou spokojeni s vaší službou nebo produktem.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="bf3d7-109">Můžete také analyzovat, jak se překrývání mění u konkrétních atributů.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="bf3d7-110">Spuštění analýzy překrytí</span><span class="sxs-lookup"><span data-stu-id="bf3d7-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="bf3d7-111">Přejděte na **Segmenty** a vyberte kartu **Přehledy (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="bf3d7-112">Vyberte **Nový** a zvolte možnost **Překrytí** v panelu **Zvolte typ přehledu**.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="bf3d7-113">Vyberte požadované segmenty a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="bf3d7-114">Volitelně vyberte jedno nebo více požadovaných polí, chcete-li analyzovat překrytí pro každou možnou hodnotu pole, a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="bf3d7-115">Zadejte název analýzy překrytí, volitelný zobrazovaný název a popis.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="bf3d7-116">Volbou **Uložit** spusťe analýzu.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="bf3d7-117">Analýza překrytí je připravena, když se stav změní z Aktualizace na Úspěšné.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="bf3d7-118">Zobrazení a optimalizace analýzy překrytí</span><span class="sxs-lookup"><span data-stu-id="bf3d7-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="bf3d7-119">Po dokončení analýzy vyhledejte podrobnosti o tomto přehledu v části **Segmenty** > **Přehledy (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Podrobnosti přehledu překrytí segmentů":::

<span data-ttu-id="bf3d7-121">Chcete-li zobrazit výsledky analýzy, vyberte příslušný přehled:</span><span class="sxs-lookup"><span data-stu-id="bf3d7-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="bf3d7-122">Počet překrývajících se členů v segmentech vybraných pro analýzu.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="bf3d7-123">Počet členů zahrnutých v jednom ze segmentů, ale nikoli ve zbývajících segmentech.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="bf3d7-124">Pokud jste při konfiguraci analýzy překryté vybrali některá pole, najdete je na příslušných kartách.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="bf3d7-125">V rozevíracím seznamu filtrů můžete vybrat libovolnou úroveň atributů, která vás zajímá, a tabulka dole zobrazí odpovídající data.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="bf3d7-126">Diferenciátory segmentů</span><span class="sxs-lookup"><span data-stu-id="bf3d7-126">Segment differentiators</span></span>

<span data-ttu-id="bf3d7-127">Diferenciátory segmentů vám pomohou zjistit, co odlišuje segment od ostatních vašich zákazníků nebo od jiného segmentu.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="bf3d7-128">Musíte pouze vybrat segment a systém identifikuje atributy a míry profilu, které odlišují vybraný segment.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="bf3d7-129">Spuštění analýzy diferenciátoru</span><span class="sxs-lookup"><span data-stu-id="bf3d7-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="bf3d7-130">Přejděte na **Segmenty** a vyberte kartu **Přehledy (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="bf3d7-131">Vyberte **Nový** a zvolte možnost **Překrytí** v panelu **Zvolte typ přehledu**.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="bf3d7-132">Vyberte segment, který chcete analyzovat, jako **Primární segment** a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="bf3d7-133">Vyberte **Všichni zákazníci** nebo **Sekundární segment**, abyste porovnali svůj primární segment a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="bf3d7-134">Volitelně vyberte jedno nebo více oblastí zájmu, aby se analýza zaměřila na konkrétní atributy, a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="bf3d7-135">Zadejte název analýzy překrytí, volitelný zobrazovaný název a popis.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="bf3d7-136">Volbou **Uložit** spusťe analýzu.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="bf3d7-137">Analýza překrytí je připravena, když se stav změní z Aktualizace na Úspěšné.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="bf3d7-138">Zobrazení a optimalizace analýzy diferenciatorů</span><span class="sxs-lookup"><span data-stu-id="bf3d7-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="bf3d7-139">Po dokončení analýzy vyhledejte podrobnosti o tomto přehledu v části **Segmenty** > **Přehledy (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Podrobnosti přehledu diferenciátoru segmentů":::

<span data-ttu-id="bf3d7-141">Chcete-li zobrazit výsledky analýzy, vyberte příslušný přehled.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="bf3d7-142">Analýza diferenciátoru zahrnuje dvě karty.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="bf3d7-143">Karta **Atributy** uvádí atributy profilu, které jsou považovány za diferenciátory.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="bf3d7-144">Karta **Míry** obsahuje diferenciátory.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="bf3d7-145">Každá karta obsahuje následující podrobnosti:</span><span class="sxs-lookup"><span data-stu-id="bf3d7-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="bf3d7-146">Hodnocený seznam diferenciátorů seřazený podle skóre rozdílnosti.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="bf3d7-147">**Skóre rozdílnosti** pro každý diferenciátor.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="bf3d7-148">Skóre rozdílu představuje stupeň rozdílnosti atributu mezi dvěma segmenty.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="bf3d7-149">Čím vyšší je skóre rozdílnosti, tím více atributů se liší mezi těmito dvěma segmenty.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="bf3d7-150">Výběrem skóre otevřete podokno **Skóre rozdílnosti** s rozdělením hodnot pro tento atribut.</span><span class="sxs-lookup"><span data-stu-id="bf3d7-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="bf3d7-151">Správa přehledů segmentů</span><span class="sxs-lookup"><span data-stu-id="bf3d7-151">Manage segment insights</span></span>

<span data-ttu-id="bf3d7-152">V přehledech můžete použít následující možnosti z panelu příkazů:</span><span class="sxs-lookup"><span data-stu-id="bf3d7-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="bf3d7-153">**Zpět** pro návrat na seznam přehledů</span><span class="sxs-lookup"><span data-stu-id="bf3d7-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="bf3d7-154">**Aktualizovat** pro opětovné spuštění analýzy</span><span class="sxs-lookup"><span data-stu-id="bf3d7-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="bf3d7-155">**Odstranit** pro odstranění tohoto přehledu</span><span class="sxs-lookup"><span data-stu-id="bf3d7-155">**Delete** to remove this insight</span></span>
