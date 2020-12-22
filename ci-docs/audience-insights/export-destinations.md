---
title: Cíle exportu
description: Exportujte data a spravujte cíle exportu.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643855"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="ecc41-103">Cíle exportu (verze Preview)</span><span class="sxs-lookup"><span data-stu-id="ecc41-103">Export destinations (preview)</span></span>

<span data-ttu-id="ecc41-104">Stránka **Cíle exportu** zobrazuje všechna umístění, která jste nastavili pro export dat.</span><span class="sxs-lookup"><span data-stu-id="ecc41-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="ecc41-105">Můžete také přidat nové cíle pro export.</span><span class="sxs-lookup"><span data-stu-id="ecc41-105">You can also add new destinations for export.</span></span> <span data-ttu-id="ecc41-106">Kromě toho zobrazuje možnosti exportu, které jsou aktuálně k dispozici.</span><span class="sxs-lookup"><span data-stu-id="ecc41-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="ecc41-107">Získejte rychlý přehled, popis a zjistěte, co můžete dělat s každou možností rozšíření.</span><span class="sxs-lookup"><span data-stu-id="ecc41-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="ecc41-108">Exportujte sjednocené profily, míry a segmenty do podporovaných aplikací relevantních pro vaši firmu.</span><span class="sxs-lookup"><span data-stu-id="ecc41-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="ecc41-109">Přejděte na **Správce** > **Cíle exportu**, kde najdete následující možnosti rozšiřitelnosti:</span><span class="sxs-lookup"><span data-stu-id="ecc41-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="ecc41-110">Doplněk karty zákazníka Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ecc41-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="ecc41-111">Konektor Správce reklam na Facebooku</span><span class="sxs-lookup"><span data-stu-id="ecc41-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="ecc41-112">Konektor Power Automate</span><span class="sxs-lookup"><span data-stu-id="ecc41-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="ecc41-113">Konektor Power Apps</span><span class="sxs-lookup"><span data-stu-id="ecc41-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="ecc41-114">Konektor Power BI</span><span class="sxs-lookup"><span data-stu-id="ecc41-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="ecc41-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="ecc41-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="ecc41-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="ecc41-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="ecc41-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="ecc41-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="ecc41-118">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="ecc41-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="ecc41-119">Konektor LiveRamp &reg;</span><span class="sxs-lookup"><span data-stu-id="ecc41-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="ecc41-120">Bot pro Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ecc41-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="ecc41-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="ecc41-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="ecc41-122">Rozhraní API pro Customer Insights</span><span class="sxs-lookup"><span data-stu-id="ecc41-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="ecc41-123">Přidání nového cíle exportu</span><span class="sxs-lookup"><span data-stu-id="ecc41-123">Add a new export destination</span></span>

