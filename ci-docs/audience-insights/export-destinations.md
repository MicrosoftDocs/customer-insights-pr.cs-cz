---
title: Export dat ze služby Customer Insights
description: Spravujte exporty ke sdílení dat.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896135"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="2285c-103">Přehled exportů (Preview)</span><span class="sxs-lookup"><span data-stu-id="2285c-103">Exports (preview) overview</span></span>

<span data-ttu-id="2285c-104">Stránka **Export** zobrazuje všechny nakonfigurované exporty.</span><span class="sxs-lookup"><span data-stu-id="2285c-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="2285c-105">Exporty sdílejí konkrétní data s různými aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="2285c-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="2285c-106">Mohou zahrnovat zákaznické profily nebo entity, schémata a podrobnosti mapování.</span><span class="sxs-lookup"><span data-stu-id="2285c-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="2285c-107">Každý export vyžaduje [připojení, které nastavil správce, ke správě ověřování a přístupu](connections.md).</span><span class="sxs-lookup"><span data-stu-id="2285c-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2285c-108">Do března 2021 exporty vytvářely propojení k odpovídající službě automaticky.</span><span class="sxs-lookup"><span data-stu-id="2285c-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="2285c-109">Export nyní vyžaduje [propojení, vytvořené a sdílené správcem](connections.md), než je budete moci vytvořit.</span><span class="sxs-lookup"><span data-stu-id="2285c-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="2285c-110">Jděte na **Data** > **Exporty** pro zobrazení stránky exportů.</span><span class="sxs-lookup"><span data-stu-id="2285c-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="2285c-111">Všechny uživatelské role mají přístup k zobrazení nakonfigurovaných exportů.</span><span class="sxs-lookup"><span data-stu-id="2285c-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="2285c-112">Pomocí vyhledávacího pole na panelu příkazů můžete najít exporty podle jejich názvu, názvu připojení nebo typu připojení.</span><span class="sxs-lookup"><span data-stu-id="2285c-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="2285c-113">Nastavení nového exportu</span><span class="sxs-lookup"><span data-stu-id="2285c-113">Set up a new export</span></span>

<span data-ttu-id="2285c-114">Chcete-li nastavit nebo upravit export, musíte mít k dispozici propojení.</span><span class="sxs-lookup"><span data-stu-id="2285c-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="2285c-115">Propojení závisí na vaší [roli uživatele](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="2285c-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="2285c-116">Správci mají přístup ke všem propojením.</span><span class="sxs-lookup"><span data-stu-id="2285c-116">Administrators have access to all connections.</span></span> <span data-ttu-id="2285c-117">Mohou také vytvářet nová propojení při nastavování exportu.</span><span class="sxs-lookup"><span data-stu-id="2285c-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="2285c-118">Přispěvatelé mohou mít přístup ke konkrétním propojením.</span><span class="sxs-lookup"><span data-stu-id="2285c-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="2285c-119">Závisí na správcích, kteří konfigurují a sdílejí propojení.</span><span class="sxs-lookup"><span data-stu-id="2285c-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="2285c-120">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2285c-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="2285c-121">Diváci mohou prohlížet pouze existující exporty, ale nemohou je vytvářet.</span><span class="sxs-lookup"><span data-stu-id="2285c-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="2285c-122">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="2285c-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2285c-123">Pokud chcete vytvořit nový cíl exportu, vyberte **Přidat export**.</span><span class="sxs-lookup"><span data-stu-id="2285c-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="2285c-124">V podokně **Nastavit export** vyberte, které propojení chcete použít.</span><span class="sxs-lookup"><span data-stu-id="2285c-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="2285c-125">[Propojení](connections.md) jsou spravována správci.</span><span class="sxs-lookup"><span data-stu-id="2285c-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="2285c-126">Zadejte požadované podrobnosti a výběrem **Uložit** vytvořte export.</span><span class="sxs-lookup"><span data-stu-id="2285c-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="2285c-127">Úprava exportu</span><span class="sxs-lookup"><span data-stu-id="2285c-127">Edit an export</span></span>

1. <span data-ttu-id="2285c-128">Vyberte vertikální tři tečky pro cíl exportu, který chcete upravit.</span><span class="sxs-lookup"><span data-stu-id="2285c-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="2285c-129">V rozevírací nabídce vyberte možnost **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="2285c-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="2285c-130">Změňte hodnoty, které chcete aktualizovat, a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="2285c-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="2285c-131">Zobrazení exportů a podrobností exportu</span><span class="sxs-lookup"><span data-stu-id="2285c-131">View Exports and export details</span></span>

<span data-ttu-id="2285c-132">Po vytvoření jsou cíle exportu uvedeny v části **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="2285c-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="2285c-133">Všichni uživatelé mohou vidět, která data jsou sdílena, a jejich nejnovější stav.</span><span class="sxs-lookup"><span data-stu-id="2285c-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="2285c-134">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="2285c-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2285c-135">Uživatelé bez oprávnění k úpravám mohou vybrat **Zobrazit** místo **Upravit** k zobrazení podrobností o exportu.</span><span class="sxs-lookup"><span data-stu-id="2285c-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="2285c-136">Toto boční podokno zobrazuje nastavení tohoto exportu.</span><span class="sxs-lookup"><span data-stu-id="2285c-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="2285c-137">Bez oprávnění k úpravám nemůžete hodnoty měnit.</span><span class="sxs-lookup"><span data-stu-id="2285c-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="2285c-138">Vyberte **Zavřít** pro návrat na stránku exportu.</span><span class="sxs-lookup"><span data-stu-id="2285c-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="2285c-139">Spuštění exportů na vyžádání</span><span class="sxs-lookup"><span data-stu-id="2285c-139">Run exports on demand</span></span>

<span data-ttu-id="2285c-140">Po konfiguraci exportu bude spuštěn s každým [plánovaným obnovením](system.md#schedule-tab), pokud má funkční připojení.</span><span class="sxs-lookup"><span data-stu-id="2285c-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="2285c-141">Chcete-li exportovat data bez čekání na plánované obnovení, přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="2285c-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="2285c-142">K dispozici jsou dvě možnosti:</span><span class="sxs-lookup"><span data-stu-id="2285c-142">You have two options:</span></span>

- <span data-ttu-id="2285c-143">Chcete-li spustit všechny exporty, vyberte **Spustit vše** na panelu příkazů.</span><span class="sxs-lookup"><span data-stu-id="2285c-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="2285c-144">Chcete-li spustit jeden export, vyberte tři tečky (...) u položky seznamu a poté vyberte **Spustit**.</span><span class="sxs-lookup"><span data-stu-id="2285c-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="2285c-145">Odebrání exportu</span><span class="sxs-lookup"><span data-stu-id="2285c-145">Remove an Export</span></span>

1. <span data-ttu-id="2285c-146">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="2285c-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2285c-147">Vyberte vertikální tři tečky pro export, který chcete odebrat.</span><span class="sxs-lookup"><span data-stu-id="2285c-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="2285c-148">V rozevírací nabídce vyberte možnost **Odebrat**.</span><span class="sxs-lookup"><span data-stu-id="2285c-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="2285c-149">Potvrďte odebrání výběrem **Odstranit** na potvrzovací obrazovce.</span><span class="sxs-lookup"><span data-stu-id="2285c-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
