---
title: Rozšíření sjednocených profilů zákazníka
description: Využijte možnosti rozšíření svých zákaznických dat.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269460"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="ce251-103">Rozšíření profilů zákazníků (náhled)</span><span class="sxs-lookup"><span data-stu-id="ce251-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="ce251-104">K rozšíření svých zákaznických dat použijte data ze zdrojů, jako je Microsoft a další partneři.</span><span class="sxs-lookup"><span data-stu-id="ce251-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra obohacení":::

<span data-ttu-id="ce251-106">V přehledech cílové skupiny přejděte na **Data** > **Rozšíření**, kde můžete pracovat s možnostmi rozšíření.</span><span class="sxs-lookup"><span data-stu-id="ce251-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="ce251-107">K vytváření nebo úpravě rozšíření musíte mít oprávnění přispěvatele nebo správce.</span><span class="sxs-lookup"><span data-stu-id="ce251-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="ce251-108">Další informace naleznete v části [Oprávnění](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ce251-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="ce251-109">Na kartě **Zjistit** najdete následující rozšíření:</span><span class="sxs-lookup"><span data-stu-id="ce251-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="ce251-110">[Značky](enrichment-microsoft-graph.md) poskytované produktem Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="ce251-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="ce251-111">[Zájmy](enrichment-microsoft-graph.md) poskytované produktem Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="ce251-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="ce251-112">[Údaje o společnosti](enrichment-leadspace.md) poskytované společností Leadspace</span><span class="sxs-lookup"><span data-stu-id="ce251-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="ce251-113">[Demografická data](enrichment-experian.md) poskytované společností Experian</span><span class="sxs-lookup"><span data-stu-id="ce251-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="ce251-114">[Údaje o poloze](enrichment-here.md) poskytované společností HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="ce251-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="ce251-115">[Vlastní data](enrichment-SFTP-custom-import.md) prostřednictvím vlastního importu protokolu (SFTP)</span><span class="sxs-lookup"><span data-stu-id="ce251-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="ce251-116">Na kartě **Moje rozšíření** se můžete podívat na rozšíření, která jste nakonfigurovali, a upravit jejich vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="ce251-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="ce251-117">Správa existujících rozšíření</span><span class="sxs-lookup"><span data-stu-id="ce251-117">Manage existing enrichments</span></span>

<span data-ttu-id="ce251-118">Přejděte do oblasti **Moje rozšíření**, kde se nacházejí všechna konfigurovaná rozšíření.</span><span class="sxs-lookup"><span data-stu-id="ce251-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="ce251-119">Každé rozšíření je uvedeno jako jeden jako řádek, který obsahuje další informace o rozšíření.</span><span class="sxs-lookup"><span data-stu-id="ce251-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="ce251-120">Výběrem rozšíření zobrazíte dostupné možnosti.</span><span class="sxs-lookup"><span data-stu-id="ce251-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="ce251-121">Alternativně můžete vybrat tři tečky (...) u položky seznamu a zobrazit možnosti.</span><span class="sxs-lookup"><span data-stu-id="ce251-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti správy rozšíření v seznamu rozšíření":::

- <span data-ttu-id="ce251-123">Možností **Zobrazit** zobrazíte podrobnosti o rozšíření s počtem rozšířených profilů zákazníků.</span><span class="sxs-lookup"><span data-stu-id="ce251-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="ce251-124">Možností **Upravit** upravíte konfiguraci rozšíření.</span><span class="sxs-lookup"><span data-stu-id="ce251-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="ce251-125">**Spustit** rozšíření k aktualizaci profilů zákazníků o nejnovější data.</span><span class="sxs-lookup"><span data-stu-id="ce251-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="ce251-126">Možností **Deaktivovat** zastavíte automatické aktualizace rozšíření při každé plánované aktualizaci.</span><span class="sxs-lookup"><span data-stu-id="ce251-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="ce251-127">Data z poslední úspěšné aktualizace budou nadále k dispozici.</span><span class="sxs-lookup"><span data-stu-id="ce251-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="ce251-128">Možností **Aktivovat** restartujete automatické aktualizace rozšíření s každou plánovanou aktualizací.</span><span class="sxs-lookup"><span data-stu-id="ce251-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="ce251-129">**Odstranění** rozšíření.</span><span class="sxs-lookup"><span data-stu-id="ce251-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="ce251-130">Výběrem ze seznamu můžete spustit nebo deaktivovat více rozšíření najednou.</span><span class="sxs-lookup"><span data-stu-id="ce251-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="ce251-131">Možnosti zobrazení a úpravy nejsou k dispozici jako hromadná akce a fungují vždy jen pro jedno rozšíření.</span><span class="sxs-lookup"><span data-stu-id="ce251-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]