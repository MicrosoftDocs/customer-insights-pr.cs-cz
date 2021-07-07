---
title: Propojení k dalším službám z Customer Insights.
description: Sdílejte data s dalšími službami.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304964"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="c487b-103">Přehled propojení (preview)</span><span class="sxs-lookup"><span data-stu-id="c487b-103">Connections (preview) overview</span></span>

<span data-ttu-id="c487b-104">Propojení jsou klíčem k povolení sdílení dat do a z Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c487b-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="c487b-105">Každé propojení navazuje sdílení dat s konkrétní službou.</span><span class="sxs-lookup"><span data-stu-id="c487b-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="c487b-106">Propojení jsou základem [konfigurace rozšíření třetích stran](enrichment-hub.md) a [konfigurace exportů](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c487b-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="c487b-107">Stejné propojení lze použít vícekrát.</span><span class="sxs-lookup"><span data-stu-id="c487b-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="c487b-108">Například jedno propojení k Dynamics 365 Marketing funguje pro více exportů a jedno propojení Leadspace lze použít pro několik rozšíření.</span><span class="sxs-lookup"><span data-stu-id="c487b-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="c487b-109">Jděte na **Správce** > **Propojení** k vytvoření a zobrazení propojení.</span><span class="sxs-lookup"><span data-stu-id="c487b-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="c487b-110">Na kartě **Propojení** se zobrazují všechna aktivní propojení.</span><span class="sxs-lookup"><span data-stu-id="c487b-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="c487b-111">Seznam zobrazuje řádek pro každé propojení.</span><span class="sxs-lookup"><span data-stu-id="c487b-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="c487b-112">Získejte rychlý přehled, popis a zjistěte, co můžete dělat s každou možností rozšiřitelnosti na kartě **Objev**.</span><span class="sxs-lookup"><span data-stu-id="c487b-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="c487b-113">Exporty</span><span class="sxs-lookup"><span data-stu-id="c487b-113">Exports</span></span>

