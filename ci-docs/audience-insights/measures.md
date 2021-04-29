---
title: Vytváření a správa měr
description: Definujte míry, které budou analyzovat a reflektovat výkon vašeho podnikání.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a94a32a04f2a8beb661c27271fe96f23d998722
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887932"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="d613c-103">Definujte a spravujte opatření</span><span class="sxs-lookup"><span data-stu-id="d613c-103">Define and manage measures</span></span>

<span data-ttu-id="d613c-104">Míry vám pomohou lépe porozumět chování zákazníků a výkonnosti podniku.</span><span class="sxs-lookup"><span data-stu-id="d613c-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="d613c-105">Zaměřují se na relevantní hodnoty ze [sjednocených profilů](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="d613c-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="d613c-106">Například firma chce vidět *celkové výdaje na zákazníka* pro pochopení historie nebo míry nákupu jednotlivých zákazníků nebo míry *celkový prodej společnosti* pro pochopení agregovaných výnosů v celé firmě.</span><span class="sxs-lookup"><span data-stu-id="d613c-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="d613c-107">Míry jsou vytvářeny pomocí nástroje pro tvorbu měr, což je platforma pro dotazování dat s různými operátory a možnostmi jednoduchého mapování.</span><span class="sxs-lookup"><span data-stu-id="d613c-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="d613c-108">Umožňuje filtrovat data, seskupovat výsledky, detekovat [cesty vztahů mezi entitami](relationships.md) a zobrazovat náhledy výstupu.</span><span class="sxs-lookup"><span data-stu-id="d613c-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="d613c-109">Pomocí nástroje pro tvorbu měr můžete plánovat obchodní aktivity dotazováním zákaznických dat a extrahováním přehledů.</span><span class="sxs-lookup"><span data-stu-id="d613c-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="d613c-110">Například vytvoření míry *celkové výdaje na zákazníka* a *celková návratnost na zákazníka* pomáhá identifikovat skupinu zákazníků s vysokými výdaji, ale s vysokou návratností.</span><span class="sxs-lookup"><span data-stu-id="d613c-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="d613c-111">[Vytvořením segmentu](segments.md) můžete řídit nejvhodnější akce, které se mají následně provést.</span><span class="sxs-lookup"><span data-stu-id="d613c-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="d613c-112">Vytvoření vlastní míry od začátku</span><span class="sxs-lookup"><span data-stu-id="d613c-112">Build your own measure from scratch</span></span>

<span data-ttu-id="d613c-113">Tato sekce vás provede vytvořením nové míry od nuly.</span><span class="sxs-lookup"><span data-stu-id="d613c-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="d613c-114">Můžete vytvořit míru s datovými atributy z datových entit, které mají nastavený vztah pro připojení k entitě zákazníka.</span><span class="sxs-lookup"><span data-stu-id="d613c-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="d613c-115">V přehledech cílové skupiny přejděte na **Míry**.</span><span class="sxs-lookup"><span data-stu-id="d613c-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="d613c-116">Vyberte **Nový** a zvolte **Vytvořit vlastní**.</span><span class="sxs-lookup"><span data-stu-id="d613c-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="d613c-117">Vyberte **Upravit jméno** a zadejte **Název** míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="d613c-118">Pokud má vaše nová konfigurace míry pouze dvě pole, například CustomerID a jeden výpočet, bude výstup přidán jako nový sloupec do entity generované systémem s názvem Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="d613c-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="d613c-119">Hodnotu míry uvidíte ve sjednoceném profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="d613c-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="d613c-120">Další míry vygenerují vlastní entity.</span><span class="sxs-lookup"><span data-stu-id="d613c-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="d613c-121">V oblasti konfigurace vyberte agregační funkci z rozevírací nabídky **Vyberte funkci**.</span><span class="sxs-lookup"><span data-stu-id="d613c-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="d613c-122">Agregační funkce zahrnují:</span><span class="sxs-lookup"><span data-stu-id="d613c-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="d613c-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="d613c-123">**Sum**</span></span>
   - <span data-ttu-id="d613c-124">**Průměr**</span><span class="sxs-lookup"><span data-stu-id="d613c-124">**Average**</span></span>
   - <span data-ttu-id="d613c-125">**Počet**</span><span class="sxs-lookup"><span data-stu-id="d613c-125">**Count**</span></span>
   - <span data-ttu-id="d613c-126">**Počet jedinečných**</span><span class="sxs-lookup"><span data-stu-id="d613c-126">**Count Unique**</span></span>
   - <span data-ttu-id="d613c-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="d613c-127">**Max**</span></span>
   - <span data-ttu-id="d613c-128">**Min.**</span><span class="sxs-lookup"><span data-stu-id="d613c-128">**Min**</span></span>
   - <span data-ttu-id="d613c-129">**První**: přebírá první hodnotu datového záznamu</span><span class="sxs-lookup"><span data-stu-id="d613c-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="d613c-130">**Poslední**: převezme poslední hodnotu, která byla přidána do datového záznamu</span><span class="sxs-lookup"><span data-stu-id="d613c-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operátory pro výpočty měr.":::

