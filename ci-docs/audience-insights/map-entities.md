---
title: Mapování entit pro sjednocení dat
description: Mapováním dat můžete vytvořit sjednocené profily zákazníků.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405388"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="da99a-103">Mapování entit a atributů</span><span class="sxs-lookup"><span data-stu-id="da99a-103">Map entities and attributes</span></span>

<span data-ttu-id="da99a-104">**Mapování** je první fáze procesu sjednocení dat v přehledech cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="da99a-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="da99a-105">Mapování se skládá ze tří fází:</span><span class="sxs-lookup"><span data-stu-id="da99a-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="da99a-106">*Výběr entity*: Identifikujte kombinovatelné entity, které vedou k datové sadě, s úplnějšími informacemi o vašich zákaznících.</span><span class="sxs-lookup"><span data-stu-id="da99a-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="da99a-107">*Výběr atributů*: U každé entity určete sloupce, které chcete zkombinovat a spárovat ve fázích *přiřazení* a *sloučení*.</span><span class="sxs-lookup"><span data-stu-id="da99a-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="da99a-108">Tyto sloupce se nazývají *Atributy*.</span><span class="sxs-lookup"><span data-stu-id="da99a-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="da99a-109">*Výběr primárního klíče a sémantického typu*: Pro každou entitu identifikujte atribut, který chcete definovat jako primární klíč pro danou entitu, a pro každý atribut identifikujte sémantický typ, který tento atribut nejlépe popisuje.</span><span class="sxs-lookup"><span data-stu-id="da99a-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="da99a-110">Další informace o obecném toku sjednocení dat naleznete na stránce [Sjednotit](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="da99a-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="da99a-111">Vyberte první entity</span><span class="sxs-lookup"><span data-stu-id="da99a-111">Select the first entities</span></span>

1. <span data-ttu-id="da99a-112">V přehledech cílové skupiny přejděte na **Data** > **Sjednocení** > **Mapování**.</span><span class="sxs-lookup"><span data-stu-id="da99a-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="da99a-113">Začněte fázi mapování výběrem možnosti **Vybrat entity**.</span><span class="sxs-lookup"><span data-stu-id="da99a-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="da99a-114">Vyberte entity a atributy, které chcete použít ve fázích *párování* a *sloučení*.</span><span class="sxs-lookup"><span data-stu-id="da99a-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="da99a-115">Můžete vybrat požadované atributy jednotlivě z entity nebo zahrnout všechny atributy z entity zaškrtnutím políčka **Zahrnout všechna pole** na úrovni entity.</span><span class="sxs-lookup"><span data-stu-id="da99a-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="da99a-116">Doporučujeme vybrat alespoň dvě entity, aby bylo možné proces sjednocení dat používat výhodně.</span><span class="sxs-lookup"><span data-stu-id="da99a-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="da99a-117">![Přiklad Přidat entity](media/data-manager-configure-map-add-entities-example.png "Přiklad Přidat entity")</span><span class="sxs-lookup"><span data-stu-id="da99a-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="da99a-118">V tomto příkladu přidáváme entity **eCommerceContacts** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="da99a-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="da99a-119">Výběrem těchto entit můžete získat přehled, kteří z online obchodních zákazníků jsou členy věrnostního programu.</span><span class="sxs-lookup"><span data-stu-id="da99a-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="da99a-120">Můžete vyhledávat klíčová slova ve všech atributech a entitách a vybrat požadované atributy, které chcete mapovat.</span><span class="sxs-lookup"><span data-stu-id="da99a-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="da99a-121">![Příklad vyhledávacích polí](media/data-manager-configure-map-search-fields-example.png "Příklad vyhledávacích polí")</span><span class="sxs-lookup"><span data-stu-id="da99a-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="da99a-122">Volbou **Použít** potvrďte svůj výběr.</span><span class="sxs-lookup"><span data-stu-id="da99a-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="da99a-123">Výběr primárního klíče a sémantického typu pro atributy</span><span class="sxs-lookup"><span data-stu-id="da99a-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="da99a-124">Po výběru entit se zobrazí stránka **Mapa** s vybranými entitami pro vaši kontrolu.</span><span class="sxs-lookup"><span data-stu-id="da99a-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="da99a-125">Definujte primární klíč pro entitu a identifikujte sémantický typ pro atribut v entitě.</span><span class="sxs-lookup"><span data-stu-id="da99a-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="da99a-126">**Primární klíč**: Vyberte jeden atribut jako primární klíč pro každou ze svých entit.</span><span class="sxs-lookup"><span data-stu-id="da99a-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="da99a-127">Aby byl atribut platným primárním klíčem, nesmí obsahovat duplicitní hodnoty, chybějící hodnoty nebo hodnoty null.</span><span class="sxs-lookup"><span data-stu-id="da99a-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="da99a-128">Atributy datových typů řetězce, celého čísla a GUID jsou podporovány jako primární klíče a budou zobrazeny v poli, ze kterého si můžete vybrat.</span><span class="sxs-lookup"><span data-stu-id="da99a-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="da99a-129">**Sémantický typ atributu**: Kategorie vašich atributů, jako je e-mailová adresa nebo jméno.</span><span class="sxs-lookup"><span data-stu-id="da99a-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="da99a-130">Chcete-li použít modely AI pro inteligentní predikci sémantiky, ušetřit čas a zlepšit přesnost, nastavte **Inteligentní mapování** na **ZAPNUTO**.</span><span class="sxs-lookup"><span data-stu-id="da99a-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="da99a-131">Inteligentní mapování využívá doporučení sémantiky založené na AI v poli **Typ**.</span><span class="sxs-lookup"><span data-stu-id="da99a-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="da99a-132">Pokud ji nastavíte na **VYPNUTO**, uvidíte naše pravidelná doporučení pro mapování.</span><span class="sxs-lookup"><span data-stu-id="da99a-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="da99a-133">Z dostupného seznamu možností můžete vybrat libovolný sémantický typ a přepsat navrhovaný výběr.</span><span class="sxs-lookup"><span data-stu-id="da99a-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="da99a-134">![Typ atributu a sémantická predikce](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Typ atributu a sémantická predikce")</span><span class="sxs-lookup"><span data-stu-id="da99a-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="da99a-135">Je také možné přidat vlastní sémantický typ entity.</span><span class="sxs-lookup"><span data-stu-id="da99a-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="da99a-136">Vyberte pole typu pro atribut a zadejte název vlastního sémantického typu.</span><span class="sxs-lookup"><span data-stu-id="da99a-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="da99a-137">Tímto způsobem můžete také změnit typy atributů, které byly systémem identifikovány.</span><span class="sxs-lookup"><span data-stu-id="da99a-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="da99a-138">Všechny atributy, pro které je sémantický typ automaticky identifikován, jsou seskupeny v sekci **Kontrola mapovaných polí**.</span><span class="sxs-lookup"><span data-stu-id="da99a-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="da99a-139">Zkontrolujte tyto atributy a jejich sémantické typy, protože se použijí ke sloučení vašich entit v kroku sloučení během sjednocení dat.</span><span class="sxs-lookup"><span data-stu-id="da99a-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="da99a-140">Atributy, které nejsou automaticky mapovány na sémantický typ, jsou seskupeny v sekci **Definování dat v nemapovaných polích**.</span><span class="sxs-lookup"><span data-stu-id="da99a-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="da99a-141">Vyberte pole sémantického typu pro nemapované atributy nebo zadejte vlastní název typu atributu.</span><span class="sxs-lookup"><span data-stu-id="da99a-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="da99a-142">![Primární klíč a typ atributu](media/data-manager-configure-map-add-attributes.png "Primární klíč a typ atributu")</span><span class="sxs-lookup"><span data-stu-id="da99a-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="da99a-143">Jedno pole by se mělo namapovat na sémantický typ Person.FullName k naplnění jména zákazníka na kartě zákazníka.</span><span class="sxs-lookup"><span data-stu-id="da99a-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="da99a-144">Jinak se zákaznické karty objeví beze jména.</span><span class="sxs-lookup"><span data-stu-id="da99a-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="da99a-145">Přidání a odebrání atributů a entit</span><span class="sxs-lookup"><span data-stu-id="da99a-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="da99a-146">V **Sjednocení** > **Mapování** vyberte **Upravit pole**.</span><span class="sxs-lookup"><span data-stu-id="da99a-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="da99a-147">V podokně **Upravit pole** přidejte nebo odeberte atributy a entity.</span><span class="sxs-lookup"><span data-stu-id="da99a-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="da99a-148">Vyhledejte nebo posunutím vyhledejte a vyberte své atributy a entity, které vás zajímají.</span><span class="sxs-lookup"><span data-stu-id="da99a-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="da99a-149">Nelze odebrat atribut nebo entitu, pokud již byly spárovány.</span><span class="sxs-lookup"><span data-stu-id="da99a-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="da99a-150">![Přidat či odebrat atributy](media/configure-data-map-edit.png "Přidat či odebrat atributy")</span><span class="sxs-lookup"><span data-stu-id="da99a-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="da99a-151">Vyberte **Použít**.</span><span class="sxs-lookup"><span data-stu-id="da99a-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="da99a-152">Přidání obrázků do profilů</span><span class="sxs-lookup"><span data-stu-id="da99a-152">Add images to profiles</span></span>

<span data-ttu-id="da99a-153">Pokud entita obsahuje adresy URL pro veřejně dostupné profily nebo loga profilů, můžete je přidat do sjednoceného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="da99a-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="da99a-154">Vyberte entitu a najděte pole, které obsahuje adresu URL obrázku profilu.</span><span class="sxs-lookup"><span data-stu-id="da99a-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="da99a-155">V poli **Typ** ručně zadejte následující hodnotu:</span><span class="sxs-lookup"><span data-stu-id="da99a-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="da99a-156">Pro osobu: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="da99a-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="da99a-157">Pro organizaci: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="da99a-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="da99a-158">Pokračujte v krocích sjednocení a zajistěte, aby atribut, který obsahuje adresu URL obrázku, byl také přidán v kroku [Sloučení](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="da99a-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="da99a-159">Nastavení atributů pro organizace</span><span class="sxs-lookup"><span data-stu-id="da99a-159">Set attributes for organizations</span></span>

<span data-ttu-id="da99a-160">U organizací (Preview) by měl být typ atributu mapován na „Organization.Name“</span><span class="sxs-lookup"><span data-stu-id="da99a-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="da99a-161">![Primární klíč a typ atributu B2B](media/configure-data-map-edit-b2b.png "Primární klíč a typ atributu B2B")</span><span class="sxs-lookup"><span data-stu-id="da99a-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="da99a-162">Další krok</span><span class="sxs-lookup"><span data-stu-id="da99a-162">Next step</span></span>

<span data-ttu-id="da99a-163">V rámci procesu sjednocení údajů přejděte na stránku **Přiřazení**.</span><span class="sxs-lookup"><span data-stu-id="da99a-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="da99a-164">Návštivte [**Přiřazení**](match-entities.md) a získejte další informace o této fázi.</span><span class="sxs-lookup"><span data-stu-id="da99a-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="da99a-165">Podívejte se na následující video: [Začínáme: Vytvoření jednotného profilu zákazníka](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="da99a-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