<span data-ttu-id="c487b-114">Pouze správci mohou konfigurovat nová propojení, ale mohou udělit přístup přispěvatelům k použití stávajících propojení.</span><span class="sxs-lookup"><span data-stu-id="c487b-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="c487b-115">Správci kontrolují, kam mohou data směřovat, přispěvatelé definují datovou část a frekvenci podle svých potřeb.</span><span class="sxs-lookup"><span data-stu-id="c487b-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="c487b-116">Další informace viz [Umožnění přispěvatelům použít připojení pro export](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c487b-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="c487b-117">Rozšíření</span><span class="sxs-lookup"><span data-stu-id="c487b-117">Enrichments</span></span>

<span data-ttu-id="c487b-118">Jenom správci mohou konfigurovat nová propojení, ale vytvořená propojení jsou vždy k dispozici správcům i přispěvatelům.</span><span class="sxs-lookup"><span data-stu-id="c487b-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="c487b-119">Správci spravují přihlašovací údaje a udělují souhlas s datovými přenosy.</span><span class="sxs-lookup"><span data-stu-id="c487b-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="c487b-120">Následně mohou správci i přispěvatelé propojení použít.</span><span class="sxs-lookup"><span data-stu-id="c487b-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="c487b-121">Přidat nové propojení</span><span class="sxs-lookup"><span data-stu-id="c487b-121">Add a new connection</span></span>

<span data-ttu-id="c487b-122">Chcete-li přidat propojení, musíte mít [oprávnění správce](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c487b-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="c487b-123">Pokud se připojíte k jiným službám společnosti Microsoft, předpokládáme, že jsou obě služby ve stejné organizaci.</span><span class="sxs-lookup"><span data-stu-id="c487b-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="c487b-124">Přejděte na **Správce** > **Propojení (náhled)**.</span><span class="sxs-lookup"><span data-stu-id="c487b-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="c487b-125">Přejde na kartu **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="c487b-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="c487b-126">Výběrem možnosti **Přidat propojení** vytvořte nové propojení.</span><span class="sxs-lookup"><span data-stu-id="c487b-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="c487b-127">Z rozbalovací nabídky vyberte, jaký typ připojení chcete vytvořit.</span><span class="sxs-lookup"><span data-stu-id="c487b-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="c487b-128">V podokně **Nastavení propojení** uveďte požadované podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="c487b-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="c487b-129">Propojení popisuje **zobrazované jméno** a typ propojení.</span><span class="sxs-lookup"><span data-stu-id="c487b-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="c487b-130">Doporučujeme zvolit název, který vysvětluje účel a cíl tohoto propojení.</span><span class="sxs-lookup"><span data-stu-id="c487b-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="c487b-131">Přesná pole závisí na tom, ke které službě se připojujete.</span><span class="sxs-lookup"><span data-stu-id="c487b-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="c487b-132">V článku o cílové službě se můžete dozvědět o podrobnostech konkrétního typu propojení.</span><span class="sxs-lookup"><span data-stu-id="c487b-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="c487b-133">Pokud chcete vytvořit propojení, vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="c487b-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="c487b-134">Můžete také vybrat **Založit** na dlaždici na kartě **Objevit**.</span><span class="sxs-lookup"><span data-stu-id="c487b-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="c487b-135">Umožnit přispěvatelům použít propojení pro export</span><span class="sxs-lookup"><span data-stu-id="c487b-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="c487b-136">Při nastavování nebo úpravách propojení pro export si vyberete, kterým uživatelům je povoleno definovat toto konkrétní propojení [exporty](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c487b-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="c487b-137">Ve výchozím nastavení je propojení k dispozici uživatelům s rolí správce.</span><span class="sxs-lookup"><span data-stu-id="c487b-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="c487b-138">Toto nastavení můžete změnit v části **Vyberte, kdo může toto propojení použít** a umožnit uživatelům s rolí přispěvatel používat toto propojení.</span><span class="sxs-lookup"><span data-stu-id="c487b-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="c487b-139">Přispěvatelé nebudou moci propojení zobrazit ani upravit.</span><span class="sxs-lookup"><span data-stu-id="c487b-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="c487b-140">Při vytváření exportu uvidí pouze zobrazované jméno a jeho typ.</span><span class="sxs-lookup"><span data-stu-id="c487b-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="c487b-141">Sdílením propojení umožňujete přispěvatelům propojení používat.</span><span class="sxs-lookup"><span data-stu-id="c487b-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="c487b-142">Přispěvatelé uvidí sdílená propojení, když nastaví export.</span><span class="sxs-lookup"><span data-stu-id="c487b-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="c487b-143">Mohou spravovat každý export, který používá toto konkrétní propojení.</span><span class="sxs-lookup"><span data-stu-id="c487b-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="c487b-144">Toto nastavení můžete změnit při zachování exportů, které již byly definovány přispěvateli.</span><span class="sxs-lookup"><span data-stu-id="c487b-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="c487b-145">Úprava propojení</span><span class="sxs-lookup"><span data-stu-id="c487b-145">Edit a connection</span></span>

1. <span data-ttu-id="c487b-146">Přejděte na **Správce** > **Propojení (náhled)**.</span><span class="sxs-lookup"><span data-stu-id="c487b-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="c487b-147">Přejde na kartu **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="c487b-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="c487b-148">Vyberte vertikální tři tečky pro cíl propojení, který chcete upravit.</span><span class="sxs-lookup"><span data-stu-id="c487b-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="c487b-149">Vyberte položku **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="c487b-149">Select **Edit**.</span></span>

1. <span data-ttu-id="c487b-150">Změňte hodnoty, které chcete aktualizovat, a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="c487b-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="c487b-151">Odebrání propojení</span><span class="sxs-lookup"><span data-stu-id="c487b-151">Remove a connection</span></span>

<span data-ttu-id="c487b-152">Pokud propojení, které odebíráte, používá rozšíření nebo export, musíte je nejprve odpojit nebo odebrat.</span><span class="sxs-lookup"><span data-stu-id="c487b-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="c487b-153">Dialogové okno odebrání vás provede příslušným rozšířením nebo exportem.</span><span class="sxs-lookup"><span data-stu-id="c487b-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="c487b-154">Oddělená rozšíření a exporty se stanou neaktivními.</span><span class="sxs-lookup"><span data-stu-id="c487b-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="c487b-155">Znovu je aktivujete přidáním dalšího propojení na stránce [Rozšíření](enrichment-hub.md) nebo [Exporty](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c487b-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="c487b-156">Přejděte na **Správce** > **Propojení (náhled)**.</span><span class="sxs-lookup"><span data-stu-id="c487b-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="c487b-157">Přejde na kartu **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="c487b-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="c487b-158">Vyberte vertikální tři tečky pro cíl propojení, který chcete odebrat.</span><span class="sxs-lookup"><span data-stu-id="c487b-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="c487b-159">V rozevírací nabídce vyberte možnost **Odebrat**.</span><span class="sxs-lookup"><span data-stu-id="c487b-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="c487b-160">Zobrazí se dialogové okno s potvrzením.</span><span class="sxs-lookup"><span data-stu-id="c487b-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="c487b-161">Pokud existují rozšíření nebo exporty, která toto propojení používají, vyberte tlačítko a podívejte se, co propojení používá.</span><span class="sxs-lookup"><span data-stu-id="c487b-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="c487b-162">**Exporty:** Můžete se rozhodnout buď odebrat nebo odpojit exporty, abyste mohli odebrat propojení.</span><span class="sxs-lookup"><span data-stu-id="c487b-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="c487b-163">Pro odpojení exportu mohou správci použít akci **Odpojit**.</span><span class="sxs-lookup"><span data-stu-id="c487b-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="c487b-164">Tato akce je k dispozici pro jednotlivé a více vybraných exportů.</span><span class="sxs-lookup"><span data-stu-id="c487b-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="c487b-165">Odpojením zachováte exportní konfiguraci, ale nebude spuštěna, dokud k ní nebude přidáno další propojení.</span><span class="sxs-lookup"><span data-stu-id="c487b-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="c487b-166">**Rozšíření:** Můžete se rozhodnout buď odebrat nebo deaktivovat rozšíření, abyste mohli odebrat propojení.</span><span class="sxs-lookup"><span data-stu-id="c487b-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="c487b-167">Jakmile propojení již nemá žádné závislosti, vraťte se zpět na **Správce** > **Propojení** a zkuste propojení znovu odebrat.</span><span class="sxs-lookup"><span data-stu-id="c487b-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="c487b-168">Odstranění potvrďte výběrem **Odstranit**.</span><span class="sxs-lookup"><span data-stu-id="c487b-168">To confirm the deletion, select **Remove**.</span></span>

