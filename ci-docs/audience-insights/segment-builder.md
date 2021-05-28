---
title: Vytvořit a spravovat segmenty
description: Vytvořte segmenty zákazníků a seskupte je podle různých atributů.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064929"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="8392a-103">Vytvořit a spravovat segmenty</span><span class="sxs-lookup"><span data-stu-id="8392a-103">Create and manage segments</span></span>

<span data-ttu-id="8392a-104">Definujte složité filtry kolem sjednocené entity zákazníka a souvisejících entit.</span><span class="sxs-lookup"><span data-stu-id="8392a-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="8392a-105">Každý segment po zpracování vytvoří sadu záznamů o zákaznících, které můžete exportovat a se kterými můžete provádět akce.</span><span class="sxs-lookup"><span data-stu-id="8392a-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="8392a-106">Segmenty jsou spravovány na stránce **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="8392a-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="8392a-107">Následující příklad ukazuje funkci segmentace.</span><span class="sxs-lookup"><span data-stu-id="8392a-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="8392a-108">Definovali jsme segment pro zákazníky, kteří si za posledních 90 dní objednali zboží alespoň za $500 *a* kteří se účastnili volání služby zákazníkům, které bylo eskalováno.</span><span class="sxs-lookup"><span data-stu-id="8392a-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Screenshot uživatelského rozhraní nástroje pro vytváření segmentů se dvěma skupinami, které určují segment zákazníka.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="8392a-110">Vytvořit nový segment</span><span class="sxs-lookup"><span data-stu-id="8392a-110">Create a new segment</span></span>

