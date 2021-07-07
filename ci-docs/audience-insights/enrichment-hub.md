---
title: Rozšíření sjednocených profilů zákazníka
description: Využijte možnosti rozšíření svých zákaznických dat.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305240"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="3ea54-103">Rozšíření profilů zákazníků (náhled)</span><span class="sxs-lookup"><span data-stu-id="3ea54-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="3ea54-104">K rozšíření svých zákaznických dat použijte data ze zdrojů, jako je Microsoft a další partneři.</span><span class="sxs-lookup"><span data-stu-id="3ea54-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stránka centra obohacení":::

<span data-ttu-id="3ea54-106">V přehledech cílové skupiny přejděte na **Data** > **Rozšíření**, kde můžete pracovat s možnostmi rozšíření.</span><span class="sxs-lookup"><span data-stu-id="3ea54-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="3ea54-107">K vytváření nebo úpravě rozšíření musíte mít oprávnění přispěvatele nebo správce.</span><span class="sxs-lookup"><span data-stu-id="3ea54-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="3ea54-108">Další informace naleznete v části [Oprávnění](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3ea54-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="3ea54-109">Na kartě **Zjistit** najdete následující rozšíření:</span><span class="sxs-lookup"><span data-stu-id="3ea54-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="3ea54-110">[Značky](enrichment-microsoft.md) poskytované společností Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ea54-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="3ea54-111">[Zájmy](enrichment-microsoft.md) poskytované společností Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ea54-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="3ea54-112">[Vylepšené adresy](enrichment-enhanced-addresses.md) poskytované společností Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ea54-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="3ea54-113">[Údaje o společnosti](enrichment-leadspace.md) poskytované společností Leadspace</span><span class="sxs-lookup"><span data-stu-id="3ea54-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="3ea54-114">[Demografické údaje](enrichment-experian.md) poskytované společností Experian</span><span class="sxs-lookup"><span data-stu-id="3ea54-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="3ea54-115">[Údaje o poloze](enrichment-here.md) poskytované společností HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="3ea54-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="3ea54-116">[Vlastní data](enrichment-SFTP-custom-import.md) prostřednictvím vlastního importu protokolu (SFTP)</span><span class="sxs-lookup"><span data-stu-id="3ea54-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="3ea54-117">Na kartě **Moje rozšíření** se můžete podívat na rozšíření, která jste nakonfigurovali, a upravit jejich vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="3ea54-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="3ea54-118">Správa existujících rozšíření</span><span class="sxs-lookup"><span data-stu-id="3ea54-118">Manage existing enrichments</span></span>

<span data-ttu-id="3ea54-119">Jděte na kartu **Moje obohacení**, kde zobrazíte všechna nakonfigurovaná obohacení.</span><span class="sxs-lookup"><span data-stu-id="3ea54-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="3ea54-120">Každé rozšíření je uvedeno jako jeden jako řádek, který obsahuje další informace o rozšíření.</span><span class="sxs-lookup"><span data-stu-id="3ea54-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="3ea54-121">Výběrem rozšíření zobrazíte dostupné možnosti.</span><span class="sxs-lookup"><span data-stu-id="3ea54-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="3ea54-122">Můžete také vybrat tři tečky (...) na položce seznamu a zobrazit možnosti.</span><span class="sxs-lookup"><span data-stu-id="3ea54-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti správy rozšíření v seznamu rozšíření":::

- <span data-ttu-id="3ea54-124">Možností **Zobrazit** zobrazíte podrobnosti o rozšíření s počtem rozšířených profilů zákazníků.</span><span class="sxs-lookup"><span data-stu-id="3ea54-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="3ea54-125">Možností **Upravit** upravíte konfiguraci rozšíření.</span><span class="sxs-lookup"><span data-stu-id="3ea54-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="3ea54-126">**Spustit** rozšíření k aktualizaci profilů zákazníků o nejnovější data.</span><span class="sxs-lookup"><span data-stu-id="3ea54-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="3ea54-127">Možností **Deaktivovat** zastavíte automatické aktualizace rozšíření při každé plánované aktualizaci.</span><span class="sxs-lookup"><span data-stu-id="3ea54-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="3ea54-128">Data z poslední úspěšné aktualizace budou nadále k dispozici.</span><span class="sxs-lookup"><span data-stu-id="3ea54-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="3ea54-129">Možností **Aktivovat** restartujete automatické aktualizace rozšíření s každou plánovanou aktualizací.</span><span class="sxs-lookup"><span data-stu-id="3ea54-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="3ea54-130">**Odstranění** rozšíření.</span><span class="sxs-lookup"><span data-stu-id="3ea54-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="3ea54-131">Výběrem ze seznamu můžete spustit nebo deaktivovat více rozšíření najednou.</span><span class="sxs-lookup"><span data-stu-id="3ea54-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="3ea54-132">Možnosti zobrazení a úpravy nejsou k dispozici jako hromadná akce a fungují vždy jen pro jedno rozšíření.</span><span class="sxs-lookup"><span data-stu-id="3ea54-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="3ea54-133">Rozšíření a propojení </span><span class="sxs-lookup"><span data-stu-id="3ea54-133">Enrichments and connections</span></span>

<span data-ttu-id="3ea54-134">Rozšíření třetích stran se konfigurují pomocí [připojení](connections.md), které správce nastaví pomocí pověření a poskytne souhlas s datovými přenosy.</span><span class="sxs-lookup"><span data-stu-id="3ea54-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="3ea54-135">propojení mohou správci a přispěvatelé použít ke konfiguraci rozšíření.</span><span class="sxs-lookup"><span data-stu-id="3ea54-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="3ea54-136">Více rozšíření stejného typu</span><span class="sxs-lookup"><span data-stu-id="3ea54-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="3ea54-137">Entita, kterou chcete rozšířit, je zadána během konfigurace rozšíření, což vám umožní rozšířit pouze podmnožinu vašich profilů.</span><span class="sxs-lookup"><span data-stu-id="3ea54-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="3ea54-138">Například obohaťte data pouze pro konkrétní segment.</span><span class="sxs-lookup"><span data-stu-id="3ea54-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="3ea54-139">Můžete nakonfigurovat několik rozšíření stejného typu a znovu použít stejné propojení .</span><span class="sxs-lookup"><span data-stu-id="3ea54-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="3ea54-140">Některá rozšíření budou mít rozšíření počtu obohacení stejného typu, které lze vytvořit.</span><span class="sxs-lookup"><span data-stu-id="3ea54-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="3ea54-141">Limity a současné použití lze zobrazit na stránce **Rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="3ea54-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
