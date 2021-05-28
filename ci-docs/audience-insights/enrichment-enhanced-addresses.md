---
title: Obohacení vylepšením adresy
description: Obohaťte a normalizujte informace o adresách profilů zákazníků s modely společnosti Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965570"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="69231-103">Obohacení profilů zákazníků o vylepšené adresy</span><span class="sxs-lookup"><span data-stu-id="69231-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="69231-104">Adresy ve vašich datech mohou být nestrukturované, neúplné nebo nesprávné.</span><span class="sxs-lookup"><span data-stu-id="69231-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="69231-105">Použijte modely společnosti Microsoft k normalizaci a obohacení vašich adres do [formátu Common Data Model](/common-data-model/schema/core/applicationcommon/address) pro lepší přesnost a přehledy.</span><span class="sxs-lookup"><span data-stu-id="69231-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="69231-106">Jak vylepšujeme adresy</span><span class="sxs-lookup"><span data-stu-id="69231-106">How we enhance addresses</span></span>

<span data-ttu-id="69231-107">Náš model prochází vylepšením adresy ve dvou krocích.</span><span class="sxs-lookup"><span data-stu-id="69231-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="69231-108">Nejprve analyzuje adresu, aby identifikovala její komponenty, a umístí je do strukturovaného formátu.</span><span class="sxs-lookup"><span data-stu-id="69231-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="69231-109">Poté pomocí umělé inteligence opravíme, doplníme a standardizujeme hodnoty v adrese.</span><span class="sxs-lookup"><span data-stu-id="69231-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="69231-110">Příklad</span><span class="sxs-lookup"><span data-stu-id="69231-110">Example</span></span>

<span data-ttu-id="69231-111">Informace o adrese mohou být v nestandardním formátu a mohou obsahovat pravopisné chyby.</span><span class="sxs-lookup"><span data-stu-id="69231-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="69231-112">Model může tyto problémy vyřešit a vytvořit konzistentní adresy v jednotných zákaznických profilech.</span><span class="sxs-lookup"><span data-stu-id="69231-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="69231-113">Omezení</span><span class="sxs-lookup"><span data-stu-id="69231-113">Limitations</span></span>

<span data-ttu-id="69231-114">Vylepšené adresy pracují pouze s hodnotami, které již existují v přijatých datech adres.</span><span class="sxs-lookup"><span data-stu-id="69231-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="69231-115">Model nikoliv:</span><span class="sxs-lookup"><span data-stu-id="69231-115">The model doesn't:</span></span> 

1. <span data-ttu-id="69231-116">Ověřte, zda je adresa platná.</span><span class="sxs-lookup"><span data-stu-id="69231-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="69231-117">Ověřte, zda jsou některé z hodnot, například PSČ nebo názvy ulic, platné.</span><span class="sxs-lookup"><span data-stu-id="69231-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="69231-118">Změňte hodnoty, které nerozpozná.</span><span class="sxs-lookup"><span data-stu-id="69231-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="69231-119">Model používá techniky založené na strojovém učení k vylepšení adres.</span><span class="sxs-lookup"><span data-stu-id="69231-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="69231-120">I když použijeme vysokou mezní hodnotu spolehlivosti, platí, že když model změní vstupní hodnotu, stejně jako u jakéhokoli modelu založeného na ML není zaručena 100% přesnost.</span><span class="sxs-lookup"><span data-stu-id="69231-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="69231-121">Podporované země nebo regiony</span><span class="sxs-lookup"><span data-stu-id="69231-121">Supported countries or regions</span></span>

<span data-ttu-id="69231-122">V současné době podporujeme obohacující adresy v těchto zemích nebo regionech:</span><span class="sxs-lookup"><span data-stu-id="69231-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="69231-123">Austrálie</span><span class="sxs-lookup"><span data-stu-id="69231-123">Australia</span></span>
- <span data-ttu-id="69231-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="69231-124">Canada</span></span>
- <span data-ttu-id="69231-125">Spojené království</span><span class="sxs-lookup"><span data-stu-id="69231-125">United Kingdom</span></span>
- <span data-ttu-id="69231-126">USA</span><span class="sxs-lookup"><span data-stu-id="69231-126">United States</span></span>

