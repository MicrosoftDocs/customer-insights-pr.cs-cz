---
title: Vztahy mezi entitami a cesty k entitám
description: Vytvářejte a spravujte vztahy mezi entitami z více zdrojů dat.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595204"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="ceeb5-103">Vztahy mezi entitami</span><span class="sxs-lookup"><span data-stu-id="ceeb5-103">Relationships between entities</span></span>

<span data-ttu-id="ceeb5-104">Vztahy vám pomůžou propojit entity a generovat graf dat, když entity sdílejí společný identifikátor (cizí klíč), na který lze odkazovat z jedné entity do druhé.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="ceeb5-105">Připojené entity umožňují definovat segmenty a míry na základě více zdrojů dat.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="ceeb5-106">Existují dva typy vztahů.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-106">There are two types of relationships.</span></span> <span data-ttu-id="ceeb5-107">Neupravitelné systémové vztahy, které jsou vytvořeny automaticky, a vlastní vztahy vytvořené a nakonfigurované uživateli.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="ceeb5-108">Během procesů párování a sloučení jsou systémové vztahy vytvořeny na pozadí na základě inteligentního párování.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="ceeb5-109">Tyto vztahy pomáhají propojit záznamy profilu zákazníka se záznamy jiných odpovídajících entit.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="ceeb5-110">Následující diagram znázorňuje vytvoření tří systémových vztahů, když je entita zákazníka spárována s dalšími entitami k vytvoření konečné entity profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ceeb5-111">![Vytváření vztahu](media/relationships-entities-merge.png "Vytváření vztahu")</span><span class="sxs-lookup"><span data-stu-id="ceeb5-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="ceeb5-112">**Vztah *CustomerToContact*** byl vytvořen mezi entitou Zákazník a entitou Kontakt.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="ceeb5-113">Entita zákazníka získá klíčové pole **Contact_contactId**, které se vztahuje ke klíčovému poli entity Kontakt **contactId**.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="ceeb5-114">**Vztah *CustomerToAccount*** byl vytvořen mezi entitou Zákazník a entitou Obchodní vztah.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="ceeb5-115">Entita zákazníka získá klíčové pole **Account_accountId**, které se vztahuje ke klíčovému poli entity Obchodní vztah **accountId**.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="ceeb5-116">**Vztah *CustomerToWebAccount*** byl vytvořen mezi entitou Zákazník a entitou WebAccount.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="ceeb5-117">Entita zákazníka získá klíčové pole **WebAccount_webaccountId**, které se vztahuje ke klíčovému poli entity WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="ceeb5-118">Vytvoření vztahu</span><span class="sxs-lookup"><span data-stu-id="ceeb5-118">Create a relationship</span></span>

<span data-ttu-id="ceeb5-119">Definujte vlastní vztahy na stránce **Vztahy**.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="ceeb5-120">Každý vztah se skládá z entity Zdroj (entity, která drží cizí klíč) a entity Cíl (entity, na kterou cizí klíč zdrojové entity odkazuje).</span><span class="sxs-lookup"><span data-stu-id="ceeb5-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="ceeb5-121">V přehledech cílové skupiny přejděte na **Data** > **Vztahy**.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="ceeb5-122">Vyberte **Nový vztah**.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="ceeb5-123">V podokně **Přidat vztah** zadejte následující informace:</span><span class="sxs-lookup"><span data-stu-id="ceeb5-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ceeb5-124">![Zadat podrobnosti vztahu](media/relationships-add.png "Zadat podrobnosti vztahu")</span><span class="sxs-lookup"><span data-stu-id="ceeb5-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="ceeb5-125">**Název vztahu**: Název, který odráží účel vztahu (například **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="ceeb5-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="ceeb5-126">**Popis**: Popis vztahu.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="ceeb5-127">**Zdrojová entita**: Vyberte entitu, která se používá jako zdroj ve vztahu (například WebLog).</span><span class="sxs-lookup"><span data-stu-id="ceeb5-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="ceeb5-128">**Kardinalita**: Vyberte kardinalitu záznamů zdrojové entity.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="ceeb5-129">Například "mnoho" znamená, že více záznamů Weblog souvisí s jedním webovým účtem.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="ceeb5-130">**Pole zdrojového klíče**: Představuje pole cizího klíče ve zdrojové entitě.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="ceeb5-131">WebLog má například cizí klíčové pole **accountId**.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="ceeb5-132">**Cílová entita**: Vyberte entitu, která se používá jako cíl ve vztahu (například WebAccount).</span><span class="sxs-lookup"><span data-stu-id="ceeb5-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="ceeb5-133">**Cílová kardinalita**: Vyberte kardinalitu záznamů cílové entity.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="ceeb5-134">Například "jedna" znamená, že více záznamů Weblog souvisí s jedním webovým účtem.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="ceeb5-135">**Cílové klíčové pole**: Toto pole představuje klíčové pole cílové entity.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="ceeb5-136">WebAccount má například klíčové pole **accountId**.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="ceeb5-137">Podporovány jsou pouze vztahy N:1 a 1:1.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="ceeb5-138">Vztahy N:N lze vytvořit pomocí dvou vztahů N:1 a entity propojení (entita, která se používá k připojení zdrojové entity a cílové entity).</span><span class="sxs-lookup"><span data-stu-id="ceeb5-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="ceeb5-139">Odstranit vztah</span><span class="sxs-lookup"><span data-stu-id="ceeb5-139">Delete a relationship</span></span>

1. <span data-ttu-id="ceeb5-140">V přehledech cílové skupiny přejděte na **Data** > **Vztahy**.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="ceeb5-141">Zaškrtněte políčka u všech vztahů, které chcete odstranit.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="ceeb5-142">Vyberte **Odstranit** v horní části tabulky **Vztahy**.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="ceeb5-143">Odstranění potvrďte.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="ceeb5-144">Další krok</span><span class="sxs-lookup"><span data-stu-id="ceeb5-144">Next step</span></span>

<span data-ttu-id="ceeb5-145">Systém a vlastní vztahy se používají k vytvoření segmentů založených na více zdrojích dat, které již nejsou prosíceny.</span><span class="sxs-lookup"><span data-stu-id="ceeb5-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="ceeb5-146">Další informace najdete v tématu [Segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ceeb5-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]