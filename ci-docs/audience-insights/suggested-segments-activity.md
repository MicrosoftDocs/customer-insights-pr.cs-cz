---
title: Navrhované segmenty na základě aktivity.
description: Nechte strojové učení, aby vám našlo nové a zajímavé segmenty založené na aktivitě zákazníků.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034059"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="e7622-103">Navrhované segmenty na základě dat aktivity (náhled)</span><span class="sxs-lookup"><span data-stu-id="e7622-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="e7622-104">Objevte zajímavé segmenty svých zákazníků na základě údajů o aktivitě zákazníků, které jsou předány do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e7622-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="e7622-105">Příkladem údajů o aktivitě jsou transakce, doba trvání podpory hovoru, nákupy nebo vrácení.</span><span class="sxs-lookup"><span data-stu-id="e7622-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="e7622-106">Chcete-li navrhnout segmenty, data aktivity se analyzují z hlediska aktuálnosti, frekvence a peněžní hodnoty (nebo trvání).</span><span class="sxs-lookup"><span data-stu-id="e7622-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="e7622-107">Případně můžete generovat [navrhované segmenty ke zlepšení míry nebo lepšímu pochopení toho, co ovlivňuje atribut](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="e7622-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Karta Navrhované segmenty zobrazující návrhy segmentů pro segmenty založené na aktivitě a atributech.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="e7622-109">Kategorizace zákazníků podle aktivity</span><span class="sxs-lookup"><span data-stu-id="e7622-109">Categorize customers by activity</span></span>

<span data-ttu-id="e7622-110">S volbou [údaje o aktivitě](activities.md) dostupnou v Customer Insights můžeme generovat návrhy, které představují skupiny zákazníků:</span><span class="sxs-lookup"><span data-stu-id="e7622-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="e7622-111">většina aktivních zákazníků</span><span class="sxs-lookup"><span data-stu-id="e7622-111">most active customers</span></span> 
- <span data-ttu-id="e7622-112">zákazníci, kteří uskutečnili nejvíce nákupů</span><span class="sxs-lookup"><span data-stu-id="e7622-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="e7622-113">zákazníci, kteří generovali největší tržby</span><span class="sxs-lookup"><span data-stu-id="e7622-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="e7622-114">zákazníci, kteří v poslední době nebyli aktivní</span><span class="sxs-lookup"><span data-stu-id="e7622-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="e7622-115">zákazníci, kteří často komunikují s vaší firmou</span><span class="sxs-lookup"><span data-stu-id="e7622-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="e7622-116">Pokud podnikáte v maloobchodě, můžete zjistit, kteří zákazníci generují největší tržby, a odměnit je kupónem.</span><span class="sxs-lookup"><span data-stu-id="e7622-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="e7622-117">Nebo můžete identifikovat příležitostné zákazníky a nabídnout jim, aby se připojili k programu odměn, aby vaši firmu navštěvovali častěji.</span><span class="sxs-lookup"><span data-stu-id="e7622-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="e7622-118">Pokud podnikáte ve zdravotnictví a poskytujete veřejnou zdravotní péči, je vaším cílem minimalizovat výdaje jednotlivých pacientů.</span><span class="sxs-lookup"><span data-stu-id="e7622-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="e7622-119">Způsobem, jak toho dosáhnout, může být snížení opakujících se návštěv poskytováním nejlepší možné péče při co nejmenším počtu návštěv.</span><span class="sxs-lookup"><span data-stu-id="e7622-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="e7622-120">V tomto případě je vaším cílem udržet nízkou frekvenci návštěv a minimalizovat opakující se náklady pro pacienty.</span><span class="sxs-lookup"><span data-stu-id="e7622-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="e7622-121">Nebo můžete identifikovat segmenty pacientů, kteří mají časté schůzky a vysoké opakující se náklady, a analyzovat tyto případy s cílem zlepšit léčbu jednotlivce.</span><span class="sxs-lookup"><span data-stu-id="e7622-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="e7622-122">Požadovaná data</span><span class="sxs-lookup"><span data-stu-id="e7622-122">Required data</span></span>

<span data-ttu-id="e7622-123">Návrhy se generují na základě vybraných vstupních údajů.</span><span class="sxs-lookup"><span data-stu-id="e7622-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="e7622-124">Profily zákazníků: Všichni zákazníci nebo členové konkrétního segmentu.</span><span class="sxs-lookup"><span data-stu-id="e7622-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="e7622-125">Časové období: minulý měsíc, minulý rok nebo jakýkoli vlastní časový rámec.</span><span class="sxs-lookup"><span data-stu-id="e7622-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="e7622-126">Typ aktivity: nákupy, maloobchodní transakce, online transakce, případy zákaznické podpory, předplatné atd.</span><span class="sxs-lookup"><span data-stu-id="e7622-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="e7622-127">Entita v Customer Insights, která obsahuje data aktivity: entita UnifiedActivity nebo entita pro konkrétní aktivitu.</span><span class="sxs-lookup"><span data-stu-id="e7622-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="e7622-128">Zahrnuté dimenze: Aktuálnost, frekvence nebo peněžní dimenze, v závislosti na vašich obchodních požadavcích.</span><span class="sxs-lookup"><span data-stu-id="e7622-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="e7622-129">Generování doporučovaných segmentů</span><span class="sxs-lookup"><span data-stu-id="e7622-129">Generate suggested segments</span></span>

1. <span data-ttu-id="e7622-130">Jděte na **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="e7622-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="e7622-131">Vyberte kartu **Návrhy (preview)**.</span><span class="sxs-lookup"><span data-stu-id="e7622-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="e7622-132">Vyberte **Najít nové návrhy** a vyberte **Zobrazit nebo očekávat chování zákazníků**.</span><span class="sxs-lookup"><span data-stu-id="e7622-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="e7622-133">Vyberte **Start** ke spuštění řízeného prostředí.</span><span class="sxs-lookup"><span data-stu-id="e7622-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="První krok průvodce konfigurací pro navrhovaný segment na základě aktivity.":::

1. <span data-ttu-id="e7622-135">Zadejte požadovaná vstupní data a pokračujte výběrem **Další**.</span><span class="sxs-lookup"><span data-stu-id="e7622-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="e7622-136">Vyberte zákazníky: Zahrňte všechny zákazníky nebo konkrétní segment.</span><span class="sxs-lookup"><span data-stu-id="e7622-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="e7622-137">Zvolte aktivitu: Vyberte typ aktivity a entity popisující aktivitu.</span><span class="sxs-lookup"><span data-stu-id="e7622-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="e7622-138">Předvolby: Nastavte časové období, které je třeba vzít v úvahu, faktory pro návrhy a mapujte atributy.</span><span class="sxs-lookup"><span data-stu-id="e7622-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="e7622-139">Zkontrolujte svůj vstup a vyberte **Spustit** ke spuštění modelu a generování návrhů.</span><span class="sxs-lookup"><span data-stu-id="e7622-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="e7622-140">V závislosti na počtu profilů zákazníků a vybraných aktivit může dokončení trvat několik minut.</span><span class="sxs-lookup"><span data-stu-id="e7622-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="e7622-141">Po vygenerování návrhů je můžete filtrovat podle dimenze nebo hodnoty, která vás nejvíce zajímá.</span><span class="sxs-lookup"><span data-stu-id="e7622-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="e7622-142">Zobrazení podrobností navrhovaného segmentu</span><span class="sxs-lookup"><span data-stu-id="e7622-142">View details of a suggested segment</span></span>

<span data-ttu-id="e7622-143">Jakmile jsou návrhy vygenerovány, najdete je v seznamu **Segmenty** > **Návrhy (náhled)** v sekci **Návrhy založené na aktivitě**.</span><span class="sxs-lookup"><span data-stu-id="e7622-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Rozšířený boční panel zobrazující podrobná data navrhovaného segmentu.":::

<span data-ttu-id="e7622-145">Vyberte **Zobrazit návrh** v navrhovaném segmentu pro zobrazení podrobností o tomto segmentu.</span><span class="sxs-lookup"><span data-stu-id="e7622-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="e7622-146">Postranní panel poskytuje podrobnosti, jako je rozsah každé dimenze ve srovnání s cílovou skupinou.</span><span class="sxs-lookup"><span data-stu-id="e7622-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="e7622-147">Rovněž zdůrazňuje počet potenciálních prvků v segmentu a odpovídající procento z celkového počtu zákazníků.</span><span class="sxs-lookup"><span data-stu-id="e7622-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="e7622-148">Pokud si chcete ponechat návrh jako segment, vyberte **Vytvořit segment**.</span><span class="sxs-lookup"><span data-stu-id="e7622-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="e7622-149">Uložení návrhu jako segmentu</span><span class="sxs-lookup"><span data-stu-id="e7622-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="e7622-150">Jděte na **Segmenty** > **Návrhy (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="e7622-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="e7622-151">Vyberte segment, který chcete uložit.</span><span class="sxs-lookup"><span data-stu-id="e7622-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="e7622-152">V postranním panelu vyberte **Vytvořit segment**.</span><span class="sxs-lookup"><span data-stu-id="e7622-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="e7622-153">Po uložení segmentu se zobrazí v seznamu segmentů na kartě **Všechny segmenty**. Nyní to může být [obnoveno nebo odstraněno jako jakýkoli jiný segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e7622-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="e7622-154">Nelze upravit podrobnosti segmentu.</span><span class="sxs-lookup"><span data-stu-id="e7622-154">You can't edit the segment details.</span></span> <span data-ttu-id="e7622-155">Můžete však změnit vstupní kritéria pro návrhy a generovat různé návrhy.</span><span class="sxs-lookup"><span data-stu-id="e7622-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="e7622-156">Aktualizace nebo úprava sadu návrhů</span><span class="sxs-lookup"><span data-stu-id="e7622-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="e7622-157">Jděte na **Segmenty** > **Návrhy (náhled)** a vyhledejte segment v části **Návrhy na základě aktivity**.</span><span class="sxs-lookup"><span data-stu-id="e7622-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="e7622-158">Volbou **Aktualizovat návrhy** aktualizujete návrhy při zachování konfigurovaných atributů.</span><span class="sxs-lookup"><span data-stu-id="e7622-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="e7622-159">Nebo vyberte **Upravit návrhy** pro úpravu nakonfigurovaných atributů.</span><span class="sxs-lookup"><span data-stu-id="e7622-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="e7622-160">Systém proces znovu spustí, vygeneruje návrhy segmentů na základě nejnovějších dat a nahradí aktuální návrhy.</span><span class="sxs-lookup"><span data-stu-id="e7622-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