1. <span data-ttu-id="d613c-132">Volbou **Přidat atribut** vyberte data, která potřebujete k vytvoření této míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="d613c-133">Vyberte kartu **Atributy**.</span><span class="sxs-lookup"><span data-stu-id="d613c-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="d613c-134">Datová entita: Vyberte entitu, která obsahuje atribut, který chcete měřit.</span><span class="sxs-lookup"><span data-stu-id="d613c-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="d613c-135">Atribut dat: Vyberte atribut, který chcete použít ve funkci agregace pro výpočet míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="d613c-136">Nelze vybrat více atributů najednou.</span><span class="sxs-lookup"><span data-stu-id="d613c-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="d613c-137">Atribut dat ze stávající míry můžete také vybrat výběrem karty **Míry**. Nebo můžete vyhledat název entity nebo míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="d613c-138">Volbou **Přidat** přidáte vybraný atribut do míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Vyberte atribut, který se má použít ve výpočtech.":::

1. <span data-ttu-id="d613c-140">Chcete-li vytvořit složitější míry, můžete přidat další atributy nebo použít matematické operátory ve své funkci míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Vytvořte komplexní míru s matematickými operátory.":::

1. <span data-ttu-id="d613c-142">Chcete-li přidat filtry, vyberte možnost **Filtr** v konfigurační oblasti.</span><span class="sxs-lookup"><span data-stu-id="d613c-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="d613c-143">V sekci **Přidat atribut** v podokně **Filtry** vyberte atribut, který chcete použít k vytvoření filtrů.</span><span class="sxs-lookup"><span data-stu-id="d613c-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="d613c-144">Nastavte operátory filtru tak, aby definovaly filtr pro každý vybraný atribut.</span><span class="sxs-lookup"><span data-stu-id="d613c-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="d613c-145">Volbou **Použít** přidáte filtry do míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="d613c-146">Chcete-li přidat dimenze, vyberte možnost **Dimenze** v konfigurační oblasti.</span><span class="sxs-lookup"><span data-stu-id="d613c-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="d613c-147">Dimenze se v entitě výstupu míry zobrazí jako sloupce.</span><span class="sxs-lookup"><span data-stu-id="d613c-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="d613c-148">Volbou **Upravit dimenze** přidáte atributy dat, podle kterých chcete seskupit hodnoty měr.</span><span class="sxs-lookup"><span data-stu-id="d613c-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="d613c-149">Například město nebo pohlaví.</span><span class="sxs-lookup"><span data-stu-id="d613c-149">For example, city or gender.</span></span> <span data-ttu-id="d613c-150">Ve výchozím nastavení je vybrána dimenze *CustomerID* k vytvoření *měr na úrovni zákazníka*.</span><span class="sxs-lookup"><span data-stu-id="d613c-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="d613c-151">Pokud chcete vytvořit *míry na úrovni podniku*, můžete odebrat výchozí míru.</span><span class="sxs-lookup"><span data-stu-id="d613c-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="d613c-152">Volbou **Hotovo** přidáte dimenze do míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="d613c-153">Pokud jsou ve vašich datech hodnoty, které potřebujete nahradit celým číslem, nahraďte například hodnotu *null* hodnotou *0*, vyberte **Pravidla**.</span><span class="sxs-lookup"><span data-stu-id="d613c-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="d613c-154">Nakonfigurujte pravidlo a ujistěte se, že jako náhradu zvolíte pouze celá čísla.</span><span class="sxs-lookup"><span data-stu-id="d613c-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="d613c-155">Pokud mezi datovou entitou, kterou jste mapovali, a entitou *Zákazník* existuje více cest, musíte zvolit jednu z identifikovaných [cest vztahů mezi entitami](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="d613c-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="d613c-156">Výsledné míry se mohou lišit v závislosti na vybrané cestě.</span><span class="sxs-lookup"><span data-stu-id="d613c-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="d613c-157">Vyberte **Předvolby dat** a vyberte cestu entity, která by měla být použita k identifikaci vaší míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="d613c-158">Pokud existuje pouze jedna cesta k entitě *Zákazník*, tento ovládací prvek se nezobrazí.</span><span class="sxs-lookup"><span data-stu-id="d613c-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="d613c-159">Volbou **Hotovo** použijete svůj výběr.</span><span class="sxs-lookup"><span data-stu-id="d613c-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Umožňuje vybrat cestu entitu pro tuto míru.":::

1. <span data-ttu-id="d613c-161">Chcete-li přidat další výpočty pro míru, vyberte **Nový výpočet**.</span><span class="sxs-lookup"><span data-stu-id="d613c-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="d613c-162">Pro nové výpočty můžete použít pouze entity na stejné cestě entity.</span><span class="sxs-lookup"><span data-stu-id="d613c-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="d613c-163">Další výpočtu se v entitě výstupu míry zobrazí jako nové sloupce.</span><span class="sxs-lookup"><span data-stu-id="d613c-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="d613c-164">Vyberte **...** na výpočtu, abyste **duplikovali**, **přejmenovali** nebo **odstranili** výpočet z míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="d613c-165">V oblasti **Náhled** uvidíte schéma dat pro entitu výstupu míry, včetně filtrů a dimenzí.</span><span class="sxs-lookup"><span data-stu-id="d613c-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="d613c-166">Náhled dynamicky reaguje na změny v konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="d613c-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="d613c-167">Volbou **Spustit** vypočtete výsledky pro konfigurovanou míru.</span><span class="sxs-lookup"><span data-stu-id="d613c-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="d613c-168">Vyberte **Uložit a zavřít**, chcete-li zachovat aktuální konfiguraci a spustit míru později.</span><span class="sxs-lookup"><span data-stu-id="d613c-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="d613c-169">Jděte na **Míry** pro zobrazení nově vytvořené míry v seznamu.</span><span class="sxs-lookup"><span data-stu-id="d613c-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="d613c-170">Vytvoření míry pomocí šablony</span><span class="sxs-lookup"><span data-stu-id="d613c-170">Use a template to build a measure</span></span>

<span data-ttu-id="d613c-171">K jejich vytváření můžete použít předdefinované šablony běžně používaných měr.</span><span class="sxs-lookup"><span data-stu-id="d613c-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="d613c-172">Podrobné popisy šablon a průvodce vám pomohou s efektivním vytvořením míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="d613c-173">Šablony vycházejí z mapovaných dat entity *Sjednocená aktivita*.</span><span class="sxs-lookup"><span data-stu-id="d613c-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="d613c-174">Ujistěte se tedy, že jste nakonfigurovali [aktivity zákazníků](activities.md) před vytvořením míry ze šablony.</span><span class="sxs-lookup"><span data-stu-id="d613c-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="d613c-175">Dostupné šablony měr:</span><span class="sxs-lookup"><span data-stu-id="d613c-175">Available measure templates:</span></span> 
- <span data-ttu-id="d613c-176">Průměrná hodnota transakce</span><span class="sxs-lookup"><span data-stu-id="d613c-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="d613c-177">Celková hodnota transakce</span><span class="sxs-lookup"><span data-stu-id="d613c-177">Total transaction value</span></span>
- <span data-ttu-id="d613c-178">Průměrné denní výnosy</span><span class="sxs-lookup"><span data-stu-id="d613c-178">Average daily revenue</span></span>
- <span data-ttu-id="d613c-179">Průměrné roční výnosy</span><span class="sxs-lookup"><span data-stu-id="d613c-179">Average yearly revenue</span></span>
- <span data-ttu-id="d613c-180">Počet transakcí</span><span class="sxs-lookup"><span data-stu-id="d613c-180">Transaction count</span></span>
- <span data-ttu-id="d613c-181">Získané věrnostní body</span><span class="sxs-lookup"><span data-stu-id="d613c-181">Loyalty points earned</span></span>
- <span data-ttu-id="d613c-182">Uplatněné věrnostní body</span><span class="sxs-lookup"><span data-stu-id="d613c-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="d613c-183">Zůstatek věrnostních bodů</span><span class="sxs-lookup"><span data-stu-id="d613c-183">Loyalty points balance</span></span>
- <span data-ttu-id="d613c-184">Životnost aktivního zákazníka</span><span class="sxs-lookup"><span data-stu-id="d613c-184">Active customer lifespan</span></span>
- <span data-ttu-id="d613c-185">Doba trvání věrnostního členství</span><span class="sxs-lookup"><span data-stu-id="d613c-185">Loyalty membership duration</span></span>
- <span data-ttu-id="d613c-186">Čas od posledního nákupu</span><span class="sxs-lookup"><span data-stu-id="d613c-186">Time since last purchase</span></span>

<span data-ttu-id="d613c-187">Následující postup popisuje kroky k vytvoření nové míry pomocí šablony.</span><span class="sxs-lookup"><span data-stu-id="d613c-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="d613c-188">V přehledech cílové skupiny přejděte na **Míry**.</span><span class="sxs-lookup"><span data-stu-id="d613c-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="d613c-189">Vyberte **Nová** a vyberte **Zvolit šablonu**.</span><span class="sxs-lookup"><span data-stu-id="d613c-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Screenshot rozevírací nabídky při vytváření nové míry se zvýrazněním šablony.":::

1. <span data-ttu-id="d613c-191">Najděte šablonu, která vyhovuje vašim potřebám, a vyberte **Zvolit šablonu**.</span><span class="sxs-lookup"><span data-stu-id="d613c-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="d613c-192">Zkontrolujte požadovaná data a vyberte **Začít**, pokud máte všechna data na místě.</span><span class="sxs-lookup"><span data-stu-id="d613c-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="d613c-193">V podokně **Upravit jméno** nastavte název míry a výstupní entitu.</span><span class="sxs-lookup"><span data-stu-id="d613c-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="d613c-194">Vyberte **Hotovo**.</span><span class="sxs-lookup"><span data-stu-id="d613c-194">Select **Done**.</span></span>

1. <span data-ttu-id="d613c-195">V části **Nastavit časové období** definujte časový rámec dat, která se mají použít.</span><span class="sxs-lookup"><span data-stu-id="d613c-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="d613c-196">Vyberte, zda chcete, aby nová míra pokrývala celou datovou sadu, výběrem možnosti **Pořád**.</span><span class="sxs-lookup"><span data-stu-id="d613c-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="d613c-197">Nebo zda chcete, aby se míra zaměřovala na **Specifické časové období**.</span><span class="sxs-lookup"><span data-stu-id="d613c-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Screenshot zobrazující část časového období při konfiguraci míry ze šablony.":::

1. <span data-ttu-id="d613c-199">V další části vyberte **Přidat data** pro výběr aktivit a namapování příslušných dat z entity *Sjednocená aktivita*.</span><span class="sxs-lookup"><span data-stu-id="d613c-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="d613c-200">Krok 1 ze 2: V části **Typ aktivity** vyberte typ entity, kterou chcete použít.</span><span class="sxs-lookup"><span data-stu-id="d613c-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="d613c-201">Pro **Aktivity** vyberte entity, které chcete mapovat.</span><span class="sxs-lookup"><span data-stu-id="d613c-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="d613c-202">Krok 2 ze 2: Vyberte atribut z entity *Sjednocená aktivita* pro komponentu požadovanou vzorcem.</span><span class="sxs-lookup"><span data-stu-id="d613c-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="d613c-203">Například pro průměrnou hodnotu transakce je to atribut představující hodnotu transakce.</span><span class="sxs-lookup"><span data-stu-id="d613c-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="d613c-204">Pro **Časové razítko aktivity** vyberte atribut z entity Unified Activity, která představuje datum a čas aktivity.</span><span class="sxs-lookup"><span data-stu-id="d613c-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="d613c-205">Jakmile je mapování dat úspěšné, můžete vidět stav jako **Kompletní** a název mapovaných aktivit a atributů.</span><span class="sxs-lookup"><span data-stu-id="d613c-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Screenshot z dokončené konfigurace šablony míry.":::

1. <span data-ttu-id="d613c-207">Nyní můžete vybrat **Spustit** k výpočtu výsledků míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="d613c-208">Chcete-li to upřesnit později, vyberte **Uložit koncept**.</span><span class="sxs-lookup"><span data-stu-id="d613c-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="d613c-209">Správa opatření</span><span class="sxs-lookup"><span data-stu-id="d613c-209">Manage your measures</span></span>

<span data-ttu-id="d613c-210">Seznam měr naleznete na stránce **Míry**.</span><span class="sxs-lookup"><span data-stu-id="d613c-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="d613c-211">Najdete informace o typu, tvůrci, datu vytvoření, statusu a stavu míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="d613c-212">Když vyberete míru ze seznamu, můžete zobrazit náhled výstupu a stáhnout soubor .CSV.</span><span class="sxs-lookup"><span data-stu-id="d613c-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="d613c-213">Chcete-li obnovit všechna vaše opatření současně, vyberte **Aktualizovat vše** bez výběru konkrétního opatření.</span><span class="sxs-lookup"><span data-stu-id="d613c-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d613c-214">![Akce ke správě jednotlivých opatření](media/measure-actions.png "Akce ke správě jednotlivých opatření")</span><span class="sxs-lookup"><span data-stu-id="d613c-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="d613c-215">Vyberte míru ze seznamu a použijte některou z následujících voleb:</span><span class="sxs-lookup"><span data-stu-id="d613c-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="d613c-216">Chcete-li zobrazit podrobnosti, vyberte název míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="d613c-217">**Upravte** konfiguraci míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="d613c-218">**Aktualizujte** míru na základě nejnovějších údajů.</span><span class="sxs-lookup"><span data-stu-id="d613c-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="d613c-219">**Přejmenujte** míru.</span><span class="sxs-lookup"><span data-stu-id="d613c-219">**Rename** the measure.</span></span>
- <span data-ttu-id="d613c-220">**Odstraňte** míry.</span><span class="sxs-lookup"><span data-stu-id="d613c-220">**Delete** the measure.</span></span>
- <span data-ttu-id="d613c-221">**Aktivujte** nebo **deaktivujte**.</span><span class="sxs-lookup"><span data-stu-id="d613c-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="d613c-222">Neaktivní míry se během [plánované aktualizace](system.md#schedule-tab) neaktualizují.</span><span class="sxs-lookup"><span data-stu-id="d613c-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="d613c-223">Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy.</span><span class="sxs-lookup"><span data-stu-id="d613c-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d613c-224">Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d613c-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d613c-225">Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy.</span><span class="sxs-lookup"><span data-stu-id="d613c-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d613c-226">Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.</span><span class="sxs-lookup"><span data-stu-id="d613c-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="d613c-227">Další krok</span><span class="sxs-lookup"><span data-stu-id="d613c-227">Next step</span></span>

<span data-ttu-id="d613c-228">K vytvoření použijete stávající míry pro vytvoření [zákaznického segmentu](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d613c-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]