<span data-ttu-id="69231-127">Adresy musí obsahovat hodnotu země / oblasti.</span><span class="sxs-lookup"><span data-stu-id="69231-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="69231-128">Nezpracováváme adresy pro země nebo oblasti, které nejsou podporovány, a adresy, které nemají zadanou zemi nebo oblast.</span><span class="sxs-lookup"><span data-stu-id="69231-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="69231-129">Konfigurace rozšíření</span><span class="sxs-lookup"><span data-stu-id="69231-129">Configure the enrichment</span></span>

1. <span data-ttu-id="69231-130">Přejděte na **Data** > **Rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="69231-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="69231-131">Vyberte **Obohatit moje data** v dlaždici **Vylepšené adresy**.</span><span class="sxs-lookup"><span data-stu-id="69231-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Screenshot dlaždice Vylepšené adresy.":::

1. <span data-ttu-id="69231-133">Vyberte **Datová sada zákazníka** a vyberte entitu obsahující adresy, které chcete rozšířit.</span><span class="sxs-lookup"><span data-stu-id="69231-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="69231-134">Můžete vybrat entitu *Zákazník* k obohacení adres ve všech vašich zákaznických profilech nebo entitu segmentu k obohacení adres pouze v zákaznických profilech obsažených v tomto segmentu.</span><span class="sxs-lookup"><span data-stu-id="69231-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="69231-135">Vyberte způsob formátování adres v datové sadě.</span><span class="sxs-lookup"><span data-stu-id="69231-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="69231-136">Pokud adresy ve vašich datech používají jedno pole, zvolte **Adresa s jedním atributem**.</span><span class="sxs-lookup"><span data-stu-id="69231-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="69231-137">Pokud adresy ve vašich datech používají více než jedno datové pole, zvolte **Adresa s více atributy**.</span><span class="sxs-lookup"><span data-stu-id="69231-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="69231-138">Země / oblast je povinná u adresy s jedním i více atributy.</span><span class="sxs-lookup"><span data-stu-id="69231-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="69231-139">Adresy, které neobsahují platné nebo podporované hodnoty země / oblasti, nebudou obohaceny</span><span class="sxs-lookup"><span data-stu-id="69231-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="69231-140">Mapujte pole adresy z vaší sjednocené entity zákazníka.</span><span class="sxs-lookup"><span data-stu-id="69231-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Vylepšená stránka pro mapování polí adresy.":::

1. <span data-ttu-id="69231-142">Výběrem možnosti **Další** dokončete mapování polí.</span><span class="sxs-lookup"><span data-stu-id="69231-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="69231-143">Zadejte název obohacení a název výstupní entity.</span><span class="sxs-lookup"><span data-stu-id="69231-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="69231-144">Po kontrole vašich voleb vyberte **Uložit rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="69231-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="69231-145">Výsledky rozšíření</span><span class="sxs-lookup"><span data-stu-id="69231-145">Enrichment results</span></span>

<span data-ttu-id="69231-146">Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů.</span><span class="sxs-lookup"><span data-stu-id="69231-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="69231-147">Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="69231-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="69231-148">Doba zpracování závisí na velikosti vašich zákaznických dat.</span><span class="sxs-lookup"><span data-stu-id="69231-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="69231-149">Po dokončení procesu obohacení můžete zkontrolovat nově obohacené údaje o zákaznických profilech v **Moje rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="69231-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="69231-150">Dále najdete čas poslední aktualizace a počet obohacených profilů.</span><span class="sxs-lookup"><span data-stu-id="69231-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="69231-151">Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.</span><span class="sxs-lookup"><span data-stu-id="69231-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="69231-152">Další kroky</span><span class="sxs-lookup"><span data-stu-id="69231-152">Next steps</span></span>

<span data-ttu-id="69231-153">Stavte na svých obohacených zákaznických údajích.</span><span class="sxs-lookup"><span data-stu-id="69231-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="69231-154">Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.</span><span class="sxs-lookup"><span data-stu-id="69231-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