<span data-ttu-id="8392a-111">Existuje několik způsobů, jak vytvořit nový segment.</span><span class="sxs-lookup"><span data-stu-id="8392a-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="8392a-112">Tato část popisuje, jak vytvořit *prázdný segment*.</span><span class="sxs-lookup"><span data-stu-id="8392a-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="8392a-113">Můžete také vytvořit *rychlý segment* na základě existujících entit nebo využijte strojové učení modely k získání *navrhovaných segmentů*.</span><span class="sxs-lookup"><span data-stu-id="8392a-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="8392a-114">Další informace: [Přehled segmentů](segments.md)</span><span class="sxs-lookup"><span data-stu-id="8392a-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="8392a-115">Při vytváření segmentu můžete uložit koncept.</span><span class="sxs-lookup"><span data-stu-id="8392a-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="8392a-116">Bude uložen jako neaktivní segment a nelze jej aktivovat, dokud není dokončen s platnou konfigurací.</span><span class="sxs-lookup"><span data-stu-id="8392a-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="8392a-117">Přejde na stránku **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="8392a-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="8392a-118">Vybrat **Nový** > **Prázdný segmeny**.</span><span class="sxs-lookup"><span data-stu-id="8392a-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="8392a-119">V podokně **Nový segment** vyberte typ segmentu:</span><span class="sxs-lookup"><span data-stu-id="8392a-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="8392a-120">**Dynamické segmenty** [obnovení](segments.md#refresh-segments) podle opakujícího se plánu.</span><span class="sxs-lookup"><span data-stu-id="8392a-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="8392a-121">**Statické segmenty** se spustí jednou, když jej vytvoříte.</span><span class="sxs-lookup"><span data-stu-id="8392a-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="8392a-122">Poskytněte **název výstupní entity** pro daný segment.</span><span class="sxs-lookup"><span data-stu-id="8392a-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="8392a-123">Volitelně zadejte zobrazované jméno a popis, který pomáhá identifikovat segment.</span><span class="sxs-lookup"><span data-stu-id="8392a-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="8392a-124">Vyberte **Další**, chcete-li se dostat na stránku **Tvůrce segmentu**, kde definujete skupinu.</span><span class="sxs-lookup"><span data-stu-id="8392a-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="8392a-125">Skupina je sada zákazníků.</span><span class="sxs-lookup"><span data-stu-id="8392a-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="8392a-126">Zvolte entitu, která obsahuje atribut, který chcete zahrnout do segmentace.</span><span class="sxs-lookup"><span data-stu-id="8392a-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="8392a-127">Vyberte atribut, podle kterého chcete segmentovat.</span><span class="sxs-lookup"><span data-stu-id="8392a-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="8392a-128">Tento atribut může mít jeden ze čtyř typů hodnot: číselný, řetězec, datum nebo logický.</span><span class="sxs-lookup"><span data-stu-id="8392a-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="8392a-129">Zvolte operátor a hodnotu vybraného atributu.</span><span class="sxs-lookup"><span data-stu-id="8392a-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8392a-130">![Vlastní filtr skupin](media/customer-group-numbers.png "Filtr skupin zákazníků")</span><span class="sxs-lookup"><span data-stu-id="8392a-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="8392a-131">Počet</span><span class="sxs-lookup"><span data-stu-id="8392a-131">Number</span></span> |<span data-ttu-id="8392a-132">Definice</span><span class="sxs-lookup"><span data-stu-id="8392a-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="8392a-133">1</span><span class="sxs-lookup"><span data-stu-id="8392a-133">1</span></span>     |<span data-ttu-id="8392a-134">Entity</span><span class="sxs-lookup"><span data-stu-id="8392a-134">Entity</span></span>          |
   |<span data-ttu-id="8392a-135">2</span><span class="sxs-lookup"><span data-stu-id="8392a-135">2</span></span>     |<span data-ttu-id="8392a-136">Atribut</span><span class="sxs-lookup"><span data-stu-id="8392a-136">Attribute</span></span>          |
   |<span data-ttu-id="8392a-137">3</span><span class="sxs-lookup"><span data-stu-id="8392a-137">3</span></span>    |<span data-ttu-id="8392a-138">Operátor</span><span class="sxs-lookup"><span data-stu-id="8392a-138">Operator</span></span>         |
   |<span data-ttu-id="8392a-139">4</span><span class="sxs-lookup"><span data-stu-id="8392a-139">4</span></span>    |<span data-ttu-id="8392a-140">Hodnota</span><span class="sxs-lookup"><span data-stu-id="8392a-140">Value</span></span>         |

   1. <span data-ttu-id="8392a-141">Chcete-li do skupiny přidat další podmínky, můžete použít dva logické operátory:</span><span class="sxs-lookup"><span data-stu-id="8392a-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="8392a-142">Operátor **AND**: Obě podmínky musí být splněny v rámci procesu segmentace.</span><span class="sxs-lookup"><span data-stu-id="8392a-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="8392a-143">Tato možnost je nejužitečnější při definování podmínek mezi různými entitami.</span><span class="sxs-lookup"><span data-stu-id="8392a-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="8392a-144">Operátor **OR**: Buď je třeba splnit jednu z podmínek v rámci procesu segmentace.</span><span class="sxs-lookup"><span data-stu-id="8392a-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="8392a-145">Tato možnost je nejužitečnější při definování více podmínek pro stejnou entitu.</span><span class="sxs-lookup"><span data-stu-id="8392a-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="8392a-146">![Operátor OR, u kterého je třeba splnit obě podmínky](media/segmentation-either-condition.png "Operátor OR, u kterého je třeba splnit obě podmínky")</span><span class="sxs-lookup"><span data-stu-id="8392a-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="8392a-147">V současné době je možné vnořit operátor **OR** do operátoru **AND**, ale ne naopak.</span><span class="sxs-lookup"><span data-stu-id="8392a-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="8392a-148">Každá skupina odpovídá skupině zákazníků.</span><span class="sxs-lookup"><span data-stu-id="8392a-148">Each group matches set of customers.</span></span> <span data-ttu-id="8392a-149">Skupiny můžete kombinovat tak, aby zahrnovaly zákazníky požadované pro váš obchodní případ.</span><span class="sxs-lookup"><span data-stu-id="8392a-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="8392a-150">Vyberte **Přidat skupinu**.</span><span class="sxs-lookup"><span data-stu-id="8392a-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="8392a-151">![Skupina zákazníků přidat skupinu](media/customer-group-add-group.png "Skupina zákazníků přidat skupinu")</span><span class="sxs-lookup"><span data-stu-id="8392a-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="8392a-152">Vyberte jednoho z nastavených operátorů: **Union**, **Intersect** nebo **Except**.</span><span class="sxs-lookup"><span data-stu-id="8392a-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8392a-153">![Skupina zákazníků přidat sjednocení](media/customer-group-union.png "Skupina zákazníků přidat sjednocení")</span><span class="sxs-lookup"><span data-stu-id="8392a-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="8392a-154">**Sjednocení** sjednotí dvě skupiny.</span><span class="sxs-lookup"><span data-stu-id="8392a-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="8392a-155">**Průnik** překrývá dvě skupiny.</span><span class="sxs-lookup"><span data-stu-id="8392a-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="8392a-156">Pouze data, která *jsou společná* pro obě skupiny, zůstanou zachována ve sjednocené skupině.</span><span class="sxs-lookup"><span data-stu-id="8392a-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="8392a-157">**Výjimka** kombinuje dvě skupiny.</span><span class="sxs-lookup"><span data-stu-id="8392a-157">**Except** combines the two groups.</span></span> <span data-ttu-id="8392a-158">Pouze data ve skupině A, která *nejsou společná* s daty ve skupině B, zůstanou zachována.</span><span class="sxs-lookup"><span data-stu-id="8392a-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="8392a-159">Pokud je entita propojena se sjednocenou entitou zákazníka prostřednictvím [Vztahů](relationships.md), musíte definovat cestu vztahu k vytvoření platného segmentu.</span><span class="sxs-lookup"><span data-stu-id="8392a-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="8392a-160">Přidávejte entity z cesty vztahu, dokud nevyberete entitu **Zákazník: CustomerInsights** z rozevíracího seznamu.</span><span class="sxs-lookup"><span data-stu-id="8392a-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="8392a-161">Poté vyberte **Všechny záznamy** pro každý krok.</span><span class="sxs-lookup"><span data-stu-id="8392a-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8392a-162">![Cesta vztahů při vytváření segmentů](media/segments-multiple-relationships.png "Cesta vztahů při vytváření segmentů")</span><span class="sxs-lookup"><span data-stu-id="8392a-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="8392a-163">Ve výchozím nastavení segmenty generují výstupní entitu, která obsahuje všechny atributy profilů zákazníků, které odpovídají definovaným filtrům.</span><span class="sxs-lookup"><span data-stu-id="8392a-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="8392a-164">Pokud je segment založen na jiných entitách než *Zákazník*, můžete do výstupní entity přidat další atributy z těchto entit.</span><span class="sxs-lookup"><span data-stu-id="8392a-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="8392a-165">Volbou **Atributy projektu** zvolte atributy, které budou připojeny k výstupní entitě.</span><span class="sxs-lookup"><span data-stu-id="8392a-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="8392a-166">Příklad: Segment je založen na entitě, která obsahuje údaje o aktivitě zákazníka, která je provázána s entitou *Zákazník*.</span><span class="sxs-lookup"><span data-stu-id="8392a-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="8392a-167">Segment vyhledá všechny zákazníky, kteří volali na technickou podporu za posledních 60 dní.</span><span class="sxs-lookup"><span data-stu-id="8392a-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="8392a-168">Můžete se rozhodnout připojit délku hovoru a počet hovorů ke všem odpovídajícím záznamům zákazníků ve výstupní entitě.</span><span class="sxs-lookup"><span data-stu-id="8392a-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="8392a-169">Tyto informace mohou být užitečné k zaslání e-mailu s užitečnými odkazy na články online nápovědy a často kladené dotazy zákazníkům, kteří často volali.</span><span class="sxs-lookup"><span data-stu-id="8392a-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="8392a-170">Projektované atributy fungují pouze pro entity, které mají vztah jedna k mnoha s entitou zákazníka.</span><span class="sxs-lookup"><span data-stu-id="8392a-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="8392a-171">Například jeden zákazník může mít více předplatných.</span><span class="sxs-lookup"><span data-stu-id="8392a-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="8392a-172">Můžete projektovat pouze atributy z entity, která se používá v každé skupině segmentového dotazu, který vytváříte.</span><span class="sxs-lookup"><span data-stu-id="8392a-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="8392a-173">Při použití operátorů sady jsou zohledněny projektované atributy.</span><span class="sxs-lookup"><span data-stu-id="8392a-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="8392a-174">Výběrem možnosti **Uložit** uložte segment.</span><span class="sxs-lookup"><span data-stu-id="8392a-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="8392a-175">Pokud budou všechny požadavky ověřeny, bude váš segment uložen a zpracován.</span><span class="sxs-lookup"><span data-stu-id="8392a-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="8392a-176">V opačném případě bude uložen jako koncept.</span><span class="sxs-lookup"><span data-stu-id="8392a-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="8392a-177">Volbou **Zpět na segmenty** přejdete zpět na stránku **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="8392a-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="8392a-178">Rychlé segmenty</span><span class="sxs-lookup"><span data-stu-id="8392a-178">Quick segments</span></span>

