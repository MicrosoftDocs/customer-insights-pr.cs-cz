---
title: Vytváření a úprava měr
description: Definujte opatření související se zákazníky pro analýzu a zohlednění výkonu určitých obchodních oblastí.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405394"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="f53e1-103">Definujte a spravujte opatření</span><span class="sxs-lookup"><span data-stu-id="f53e1-103">Define and manage measures</span></span>

<span data-ttu-id="f53e1-104">**Opatření** představují klíčové ukazatele výkonnosti, které odrážejí výkonnost a zdraví konkrétních obchodních oblastí.</span><span class="sxs-lookup"><span data-stu-id="f53e1-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="f53e1-105">Přehledy cílové skupiny poskytuje intuitivní prostředí pro vytváření různých typů měr pomocí nástroje pro vytváření dotazů, které nevyžaduje ruční kódování nebo ověřování měr.</span><span class="sxs-lookup"><span data-stu-id="f53e1-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="f53e1-106">Obchodní opatření můžete sledovat na **Domovské stránce**, zobrazit opatření pro konkrétní zákazníky na **Kartě zákazníka** a použít opatření k definování segmentů zákazníků na stránce **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="f53e1-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="f53e1-107">Vytvořit nové opatření</span><span class="sxs-lookup"><span data-stu-id="f53e1-107">Create a measure</span></span>

