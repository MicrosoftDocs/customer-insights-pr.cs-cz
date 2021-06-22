---
title: Vztahy mezi entitami a cesty k entitám
description: Vytvářejte a spravujte vztahy mezi entitami z více zdrojů dat.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171156"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="48627-103">Vztahy mezi entitami</span><span class="sxs-lookup"><span data-stu-id="48627-103">Relationships between entities</span></span>

<span data-ttu-id="48627-104">Vztahy propojují entity a definují graf dat, když entity sdílejí společný identifikátor (cizí klíč).</span><span class="sxs-lookup"><span data-stu-id="48627-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="48627-105">Na tento cizí klíč lze odkazovat z jedné entity do druhé.</span><span class="sxs-lookup"><span data-stu-id="48627-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="48627-106">Propojené entity umožňují definovat segmenty a míry na základě více zdrojů dat.</span><span class="sxs-lookup"><span data-stu-id="48627-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="48627-107">Existují tři typy vztahů:</span><span class="sxs-lookup"><span data-stu-id="48627-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="48627-108">Neupravitelné systémové vztahy, vytvořené systémem jako součást procesu sjednocení dat</span><span class="sxs-lookup"><span data-stu-id="48627-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="48627-109">Neupravitelné zděděné vztahy, které se vytvářejí automaticky během přijímání zdrojů dat</span><span class="sxs-lookup"><span data-stu-id="48627-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="48627-110">Upravitelné vlastní vztahy, vytvořené a konfigurované uživateli</span><span class="sxs-lookup"><span data-stu-id="48627-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="48627-111">Neupravitelné systémové vztahy</span><span class="sxs-lookup"><span data-stu-id="48627-111">Non-editable system relationships</span></span>

<span data-ttu-id="48627-112">Během sjednocení dat se automaticky vytvářejí systémové vztahy na základě inteligentního párování.</span><span class="sxs-lookup"><span data-stu-id="48627-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="48627-113">Tyto vztahy pomáhají propojit záznamy profilu zákazníka s odpovídajícími záznamy.</span><span class="sxs-lookup"><span data-stu-id="48627-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="48627-114">Následující diagram ilustruje vytvoření tří systémových vztahů.</span><span class="sxs-lookup"><span data-stu-id="48627-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="48627-115">Entita zákazníka je spárována s jinými entitami za účelem vytvoření sjednocené entity *Zákazník*.</span><span class="sxs-lookup"><span data-stu-id="48627-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram s cestami vztahů pro entitu zákazníka se třemi vztahy 1:N.":::

- <span data-ttu-id="48627-117">**Vztah *CustomerToContact*** byl vytvořen mezi entitou *Zákazník* a entitou *Kontakt*.</span><span class="sxs-lookup"><span data-stu-id="48627-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="48627-118">Entita *Zákazník* získá klíčové pole **Contact_contactID**, které se vztahuje ke klíčovému poli **contactID** entity *Kontakt*.</span><span class="sxs-lookup"><span data-stu-id="48627-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="48627-119">**Vztah *CustomerToAccount*** byl vytvořen mezi entitou *Zákazník* a entitou *Obchodní vztah*.</span><span class="sxs-lookup"><span data-stu-id="48627-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="48627-120">Entita *Zákazník* získá klíčové pole **Account_accountID**, které se vztahuje ke klíčovému poli **accountID** entity *Obchodní vztah*.</span><span class="sxs-lookup"><span data-stu-id="48627-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="48627-121">**Vztah *CustomerToWebAccount*** byl vytvořen mezi entitou *Zákazník* a entitou *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="48627-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="48627-122">Entita *Zákazník* získá klíčové pole **WebAccount_webaccountID**, které se vztahuje ke klíčovému poli **webaccountID** entity *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="48627-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="48627-123">Neupravitelné zděděné vztahy</span><span class="sxs-lookup"><span data-stu-id="48627-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="48627-124">Během procesu přijímání dat systém hledá ve zdrojích dat existující vztahy.</span><span class="sxs-lookup"><span data-stu-id="48627-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="48627-125">Pokud neexistuje žádný vztah, systém ho automaticky vytvoří.</span><span class="sxs-lookup"><span data-stu-id="48627-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="48627-126">Tyto vztahy se také používají v následných procesech.</span><span class="sxs-lookup"><span data-stu-id="48627-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="48627-127">Vytvoření vlastního vztahu</span><span class="sxs-lookup"><span data-stu-id="48627-127">Create a custom relationship</span></span>

