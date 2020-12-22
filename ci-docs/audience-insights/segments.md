---
title: Vytvořit a spravovat segmenty
description: Vytvořte segmenty zákazníků a seskupte je podle různých atributů.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405403"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="c20d8-103">Vytvořit a spravovat segmenty</span><span class="sxs-lookup"><span data-stu-id="c20d8-103">Create and manage segments</span></span>

<span data-ttu-id="c20d8-104">Segmenty umožňují seskupit zákazníky na základě demografických, transakčních nebo behaviorálních atributů.</span><span class="sxs-lookup"><span data-stu-id="c20d8-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="c20d8-105">Segmenty můžete použít k cílení propagačních kampaní, prodejních aktivit a akcí podpory zákazníků k dosažení vašich obchodních cílů.</span><span class="sxs-lookup"><span data-stu-id="c20d8-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="c20d8-106">Můžete definovat složité filtry kolem entity Profil zákazníka a souvisejících entit.</span><span class="sxs-lookup"><span data-stu-id="c20d8-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="c20d8-107">Každý segment po zpracování vytvoří sadu záznamů o zákaznících, které můžete exportovat a se kterými můžete provádět akce.</span><span class="sxs-lookup"><span data-stu-id="c20d8-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="c20d8-108">Použijí se některé [servisní limity](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="c20d8-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="c20d8-109">Pokud není uvedeno jinak, všechny segmenty jsou **Dynamické segmenty**, které se obnovují podle opakujícího se plánu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="c20d8-110">Následující příklad ukazuje funkci segmentace.</span><span class="sxs-lookup"><span data-stu-id="c20d8-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="c20d8-111">Definovali jsme segment pro zákazníky, kteří si za posledních 90 dní objednali zboží alespoň za $500 *a* kteří se účastnili volání služby zákazníkům, které bylo eskalováno.</span><span class="sxs-lookup"><span data-stu-id="c20d8-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c20d8-112">![Více skupin](media/segmentation-group1-2.png "Více skupin")</span><span class="sxs-lookup"><span data-stu-id="c20d8-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="c20d8-113">Vytvořit nový segment</span><span class="sxs-lookup"><span data-stu-id="c20d8-113">Create a new segment</span></span>

<span data-ttu-id="c20d8-114">Segmenty jsou spravovány na stránce **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="c20d8-115">V přehledech cílové skupiny přejděte na stránku **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c20d8-116">Vybrat **Nový** > **Prázdný segmeny**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="c20d8-117">V podokně **Nový segment** zvolte typ segmentu a zadejte **Název**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="c20d8-118">Volitelně zadejte zobrazované jméno a popis, který pomáhá identifikovat segment.</span><span class="sxs-lookup"><span data-stu-id="c20d8-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="c20d8-119">Vyberte **Další**, chcete-li se dostat na stránku **Tvůrce segmentu**, kde definujete skupinu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="c20d8-120">Skupina je sada zákazníků.</span><span class="sxs-lookup"><span data-stu-id="c20d8-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="c20d8-121">Zvolte entitu, která obsahuje atribut, který chcete zahrnout do segmentace.</span><span class="sxs-lookup"><span data-stu-id="c20d8-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="c20d8-122">Vyberte atribut, podle kterého chcete segmentovat.</span><span class="sxs-lookup"><span data-stu-id="c20d8-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="c20d8-123">Tento atribut může mít jeden ze čtyř typů hodnot: číselný, řetězec, datum nebo logický.</span><span class="sxs-lookup"><span data-stu-id="c20d8-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="c20d8-124">Zvolte operátor a hodnotu vybraného atributu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c20d8-125">![Vlastní filtr skupin](media/customer-group-numbers.png "Filtr skupin zákazníků")</span><span class="sxs-lookup"><span data-stu-id="c20d8-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="c20d8-126">Počet</span><span class="sxs-lookup"><span data-stu-id="c20d8-126">Number</span></span> |<span data-ttu-id="c20d8-127">definice</span><span class="sxs-lookup"><span data-stu-id="c20d8-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="c20d8-128">1</span><span class="sxs-lookup"><span data-stu-id="c20d8-128">1</span></span>     |<span data-ttu-id="c20d8-129">Entity</span><span class="sxs-lookup"><span data-stu-id="c20d8-129">Entity</span></span>          |
   |<span data-ttu-id="c20d8-130">2</span><span class="sxs-lookup"><span data-stu-id="c20d8-130">2</span></span>     |<span data-ttu-id="c20d8-131">Atribut</span><span class="sxs-lookup"><span data-stu-id="c20d8-131">Attribute</span></span>          |
   |<span data-ttu-id="c20d8-132">3</span><span class="sxs-lookup"><span data-stu-id="c20d8-132">3</span></span>    |<span data-ttu-id="c20d8-133">Operátor</span><span class="sxs-lookup"><span data-stu-id="c20d8-133">Operator</span></span>         |
   |<span data-ttu-id="c20d8-134">4</span><span class="sxs-lookup"><span data-stu-id="c20d8-134">4</span></span>    |<span data-ttu-id="c20d8-135">Hodnota</span><span class="sxs-lookup"><span data-stu-id="c20d8-135">Value</span></span>         |

8. <span data-ttu-id="c20d8-136">Pokud je entita propojena se sjednocenou entitou zákazníka prostřednictvím [Vztahů](relationships.md), musíte definovat cestu vztahu k vytvoření platného segmentu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="c20d8-137">Přidávejte entity z cesty vztahu, dokud nevyberete entitu **Zákazník: CustomerInsights** z rozevíracího seznamu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="c20d8-138">Pak zvolte **Všechny záznamy** pro každou podmínku.</span><span class="sxs-lookup"><span data-stu-id="c20d8-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c20d8-139">![Cesta vztahů při vytváření segmentů](media/segments-multiple-relationships.png "Cesta vztahů při vytváření segmentů")</span><span class="sxs-lookup"><span data-stu-id="c20d8-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="c20d8-140">Výběrem možnosti **Uložit** uložte segment.</span><span class="sxs-lookup"><span data-stu-id="c20d8-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="c20d8-141">Pokud budou všechny požadavky ověřeny, bude váš segment uložen a zpracován.</span><span class="sxs-lookup"><span data-stu-id="c20d8-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="c20d8-142">V opačném případě bude uložen jako koncept.</span><span class="sxs-lookup"><span data-stu-id="c20d8-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="c20d8-143">Volbou **Zpět na segmenty** přejdete zpět na stránku **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="c20d8-144">Správa existujících segmentů</span><span class="sxs-lookup"><span data-stu-id="c20d8-144">Manage existing segments</span></span>

<span data-ttu-id="c20d8-145">Na stránce **Segmenty** můžete zobrazit všechny uložené segmenty a spravovat je.</span><span class="sxs-lookup"><span data-stu-id="c20d8-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="c20d8-146">Každý segment je reprezentován řádkem, která obsahuje další informace o segmentu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="c20d8-147">Segmenty ve sloupci můžete třídit výběrem záhlaví sloupce.</span><span class="sxs-lookup"><span data-stu-id="c20d8-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="c20d8-148">Použijte pole **Vyhledávání** v pravém horním rohu a filtrujte segmenty.</span><span class="sxs-lookup"><span data-stu-id="c20d8-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c20d8-149">![Možnosti správy existujícího segmentu](media/segments-selected-segment.png "Možnosti správy existujícího segmentu")</span><span class="sxs-lookup"><span data-stu-id="c20d8-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="c20d8-150">Když vyberete segment, jsou k dispozici následující akce:</span><span class="sxs-lookup"><span data-stu-id="c20d8-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="c20d8-151">**Zobrazit** podrobnosti o segmentu, včetně trendu počtu členů, náhledu členů segmentu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="c20d8-152">**Upravit** segment změnit jeho vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="c20d8-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="c20d8-153">**Obnovit** segment a zahrnout nejnovější data.</span><span class="sxs-lookup"><span data-stu-id="c20d8-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="c20d8-154">**Aktivace** nebo **deaktivace** segmentu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="c20d8-155">Segmenty mají dva možné stavy – aktivní nebo neaktivní.</span><span class="sxs-lookup"><span data-stu-id="c20d8-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="c20d8-156">Tyto stavy jsou užitečné při úpravách segmentu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="c20d8-157">Pro neaktivní segmenty existuje jejich definice, ale zatím neobsahuje žádné zákazníky.</span><span class="sxs-lookup"><span data-stu-id="c20d8-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="c20d8-158">Když aktivujete segment, jeho stav se změní z „neaktivní“ na „aktivní“ a začne hledat zákazníky, kteří odpovídají definici segmentu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="c20d8-159">Pokud je konfigurována [plánovaná aktualizace](system.md#schedule-tab), neaktivní segmenty mají **Stav** uveden jako **Přeskočeno**, což označuje, že u nich neproběhl ani pokus o aktualizaci.</span><span class="sxs-lookup"><span data-stu-id="c20d8-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="c20d8-160">Když je neaktivní segment aktivován, aktualizuje se a bude součástí plánovaných aktualizací.</span><span class="sxs-lookup"><span data-stu-id="c20d8-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="c20d8-161">Případně můžete použít funkci **Plánovat později** v rozevíracím seznamu **Aktivovat/deaktivovat** pro určení budoucího data a času aktivace a deaktivace konkrétního segmentu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="c20d8-162">**Přejmenovat** segment.</span><span class="sxs-lookup"><span data-stu-id="c20d8-162">**Rename** the segment.</span></span>
- <span data-ttu-id="c20d8-163">**Stáhnout** seznam členů jako soubor .CSV.</span><span class="sxs-lookup"><span data-stu-id="c20d8-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="c20d8-164">Možnost **Přidat do** odešle seznam ID zákazníků v segmentu ke zpracování v jiné aplikaci.</span><span class="sxs-lookup"><span data-stu-id="c20d8-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="c20d8-165">**Odstranit** segment.</span><span class="sxs-lookup"><span data-stu-id="c20d8-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="c20d8-166">Aktualizovat segmenty</span><span class="sxs-lookup"><span data-stu-id="c20d8-166">Refresh segments</span></span>

<span data-ttu-id="c20d8-167">Můžete aktualizovat všechny segmenty najednou výběrem **Aktualizovat vše** na stránce **Segmenty** nebo můžete aktualizovat jeden nebo více segmentů, když je vyberete a z možností vyberete volbu **Aktualizovat**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="c20d8-168">Případně můžete nakonfigurovat opakovanou aktualizaci **Správce** > **Systém** > **Plán**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="c20d8-169">Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy.</span><span class="sxs-lookup"><span data-stu-id="c20d8-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c20d8-170">Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c20d8-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c20d8-171">Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy.</span><span class="sxs-lookup"><span data-stu-id="c20d8-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c20d8-172">Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.</span><span class="sxs-lookup"><span data-stu-id="c20d8-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="c20d8-173">Stahujte a exportujte segmenty</span><span class="sxs-lookup"><span data-stu-id="c20d8-173">Download and export segments</span></span>

<span data-ttu-id="c20d8-174">Můžete si stáhnout své segmenty do souboru CSV nebo je exportovat do Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c20d8-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="c20d8-175">Stáhněte segmenty do souboru CSV</span><span class="sxs-lookup"><span data-stu-id="c20d8-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="c20d8-176">V přehledech cílové skupiny přejděte na stránku **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c20d8-177">Vyberte tři tečky v dlaždici konkrétního segmentu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c20d8-178">Vyberte **Stáhnout jako CSV** z rozevíracího seznamu akcí.</span><span class="sxs-lookup"><span data-stu-id="c20d8-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="c20d8-179">Exportovat segmenty do aplikace Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="c20d8-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="c20d8-180">Před exportem segmentů do Dynamics 365 Sales musí administrátor [vytvořit cíl exportu](export-destinations.md) pro Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c20d8-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="c20d8-181">V přehledech cílové skupiny přejděte na stránku **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c20d8-182">Vyberte tři tečky v dlaždici konkrétního segmentu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c20d8-183">Vyberte **Přidat do** z rozevíracího seznamu akcí a vyberte cílové místo exportu, do kterého chcete data odeslat.</span><span class="sxs-lookup"><span data-stu-id="c20d8-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="c20d8-184">Režim konceptu pro segmenty</span><span class="sxs-lookup"><span data-stu-id="c20d8-184">Draft mode for segments</span></span>

<span data-ttu-id="c20d8-185">Pokud nejsou splněny všechny požadavky na zpracování segmentu, můžete segment uložit jako koncept a získat k němu přístup ze stránky **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="c20d8-186">Bude uložen jako neaktivní segment a nelze jej aktivovat, dokud nebude platný.</span><span class="sxs-lookup"><span data-stu-id="c20d8-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="c20d8-187">Přidání dalších podmínek do skupiny</span><span class="sxs-lookup"><span data-stu-id="c20d8-187">Add more conditions to a group</span></span>

<span data-ttu-id="c20d8-188">Chcete-li do skupiny přidat další podmínky, můžete použít dva logické operátory:</span><span class="sxs-lookup"><span data-stu-id="c20d8-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="c20d8-189">Operátor **AND**: Obě podmínky musí být splněny v rámci procesu segmentace.</span><span class="sxs-lookup"><span data-stu-id="c20d8-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="c20d8-190">Tato možnost je nejužitečnější při definování podmínek mezi různými entitami.</span><span class="sxs-lookup"><span data-stu-id="c20d8-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="c20d8-191">Operátor **OR**: Buď je třeba splnit jednu z podmínek v rámci procesu segmentace.</span><span class="sxs-lookup"><span data-stu-id="c20d8-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="c20d8-192">Tato možnost je nejužitečnější při definování více podmínek pro stejnou entitu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c20d8-193">![Operátor OR, u kterého je třeba splnit obě podmínky](media/segmentation-either-condition.png "Operátor OR, u kterého je třeba splnit obě podmínky")</span><span class="sxs-lookup"><span data-stu-id="c20d8-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="c20d8-194">V současné době je možné vnořit operátor **OR** do operátoru **AND**, ale ne naopak.</span><span class="sxs-lookup"><span data-stu-id="c20d8-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="c20d8-195">Zkombinování více skupin</span><span class="sxs-lookup"><span data-stu-id="c20d8-195">Combine multiple groups</span></span>

<span data-ttu-id="c20d8-196">Každá skupina produkuje specifický soubor zákazníků.</span><span class="sxs-lookup"><span data-stu-id="c20d8-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="c20d8-197">Tyto skupiny můžete zkombinovat a zahrnout zákazníky potřebné pro váš obchodní případ.</span><span class="sxs-lookup"><span data-stu-id="c20d8-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="c20d8-198">V přehledech cílové skupiny přejděte na stránku **Segmenty** a vyberte segment.</span><span class="sxs-lookup"><span data-stu-id="c20d8-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="c20d8-199">Vyberte **Přidat skupinu**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c20d8-200">![Skupina zákazníků přidat skupinu](media/customer-group-add-group.png "Skupina zákazníků přidat skupinu")</span><span class="sxs-lookup"><span data-stu-id="c20d8-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="c20d8-201">Vyberte jeden z následujících operátorů sady: **Sjednocení**, **Průnik** nebo **Kromě**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c20d8-202">![Skupina zákazníků přidat sjednocení](media/customer-group-union.png "Skupina zákazníků přidat sjednocení")</span><span class="sxs-lookup"><span data-stu-id="c20d8-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="c20d8-203">Vyberte operátor sady, abyste mohli definovat novou skupinu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="c20d8-204">Uložením různých skupin určíte, jaká data se uchovají:</span><span class="sxs-lookup"><span data-stu-id="c20d8-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="c20d8-205">**Sjednocení** sjednotí dvě skupiny.</span><span class="sxs-lookup"><span data-stu-id="c20d8-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="c20d8-206">**Průnik** překrývá dvě skupiny.</span><span class="sxs-lookup"><span data-stu-id="c20d8-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="c20d8-207">Pouze data, která *jsou společná* pro obě skupiny, zůstanou zachována ve sjednocené skupině.</span><span class="sxs-lookup"><span data-stu-id="c20d8-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="c20d8-208">**Výjimka** kombinuje dvě skupiny.</span><span class="sxs-lookup"><span data-stu-id="c20d8-208">**Except** combines the two groups.</span></span> <span data-ttu-id="c20d8-209">Pouze data ve skupině A, která *nejsou společná* s daty ve skupině B, zůstanou zachována.</span><span class="sxs-lookup"><span data-stu-id="c20d8-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="c20d8-210">Zobrazit historii zpracování a členy segmentu</span><span class="sxs-lookup"><span data-stu-id="c20d8-210">View processing history and segment members</span></span>

<span data-ttu-id="c20d8-211">Konsolidovaná data o segmentu můžete zobrazit kontrolou jeho podrobností.</span><span class="sxs-lookup"><span data-stu-id="c20d8-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="c20d8-212">Na stránce **Segmenty** vyberte segment, který chcete zkontrolovat.</span><span class="sxs-lookup"><span data-stu-id="c20d8-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="c20d8-213">Horní část stránky obsahuje graf trendů, který vizualizuje změny v počtu členů.</span><span class="sxs-lookup"><span data-stu-id="c20d8-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="c20d8-214">Najeďte na datové body, abyste viděli počet členů k určitému datu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="c20d8-215">Můžete aktualizovat časový rámec vizualizace.</span><span class="sxs-lookup"><span data-stu-id="c20d8-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c20d8-216">![Časový rozsah segmentu](media/segment-time-range.png "Časový rozsah segmentu")</span><span class="sxs-lookup"><span data-stu-id="c20d8-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="c20d8-217">Spodní část obsahuje seznam členů segmentu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="c20d8-218">Pole, která se zobrazí v tomto seznamu, jsou založena na atributech entit segmentu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="c20d8-219">Seznam je náhledem odpovídajících členů segmentu a zobrazuje prvních 100 záznamů segmentu, takže jej můžete rychle vyhodnotit a v případě potřeby zkontrolovat jeho definice.</span><span class="sxs-lookup"><span data-stu-id="c20d8-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="c20d8-220">Chcete-li zobrazit všechny odpovídající záznamy, je třeba [segment exportovat](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c20d8-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="c20d8-221">Rychlé segmenty</span><span class="sxs-lookup"><span data-stu-id="c20d8-221">Quick segments</span></span>

<span data-ttu-id="c20d8-222">Kromě nástroje pro vytváření segmentů existuje další cesta k vytváření segmentů.</span><span class="sxs-lookup"><span data-stu-id="c20d8-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="c20d8-223">Rychlé segmenty vám umožňují rychle a snadno vytvářet jednoduché segmenty s jediným operátorem.</span><span class="sxs-lookup"><span data-stu-id="c20d8-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="c20d8-224">Na stránce **Segmenty** vyberte **Nový** > **Rychle vytvořte z**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="c20d8-225">Vyberte možnost **Profily**, chcete-li vytvořit segment založený na sjednocené entitě Zákazník.</span><span class="sxs-lookup"><span data-stu-id="c20d8-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="c20d8-226">Vyberte možnost **Opatření**, chcete-li vytvořit segment kolem každého typu atributu zákazníka, které jste dříve vytvořili na stránce **Opatření**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="c20d8-227">Vyberte možnost **Analytické nástroje**, chcete-li sestavit segment kolem jedné z výstupních entit, které jste vygenerovali pomocí funkcí **Predikce** nebo **Vlastní modely**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="c20d8-228">V dialogovém okně **Nový rychlý segment** vyberte atribut z rozbalovací nabídky **Pole**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="c20d8-229">Systém vám poskytne další přehledy, které vám pomohou vytvořit lepší segmenty vašich zákazníků.</span><span class="sxs-lookup"><span data-stu-id="c20d8-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="c20d8-230">Pro kategorická pole zobrazíme 10 nejlepších zákazníků.</span><span class="sxs-lookup"><span data-stu-id="c20d8-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="c20d8-231">Vyberte **Hodnotu** a zvolte **Hodnotit**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="c20d8-232">U číselného atributu systém zobrazí, jaká hodnota atributu spadá pod percentil každého zákazníka.</span><span class="sxs-lookup"><span data-stu-id="c20d8-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="c20d8-233">Zvolte **Operátor** a **Hodnotu** a pak vyberte **Zkontrolovat**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="c20d8-234">Systém vám poskytne **Odhadovanou velikost segmentu**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="c20d8-235">Můžete zvolit, zda chcete vygenerovat segment, který jste definovali, nebo jej nejprve znovu navštívit, abyste získali jinou velikost segmentu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c20d8-236">![Název a odhad pro rychlý segment](media/quick-segment-name.png "Název a odhad pro rychlý segment")</span><span class="sxs-lookup"><span data-stu-id="c20d8-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="c20d8-237">Zadejte **Název** svého sgmentu.</span><span class="sxs-lookup"><span data-stu-id="c20d8-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="c20d8-238">Volitelně zadejte **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="c20d8-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="c20d8-239">Výběrem možnosti **Uložit** vytvořte segment.</span><span class="sxs-lookup"><span data-stu-id="c20d8-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="c20d8-240">Po dokončení zpracování segmentu jej můžete zobrazit jako jakýkoli jiný segment, který jste vytvořili.</span><span class="sxs-lookup"><span data-stu-id="c20d8-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="c20d8-241">Pro následující scénáře doporučujeme používat tvůrce segmentů spíše než doporučené funkce segmentů:</span><span class="sxs-lookup"><span data-stu-id="c20d8-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="c20d8-242">Vytváření segmentů s filtry v kategorických polích, kde se operátor liší od operátoru **Je**</span><span class="sxs-lookup"><span data-stu-id="c20d8-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="c20d8-243">Vytváření segmentů s filtry na číselných polích, kde je operátor jiný, než **Mezi**, **Větší než** a **Méně než**</span><span class="sxs-lookup"><span data-stu-id="c20d8-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="c20d8-244">Vytváření segmentů s filtry v polích typu data</span><span class="sxs-lookup"><span data-stu-id="c20d8-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="c20d8-245">Další kroky</span><span class="sxs-lookup"><span data-stu-id="c20d8-245">Next steps</span></span>

<span data-ttu-id="c20d8-246">[Exportujtesegment](export-destinations.md) a prozkoumejte [Kartu zákazníka](customer-card-add-in.md) a [Konektory](export-power-bi.md), abyste získali přehled o úrovni zákazníka.</span><span class="sxs-lookup"><span data-stu-id="c20d8-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