<span data-ttu-id="f53e1-108">Tato část vás provede vytvořením opatření od začátku.</span><span class="sxs-lookup"><span data-stu-id="f53e1-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="f53e1-109">Můžete vytvářet opatřen s daty z více zdrojů dat, které jsou propojeny prostřednictvím entity Zákazník.</span><span class="sxs-lookup"><span data-stu-id="f53e1-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="f53e1-110">Použijí se některé [servisní limity](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="f53e1-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="f53e1-111">V přehledech cílové skupiny přejděte na **Míry**.</span><span class="sxs-lookup"><span data-stu-id="f53e1-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="f53e1-112">Vyberte **Nové opatření**.</span><span class="sxs-lookup"><span data-stu-id="f53e1-112">Select **New measure**.</span></span>

3. <span data-ttu-id="f53e1-113">Zvolte **Typ** opatření:</span><span class="sxs-lookup"><span data-stu-id="f53e1-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="f53e1-114">**Atribut záazníka**: Jedno pole na zákazníka, které odráží skóre, hodnotu nebo stav pro zákazníka.</span><span class="sxs-lookup"><span data-stu-id="f53e1-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="f53e1-115">Atributy zákazníka jsou vytvořeny jako atributy v nové systémové entitě nazývané **Opatření zákazníka**.</span><span class="sxs-lookup"><span data-stu-id="f53e1-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="f53e1-116">**Opatření zákazníka**: Přehledy o chování zákazníků s rozdělením podle vybraných dimenzí.</span><span class="sxs-lookup"><span data-stu-id="f53e1-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="f53e1-117">Pro každé opatření je generována nová entita, potenciálně s více záznamy na zákazníka.</span><span class="sxs-lookup"><span data-stu-id="f53e1-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="f53e1-118">**Obchodní opatření**: Sleduje výkonnost a zdraví podniku.</span><span class="sxs-lookup"><span data-stu-id="f53e1-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="f53e1-119">Obchodní opatření mohou mít dva různé výstupy: číselný výstup, který se zobrazí na **Domovské stránce** nebo novou entitu, kterou najdete na stránce **Entity**.</span><span class="sxs-lookup"><span data-stu-id="f53e1-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="f53e1-120">Zadejte **Název** a volitelný **Zobrazovaný název** a pak vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="f53e1-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="f53e1-121">V sekci **Entity** z rozevíracího seznamu vyberte první entitu.</span><span class="sxs-lookup"><span data-stu-id="f53e1-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="f53e1-122">V tomto okamžiku byste se měli rozhodnout, zda jsou v rámci definice míry potřeba další entity.</span><span class="sxs-lookup"><span data-stu-id="f53e1-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f53e1-123">![Definice opatření](media/measure-definition.png "Definice míry")</span><span class="sxs-lookup"><span data-stu-id="f53e1-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="f53e1-124">Chcete-li přidat další entity, vyberte **Přidat entitu** a vyberte entity, které chcete pro opatření použít.</span><span class="sxs-lookup"><span data-stu-id="f53e1-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f53e1-125">Můžete vybrat entity, které mají vztah s počáteční entitou.</span><span class="sxs-lookup"><span data-stu-id="f53e1-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="f53e1-126">Další informace o definování vztahů najdete v tématu [Vztahy](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="f53e1-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="f53e1-127">Volitelně můžete nakonfigurovat proměnné.</span><span class="sxs-lookup"><span data-stu-id="f53e1-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="f53e1-128">V části **Proměnné** vyberte **Nová proměnná**.</span><span class="sxs-lookup"><span data-stu-id="f53e1-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="f53e1-129">Proměnné jsou výpočty, které jsou prováděny v každém z vybraných záznamů.</span><span class="sxs-lookup"><span data-stu-id="f53e1-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="f53e1-130">Například sčítání prodejních míst (POS) a online prodeje pro každý záznam zákazníka.</span><span class="sxs-lookup"><span data-stu-id="f53e1-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="f53e1-131">Zadejte **Název** proměnné.</span><span class="sxs-lookup"><span data-stu-id="f53e1-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="f53e1-132">V oblasti **Výraz** zvolte pole, se kterým chcete začít výpočet.</span><span class="sxs-lookup"><span data-stu-id="f53e1-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="f53e1-133">Zadejte výraz do oblasti **Výraz** a vyberte další pole, která mají být zahrnuta do výpočtu.</span><span class="sxs-lookup"><span data-stu-id="f53e1-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f53e1-134">V současné době jsou podporovány pouze aritmetické výrazy.</span><span class="sxs-lookup"><span data-stu-id="f53e1-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="f53e1-135">Kromě toho není podporován variabilní výpočet pro entity z různých [cest entit](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="f53e1-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="f53e1-136">Vyberte **Hotovo**.</span><span class="sxs-lookup"><span data-stu-id="f53e1-136">Select **Done**.</span></span>

11. <span data-ttu-id="f53e1-137">V části **Definice opatření** definujete, jak jsou vybrané entity a vypočtené proměnné agregovány v nové entitě nebo atributu měření.</span><span class="sxs-lookup"><span data-stu-id="f53e1-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="f53e1-138">Vyberte **Nová dimenze**.</span><span class="sxs-lookup"><span data-stu-id="f53e1-138">Select **New dimension**.</span></span> <span data-ttu-id="f53e1-139">Dimenzi si můžete představit jako funkci *seskupit dle*.</span><span class="sxs-lookup"><span data-stu-id="f53e1-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="f53e1-140">Datový výstup entity nebo atributu Opatření bude seskupen podle všech definovaných dimenzí.</span><span class="sxs-lookup"><span data-stu-id="f53e1-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f53e1-141">![Zvolit agregační cyklus](media/measures-businessreport-measure-definition2.png "Zvolit agregační cyklus")</span><span class="sxs-lookup"><span data-stu-id="f53e1-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="f53e1-142">Vyberte nebo zadejte následující informace jako součást definice dimenze:</span><span class="sxs-lookup"><span data-stu-id="f53e1-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="f53e1-143">**Entita**: Pokud definujete entitu Opatření, měla by obsahovat alespoň jeden atribut.</span><span class="sxs-lookup"><span data-stu-id="f53e1-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="f53e1-144">Pokud definujete atribut Opatření, bude ve výchozím nastavení obsahovat pouze jeden atribut.</span><span class="sxs-lookup"><span data-stu-id="f53e1-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="f53e1-145">Tento výběr je o výběru entity, která obsahuje tento atribut.</span><span class="sxs-lookup"><span data-stu-id="f53e1-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="f53e1-146">**Pole**: Zvolte konkrétní atribut, který má být zahrnut buď do entity Opatření, nebo atributu.</span><span class="sxs-lookup"><span data-stu-id="f53e1-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="f53e1-147">**Kbelík**: Zvolte, zda chcete agregovat data na denní, měsíční nebo roční bázi.</span><span class="sxs-lookup"><span data-stu-id="f53e1-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="f53e1-148">Je to povinný výběr, pouze pokud jste vybrali atribut Typ data.</span><span class="sxs-lookup"><span data-stu-id="f53e1-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="f53e1-149">**Jako**: Definuje název nového pole.</span><span class="sxs-lookup"><span data-stu-id="f53e1-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="f53e1-150">**Zobrazované jméno**: Definuje zobrazované jméno pole.</span><span class="sxs-lookup"><span data-stu-id="f53e1-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f53e1-151">Vaše obchodní opatření bude uloženo jako entita s jedním číslem a zobrazí se na **Domovské stránce**, pokud k opatření nepřidáte další dimenze.</span><span class="sxs-lookup"><span data-stu-id="f53e1-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="f53e1-152">Po přidání dalších dimenzí se opatření *nezobrazí* na **Domovské stránce**.</span><span class="sxs-lookup"><span data-stu-id="f53e1-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="f53e1-153">Volitelně přidejte funkce agregace.</span><span class="sxs-lookup"><span data-stu-id="f53e1-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="f53e1-154">Jakákoli agregace, kterou vytvoříte, má za následek novou hodnotu v rámci entity nebo atributu Opatření.</span><span class="sxs-lookup"><span data-stu-id="f53e1-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="f53e1-155">Podporované agregační funkce jsou: **Min**, **Maxi**, **Průměr**, **Medián**, **Součet**, **Počet jedinečných**, **První** (bere první záznam hodnoty dimenze) a **Poslední** (bere poslední záznam přidaný na hodnotu dimenze).</span><span class="sxs-lookup"><span data-stu-id="f53e1-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="f53e1-156">Výběrem možnosti **Uložit** použijete změny na opatření.</span><span class="sxs-lookup"><span data-stu-id="f53e1-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="f53e1-157">Správa opatření</span><span class="sxs-lookup"><span data-stu-id="f53e1-157">Manage your measures</span></span>

<span data-ttu-id="f53e1-158">Po vytvoření alespoň jedné míry se na stránce **Míry** zobrazí seznam měr.</span><span class="sxs-lookup"><span data-stu-id="f53e1-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="f53e1-159">Najdete zde informace o typu opatření, autorovi, datu a čase vytvoření, datu a datu poslední úpravy, stavu (zda je opatření aktivní, neaktivní nebo neúspěšné) a o datu a čase poslední aktualizace.</span><span class="sxs-lookup"><span data-stu-id="f53e1-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="f53e1-160">Když vyberete opatření ze seznamu, zobrazí se náhled jeho výstupu.</span><span class="sxs-lookup"><span data-stu-id="f53e1-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="f53e1-161">Chcete-li obnovit všechna vaše opatření současně, vyberte **Aktualizovat vše** bez výběru konkrétního opatření.</span><span class="sxs-lookup"><span data-stu-id="f53e1-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f53e1-162">![Akce ke správě jednotlivých opatření](media/measure-actions.png "Akce ke správě jednotlivých opatření")</span><span class="sxs-lookup"><span data-stu-id="f53e1-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="f53e1-163">Případně vyberte opatření ze seznamu a proveďte jednu z následujících akcí:</span><span class="sxs-lookup"><span data-stu-id="f53e1-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="f53e1-164">Chcete-li zobrazit podrobnosti, vyberte název opatření.</span><span class="sxs-lookup"><span data-stu-id="f53e1-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="f53e1-165">**Upravte** konfiguraci opatření.</span><span class="sxs-lookup"><span data-stu-id="f53e1-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="f53e1-166">**Přejmenujte** opatření.</span><span class="sxs-lookup"><span data-stu-id="f53e1-166">**Rename** the measure.</span></span>
- <span data-ttu-id="f53e1-167">**Odstraňte** opatření.</span><span class="sxs-lookup"><span data-stu-id="f53e1-167">**Delete** the measure.</span></span>
- <span data-ttu-id="f53e1-168">Vyberte tři tečky (...) a poté **Obnovit** pro zahájení procesu aktualizace opatření.</span><span class="sxs-lookup"><span data-stu-id="f53e1-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="f53e1-169">Vyberte tři tečky (...) a poté **Stáhnout**, chcete-li získat .CSV soubor opatření.</span><span class="sxs-lookup"><span data-stu-id="f53e1-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="f53e1-170">Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy.</span><span class="sxs-lookup"><span data-stu-id="f53e1-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f53e1-171">Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f53e1-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f53e1-172">Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy.</span><span class="sxs-lookup"><span data-stu-id="f53e1-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f53e1-173">Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.</span><span class="sxs-lookup"><span data-stu-id="f53e1-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="f53e1-174">Další krok</span><span class="sxs-lookup"><span data-stu-id="f53e1-174">Next step</span></span>

<span data-ttu-id="f53e1-175">Existující opatření můžete použít k vytvoření prvního segmentu zákazníků na stránce **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="f53e1-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="f53e1-176">Další informace najdete v tématu [Segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f53e1-176">For more information, see [Segments](segments.md).</span></span>