<span data-ttu-id="48627-128">Vztah se skládá ze *zdrojové entity* obsahující cizí klíč a *cílové entity* na kterou cizí klíč zdrojové entity ukazuje.</span><span class="sxs-lookup"><span data-stu-id="48627-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="48627-129">V přehledech cílové skupiny přejděte na **Data** > **Vztahy**.</span><span class="sxs-lookup"><span data-stu-id="48627-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="48627-130">Vyberte **Nový vztah**.</span><span class="sxs-lookup"><span data-stu-id="48627-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="48627-131">V podokně **Nový vztah** zadejte následující informace:</span><span class="sxs-lookup"><span data-stu-id="48627-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Boční podokno Nový vztah s prázdnými vstupními poli.":::

   - <span data-ttu-id="48627-133">**Název vztahu**: Název, který vyjadřuje účel vztahu.</span><span class="sxs-lookup"><span data-stu-id="48627-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="48627-134">Příklad: CustomerToSupportCase (vztah mezi zákazníkem a případem podpory).</span><span class="sxs-lookup"><span data-stu-id="48627-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="48627-135">**Popis**: Popis vztahu.</span><span class="sxs-lookup"><span data-stu-id="48627-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="48627-136">**Zdrojová entita**: Entita, která se ve vztahu používá jako zdroj.</span><span class="sxs-lookup"><span data-stu-id="48627-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="48627-137">Příklad: SupportCase (případ podpory).</span><span class="sxs-lookup"><span data-stu-id="48627-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="48627-138">**Cílová entita**: Entita, která se ve vztahu používá jako cíl.</span><span class="sxs-lookup"><span data-stu-id="48627-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="48627-139">Příklad: Customer (zákazník).</span><span class="sxs-lookup"><span data-stu-id="48627-139">Example: Customer.</span></span>
   - <span data-ttu-id="48627-140">**Kardinalita zdroje**: Určete kardinalitu zdrojové entity.</span><span class="sxs-lookup"><span data-stu-id="48627-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="48627-141">Kardinalita popisuje počet možných prvků v sadě.</span><span class="sxs-lookup"><span data-stu-id="48627-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="48627-142">Vždy je ve vztahu ke kardinalitě cíle.</span><span class="sxs-lookup"><span data-stu-id="48627-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="48627-143">Můžete si vybrat hodnotu **Jeden** nebo **Mnoho**.</span><span class="sxs-lookup"><span data-stu-id="48627-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="48627-144">Podporovány jsou pouze vztahy N:1 a 1:1.</span><span class="sxs-lookup"><span data-stu-id="48627-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="48627-145">Vztah mnoha k jednomu jinému: Více zdrojových záznamů se může vztahovat k jednomu cílovému záznamu.</span><span class="sxs-lookup"><span data-stu-id="48627-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="48627-146">Příklad: Několik případů podpory od jednoho zákazníka.</span><span class="sxs-lookup"><span data-stu-id="48627-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="48627-147">Vztah jednoho k jednomu jinému: Jeden záznam zdroje se vztahuje k jednomu cílovému záznamu.</span><span class="sxs-lookup"><span data-stu-id="48627-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="48627-148">Příklad: Jedno věrnostní ID pro jednoho zákazníka.</span><span class="sxs-lookup"><span data-stu-id="48627-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="48627-149">Vztahy „mnoho k mnoha jiným“ lze vytvořit pomocí dvou vztahů „mnoho k jednomu“ a propojovací entity, která spojuje zdrojovou entitu a cílovou entitu.</span><span class="sxs-lookup"><span data-stu-id="48627-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="48627-150">**Cílová kardinalita**: Vyberte kardinalitu záznamů cílové entity.</span><span class="sxs-lookup"><span data-stu-id="48627-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="48627-151">**Pole zdrojového klíče**: Pole cizího klíče ve zdrojové entitě.</span><span class="sxs-lookup"><span data-stu-id="48627-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="48627-152">Příklad: SupportCase může použít CaseID jako pole cizího klíče.</span><span class="sxs-lookup"><span data-stu-id="48627-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="48627-153">**Pole cílového klíče**: Klíčové pole cílové entity.</span><span class="sxs-lookup"><span data-stu-id="48627-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="48627-154">Příklad: Customer může použít klíčové pole **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="48627-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="48627-155">Výběrem položky **Uložit** vytvoříte vlastní vztah.</span><span class="sxs-lookup"><span data-stu-id="48627-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="48627-156">Zobrazení vztahů</span><span class="sxs-lookup"><span data-stu-id="48627-156">View relationships</span></span>

