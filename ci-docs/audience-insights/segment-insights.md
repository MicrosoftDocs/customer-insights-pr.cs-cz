---
title: Přehledy existujících segmentů
description: Získejte přehled o existujících segmentech a podívejte se na rozdíly a společné rysy.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 90ebcaab896c628b04e751ad9857e924749895e7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595326"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="97a3b-103">Přehledy pro segmenty (Preview)</span><span class="sxs-lookup"><span data-stu-id="97a3b-103">Segment insights (preview)</span></span>

<span data-ttu-id="97a3b-104">Získejte další informace a přehledy o vašich stávajících segmentech.</span><span class="sxs-lookup"><span data-stu-id="97a3b-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="97a3b-105">Zjistěte, co odlišuje dva segmenty nebo co mají společné.</span><span class="sxs-lookup"><span data-stu-id="97a3b-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="97a3b-106">Překrytí segmentů</span><span class="sxs-lookup"><span data-stu-id="97a3b-106">Segment overlap</span></span>

<span data-ttu-id="97a3b-107">Analýza překrytí segmentů ukazuje, kolik a které zákazníky sdílejí dva nebo více segmentů.</span><span class="sxs-lookup"><span data-stu-id="97a3b-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="97a3b-108">Například jak se segment častých zákazníků překrývá se segmentem, který obsahuje zákazníky, kteří jsou spokojeni s vaší službou nebo produktem.</span><span class="sxs-lookup"><span data-stu-id="97a3b-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="97a3b-109">Můžete také analyzovat, jak se překrývání mění u konkrétních atributů.</span><span class="sxs-lookup"><span data-stu-id="97a3b-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="97a3b-110">Spuštění analýzy překrytí</span><span class="sxs-lookup"><span data-stu-id="97a3b-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="97a3b-111">Přejděte na **Segmenty** a vyberte kartu **Přehledy (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="97a3b-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="97a3b-112">Vyberte **Nový** a zvolte možnost **Překrytí** v panelu **Zvolte typ přehledu**.</span><span class="sxs-lookup"><span data-stu-id="97a3b-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="97a3b-113">Vyberte požadované segmenty a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="97a3b-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="97a3b-114">Volitelně vyberte jedno nebo více požadovaných polí, chcete-li analyzovat překrytí pro každou možnou hodnotu pole, a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="97a3b-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="97a3b-115">Zadejte název analýzy překrytí, volitelný zobrazovaný název a popis.</span><span class="sxs-lookup"><span data-stu-id="97a3b-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="97a3b-116">Volbou **Uložit** spusťe analýzu.</span><span class="sxs-lookup"><span data-stu-id="97a3b-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="97a3b-117">Analýza překrytí je připravena, když se stav změní z Aktualizace na Úspěšné.</span><span class="sxs-lookup"><span data-stu-id="97a3b-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="97a3b-118">Zobrazení a optimalizace analýzy překrytí</span><span class="sxs-lookup"><span data-stu-id="97a3b-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="97a3b-119">Po dokončení analýzy vyhledejte podrobnosti o tomto přehledu v části **Segmenty** > **Přehledy (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="97a3b-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Podrobnosti přehledu překrytí segmentů":::

<span data-ttu-id="97a3b-121">Chcete-li zobrazit výsledky analýzy, vyberte příslušný přehled:</span><span class="sxs-lookup"><span data-stu-id="97a3b-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="97a3b-122">Počet překrývajících se členů v segmentech vybraných pro analýzu.</span><span class="sxs-lookup"><span data-stu-id="97a3b-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="97a3b-123">Počet členů zahrnutých v jednom ze segmentů, ale nikoli ve zbývajících segmentech.</span><span class="sxs-lookup"><span data-stu-id="97a3b-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="97a3b-124">Pokud jste při konfiguraci analýzy překryté vybrali některá pole, najdete je na příslušných kartách.</span><span class="sxs-lookup"><span data-stu-id="97a3b-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="97a3b-125">V rozevíracím seznamu filtrů můžete vybrat libovolnou úroveň atributů, která vás zajímá, a tabulka dole zobrazí odpovídající data.</span><span class="sxs-lookup"><span data-stu-id="97a3b-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="97a3b-126">Diferenciátory segmentů</span><span class="sxs-lookup"><span data-stu-id="97a3b-126">Segment differentiators</span></span>

<span data-ttu-id="97a3b-127">Diferenciátory segmentů vám pomohou zjistit, co odlišuje segment od ostatních vašich zákazníků nebo od jiného segmentu.</span><span class="sxs-lookup"><span data-stu-id="97a3b-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="97a3b-128">Musíte pouze vybrat segment a systém identifikuje atributy a míry profilu, které odlišují vybraný segment.</span><span class="sxs-lookup"><span data-stu-id="97a3b-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="97a3b-129">Spuštění analýzy diferenciátoru</span><span class="sxs-lookup"><span data-stu-id="97a3b-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="97a3b-130">Přejděte na **Segmenty** a vyberte kartu **Přehledy (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="97a3b-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="97a3b-131">Vyberte **Nový** a zvolte možnost **Překrytí** v panelu **Zvolte typ přehledu**.</span><span class="sxs-lookup"><span data-stu-id="97a3b-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="97a3b-132">Vyberte segment, který chcete analyzovat, jako **Primární segment** a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="97a3b-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="97a3b-133">Vyberte **Všichni zákazníci** nebo **Sekundární segment**, abyste porovnali svůj primární segment a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="97a3b-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="97a3b-134">Volitelně vyberte jedno nebo více oblastí zájmu, aby se analýza zaměřila na konkrétní atributy, a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="97a3b-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="97a3b-135">Zadejte název analýzy překrytí, volitelný zobrazovaný název a popis.</span><span class="sxs-lookup"><span data-stu-id="97a3b-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="97a3b-136">Volbou **Uložit** spusťe analýzu.</span><span class="sxs-lookup"><span data-stu-id="97a3b-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="97a3b-137">Analýza překrytí je připravena, když se stav změní z Aktualizace na Úspěšné.</span><span class="sxs-lookup"><span data-stu-id="97a3b-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="97a3b-138">Zobrazení a optimalizace analýzy diferenciatorů</span><span class="sxs-lookup"><span data-stu-id="97a3b-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="97a3b-139">Po dokončení analýzy vyhledejte podrobnosti o tomto přehledu v části **Segmenty** > **Přehledy (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="97a3b-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Podrobnosti přehledu diferenciátoru segmentů":::

<span data-ttu-id="97a3b-141">Chcete-li zobrazit výsledky analýzy, vyberte příslušný přehled.</span><span class="sxs-lookup"><span data-stu-id="97a3b-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="97a3b-142">Analýza diferenciátoru zahrnuje dvě karty.</span><span class="sxs-lookup"><span data-stu-id="97a3b-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="97a3b-143">Karta **Atributy** uvádí atributy profilu, které jsou považovány za diferenciátory.</span><span class="sxs-lookup"><span data-stu-id="97a3b-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="97a3b-144">Karta **Míry** obsahuje diferenciátory.</span><span class="sxs-lookup"><span data-stu-id="97a3b-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="97a3b-145">Každá karta obsahuje následující podrobnosti:</span><span class="sxs-lookup"><span data-stu-id="97a3b-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="97a3b-146">Hodnocený seznam diferenciátorů seřazený podle skóre rozdílnosti.</span><span class="sxs-lookup"><span data-stu-id="97a3b-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="97a3b-147">**Skóre rozdílnosti** pro každý diferenciátor.</span><span class="sxs-lookup"><span data-stu-id="97a3b-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="97a3b-148">Skóre rozdílu představuje stupeň rozdílnosti atributu mezi dvěma segmenty.</span><span class="sxs-lookup"><span data-stu-id="97a3b-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="97a3b-149">Čím vyšší je skóre rozdílnosti, tím více atributů se liší mezi těmito dvěma segmenty.</span><span class="sxs-lookup"><span data-stu-id="97a3b-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="97a3b-150">Výběrem skóre otevřete podokno **Skóre rozdílnosti** s rozdělením hodnot pro tento atribut.</span><span class="sxs-lookup"><span data-stu-id="97a3b-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="97a3b-151">Správa přehledů segmentů</span><span class="sxs-lookup"><span data-stu-id="97a3b-151">Manage segment insights</span></span>

<span data-ttu-id="97a3b-152">V přehledech můžete použít následující možnosti z panelu příkazů:</span><span class="sxs-lookup"><span data-stu-id="97a3b-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="97a3b-153">**Zpět** pro návrat na seznam přehledů</span><span class="sxs-lookup"><span data-stu-id="97a3b-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="97a3b-154">**Aktualizovat** pro opětovné spuštění analýzy</span><span class="sxs-lookup"><span data-stu-id="97a3b-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="97a3b-155">**Odstranit** pro odstranění tohoto přehledu</span><span class="sxs-lookup"><span data-stu-id="97a3b-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]