<span data-ttu-id="8392a-179">Rychlé segmenty umožňují rychle vytvářet jednoduché segmenty jediným operátorem a získat tak rychlejší přehledy.</span><span class="sxs-lookup"><span data-stu-id="8392a-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="8392a-180">Na stránce **Segmenty** vyberte **Nový** > **Vytvořit z**.</span><span class="sxs-lookup"><span data-stu-id="8392a-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="8392a-181">Vyberte možnost **Profiley**, chcete-li vytvořit segment založený na entitě *sjednocený zákazník*.</span><span class="sxs-lookup"><span data-stu-id="8392a-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="8392a-182">Vyberte možnost **Míry**, pokud chcete vytvořit segment kolem měr, které jste dříve vytvořili.</span><span class="sxs-lookup"><span data-stu-id="8392a-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="8392a-183">Vyberte možnost **Analytické nástroje**, chcete-li sestavit segment kolem jedné z výstupních entit, které jste vygenerovali pomocí funkcí **Predikce** nebo **Vlastní modely**.</span><span class="sxs-lookup"><span data-stu-id="8392a-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="8392a-184">V dialogovém okně **Nový rychlý segment** vyberte atribut z rozbalovací nabídky **Pole**.</span><span class="sxs-lookup"><span data-stu-id="8392a-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="8392a-185">Systém vám poskytne další přehledy, které vám pomohou vytvořit lepší segmenty vašich zákazníků.</span><span class="sxs-lookup"><span data-stu-id="8392a-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="8392a-186">Pro kategorická pole zobrazíme 10 nejlepších zákazníků.</span><span class="sxs-lookup"><span data-stu-id="8392a-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="8392a-187">Vyberte **Hodnotu** a zvolte **Hodnotit**.</span><span class="sxs-lookup"><span data-stu-id="8392a-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="8392a-188">U číselného atributu systém zobrazí, jaká hodnota atributu spadá pod percentil každého zákazníka.</span><span class="sxs-lookup"><span data-stu-id="8392a-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="8392a-189">Zvolte **Operátor** a **Hodnotu** a pak vyberte **Zkontrolovat**.</span><span class="sxs-lookup"><span data-stu-id="8392a-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="8392a-190">Systém vám poskytne **Odhadovanou velikost segmentu**.</span><span class="sxs-lookup"><span data-stu-id="8392a-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="8392a-191">Můžete zvolit, zda chcete vygenerovat segment, který jste definovali, nebo jej nejprve znovu navštívit, abyste získali jinou velikost segmentu.</span><span class="sxs-lookup"><span data-stu-id="8392a-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8392a-192">![Název a odhad pro rychlý segment](media/quick-segment-name.png "Název a odhad pro rychlý segment")</span><span class="sxs-lookup"><span data-stu-id="8392a-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="8392a-193">Zadejte **Název** svého sgmentu.</span><span class="sxs-lookup"><span data-stu-id="8392a-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="8392a-194">Volitelně zadejte **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="8392a-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="8392a-195">Výběrem možnosti **Uložit** vytvořte segment.</span><span class="sxs-lookup"><span data-stu-id="8392a-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="8392a-196">Po dokončení zpracování segmentu jej můžete zobrazit jako jakýkoli jiný segment, který jste vytvořili.</span><span class="sxs-lookup"><span data-stu-id="8392a-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8392a-197">Další kroky</span><span class="sxs-lookup"><span data-stu-id="8392a-197">Next steps</span></span>

<span data-ttu-id="8392a-198">[Exportujtesegment](export-destinations.md) a prozkoumejte [Kartu zákazníka](customer-card-add-in.md) a [Konektory](export-power-bi.md), abyste získali přehled o úrovni zákazníka.</span><span class="sxs-lookup"><span data-stu-id="8392a-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
