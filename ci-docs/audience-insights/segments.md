---
title: Segmenty v přehledech cílové skupiny
description: Vytvořte přehled segmentů a způsob jejich vytváření a správy.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306249"
---
# <a name="segments-overview"></a><span data-ttu-id="15a87-103">Přehled segmentů</span><span class="sxs-lookup"><span data-stu-id="15a87-103">Segments overview</span></span>

<span data-ttu-id="15a87-104">Segmenty umožňují seskupit zákazníky na základě demografických, transakčních nebo behaviorálních atributů.</span><span class="sxs-lookup"><span data-stu-id="15a87-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="15a87-105">Segmenty můžete použít k cílení propagačních kampaní, prodejních aktivit a akcí podpory zákazníků k dosažení vašich obchodních cílů.</span><span class="sxs-lookup"><span data-stu-id="15a87-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="15a87-106">Profily zákazníků, které odpovídají filtrům definice segmentu, se označují jako *prvky* segmentu.</span><span class="sxs-lookup"><span data-stu-id="15a87-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="15a87-107">Použijí se některé [servisní limity](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="15a87-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="15a87-108">Vytvořit nový segment</span><span class="sxs-lookup"><span data-stu-id="15a87-108">Create a new segment</span></span>

<span data-ttu-id="15a87-109">Existuje několik způsobů, jak vytvořit nový segment:</span><span class="sxs-lookup"><span data-stu-id="15a87-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="15a87-110">Složitý segment s nástrojem pro vytváření segmentů: [Prázdný segment](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="15a87-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="15a87-111">Jednoduché segmenty s jedním operátorem: [Rychlý segment](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="15a87-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="15a87-112">Způsob vyhledání podobných zákazníků pomocí technologie AI: [Podobní zákazníci](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="15a87-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="15a87-113">Návrhy využívající AI založené na mírách nebo atributech: [Navrhované segmenty ke zlepšení měr](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="15a87-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="15a87-114">Návrhy založené na činnostech: [Navrhované segmenty na základě aktivity zákazníků](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="15a87-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="15a87-115">Správa existujících segmentů</span><span class="sxs-lookup"><span data-stu-id="15a87-115">Manage existing segments</span></span>

<span data-ttu-id="15a87-116">Jděte na stránku **segmenty**, kde můžete zobrazit všechny uložené segmenty a spravovat je.</span><span class="sxs-lookup"><span data-stu-id="15a87-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="15a87-117">Každý segment je reprezentován řádkem, která obsahuje další informace o segmentu.</span><span class="sxs-lookup"><span data-stu-id="15a87-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Vybraný segment s rozevíracím seznamem možností a dostupnými možnostmi.":::

<span data-ttu-id="15a87-119">Když vyberete segment, jsou k dispozici následující akce:</span><span class="sxs-lookup"><span data-stu-id="15a87-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="15a87-120">**Zobrazit** podrobnosti o segmentu, včetně trendu počtu členů, náhledu členů segmentu.</span><span class="sxs-lookup"><span data-stu-id="15a87-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="15a87-121">**Upravit** segment změnit jeho vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="15a87-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="15a87-122">**Vytvořit duplicitu** segmentu.</span><span class="sxs-lookup"><span data-stu-id="15a87-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="15a87-123">Můžete se rozhodnout upravit její vlastnosti hned nebo duplicitu jednoduše uložit.</span><span class="sxs-lookup"><span data-stu-id="15a87-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="15a87-124">**Obnovit** segment a zahrnout nejnovější data.</span><span class="sxs-lookup"><span data-stu-id="15a87-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="15a87-125">**Aktivace** nebo **deaktivace** segmentu.</span><span class="sxs-lookup"><span data-stu-id="15a87-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="15a87-126">Segmenty mají dva možné stavy – aktivní nebo neaktivní.</span><span class="sxs-lookup"><span data-stu-id="15a87-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="15a87-127">Tyto stavy jsou užitečné při úpravách segmentu.</span><span class="sxs-lookup"><span data-stu-id="15a87-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="15a87-128">Pro neaktivní segmenty existuje jejich definice, ale zatím neobsahuje žádné zákazníky.</span><span class="sxs-lookup"><span data-stu-id="15a87-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="15a87-129">Když aktivujete segment, jeho stav se změní z „neaktivní“ na „aktivní“ a začne hledat zákazníky, kteří odpovídají definici segmentu.</span><span class="sxs-lookup"><span data-stu-id="15a87-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="15a87-130">Pokud je konfigurována [plánovaná aktualizace](system.md#schedule-tab), neaktivní segmenty mají **Stav** uveden jako **Přeskočeno**, což označuje, že u nich neproběhl ani pokus o aktualizaci.</span><span class="sxs-lookup"><span data-stu-id="15a87-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="15a87-131">Když je neaktivní segment aktivován, aktualizuje se a bude součástí plánovaných aktualizací.</span><span class="sxs-lookup"><span data-stu-id="15a87-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="15a87-132">Případně můžete použít funkci **Plánovat později** v rozevíracím seznamu **Aktivovat/deaktivovat** pro určení budoucího data a času aktivace a deaktivace konkrétního segmentu.</span><span class="sxs-lookup"><span data-stu-id="15a87-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="15a87-133">**Přejmenovat** segment.</span><span class="sxs-lookup"><span data-stu-id="15a87-133">**Rename** the segment.</span></span>
- <span data-ttu-id="15a87-134">**Stáhnout** seznam členů jako soubor .CSV.</span><span class="sxs-lookup"><span data-stu-id="15a87-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="15a87-135">Možnost **Spravovat exporty** zobrazí segment související s exportem a umožní jeho správu.</span><span class="sxs-lookup"><span data-stu-id="15a87-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="15a87-136">Další informace o exportech.</span><span class="sxs-lookup"><span data-stu-id="15a87-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="15a87-137">**Odstranit** segment.</span><span class="sxs-lookup"><span data-stu-id="15a87-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="15a87-138">Aktualizovat segmenty</span><span class="sxs-lookup"><span data-stu-id="15a87-138">Refresh segments</span></span>

<span data-ttu-id="15a87-139">Můžete aktualizovat všechny segmenty najednou výběrem **Aktualizovat vše** na stránce **Segmenty** nebo můžete aktualizovat jeden nebo více segmentů, když je vyberete a z možností vyberete volbu **Aktualizovat**.</span><span class="sxs-lookup"><span data-stu-id="15a87-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="15a87-140">Případně můžete nakonfigurovat opakovanou aktualizaci **Správce** > **Systém** > **Plán**.</span><span class="sxs-lookup"><span data-stu-id="15a87-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="15a87-141">Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy.</span><span class="sxs-lookup"><span data-stu-id="15a87-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="15a87-142">Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="15a87-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="15a87-143">Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy.</span><span class="sxs-lookup"><span data-stu-id="15a87-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="15a87-144">Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.</span><span class="sxs-lookup"><span data-stu-id="15a87-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="15a87-145">Export segmentů</span><span class="sxs-lookup"><span data-stu-id="15a87-145">Export segments</span></span>

<span data-ttu-id="15a87-146">Segment můžete exportovat ze stránky segmentů nebo ze [stránky exportů](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="15a87-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="15a87-147">Přejde na stránku **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="15a87-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="15a87-148">Vyberte možnost **Zobrazit další [...]** pro segment, který chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="15a87-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="15a87-149">V rozevíracím seznamu akcí vyberte **Spravovat exporty**.</span><span class="sxs-lookup"><span data-stu-id="15a87-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="15a87-150">Otevře se stránka **Exporty (preview) pro segment**.</span><span class="sxs-lookup"><span data-stu-id="15a87-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="15a87-151">Můžete zobrazit všechny konfigurované exporty seskupené podle exportů, které obsahují aktuální segment nebo jej neobsahují.</span><span class="sxs-lookup"><span data-stu-id="15a87-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="15a87-152">Chcete-li přidat vybraný segment do exportu, vyberte export v seznamu a vyberte **Přidat segment**.</span><span class="sxs-lookup"><span data-stu-id="15a87-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="15a87-153">Chcete-li vytvořit nový export s vybraným segmentem, vyberte **Přidat export**.</span><span class="sxs-lookup"><span data-stu-id="15a87-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="15a87-154">Další informace o vytváření exportů najdete v části [Nastavení nového exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="15a87-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="15a87-155">Výběrem možnosti **Zpět** se vraťte na hlavní stránku pro segmenty.</span><span class="sxs-lookup"><span data-stu-id="15a87-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="15a87-156">Zobrazit historii zpracování a členy segmentu</span><span class="sxs-lookup"><span data-stu-id="15a87-156">View processing history and segment members</span></span>

<span data-ttu-id="15a87-157">Konsolidovaná data o segmentu můžete zobrazit kontrolou jeho podrobností.</span><span class="sxs-lookup"><span data-stu-id="15a87-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="15a87-158">Na stránce **Segmenty** vyberte segment, který chcete zkontrolovat.</span><span class="sxs-lookup"><span data-stu-id="15a87-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="15a87-159">Horní část stránky obsahuje graf trendů, který vizualizuje změny v počtu členů.</span><span class="sxs-lookup"><span data-stu-id="15a87-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="15a87-160">Najeďte na datové body, abyste viděli počet členů k určitému datu.</span><span class="sxs-lookup"><span data-stu-id="15a87-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="15a87-161">Můžete aktualizovat časový rámec vizualizace.</span><span class="sxs-lookup"><span data-stu-id="15a87-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="15a87-162">![Časový rozsah segmentu](media/segment-time-range.png "Časový rozsah segmentu")</span><span class="sxs-lookup"><span data-stu-id="15a87-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="15a87-163">Spodní část obsahuje seznam členů segmentu.</span><span class="sxs-lookup"><span data-stu-id="15a87-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="15a87-164">Pole, která se zobrazí v tomto seznamu, jsou založena na atributech entit segmentu.</span><span class="sxs-lookup"><span data-stu-id="15a87-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="15a87-165">Seznam je náhledem odpovídajících členů segmentu a zobrazuje prvních 100 záznamů segmentu, takže jej můžete rychle vyhodnotit a v případě potřeby zkontrolovat jeho definice.</span><span class="sxs-lookup"><span data-stu-id="15a87-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="15a87-166">Chcete-li zobrazit všechny odpovídající záznamy, je třeba [segment exportovat](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="15a87-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
