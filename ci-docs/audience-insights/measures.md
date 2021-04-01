---
title: Vytváření a správa měr
description: Definujte míry, které budou analyzovat a reflektovat výkon vašeho podnikání.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654724"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="781d6-103">Definujte a spravujte opatření</span><span class="sxs-lookup"><span data-stu-id="781d6-103">Define and manage measures</span></span>

<span data-ttu-id="781d6-104">Míry vám pomohou lépe pochopit chování zákazníků a obchodní výkonnost načtením příslušných hodnot ze [sjednocených profilů](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="781d6-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="781d6-105">Například firma chce vidět *celkové výdaje na zákazníka*, aby porozuměla historii nákupů jednotlivých zákazníků.</span><span class="sxs-lookup"><span data-stu-id="781d6-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="781d6-106">Nebo změřit *celkový prodej společnosti*, aby porozuměla agregovaným výnosům v celém podniku.</span><span class="sxs-lookup"><span data-stu-id="781d6-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="781d6-107">Míry jsou vytvářeny pomocí nástroje pro tvorbu měr, což je platforma pro dotazování dat s různými operátory a možnostmi jednoduchého mapování.</span><span class="sxs-lookup"><span data-stu-id="781d6-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="781d6-108">Umožňuje filtrovat data, seskupovat výsledky, detekovat [cesty vztahů mezi entitami](relationships.md) a zobrazovat náhledy výstupu.</span><span class="sxs-lookup"><span data-stu-id="781d6-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="781d6-109">Pomocí nástroje pro tvorbu měr můžete plánovat obchodní aktivity dotazováním zákaznických dat a extrahováním přehledů.</span><span class="sxs-lookup"><span data-stu-id="781d6-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="781d6-110">Například vytvoření míry *celkové výdaje na zákazníka* a *celková návratnost na zákazníka* pomáhá identifikovat skupinu zákazníků s vysokými výdaji, ale s vysokou návratností.</span><span class="sxs-lookup"><span data-stu-id="781d6-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="781d6-111">[Vytvořením segmentu](segments.md) můžete řídit nejvhodnější akce, které se mají následně provést.</span><span class="sxs-lookup"><span data-stu-id="781d6-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="781d6-112">Vytvořit nové opatření</span><span class="sxs-lookup"><span data-stu-id="781d6-112">Create a measure</span></span>

<span data-ttu-id="781d6-113">Tato sekce vás provede vytvořením nové míry od nuly.</span><span class="sxs-lookup"><span data-stu-id="781d6-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="781d6-114">Můžete vytvořit míru s datovými atributy z datových entit, které mají nastavený vztah pro připojení k entitě zákazníka.</span><span class="sxs-lookup"><span data-stu-id="781d6-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="781d6-115">V přehledech cílové skupiny přejděte na **Míry**.</span><span class="sxs-lookup"><span data-stu-id="781d6-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="781d6-116">Vyberte **Nové**.</span><span class="sxs-lookup"><span data-stu-id="781d6-116">Select **New**.</span></span>

1. <span data-ttu-id="781d6-117">Vyberte **Upravit jméno** a zadejte **Název** míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="781d6-118">Pokud má vaše nová konfigurace míry pouze dvě pole, například CustomerID a jeden výpočet, bude výstup přidán jako nový sloupec do entity generované systémem s názvem Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="781d6-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="781d6-119">Hodnotu míry uvidíte ve sjednoceném profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="781d6-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="781d6-120">Další míry vygenerují vlastní entity.</span><span class="sxs-lookup"><span data-stu-id="781d6-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="781d6-121">V oblasti konfigurace vyberte agregační funkci z rozevírací nabídky **Vyberte funkci**.</span><span class="sxs-lookup"><span data-stu-id="781d6-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="781d6-122">Agregační funkce zahrnují:</span><span class="sxs-lookup"><span data-stu-id="781d6-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="781d6-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="781d6-123">**Sum**</span></span>
   - <span data-ttu-id="781d6-124">**Průměr**</span><span class="sxs-lookup"><span data-stu-id="781d6-124">**Average**</span></span>
   - <span data-ttu-id="781d6-125">**Počet**</span><span class="sxs-lookup"><span data-stu-id="781d6-125">**Count**</span></span>
   - <span data-ttu-id="781d6-126">**Počet jedinečných**</span><span class="sxs-lookup"><span data-stu-id="781d6-126">**Count Unique**</span></span>
   - <span data-ttu-id="781d6-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="781d6-127">**Max**</span></span>
   - <span data-ttu-id="781d6-128">**Min.**</span><span class="sxs-lookup"><span data-stu-id="781d6-128">**Min**</span></span>
   - <span data-ttu-id="781d6-129">**První**: přebírá první hodnotu datového záznamu</span><span class="sxs-lookup"><span data-stu-id="781d6-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="781d6-130">**Poslední**: převezme poslední hodnotu, která byla přidána do datového záznamu</span><span class="sxs-lookup"><span data-stu-id="781d6-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operátory pro výpočty měr.":::

1. <span data-ttu-id="781d6-132">Volbou **Přidat atribut** vyberte data, která potřebujete k vytvoření této míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="781d6-133">Vyberte kartu **Atributy**.</span><span class="sxs-lookup"><span data-stu-id="781d6-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="781d6-134">Datová entita: Vyberte entitu, která obsahuje atribut, který chcete měřit.</span><span class="sxs-lookup"><span data-stu-id="781d6-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="781d6-135">Atribut dat: Vyberte atribut, který chcete použít ve funkci agregace pro výpočet míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="781d6-136">Nelze vybrat více atributů najednou.</span><span class="sxs-lookup"><span data-stu-id="781d6-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="781d6-137">Atribut dat ze stávající míry můžete také vybrat výběrem karty **Míry**. Nebo můžete vyhledat název entity nebo míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="781d6-138">Volbou **Přidat** přidáte vybraný atribut do míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Vyberte atribut, který se má použít ve výpočtech.":::

1. <span data-ttu-id="781d6-140">Chcete-li vytvořit složitější míry, můžete přidat další atributy nebo použít matematické operátory ve své funkci míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Vytvořte komplexní míru s matematickými operátory.":::

1. <span data-ttu-id="781d6-142">Chcete-li přidat filtry, vyberte možnost **Filtr** v konfigurační oblasti.</span><span class="sxs-lookup"><span data-stu-id="781d6-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="781d6-143">V sekci **Přidat atribut** v podokně **Filtry** vyberte atribut, který chcete použít k vytvoření filtrů.</span><span class="sxs-lookup"><span data-stu-id="781d6-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="781d6-144">Nastavte operátory filtru tak, aby definovaly filtr pro každý vybraný atribut.</span><span class="sxs-lookup"><span data-stu-id="781d6-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="781d6-145">Volbou **Použít** přidáte filtry do míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="781d6-146">Chcete-li přidat dimenze, vyberte možnost **Dimenze** v konfigurační oblasti.</span><span class="sxs-lookup"><span data-stu-id="781d6-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="781d6-147">Dimenze se v entitě výstupu míry zobrazí jako sloupce.</span><span class="sxs-lookup"><span data-stu-id="781d6-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="781d6-148">Volbou **Upravit dimenze** přidáte atributy dat, podle kterých chcete seskupit hodnoty měr.</span><span class="sxs-lookup"><span data-stu-id="781d6-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="781d6-149">Například město nebo pohlaví.</span><span class="sxs-lookup"><span data-stu-id="781d6-149">For example, city or gender.</span></span> <span data-ttu-id="781d6-150">Ve výchozím nastavení je vybrána dimenze *CustomerID* k vytvoření *měr na úrovni zákazníka*.</span><span class="sxs-lookup"><span data-stu-id="781d6-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="781d6-151">Pokud chcete vytvořit *míry na úrovni podniku*, můžete odebrat výchozí míru.</span><span class="sxs-lookup"><span data-stu-id="781d6-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="781d6-152">Volbou **Hotovo** přidáte dimenze do míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="781d6-153">Pokud mezi datovou entitou, kterou jste mapovali, a entitou *Zákazník* existuje více cest, musíte zvolit jednu z identifikovaných [cest vztahů mezi entitami](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="781d6-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="781d6-154">Výsledné míry se mohou lišit v závislosti na vybrané cestě.</span><span class="sxs-lookup"><span data-stu-id="781d6-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="781d6-155">Vyberte **Předvolby dat** a vyberte cestu entity, která by měla být použita k identifikaci vaší míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="781d6-156">Pokud existuje pouze jedna cesta k entitě *Zákazník*, tento ovládací prvek se nezobrazí.</span><span class="sxs-lookup"><span data-stu-id="781d6-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="781d6-157">Volbou **Hotovo** použijete svůj výběr.</span><span class="sxs-lookup"><span data-stu-id="781d6-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Umožňuje vybrat cestu entitu pro tuto míru.":::

1. <span data-ttu-id="781d6-159">Chcete-li přidat další výpočty pro míru, vyberte **Nový výpočet**.</span><span class="sxs-lookup"><span data-stu-id="781d6-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="781d6-160">Pro nové výpočty můžete použít pouze entity na stejné cestě entity.</span><span class="sxs-lookup"><span data-stu-id="781d6-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="781d6-161">Další výpočtu se v entitě výstupu míry zobrazí jako nové sloupce.</span><span class="sxs-lookup"><span data-stu-id="781d6-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="781d6-162">Vyberte **...** na výpočtu, abyste **duplikovali**, **přejmenovali** nebo **odstranili** výpočet z míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="781d6-163">V oblasti **Náhled** uvidíte schéma dat pro entitu výstupu míry, včetně filtrů a dimenzí.</span><span class="sxs-lookup"><span data-stu-id="781d6-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="781d6-164">Náhled dynamicky reaguje na změny v konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="781d6-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="781d6-165">Volbou **Spustit** vypočtete výsledky pro konfigurovanou míru.</span><span class="sxs-lookup"><span data-stu-id="781d6-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="781d6-166">Vyberte **Uložit a zavřít**, chcete-li zachovat aktuální konfiguraci a spustit míru později.</span><span class="sxs-lookup"><span data-stu-id="781d6-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="781d6-167">Jděte na **Míry** pro zobrazení nově vytvořené míry v seznamu.</span><span class="sxs-lookup"><span data-stu-id="781d6-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="781d6-168">Správa opatření</span><span class="sxs-lookup"><span data-stu-id="781d6-168">Manage your measures</span></span>

<span data-ttu-id="781d6-169">Po [vytvoření míry](#create-a-measure) se na stránce **Míry** zobrazí seznam měr.</span><span class="sxs-lookup"><span data-stu-id="781d6-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="781d6-170">Najdete informace o typu, tvůrci, datu vytvoření, statusu a stavu míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="781d6-171">Když vyberete míru ze seznamu, můžete zobrazit náhled výstupu a stáhnout soubor .CSV.</span><span class="sxs-lookup"><span data-stu-id="781d6-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="781d6-172">Chcete-li obnovit všechna vaše opatření současně, vyberte **Aktualizovat vše** bez výběru konkrétního opatření.</span><span class="sxs-lookup"><span data-stu-id="781d6-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="781d6-173">![Akce ke správě jednotlivých opatření](media/measure-actions.png "Akce ke správě jednotlivých opatření")</span><span class="sxs-lookup"><span data-stu-id="781d6-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="781d6-174">Vyberte míru ze seznamu a použijte některou z následujících voleb:</span><span class="sxs-lookup"><span data-stu-id="781d6-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="781d6-175">Chcete-li zobrazit podrobnosti, vyberte název míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="781d6-176">**Upravte** konfiguraci míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="781d6-177">**Aktualizujte** míru na základě nejnovějších údajů.</span><span class="sxs-lookup"><span data-stu-id="781d6-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="781d6-178">**Přejmenujte** míru.</span><span class="sxs-lookup"><span data-stu-id="781d6-178">**Rename** the measure.</span></span>
- <span data-ttu-id="781d6-179">**Odstraňte** míry.</span><span class="sxs-lookup"><span data-stu-id="781d6-179">**Delete** the measure.</span></span>
- <span data-ttu-id="781d6-180">**Aktivujte** nebo **deaktivujte**.</span><span class="sxs-lookup"><span data-stu-id="781d6-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="781d6-181">Neaktivní míry se během [plánované aktualizace](system.md#schedule-tab) neaktualizují.</span><span class="sxs-lookup"><span data-stu-id="781d6-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="781d6-182">Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy.</span><span class="sxs-lookup"><span data-stu-id="781d6-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="781d6-183">Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="781d6-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="781d6-184">Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy.</span><span class="sxs-lookup"><span data-stu-id="781d6-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="781d6-185">Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.</span><span class="sxs-lookup"><span data-stu-id="781d6-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="781d6-186">Další krok</span><span class="sxs-lookup"><span data-stu-id="781d6-186">Next step</span></span>

<span data-ttu-id="781d6-187">K vytvoření použijete stávající míry pro vytvoření [zákaznického segmentu](segments.md).</span><span class="sxs-lookup"><span data-stu-id="781d6-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]