<span data-ttu-id="48627-157">Stránka Vztahy uvádí seznam všech vztahů, které byly vytvořeny.</span><span class="sxs-lookup"><span data-stu-id="48627-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="48627-158">Každý řádek představuje vztah, který zahrnuje také podrobnosti o zdrojové entitě, cílové entitě a kardinalitě.</span><span class="sxs-lookup"><span data-stu-id="48627-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Seznam vztahů a možnosti na panelu akcí na stránce Vztahy.":::

<span data-ttu-id="48627-160">Tato stránka nabízí sadu možností pro stávající a nové vztahy:</span><span class="sxs-lookup"><span data-stu-id="48627-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="48627-161">**Nový vztah**: [Vytvoření vlastního vztahu](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="48627-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="48627-162">**Vizualizér** :[Prozkoumejte vizualizér vztahů](#explore-the-relationship-visualizer) a zobrazte si síťový diagram stávajících vztahů a jejich kardinalitu.</span><span class="sxs-lookup"><span data-stu-id="48627-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="48627-163">**Filtrovat podle**: Vyberte typ vztahů, které se mají zobrazit v seznamu.</span><span class="sxs-lookup"><span data-stu-id="48627-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="48627-164">**Vyhledat vztahy**: U vlastností vztahů použijte textové vyhledávání.</span><span class="sxs-lookup"><span data-stu-id="48627-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="48627-165">Prohlídka vizualizéru vztahů</span><span class="sxs-lookup"><span data-stu-id="48627-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="48627-166">Vizualizér vztahů zobrazuje si síťový diagram stávajících vztahů mezi propojenými entitami a jejich kardinalitu.</span><span class="sxs-lookup"><span data-stu-id="48627-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="48627-167">Chcete-li si zobrazení přizpůsobit, můžete změnit polohu polí jejich přetažením na plátně.</span><span class="sxs-lookup"><span data-stu-id="48627-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Snímek síťového diagramu vizualizátoru vztahů s propojením mezi souvisejícími entitami.":::

<span data-ttu-id="48627-169">Dostupné možnosti:</span><span class="sxs-lookup"><span data-stu-id="48627-169">Available options:</span></span> 
- <span data-ttu-id="48627-170">**Exportovat jako obrázek**: Uloží aktuální zobrazení jako obrazový soubor.</span><span class="sxs-lookup"><span data-stu-id="48627-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="48627-171">**Změnit na vodorovné/svislé rozložení**: Změňte zarovnání entit a vztahů.</span><span class="sxs-lookup"><span data-stu-id="48627-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="48627-172">**Upravit**: Aktualizujte vlastnosti vlastních vztahů v podokně úprav a uložte změny.</span><span class="sxs-lookup"><span data-stu-id="48627-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="48627-173">Správa existujících vztahů</span><span class="sxs-lookup"><span data-stu-id="48627-173">Manage existing relationships</span></span> 

<span data-ttu-id="48627-174">Na stránce Vztahy je každý vztah reprezentován řádkem.</span><span class="sxs-lookup"><span data-stu-id="48627-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="48627-175">Vyberte vztah a zvolte jednu z následujících možností:</span><span class="sxs-lookup"><span data-stu-id="48627-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="48627-176">**Upravit**: Aktualizujte vlastnosti vlastních vztahů v podokně úprav a uložte změny.</span><span class="sxs-lookup"><span data-stu-id="48627-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="48627-177">**Odstranit**: Odstranění vlastních vztahů.</span><span class="sxs-lookup"><span data-stu-id="48627-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="48627-178">**Zobrazit** : Zobrazení systémem vytvořených a zděděných vztahů.</span><span class="sxs-lookup"><span data-stu-id="48627-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="48627-179">Další krok</span><span class="sxs-lookup"><span data-stu-id="48627-179">Next step</span></span>

<span data-ttu-id="48627-180">Systémové a vlastní vztahy se používají k [vytvoření segmentů](segments.md) založených na více zdrojích dat, které již nejsou izolovány.</span><span class="sxs-lookup"><span data-stu-id="48627-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
