---
title: Sloučení entit ve sjednocení dat
description: Sloučením entit můžete vytvořit sjednocené profily zákazníků.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268494"
---
# <a name="merge-entities"></a><span data-ttu-id="6c0ee-103">Správa entit</span><span class="sxs-lookup"><span data-stu-id="6c0ee-103">Merge entities</span></span>

<span data-ttu-id="6c0ee-104">Fáze sloučení je poslední fází v procesu sjednocení dat.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="6c0ee-105">Jeho účelem je slazování protichůdných údajů.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="6c0ee-106">Příklady konfliktních dat mohou zahrnovat jméno zákazníka, které se nachází ve dvou vašich datových sadách, ale v každé z nich se zobrazuje trochu jinak ("Grant Marshall" versus "Grant Marshal") nebo telefonní číslo, které se liší ve formátu (617-803-091X versus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="6c0ee-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="6c0ee-107">Sloučení těchto konfliktních datových bodů se provádí na základě atribut - atribut.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="6c0ee-108">Po dokončení [fáze párování](match-entities.md) můžete zahájit fázi sloučení výběrem dlaždice **Sloučit** na stránce **Sjednotit**.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="6c0ee-109">Zkkontrolovat systémová doporučení</span><span class="sxs-lookup"><span data-stu-id="6c0ee-109">Review system recommendations</span></span>

<span data-ttu-id="6c0ee-110">Na stránce **Sloučení** můžete zvolit a vyloučit atributy, které mají být sloučeny v rámci entity jednotného profilu zákazníka (výsledek procesu konfigurace).</span><span class="sxs-lookup"><span data-stu-id="6c0ee-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="6c0ee-111">Některé atributy jsou systémem automaticky sloučeny.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="6c0ee-112">Prohlédnout sloučené atributy</span><span class="sxs-lookup"><span data-stu-id="6c0ee-112">View merged attributes</span></span>

<span data-ttu-id="6c0ee-113">Chcete-li zobrazit atributy, které jsou zahrnuty v jednom z automaticky sloučených atributů, vyberte tento sloučený atribut.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="6c0ee-114">Dva atributy, které tvoří tento sloučený atribut, se zobrazí ve dvou nových řádcích pod sloučeným atributem.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6c0ee-115">![Vybrat sloučený atribut](media/configure-data-merge-profile-attributes.png "Vybrat sloučený atribut")</span><span class="sxs-lookup"><span data-stu-id="6c0ee-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="6c0ee-116">Oddělit sloučené atributy</span><span class="sxs-lookup"><span data-stu-id="6c0ee-116">Separate merged attributes</span></span>

<span data-ttu-id="6c0ee-117">Chcete-li oddělit nebo zrušit sloučení některých automaticky sloučených atributů, vyhledejte atribut v tabulce **Atributy profilu**.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="6c0ee-118">Vyberte tlačítko se třemi tečkami (...).</span><span class="sxs-lookup"><span data-stu-id="6c0ee-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="6c0ee-119">V rozevíracím seznamu vyberte **Oddělit pole**.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="6c0ee-120">Odebrat sloučené atributy</span><span class="sxs-lookup"><span data-stu-id="6c0ee-120">Remove merged attributes</span></span>

<span data-ttu-id="6c0ee-121">Chcete-li vyloučit atribut z entity profilu konečného zákazníka, najděte ho v tabulce **Atributy profilu**.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="6c0ee-122">Vyberte tlačítko se třemi tečkami (...).</span><span class="sxs-lookup"><span data-stu-id="6c0ee-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="6c0ee-123">V rozevíracím seznamu vyberte **Neslučovat**.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="6c0ee-124">Atribut je přesunut do části **Odebrat ze záznamu zákazníka**.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="6c0ee-125">Ruční přidání sloučeného atributu</span><span class="sxs-lookup"><span data-stu-id="6c0ee-125">Manually add a merged attribute</span></span>

<span data-ttu-id="6c0ee-126">Chcete-li přidat sloučený atribut, přejděte na stránku **Sloučení**.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="6c0ee-127">Vyberte **Přidat sloučený atribut**.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="6c0ee-128">Zadejte **Název**, který chcete později identifikovat na stránce **Sloučení**.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="6c0ee-129">Volitelně zadejte **Zobrazované jméno**, které se zobrazí ve sjednocené entitě Profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="6c0ee-130">Nakonfigurujte **Vybrat duplicitní atributy**, abyste vybrali atributy, které chcete sloučit ze spárovaných entit.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="6c0ee-131">Můžete také vyhledat atributy.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="6c0ee-132">Nastavte **Hodnotu podle důležitosti**, abyste upřednostnili jeden atribut nad ostatními.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="6c0ee-133">Pokud například entita *WebAccountCSV* obsahuje nejpřesnější údaje o atributu *Celá jména*, můžete tuto entitu upřednostnit před *ContactCSV* výběrem možnosti *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="6c0ee-134">V důsledku se *webAccountCSV* přesune na první prioritu, zatímco *ContactCSV* se přesune na druhou prioritu při tahání hodnoty pro atribut *Celé jméno*.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="6c0ee-135">Spuštění sloučení</span><span class="sxs-lookup"><span data-stu-id="6c0ee-135">Run your merge</span></span>

<span data-ttu-id="6c0ee-136">Ať už ručně sloučíte atributy nebo necháte systém je sloučit, můžete vždy spustit sloučení.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="6c0ee-137">Vyberte **Spustit** na stránce **Sloučení**, chcete-li zahájit proces.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6c0ee-138">![Ukládání a spuštění sloučení dat](media/configure-data-merge-save-run.png "Ukládání a spuštění sloučení dat")</span><span class="sxs-lookup"><span data-stu-id="6c0ee-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="6c0ee-139">Chcete-li provést další změny a znovu spustit krok, můžete zrušit probíhající slučování.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="6c0ee-140">Vyberte text **Aktualizace** a vyberte **Zrušit úlohu** v postranním podokně, které se objeví.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="6c0ee-141">Po **Aktualizaci** se text změní na **Úspěšný**, sloučení se dokončilo a vyřešilo rozpory ve vašich údajích podle zásad, které jste definovali.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="6c0ee-142">Sloučené a nesloučené atributy jsou zahrnuty v entitě sjednoceného profilu.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="6c0ee-143">Vyloučené atributy nejsou zahrnuty v entitě sjednoceného profilu.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="6c0ee-144">Pokud to nebylo poprvé, kdy jste úspěšně provedli sloučení, všechny následné procesy, včetně obohacení, segmentace a opatření, se automaticky znovu spustí.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="6c0ee-145">Po opětovném spuštění všech navazujících procesů budou profily zákazníků odrážet všechny provedené změny.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="6c0ee-146">Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="6c0ee-147">Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="6c0ee-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="6c0ee-148">Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="6c0ee-149">Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="6c0ee-150">Další krok</span><span class="sxs-lookup"><span data-stu-id="6c0ee-150">Next Step</span></span>

<span data-ttu-id="6c0ee-151">Konfigurujte [Aktivity](activities.md), [obohacení](enrichment-microsoft-graph.md) nebo [Vztahy](relationships.md) pro další přehledy o zákaznících.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="6c0ee-152">Pokud jste již nakonfigurovali aktivity, obohacení nebo Vztahy, nebo pokud jste definovali segmenty, budou automaticky zpracovány, aby se využily nejnovější údaje o zákaznících.</span><span class="sxs-lookup"><span data-stu-id="6c0ee-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]