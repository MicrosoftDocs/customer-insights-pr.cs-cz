---
title: Rozšíření profilů zákazníků daty od společnosti Microsoft
description: Použijte vlastnická data od společnosti Microsoft k rozšíření svých zákaznických dat o afinitu ke značce a zájmem.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064883"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="a143c-103">Obohaťte si zákaznické profily značkami a zájmovými skupinami (preview)</span><span class="sxs-lookup"><span data-stu-id="a143c-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="a143c-104">Použijte vlastnická data společnosti Microsoft k rozšíření svých zákaznických dat o afinitu ke značce a zájmem.</span><span class="sxs-lookup"><span data-stu-id="a143c-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="a143c-105">Tato náklonnost je určována na základě údajů od osob z podobné demografické skupiny jako vaši zákazníci.</span><span class="sxs-lookup"><span data-stu-id="a143c-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="a143c-106">Tyto informace vám pomohou lépe porozumět a rozdělit zákazníky podle jejich náklonnosti ke konkrétním značkám a zájmům.</span><span class="sxs-lookup"><span data-stu-id="a143c-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="a143c-107">V přehledech cílové skupiny přejděte na **Data** > **Rozšíření**, kde můžete [nakonfigurovat a zobrazit rozšíření](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="a143c-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="a143c-108">Chcete-li nakonfigurovat rozšíření o náklonnost ke značkám, přejděte na kartu **Zjistit** a vyberte **Rozšířit moje data** na dlaždici **Značky**.</span><span class="sxs-lookup"><span data-stu-id="a143c-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="a143c-109">Chcete-li nakonfigurovat rozšíření o náklonnost k zájmům, přejděte na kartu **Zjistit** a vyberte **Rozšířit moje data** na dlaždici **Zájmy**.</span><span class="sxs-lookup"><span data-stu-id="a143c-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a143c-110">![Dlaždice Značky a zájmy](media/BrandsInterest-tile-Hub.png "Dlaždice Značky a zájmy")</span><span class="sxs-lookup"><span data-stu-id="a143c-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="a143c-111">Jak určujeme afinity</span><span class="sxs-lookup"><span data-stu-id="a143c-111">How we determine affinities</span></span>

<span data-ttu-id="a143c-112">Údaje online vyhledávání společnosti Microsoft používáme k vyhledání afinity ke značkám a zájmy v různých demografických segmentech (definovaných podle věku, pohlaví nebo polohy).</span><span class="sxs-lookup"><span data-stu-id="a143c-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="a143c-113">Objem online vyhledávání pro určitou značku nebo zájem určuje, jak velkou afinitu má demografický segment ve srovnání s jinými segmenty k této značce nebo zájmu.</span><span class="sxs-lookup"><span data-stu-id="a143c-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="a143c-114">Úroveň a skóre afinity</span><span class="sxs-lookup"><span data-stu-id="a143c-114">Affinity level and score</span></span>

<span data-ttu-id="a143c-115">U každého rozšířeného zákaznického profilu poskytujeme dvě související hodnoty -–úroveň afinity a skóre afinity.</span><span class="sxs-lookup"><span data-stu-id="a143c-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="a143c-116">Tyto hodnoty vám pomohou určit, jak silná je afinita k demografickému segmentu daného profilu, ke značce nebo zájmu ve srovnání s jinými demografickými segmenty.</span><span class="sxs-lookup"><span data-stu-id="a143c-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="a143c-117">*Úroveň afinity* se skládá ze čtyř úrovní a *skóre afinity* se počítá na 100bodové stupnici, která se mapuje na úrovně afinity.</span><span class="sxs-lookup"><span data-stu-id="a143c-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="a143c-118">Úroveň afinity</span><span class="sxs-lookup"><span data-stu-id="a143c-118">Affinity level</span></span> |<span data-ttu-id="a143c-119">Skóre příbuznosti</span><span class="sxs-lookup"><span data-stu-id="a143c-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="a143c-120">Velmi vysoká</span><span class="sxs-lookup"><span data-stu-id="a143c-120">Very high</span></span>     | <span data-ttu-id="a143c-121">85–100</span><span class="sxs-lookup"><span data-stu-id="a143c-121">85-100</span></span>       |
|<span data-ttu-id="a143c-122">vysokou</span><span class="sxs-lookup"><span data-stu-id="a143c-122">High</span></span>     | <span data-ttu-id="a143c-123">70–84</span><span class="sxs-lookup"><span data-stu-id="a143c-123">70-84</span></span>        |
|<span data-ttu-id="a143c-124">střední</span><span class="sxs-lookup"><span data-stu-id="a143c-124">Medium</span></span>     | <span data-ttu-id="a143c-125">35–69</span><span class="sxs-lookup"><span data-stu-id="a143c-125">35-69</span></span>        |
|<span data-ttu-id="a143c-126">nízkou</span><span class="sxs-lookup"><span data-stu-id="a143c-126">Low</span></span>     | <span data-ttu-id="a143c-127">1–34</span><span class="sxs-lookup"><span data-stu-id="a143c-127">1-34</span></span>        |

