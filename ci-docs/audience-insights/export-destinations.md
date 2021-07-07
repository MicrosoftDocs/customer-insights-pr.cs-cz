---
title: Export dat ze služby Customer Insights
description: Spravujte exporty ke sdílení dat.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305470"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="aa9fb-103">Přehled exportů (Preview)</span><span class="sxs-lookup"><span data-stu-id="aa9fb-103">Exports (preview) overview</span></span>

<span data-ttu-id="aa9fb-104">Stránka **Export** zobrazuje všechny nakonfigurované exporty.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="aa9fb-105">Exporty sdílejí konkrétní data s různými aplikacemi.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="aa9fb-106">Mohou zahrnovat zákaznické profily nebo entity, schémata a podrobnosti mapování.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="aa9fb-107">Každý export vyžaduje [připojení, které nastavil správce, ke správě ověřování a přístupu](connections.md).</span><span class="sxs-lookup"><span data-stu-id="aa9fb-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="aa9fb-108">Jděte na **Data** > **Exporty** pro zobrazení stránky exportů.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="aa9fb-109">Všechny uživatelské role mohou zobrazit nakonfigurované exporty.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-109">All user roles can view configured exports.</span></span> <span data-ttu-id="aa9fb-110">Pomocí vyhledávacího pole na panelu příkazů vyhledejte exporty podle jejich názvu, názvu připojení nebo typu připojení.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="aa9fb-111">Nastavení nového exportu</span><span class="sxs-lookup"><span data-stu-id="aa9fb-111">Set up a new export</span></span>

