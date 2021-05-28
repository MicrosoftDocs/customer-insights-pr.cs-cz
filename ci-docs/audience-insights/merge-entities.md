---
title: Sloučení entit ve sjednocení dat
description: Sloučením entit můžete vytvořit sjednocené profily zákazníků.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085568"
---
# <a name="merge-entities"></a><span data-ttu-id="2c769-103">Správa entit</span><span class="sxs-lookup"><span data-stu-id="2c769-103">Merge entities</span></span>

<span data-ttu-id="2c769-104">Fáze sloučení je poslední fází v procesu sjednocení dat.</span><span class="sxs-lookup"><span data-stu-id="2c769-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="2c769-105">Jeho účelem je slazování protichůdných údajů.</span><span class="sxs-lookup"><span data-stu-id="2c769-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="2c769-106">Příklady konfliktních dat mohou zahrnovat jméno zákazníka, které se nachází ve dvou vašich datových sadách, ale v každé z nich se zobrazuje trochu jinak ("Grant Marshall" versus "Grant Marshal") nebo telefonní číslo, které se liší ve formátu (617-803-091X versus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="2c769-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="2c769-107">Sloučení těchto konfliktních datových bodů se provádí na základě atribut - atribut.</span><span class="sxs-lookup"><span data-stu-id="2c769-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Stránka sloučení v procesu sjednocení dat zobrazující tabulku se sloučenými poli, která definují sjednocený profil zákazníka.":::

<span data-ttu-id="2c769-109">Po dokončení [fáze párování](match-entities.md) můžete zahájit fázi sloučení výběrem dlaždice **Sloučit** na stránce **Sjednotit**.</span><span class="sxs-lookup"><span data-stu-id="2c769-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="2c769-110">Zkkontrolovat systémová doporučení</span><span class="sxs-lookup"><span data-stu-id="2c769-110">Review system recommendations</span></span>

<span data-ttu-id="2c769-111">V části **Data** > **Sjednotit** > **Sloučit** vybíráte a vylučujete atributy ke sloučení v rámci entity sjednoceného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="2c769-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="2c769-112">Sjednocený profil zákazníka je výsledkem procesu sjednocení dat.</span><span class="sxs-lookup"><span data-stu-id="2c769-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="2c769-113">Některé atributy jsou systémem automaticky sloučeny.</span><span class="sxs-lookup"><span data-stu-id="2c769-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="2c769-114">Chcete-li zobrazit atributy, které jsou zahrnuty v jednom z vašich automaticky sloučených atributů, vyberte tento sloučený atribut na kartě **Zákaznická pole** tabulky.</span><span class="sxs-lookup"><span data-stu-id="2c769-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="2c769-115">Atributy, které tvoří tento sloučený atribut, se zobrazí ve dvou nových řádcích pod sloučeným atributem.</span><span class="sxs-lookup"><span data-stu-id="2c769-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="2c769-116">Oddělení, přejmenování, vyloučení a úprava sloučených polí</span><span class="sxs-lookup"><span data-stu-id="2c769-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="2c769-117">Můžete změnit způsob, jakým systém zpracovává sloučené atributy, aby vygeneroval sjednocený profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="2c769-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="2c769-118">Vyberte **Zobrazit více** a zvolte, co chcete změnit.</span><span class="sxs-lookup"><span data-stu-id="2c769-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Možnosti v rozevírací nabídce Zobrazit více pro správu sloučených atributů.":::

<span data-ttu-id="2c769-120">Další informace naleznete v následujících částech.</span><span class="sxs-lookup"><span data-stu-id="2c769-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="2c769-121">Oddělení sloučených polí</span><span class="sxs-lookup"><span data-stu-id="2c769-121">Separate merged fields</span></span>

<span data-ttu-id="2c769-122">Chcete-li oddělit sloučená pole, vyhledejte atribut v tabulce.</span><span class="sxs-lookup"><span data-stu-id="2c769-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="2c769-123">Oddělená pole se zobrazují jako jednotlivé datové body ve sjednoceném profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="2c769-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="2c769-124">Vyberte sloučené pole.</span><span class="sxs-lookup"><span data-stu-id="2c769-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="2c769-125">Vyberte **Zobrazit více** a zvolte **Oddělená pole**.</span><span class="sxs-lookup"><span data-stu-id="2c769-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="2c769-126">Oddělení potvrďte.</span><span class="sxs-lookup"><span data-stu-id="2c769-126">Confirm the separation.</span></span>

1. <span data-ttu-id="2c769-127">Vyberte **Uložit** a **Spustit** ke zpracování změn.</span><span class="sxs-lookup"><span data-stu-id="2c769-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="2c769-128">Přejmenování sloučených polí</span><span class="sxs-lookup"><span data-stu-id="2c769-128">Rename merged fields</span></span>

<span data-ttu-id="2c769-129">Změňte zobrazované jméno sloučených atributů.</span><span class="sxs-lookup"><span data-stu-id="2c769-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="2c769-130">Název výstupní entity nelze změnit.</span><span class="sxs-lookup"><span data-stu-id="2c769-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="2c769-131">Vyberte sloučené pole.</span><span class="sxs-lookup"><span data-stu-id="2c769-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="2c769-132">Vyberte **Zobrazit více** a zvolte **Přejmenovat**.</span><span class="sxs-lookup"><span data-stu-id="2c769-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="2c769-133">Potvrďte změněné zobrazované jméno.</span><span class="sxs-lookup"><span data-stu-id="2c769-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="2c769-134">Vyberte **Uložit** a **Spustit** ke zpracování změn.</span><span class="sxs-lookup"><span data-stu-id="2c769-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="2c769-135">Vyloučit sloučená pole</span><span class="sxs-lookup"><span data-stu-id="2c769-135">Exclude merged fields</span></span>

<span data-ttu-id="2c769-136">Vylučte atribut ze sjednoceného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="2c769-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="2c769-137">Pokud se pole používá v jiných procesech, například v segmentu, před vyloučením z profilu zákazníka jej z těchto procesů odstraňte.</span><span class="sxs-lookup"><span data-stu-id="2c769-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="2c769-138">Vyberte sloučené pole.</span><span class="sxs-lookup"><span data-stu-id="2c769-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="2c769-139">Vyberte **Zobrazit více** a zvolte **Vyloučit**.</span><span class="sxs-lookup"><span data-stu-id="2c769-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="2c769-140">Potvrďte vyloučení.</span><span class="sxs-lookup"><span data-stu-id="2c769-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="2c769-141">Vyberte **Uložit** a **Spustit** ke zpracování změn.</span><span class="sxs-lookup"><span data-stu-id="2c769-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="2c769-142">Na stránce **Sloučit** vyberte **Vyloučit pole** pro zobrazení seznamu všech vyloučených polí.</span><span class="sxs-lookup"><span data-stu-id="2c769-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="2c769-143">V tomto podokně je možné přidat vyloučená pole zpět.</span><span class="sxs-lookup"><span data-stu-id="2c769-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="2c769-144">Ruční zkombinování polí</span><span class="sxs-lookup"><span data-stu-id="2c769-144">Manually combine fields</span></span>

<span data-ttu-id="2c769-145">Ručně zadejte sloučený atribut.</span><span class="sxs-lookup"><span data-stu-id="2c769-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="2c769-146">Na stránce **Sloučit** vyberte **Zkombinovat pole**.</span><span class="sxs-lookup"><span data-stu-id="2c769-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="2c769-147">Zadejte **Název** a **Název výstupního pole**.</span><span class="sxs-lookup"><span data-stu-id="2c769-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="2c769-148">Vyberte pole k přidání.</span><span class="sxs-lookup"><span data-stu-id="2c769-148">Choose a field to add.</span></span> <span data-ttu-id="2c769-149">Vyberte **Přidat pole** ke zkombinování více polí.</span><span class="sxs-lookup"><span data-stu-id="2c769-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="2c769-150">Potvrďte vyloučení.</span><span class="sxs-lookup"><span data-stu-id="2c769-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="2c769-151">Vyberte **Uložit** a **Spustit** ke zpracování změn.</span><span class="sxs-lookup"><span data-stu-id="2c769-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="2c769-152">Změna pořadí polí</span><span class="sxs-lookup"><span data-stu-id="2c769-152">Change the order of fields</span></span>

<span data-ttu-id="2c769-153">Některé entity obsahují více podrobností než jiné.</span><span class="sxs-lookup"><span data-stu-id="2c769-153">Some entities contain more details than others.</span></span> <span data-ttu-id="2c769-154">Pokud entita obsahuje nejnovější data o poli, můžete ji při slučování hodnot upřednostnit před jinými entitami.</span><span class="sxs-lookup"><span data-stu-id="2c769-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="2c769-155">Vyberte sloučené pole.</span><span class="sxs-lookup"><span data-stu-id="2c769-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="2c769-156">Vyberte **Zobrazit více** a zvolte **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="2c769-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="2c769-157">V podokně **Zkombinovat pole** vyberte **Přesunout nahoru / dolů** k nastavení pořadí nebo je přetáhněte na požadované místo.</span><span class="sxs-lookup"><span data-stu-id="2c769-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="2c769-158">Změnu potvrďte.</span><span class="sxs-lookup"><span data-stu-id="2c769-158">Confirm the change.</span></span>

1. <span data-ttu-id="2c769-159">Vyberte **Uložit** a **Spustit** ke zpracování změn.</span><span class="sxs-lookup"><span data-stu-id="2c769-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="2c769-160">Spuštění sloučení</span><span class="sxs-lookup"><span data-stu-id="2c769-160">Run your merge</span></span>

<span data-ttu-id="2c769-161">Ať už ručně sloučíte atributy nebo necháte systém je sloučit, můžete vždy spustit sloučení.</span><span class="sxs-lookup"><span data-stu-id="2c769-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="2c769-162">Vyberte **Spustit** na stránce **Sloučení**, chcete-li zahájit proces.</span><span class="sxs-lookup"><span data-stu-id="2c769-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2c769-163">![Ukládání a spuštění sloučení dat](media/configure-data-merge-save-run.png "Ukládání a spuštění sloučení dat")</span><span class="sxs-lookup"><span data-stu-id="2c769-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="2c769-164">Zvolte **Spustit pouze sloučení**, pokud chcete vidět pouze výstup odražený v entitě sjednoceného zákazníka.</span><span class="sxs-lookup"><span data-stu-id="2c769-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="2c769-165">Následné procesy budou aktualizovány jako [definované v plánu aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2c769-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="2c769-166">Zvolte **Spustit procesy sloučení a následné procesy** k aktualizaci systému změnami.</span><span class="sxs-lookup"><span data-stu-id="2c769-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="2c769-167">Všechny procesy, včetně obohacení, segmentů a opatření, se znovu spustí automaticky.</span><span class="sxs-lookup"><span data-stu-id="2c769-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="2c769-168">Po dokončení všech následných procesů budou profily zákazníků odrážet všechny provedené změny.</span><span class="sxs-lookup"><span data-stu-id="2c769-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="2c769-169">Chcete-li provést další změny a znovu spustit krok, můžete zrušit probíhající sloučení.</span><span class="sxs-lookup"><span data-stu-id="2c769-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="2c769-170">Vyberte text **Aktualizace** a vyberte **Zrušit úlohu** v postranním podokně, které se objeví.</span><span class="sxs-lookup"><span data-stu-id="2c769-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="2c769-171">Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy.</span><span class="sxs-lookup"><span data-stu-id="2c769-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2c769-172">Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2c769-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2c769-173">Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy.</span><span class="sxs-lookup"><span data-stu-id="2c769-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2c769-174">Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.</span><span class="sxs-lookup"><span data-stu-id="2c769-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="2c769-175">Další krok</span><span class="sxs-lookup"><span data-stu-id="2c769-175">Next Step</span></span>

<span data-ttu-id="2c769-176">Konfigurujte [Aktivity](activities.md), [obohacení](enrichment-hub.md) nebo [Vztahy](relationships.md) pro další přehledy o zákaznících.</span><span class="sxs-lookup"><span data-stu-id="2c769-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="2c769-177">Pokud jste již nakonfigurovali aktivity, obohacení nebo segmenty, budou automaticky zpracovány, aby používaly nejnovější údaje o zákaznících.</span><span class="sxs-lookup"><span data-stu-id="2c769-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