<span data-ttu-id="a143c-128">V závislosti na granularitě, kterou chcete pro měření afinity, můžete použít buď úroveň nebo skóre afinity.</span><span class="sxs-lookup"><span data-stu-id="a143c-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="a143c-129">Skóre afinity vám dává přesnější kontrolu.</span><span class="sxs-lookup"><span data-stu-id="a143c-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="a143c-130">Podporované země/oblasti</span><span class="sxs-lookup"><span data-stu-id="a143c-130">Supported countries/regions</span></span>

<span data-ttu-id="a143c-131">V současné době podporujeme následující země/oblasti: Austrálie, Kanada (angličtina), Francie, Německo, Spojené království nebo Spojené státy americké (angličtina).</span><span class="sxs-lookup"><span data-stu-id="a143c-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="a143c-132">Chcete-li vybrat zemi, otevřete **Rozšíření značek** nebo **Rozšíření zájmů** a vyberte **Změnit** vedle **Země/oblasti**.</span><span class="sxs-lookup"><span data-stu-id="a143c-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="a143c-133">V podokně **Nastavení země/oblasti** vyberte požadovanou možnost a vyberte **Použít**.</span><span class="sxs-lookup"><span data-stu-id="a143c-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="a143c-134">Důsledky výběru země</span><span class="sxs-lookup"><span data-stu-id="a143c-134">Implications related to country selection</span></span>

