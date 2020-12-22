---
title: Vztahy mezi entitami a cesty k entitám
description: Vytvářejte a spravujte vztahy mezi entitami z více zdrojů dat.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405397"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="dc669-103">Vztahy mezi entitami</span><span class="sxs-lookup"><span data-stu-id="dc669-103">Relationships between entities</span></span>

<span data-ttu-id="dc669-104">Vztahy vám pomůžou propojit entity a generovat graf dat, když entity sdílejí společný identifikátor (cizí klíč), na který lze odkazovat z jedné entity do druhé.</span><span class="sxs-lookup"><span data-stu-id="dc669-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="dc669-105">Připojené entity umožňují definovat segmenty a míry na základě více zdrojů dat.</span><span class="sxs-lookup"><span data-stu-id="dc669-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="dc669-106">Existují dva typy vztahů.</span><span class="sxs-lookup"><span data-stu-id="dc669-106">There are two types of relationships.</span></span> <span data-ttu-id="dc669-107">Neupravitelné systémové vztahy, které jsou vytvořeny automaticky, a vlastní vztahy vytvořené a nakonfigurované uživateli.</span><span class="sxs-lookup"><span data-stu-id="dc669-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="dc669-108">Během procesů párování a sloučení jsou systémové vztahy vytvořeny na pozadí na základě inteligentního párování.</span><span class="sxs-lookup"><span data-stu-id="dc669-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="dc669-109">Tyto vztahy pomáhají propojit záznamy profilu zákazníka se záznamy jiných odpovídajících entit.</span><span class="sxs-lookup"><span data-stu-id="dc669-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="dc669-110">Následující diagram znázorňuje vytvoření tří systémových vztahů, když je entita zákazníka spárována s dalšími entitami k vytvoření konečné entity profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="dc669-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dc669-111">![Vytváření vztahu](media/relationships-entities-merge.png "Vytváření vztahu")</span><span class="sxs-lookup"><span data-stu-id="dc669-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="dc669-112">**Vztah *CustomerToContact*** byl vytvořen mezi entitou Zákazník a entitou Kontakt.</span><span class="sxs-lookup"><span data-stu-id="dc669-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="dc669-113">Entita zákazníka získá klíčové pole **Contact_contactId**, které se vztahuje ke klíčovému poli entity Kontakt **contactId**.</span><span class="sxs-lookup"><span data-stu-id="dc669-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="dc669-114">**Vztah _CustomerToAccount_** byl vytvořen mezi entitou Zákazník a entitou Obchodní vztah.</span><span class="sxs-lookup"><span data-stu-id="dc669-114">**_CustomerToAccount_ relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="dc669-115">Entita zákazníka získá klíčové pole **Account_accountId**, které se vztahuje ke klíčovému poli entity Obchodní vztah **accountId**.</span><span class="sxs-lookup"><span data-stu-id="dc669-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="dc669-116">**Vztah _CustomerToWebAccount_** byl vytvořen mezi entitou Zákazník a entitou WebAccount.</span><span class="sxs-lookup"><span data-stu-id="dc669-116">**_CustomerToWebAccount_ relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="dc669-117">Entita zákazníka získá klíčové pole **WebAccount_webaccountId**, které se vztahuje ke klíčovému poli entity WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="dc669-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="dc669-118">Vytvoření vztahu</span><span class="sxs-lookup"><span data-stu-id="dc669-118">Create a relationship</span></span>