<span data-ttu-id="ecc41-124">Chcete-li přidat cíle exportu, musíte mít [oprávnění správce](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ecc41-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="ecc41-125">Pokud exportujete do služeb společnosti Microsoft, předpokládáme, že obě služby jsou ve stejné organizaci.</span><span class="sxs-lookup"><span data-stu-id="ecc41-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="ecc41-126">Přejděte na **Správce** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="ecc41-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ecc41-127">Přepněte na kartu **Moje cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="ecc41-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="ecc41-128">Vyberte **Přidat cíl**, chcete-li vytvořit nový cíl exportu.</span><span class="sxs-lookup"><span data-stu-id="ecc41-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="ecc41-129">V podokně **Přidat cíl** vyberte **Typ** cíle exportu v rozevíracím seznamu.</span><span class="sxs-lookup"><span data-stu-id="ecc41-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="ecc41-130">Zadejte požadované podrobnosti a vyberte **Další** pro vytvoření cílle exportu.</span><span class="sxs-lookup"><span data-stu-id="ecc41-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="ecc41-131">Můžete také vybrat **Založit** na dlaždici na kartě **Objevit**.</span><span class="sxs-lookup"><span data-stu-id="ecc41-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="ecc41-132">Zobrazit cíle exportu</span><span class="sxs-lookup"><span data-stu-id="ecc41-132">View Export destinations</span></span>

<span data-ttu-id="ecc41-133">Po vytvoření exportních cílů je najdete v tabulce na kartě **Moje cíle exportu**. Tato tabulka má tři sloupce:</span><span class="sxs-lookup"><span data-stu-id="ecc41-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="ecc41-134">**Zobrazovaný název**: Název, který jste zadali při vytváření cíle.</span><span class="sxs-lookup"><span data-stu-id="ecc41-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="ecc41-135">**Typ**: Typ cíle exportu, který jste nastavili při vytváření cíle.</span><span class="sxs-lookup"><span data-stu-id="ecc41-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="ecc41-136">**Vytvořeno**: Datum vytvoření cíle.</span><span class="sxs-lookup"><span data-stu-id="ecc41-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="ecc41-137">Úprava cíle exportu</span><span class="sxs-lookup"><span data-stu-id="ecc41-137">Edit an export destination</span></span>

1. <span data-ttu-id="ecc41-138">Vyberte vertikální tři tečky pro cíl exportu, který chcete upravit.</span><span class="sxs-lookup"><span data-stu-id="ecc41-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ecc41-139">![Vertikální tři tečky](media/export-destinations-page-ellipsis.png "Vertikální tři tečky")</span><span class="sxs-lookup"><span data-stu-id="ecc41-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="ecc41-140">V rozevírací nabídce vyberte **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="ecc41-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="ecc41-141">Změňte hodnoty, které vyžadují aktualizaci, a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="ecc41-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="ecc41-142">Export dat na vyžádání</span><span class="sxs-lookup"><span data-stu-id="ecc41-142">Export data on demand</span></span>

<span data-ttu-id="ecc41-143">Po konfiguraci konektoru pro cíl exportu bude export probíhat při každé [naplánované aktualizaci](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ecc41-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="ecc41-144">Chcete-li exportovat data bez čekání na naplánované obnovení, přejděte na kartu **Moje cíle exportu** na **Správce** > **Exportovat cíle**.</span><span class="sxs-lookup"><span data-stu-id="ecc41-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ecc41-145">![Vertikální tři tečky](media/export-destinations-page-ellipsis.png "Vertikální tři tečky")</span><span class="sxs-lookup"><span data-stu-id="ecc41-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="ecc41-146">Vyberte **Exportovat** nad seznamem, chcete-li spustit export do všech exportních cílů současně.</span><span class="sxs-lookup"><span data-stu-id="ecc41-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="ecc41-147">Vyberte tři tečky (...) za položkou seznamu a poté vyberte možnost **Exportovat** a spusťte export pro jeden cíl exportu.</span><span class="sxs-lookup"><span data-stu-id="ecc41-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="ecc41-148">Odebrání cíle exportu</span><span class="sxs-lookup"><span data-stu-id="ecc41-148">Remove an Export destination</span></span>

<span data-ttu-id="ecc41-149">Chcete-li odebrat cíl exportu, začněte na hlavní stránce **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="ecc41-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="ecc41-150">Vyberte vertikální tři tečky pro cíl exportu, který chcete odebrat.</span><span class="sxs-lookup"><span data-stu-id="ecc41-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ecc41-151">![Vertikální tři tečky](media/export-destinations-page-ellipsis.png "Vertikální tři tečky")</span><span class="sxs-lookup"><span data-stu-id="ecc41-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="ecc41-152">V rozevírací nabídce vyberte možnost **Odebrat**.</span><span class="sxs-lookup"><span data-stu-id="ecc41-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="ecc41-153">Potvrďte odebrání výběrem **Odstranit** na potvrzovací obrazovce.</span><span class="sxs-lookup"><span data-stu-id="ecc41-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