<span data-ttu-id="aa9fb-112">Chcete-li nastavit nebo upravit export, musíte mít k dispozici propojení.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="aa9fb-113">Propojení závisí na vaší [roli uživatele](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="aa9fb-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="aa9fb-114">Správci mají přístup ke všem propojením.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-114">Administrators have access to all connections.</span></span> <span data-ttu-id="aa9fb-115">Mohou také vytvářet nová propojení při nastavování exportu.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="aa9fb-116">Přispěvatelé mohou mít přístup ke konkrétním propojením.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="aa9fb-117">Závisí na správcích, kteří konfigurují a sdílejí propojení.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="aa9fb-118">Seznam exportů zobrazuje ve sloupci **Vaše oprávnění** údaj o tom, zda mohou přispěvatelé export upravovat nebo pouze zobrazit.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="aa9fb-119">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="aa9fb-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="aa9fb-120">Diváci mohou prohlížet pouze existující exporty, ale nemohou je vytvářet.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="aa9fb-121">Definování nového exportu</span><span class="sxs-lookup"><span data-stu-id="aa9fb-121">Define a new export</span></span>

1. <span data-ttu-id="aa9fb-122">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aa9fb-123">Pokud chcete vytvořit nový export, vyberte příkaz **Přidat export**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="aa9fb-124">V podokně **Nastavit export** vyberte, které propojení chcete použít.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="aa9fb-125">[Propojení](connections.md) jsou spravována správci.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="aa9fb-126">Zadejte požadované podrobnosti a výběrem **Uložit** vytvořte export.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="aa9fb-127">Definování nového exportu na základě existujícího exportu</span><span class="sxs-lookup"><span data-stu-id="aa9fb-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="aa9fb-128">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aa9fb-129">V seznamu exportů vyberte export, který chcete duplikovat.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="aa9fb-130">Výběrem příkazu **Vytvořit duplikát** na panelu příkazů otevřete podokno **Nastavit export** s podrobnostmi vybraného exportu.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="aa9fb-131">Zkontrolujte a upravte export a výběrem příkazu **Uložit** vytvořte nový export.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="aa9fb-132">Úprava exportu</span><span class="sxs-lookup"><span data-stu-id="aa9fb-132">Edit an export</span></span>

1. <span data-ttu-id="aa9fb-133">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aa9fb-134">V seznamu exportů vyberte export, který chcete upravit.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="aa9fb-135">V panelu příkazů vyberte **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="aa9fb-136">Změňte hodnoty, které chcete aktualizovat, a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="aa9fb-137">Zobrazení exportů a podrobností exportu</span><span class="sxs-lookup"><span data-stu-id="aa9fb-137">View exports and export details</span></span>

<span data-ttu-id="aa9fb-138">Po vytvoření jsou cíle exportu uvedeny v části **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="aa9fb-139">Všichni uživatelé mohou vidět, která data jsou sdílena, a jejich nejnovější stav.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="aa9fb-140">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aa9fb-141">Vyberte uživatele bez oprávnění k úpravám **Zobrazit** namísto **Upravit**, abyste mohli zobrazit podrobnosti exportu.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="aa9fb-142">Postranní podokno ukazuje konfiguraci exportu.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="aa9fb-143">Bez oprávnění k úpravám nemůžete hodnoty měnit.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="aa9fb-144">Vyberte **Zavřít** pro návrat na stránku exportu.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="aa9fb-145">Plánování a spuštění exportů</span><span class="sxs-lookup"><span data-stu-id="aa9fb-145">Schedule and run exports</span></span>

<span data-ttu-id="aa9fb-146">Každý export, který konfigurujete, má plán aktualizace.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="aa9fb-147">Během aktualizace systém hledá nová nebo aktualizovaná data, která mají být zahrnuta do exportu.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="aa9fb-148">Ve výchozím nastavení jsou exporty spouštěny jako součást každé [plánované aktualizace systému](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="aa9fb-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="aa9fb-149">Plán aktualizace můžete upravit nebo jej vypnout, aby se exporty spouštěly ručně.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="aa9fb-150">Plány exportu závisí na stavu vašeho prostředí.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="aa9fb-151">Pokud probíhají aktualizace [závislostí](system.md#refresh-policies), když by měl začít plánovaný export, systém nejprve dokončí aktualizace a poté spustí export.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="aa9fb-152">Ve sloupci **Aktualizováno** vidíte, kdy byl export naposledy aktualizován.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="aa9fb-153">Plánování exportů</span><span class="sxs-lookup"><span data-stu-id="aa9fb-153">Schedule exports</span></span>

<span data-ttu-id="aa9fb-154">Můžete definovat vlastní plány aktualizací pro jednotlivé exporty nebo několik exportů najednou.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="aa9fb-155">Aktuálně definovaný plán je uveden ve sloupci **Plán** seznamu exportů.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="aa9fb-156">Oprávnění ke změně plánu je stejné jako u [úpravy a definování exportů](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="aa9fb-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="aa9fb-157">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aa9fb-158">Vyberte export, který chcete naplánovat.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="aa9fb-159">V panelu příkazů vyberte možnost **Plánovat**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="aa9fb-160">V podokně **Naplánovat export** nastavte vlastnost **Naplánovat spuštění** na **Zapnuto**, aby byl export spuštěn automaticky.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="aa9fb-161">Nastavte tuto možnost na **Vypnuto**, chcete-li aktualizovat ručně.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="aa9fb-162">U automaticky aktualizovaných exportů zvolte hodnotu **Opakování** a zadejte její podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="aa9fb-163">Definovaný čas platí pro všechny instance opakování.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="aa9fb-164">Je to čas, kdy by se měl export začít aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="aa9fb-165">Změny použijte a aktivujte výběrem příkazu **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="aa9fb-166">Při úpravách plánu pro několik exportů je třeba provést výběr v poli **Zachovat nebo přepsat plány**:</span><span class="sxs-lookup"><span data-stu-id="aa9fb-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="aa9fb-167">**Zachovat jednotlivé plány**: Zachovat dříve definovaný plán pro vybrané exporty a pouze je deaktivovat nebo povolit.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="aa9fb-168">**Definujte nový plán pro všechny vybrané exporty**: Přepsat existující plány vybraných exportů.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="aa9fb-169">Spuštění exportů na vyžádání</span><span class="sxs-lookup"><span data-stu-id="aa9fb-169">Run exports on demand</span></span>

<span data-ttu-id="aa9fb-170">Chcete-li exportovat data bez čekání na plánované obnovení, přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="aa9fb-171">Chcete-li spustit všechny exporty, vyberte **Spustit vše** na panelu příkazů.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="aa9fb-172">Tato akce spustí pouze exporty, které mají aktivní plán.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="aa9fb-173">Chcete-li spustit jeden export, vyberte jej v seznamu a v panelu příkazů vyberte **Spustit**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="aa9fb-174">Takto spustíte export bez aktivního plánu.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="aa9fb-175">Odebrání exportu</span><span class="sxs-lookup"><span data-stu-id="aa9fb-175">Remove an Export</span></span>

1. <span data-ttu-id="aa9fb-176">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aa9fb-177">Vyberte export, který chcete odebrat.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="aa9fb-178">V panelu příkazů vyberte příkaz **Odebrat**.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="aa9fb-179">Potvrďte odebrání výběrem **Odstranit** na potvrzovací obrazovce.</span><span class="sxs-lookup"><span data-stu-id="aa9fb-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