<span data-ttu-id="dc669-119">Definujte vlastní vztahy na stránce **Vztahy**.</span><span class="sxs-lookup"><span data-stu-id="dc669-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="dc669-120">Každý vztah se skládá z entity Zdroj (entity, která drží cizí klíč) a entity Cíl (entity, na kterou cizí klíč zdrojové entity odkazuje).</span><span class="sxs-lookup"><span data-stu-id="dc669-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="dc669-121">V přehledech cílové skupiny přejděte na **Data** > **Vztahy**.</span><span class="sxs-lookup"><span data-stu-id="dc669-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="dc669-122">Vyberte **Nový vztah**.</span><span class="sxs-lookup"><span data-stu-id="dc669-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="dc669-123">V podokně **Přidat vztah** zadejte následující informace:</span><span class="sxs-lookup"><span data-stu-id="dc669-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dc669-124">![Zadat podrobnosti vztahu](media/relationships-add.png "Zadat podrobnosti vztahu")</span><span class="sxs-lookup"><span data-stu-id="dc669-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="dc669-125">**Název vztahu**: Název, který odráží účel vztahu (například **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="dc669-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="dc669-126">**Popis**: Popis vztahu.</span><span class="sxs-lookup"><span data-stu-id="dc669-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="dc669-127">**Zdrojová entita**: Vyberte entitu, která se používá jako zdroj ve vztahu (například WebLog).</span><span class="sxs-lookup"><span data-stu-id="dc669-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="dc669-128">**Kardinalita**: Vyberte kardinalitu záznamů zdrojové entity.</span><span class="sxs-lookup"><span data-stu-id="dc669-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="dc669-129">Například "mnoho" znamená, že více záznamů Weblog souvisí s jedním webovým účtem.</span><span class="sxs-lookup"><span data-stu-id="dc669-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="dc669-130">**Pole zdrojového klíče**: Představuje pole cizího klíče ve zdrojové entitě.</span><span class="sxs-lookup"><span data-stu-id="dc669-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="dc669-131">WebLog má například cizí klíčové pole **accountId**.</span><span class="sxs-lookup"><span data-stu-id="dc669-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="dc669-132">**Cílová entita**: Vyberte entitu, která se používá jako cíl ve vztahu (například WebAccount).</span><span class="sxs-lookup"><span data-stu-id="dc669-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="dc669-133">**Cílová kardinalita**: Vyberte kardinalitu záznamů cílové entity.</span><span class="sxs-lookup"><span data-stu-id="dc669-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="dc669-134">Například "jedna" znamená, že více záznamů Weblog souvisí s jedním webovým účtem.</span><span class="sxs-lookup"><span data-stu-id="dc669-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="dc669-135">**Cílové klíčové pole**: Toto pole představuje klíčové pole cílové entity.</span><span class="sxs-lookup"><span data-stu-id="dc669-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="dc669-136">WebAccount má například klíčové pole **accountId**.</span><span class="sxs-lookup"><span data-stu-id="dc669-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="dc669-137">Podporovány jsou pouze vztahy N:1 a 1:1.</span><span class="sxs-lookup"><span data-stu-id="dc669-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="dc669-138">Vztahy N:N lze vytvořit pomocí dvou vztahů N:1 a entity propojení (entita, která se používá k připojení zdrojové entity a cílové entity).</span><span class="sxs-lookup"><span data-stu-id="dc669-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="dc669-139">Odstranit vztah</span><span class="sxs-lookup"><span data-stu-id="dc669-139">Delete a relationship</span></span>

1. <span data-ttu-id="dc669-140">V přehledech cílové skupiny přejděte na **Data** > **Vztahy**.</span><span class="sxs-lookup"><span data-stu-id="dc669-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="dc669-141">Zaškrtněte políčka u všech vztahů, které chcete odstranit.</span><span class="sxs-lookup"><span data-stu-id="dc669-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="dc669-142">Vyberte **Odstranit** v horní části tabulky **Vztahy**.</span><span class="sxs-lookup"><span data-stu-id="dc669-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="dc669-143">Odstranění potvrďte.</span><span class="sxs-lookup"><span data-stu-id="dc669-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="dc669-144">Další krok</span><span class="sxs-lookup"><span data-stu-id="dc669-144">Next step</span></span>

<span data-ttu-id="dc669-145">Systém a vlastní vztahy se používají k vytvoření segmentů založených na více zdrojích dat, které již nejsou prosíceny.</span><span class="sxs-lookup"><span data-stu-id="dc669-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="dc669-146">Další informace najdete v tématu [Segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="dc669-146">For more information, see [Segments](segments.md).</span></span>