- <span data-ttu-id="a143c-135">Při [výběru vlastních značek](#define-your-brands-or-interests) systém poskytne návrhy na základě vybrané země nebo oblasti.</span><span class="sxs-lookup"><span data-stu-id="a143c-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="a143c-136">Při [výběru odvětví](#define-your-brands-or-interests) se vám zobrazí nejrelevantnější značky nebo zájmy na základě vybrané země nebo oblasti.</span><span class="sxs-lookup"><span data-stu-id="a143c-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="a143c-137">Při [rozšiřování profilů](#refresh-enrichment) dojde k rozšíření profilů zákazníků, pro které získáme údaje o vybraných značkách a zájmech.</span><span class="sxs-lookup"><span data-stu-id="a143c-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="a143c-138">Včetně profilů, které nejsou ve vybrané zemi nebo oblasti.</span><span class="sxs-lookup"><span data-stu-id="a143c-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="a143c-139">Pokud jste například vybrali Německo, rozšíříme profily nacházející se ve Spojených státech, pokud máme k dispozici údaje o vybraných značkách a zájmech v USA.</span><span class="sxs-lookup"><span data-stu-id="a143c-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="a143c-140">Konfigurace rozšíření</span><span class="sxs-lookup"><span data-stu-id="a143c-140">Configure Enrichment</span></span>

<span data-ttu-id="a143c-141">Asistované prostředí vám pomůže s konfigurací obohacení.</span><span class="sxs-lookup"><span data-stu-id="a143c-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="a143c-142">Uveďte své značky nebo zájmy</span><span class="sxs-lookup"><span data-stu-id="a143c-142">Define your brands or interests</span></span>

<span data-ttu-id="a143c-143">Vyberte jednu z následujících možností:</span><span class="sxs-lookup"><span data-stu-id="a143c-143">Select one of the following options:</span></span>

- <span data-ttu-id="a143c-144">**Odvětví**: Systém identifikuje top značky nebo zájmy relevantní pro váš obor a obohacuje o ně vaše zákaznická data.</span><span class="sxs-lookup"><span data-stu-id="a143c-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="a143c-145">**Vyberte vlastní**: Ze seznamu značek nebo zájmů, které jsou pro vaši organizaci nejvhodnější, vyberte až pět položek.</span><span class="sxs-lookup"><span data-stu-id="a143c-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="a143c-146">Chcete-li přidat značku nebo zájem, zadejte je do vstupní oblasti a získejte návrhy na základě odpovídajících podmínek.</span><span class="sxs-lookup"><span data-stu-id="a143c-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="a143c-147">Pokud neuvedeme značku nebo zájem, který hledáte, pošlete nám zpětnou vazbu pomocí odkazu **Navrhnout**.</span><span class="sxs-lookup"><span data-stu-id="a143c-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="a143c-148">Kontrola předvoleb rozšíření</span><span class="sxs-lookup"><span data-stu-id="a143c-148">Review enrichment preferences</span></span>

<span data-ttu-id="a143c-149">Zkontrolujte své výchozí předvolby rozšíření a podle potřeby je aktualizujte.</span><span class="sxs-lookup"><span data-stu-id="a143c-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Screenshot okna předvoleb rozšíření.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="a143c-151">Vyberte entitu, kterou chcete rozšířit.</span><span class="sxs-lookup"><span data-stu-id="a143c-151">Select entity to enrich</span></span>

<span data-ttu-id="a143c-152">Vyberte **Rozšířená entita** a vyberte datovou sadu, kterou chcete rozšířit o firemní data od společnosti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a143c-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="a143c-153">Můžete vybrat entitu Zákazník k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.</span><span class="sxs-lookup"><span data-stu-id="a143c-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="a143c-154">Mapování polí</span><span class="sxs-lookup"><span data-stu-id="a143c-154">Map your fields</span></span>

<span data-ttu-id="a143c-155">Namapujte pole z vaší sjednocené entity zákazníka a definujte demografický segment, který má systém použít k rozšíření vašich zákaznických dat.</span><span class="sxs-lookup"><span data-stu-id="a143c-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="a143c-156">Namapujte zemi/oblast a alespoň atributy Datum narození nebo Pohlaví.</span><span class="sxs-lookup"><span data-stu-id="a143c-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="a143c-157">Kromě toho je nutné namapovat alespoň jedno z měst (a kraj) nebo PSČ.</span><span class="sxs-lookup"><span data-stu-id="a143c-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="a143c-158">Volbou **Upravit** definujete mapování polí a když máte hotovo, vyberte **Použít**.</span><span class="sxs-lookup"><span data-stu-id="a143c-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="a143c-159">Vyberte **Uložit** pro dokončení mapování pole.</span><span class="sxs-lookup"><span data-stu-id="a143c-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="a143c-160">Jsou podporovány následující formáty a hodnoty, hodnoty nerozlišují velká a malá písmena:</span><span class="sxs-lookup"><span data-stu-id="a143c-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="a143c-161">**Datum narození**: Během příjmu dat doporučujeme převést datum narození na typ Datum a čas.</span><span class="sxs-lookup"><span data-stu-id="a143c-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="a143c-162">Alternativně to může být řetězec ve formátu [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) „rrrr-MM-dd“ nebo „rrrr-MM-ddTHH: mm: ssZ“.</span><span class="sxs-lookup"><span data-stu-id="a143c-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="a143c-163">**Pohlaví**: Muž, žena, neznámý</span><span class="sxs-lookup"><span data-stu-id="a143c-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="a143c-164">**PSČ**: Pětimístné PSČ pro USA, standardní PSČ všude jinde</span><span class="sxs-lookup"><span data-stu-id="a143c-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="a143c-165">**Město**: Název města v angličtině</span><span class="sxs-lookup"><span data-stu-id="a143c-165">**City**: City name in English</span></span>
- <span data-ttu-id="a143c-166">**Kraj**: Dvoupísmenná zkratka pro USA a Kanadu.</span><span class="sxs-lookup"><span data-stu-id="a143c-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="a143c-167">Dvou- nebo třípísmenná zkratka pro Austrálii.</span><span class="sxs-lookup"><span data-stu-id="a143c-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="a143c-168">Nelze použít ve Francii, Německu nebo Velké Británii.</span><span class="sxs-lookup"><span data-stu-id="a143c-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="a143c-169">**Země/oblast**:</span><span class="sxs-lookup"><span data-stu-id="a143c-169">**Country/Region**:</span></span>

  - <span data-ttu-id="a143c-170">US: Spojené státy americké, Spojené státy, USA, US, Amerika</span><span class="sxs-lookup"><span data-stu-id="a143c-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="a143c-171">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="a143c-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="a143c-172">GB: Spojené království, UK, Velká Británie, GB, Spojené království Velké Británie a Severního Irska, Spojené království Velké Británie</span><span class="sxs-lookup"><span data-stu-id="a143c-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="a143c-173">AU: Austrálie, AU, Australské společenství</span><span class="sxs-lookup"><span data-stu-id="a143c-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="a143c-174">FR: Francie, FR, Francouzská republika</span><span class="sxs-lookup"><span data-stu-id="a143c-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="a143c-175">DE: Německo, němčina, Deutschland, Allemagne, DE, Spolková republika Německo, Německo</span><span class="sxs-lookup"><span data-stu-id="a143c-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="a143c-176">Kontrola a pojmenování rozšíření</span><span class="sxs-lookup"><span data-stu-id="a143c-176">Review and name the enrichment</span></span>

<span data-ttu-id="a143c-177">Nakonec si přečtěte informace a uveďte název rozšíření.</span><span class="sxs-lookup"><span data-stu-id="a143c-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Stránka kontroly zájmů a pojmenování.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="a143c-179">Aktualizace rozšíření</span><span class="sxs-lookup"><span data-stu-id="a143c-179">Refresh enrichment</span></span>

<span data-ttu-id="a143c-180">Spusťte obohacení po konfiguraci značek, zájmů a mapování terénu pro demografii.</span><span class="sxs-lookup"><span data-stu-id="a143c-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="a143c-181">Chcete-li zahájit proces, vyberte **Spustit** na stránce konfigurace značek nebo zájmů.</span><span class="sxs-lookup"><span data-stu-id="a143c-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="a143c-182">Kromě toho můžete nechat systém spustit rozšíření automaticky jako součást plánované aktualizace.</span><span class="sxs-lookup"><span data-stu-id="a143c-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="a143c-183">V závislosti na velikosti vašich zákaznických dat může dokončení obohacování trvat několik minut.</span><span class="sxs-lookup"><span data-stu-id="a143c-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="a143c-184">Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy.</span><span class="sxs-lookup"><span data-stu-id="a143c-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a143c-185">Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a143c-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a143c-186">Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy.</span><span class="sxs-lookup"><span data-stu-id="a143c-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a143c-187">Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.</span><span class="sxs-lookup"><span data-stu-id="a143c-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a143c-188">Výsledky rozšíření</span><span class="sxs-lookup"><span data-stu-id="a143c-188">Enrichment results</span></span>

<span data-ttu-id="a143c-189">Po spuštění procesu rozšíření přejděte na **Moje rozšíření**, kde zkontrolujte celkový počet rozšířených zákazníků a rozpis značek nebo zájmů v rozšířených profilech zákazníků.</span><span class="sxs-lookup"><span data-stu-id="a143c-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Náhled výsledků po spuštění procesu rozšíření":::

<span data-ttu-id="a143c-191">Prohlédněte si obohacená data výběrem **Zobrazit obohacená data** v grafu.</span><span class="sxs-lookup"><span data-stu-id="a143c-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="a143c-192">Obohatená data pro značky obsahuje entita **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="a143c-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="a143c-193">Data pro zájmy jsou v entitě **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="a143c-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="a143c-194">Tyto entity najdete také ve skupině **Rozšíření** v umístění **Data** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="a143c-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="a143c-195">Zobrazení rozšíření dat na kartě zákazníka</span><span class="sxs-lookup"><span data-stu-id="a143c-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="a143c-196">Náklonnost ke značkám a zájmům lze zobrazit také na jednotlivých kartách zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a143c-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="a143c-197">Jděte na **Zákazníci** a vyberte profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a143c-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="a143c-198">Na kartě zákazníka najdete grafy značek nebo zájmů, ke kterým mají lidé v demografickém profilu zákazníka náklonnost.</span><span class="sxs-lookup"><span data-stu-id="a143c-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Karta zákazníka s rozšířenými daty":::

## <a name="next-steps"></a><span data-ttu-id="a143c-200">Další kroky</span><span class="sxs-lookup"><span data-stu-id="a143c-200">Next steps</span></span>

<span data-ttu-id="a143c-201">Stavte na svých obohacených zákaznických údajích.</span><span class="sxs-lookup"><span data-stu-id="a143c-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a143c-202">Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.</span><span class="sxs-lookup"><span data-stu-id="a143c-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
