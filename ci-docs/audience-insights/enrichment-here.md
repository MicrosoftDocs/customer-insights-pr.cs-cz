---
title: Rozšíření od třetí strany HERE Technologies
description: Obecné informace o rozšíření od třetí strany HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896043"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="a44c0-103">Rozšíření profilů zákazníků od HERE Technologies (Preview)</span><span class="sxs-lookup"><span data-stu-id="a44c0-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="a44c0-104">HERE Technologies je společnost postavená na lokalizační platformě, která poskytuje data a služby týkající se umístění.</span><span class="sxs-lookup"><span data-stu-id="a44c0-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="a44c0-105">Se službami rozšíření dat HERE Technologies můžete dosáhnout přesnějšího porozumění polohy svých zákazníků normalizací adres, získáním zeměpisné šířky a délky atd.</span><span class="sxs-lookup"><span data-stu-id="a44c0-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a44c0-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="a44c0-106">Prerequisites</span></span>

<span data-ttu-id="a44c0-107">Chcete-li nakonfigurovat rozšíření společnosti HERE Technologies, musíte splnit následující předpoklady:</span><span class="sxs-lookup"><span data-stu-id="a44c0-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a44c0-108">Musíte mít aktivní předplatné HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a44c0-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="a44c0-109">Chcete-li získat předplatné, můžete se [registrovat zde](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) nebo [kontaktujte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) přímo.</span><span class="sxs-lookup"><span data-stu-id="a44c0-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="a44c0-110">Zjistěte více o HERE Technologies Location Enrichment.</span><span class="sxs-lookup"><span data-stu-id="a44c0-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="a44c0-111">Zde je k dispozici [propojení](connections.md) HERE *nebo* máte oprávnění [správce](permissions.md#administrator) a klíč API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a44c0-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="a44c0-112">Konfigurace rozšíření</span><span class="sxs-lookup"><span data-stu-id="a44c0-112">Configure the enrichment</span></span>

1. <span data-ttu-id="a44c0-113">Přejděte na **Data** > **Rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="a44c0-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="a44c0-114">Vyberte **Rozšířit moje data** v dlaždici HERE Technologies a vyberte **Začít**.</span><span class="sxs-lookup"><span data-stu-id="a44c0-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a44c0-115">![Dlaždice HERE Technologies](media/HERE-tile.png "Dlaždice HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="a44c0-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="a44c0-116">V rozevíracím seznamu vyberte [propojení](connections.md).</span><span class="sxs-lookup"><span data-stu-id="a44c0-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="a44c0-117">Pokud není k dispozici propojení, kontaktujte správce.</span><span class="sxs-lookup"><span data-stu-id="a44c0-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="a44c0-118">Pokud jste správce, můžete vytvořit propojení výběrem možnosti **Přidat propojení**.</span><span class="sxs-lookup"><span data-stu-id="a44c0-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="a44c0-119">V rozevírací nabídce zvolte **HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="a44c0-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="a44c0-120">Výběr připojení potvrďte výběrem **Připojit k HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="a44c0-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="a44c0-121">Vyberte **Další** a zvolte **datovou sadu zákazníka**, kterou chcete rozšířit o údaje o poloze od společnosti HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a44c0-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="a44c0-122">Můžete vybrat entitu **Zákazník** k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.</span><span class="sxs-lookup"><span data-stu-id="a44c0-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Screenshot výběru sady zákaznických dat.":::

1. <span data-ttu-id="a44c0-124">Zvolte, zda chcete mapovat pole na primární nebo sekundární adresu.</span><span class="sxs-lookup"><span data-stu-id="a44c0-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="a44c0-125">Můžete určit mapování polí pro obě adresy a profily pro obě adresy obohatit samostatně.</span><span class="sxs-lookup"><span data-stu-id="a44c0-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="a44c0-126">Například pokud existuje adresa domů a do zaměstnání.</span><span class="sxs-lookup"><span data-stu-id="a44c0-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="a44c0-127">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="a44c0-127">Select **Next**.</span></span>

1. <span data-ttu-id="a44c0-128">Definujte, která pole z vašich sjednocených profilů se mají použít k vyhledání odpovídajících dat umístění od HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a44c0-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="a44c0-129">Pole **Ulice 1** a **Poštovní směrovací číslo** jsou povinná pro vybranou primární a/nebo sekundární adresu.</span><span class="sxs-lookup"><span data-stu-id="a44c0-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="a44c0-130">Pro vyšší přesnost shody lze přidat více polí.</span><span class="sxs-lookup"><span data-stu-id="a44c0-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a44c0-131">![Stránka konfigurace rozšíření od HERE Technologies](media/enrichment-HERE-configuration.png "Stránka konfigurace rozšíření od HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="a44c0-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="a44c0-132">Výběrem možnosti **Další** dokončete mapování polí.</span><span class="sxs-lookup"><span data-stu-id="a44c0-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="a44c0-133">Zadejte jméno rozšíření.</span><span class="sxs-lookup"><span data-stu-id="a44c0-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="a44c0-134">1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="a44c0-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="a44c0-135">Konfigurace propojení pro HERE technologies</span><span class="sxs-lookup"><span data-stu-id="a44c0-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="a44c0-136">Abyste mohli konfigurovat propojení, musíte být správce.</span><span class="sxs-lookup"><span data-stu-id="a44c0-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="a44c0-137">Při konfiguraci rozšíření vyberte **Přidat připojení** *nebo* přejděte na **Správce** > **Připojení** a v dlaždici HERE Technologies vyberte **Nastavit**.</span><span class="sxs-lookup"><span data-stu-id="a44c0-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="a44c0-138">Do pole **Zobrazované jméno** zadejte jméno.</span><span class="sxs-lookup"><span data-stu-id="a44c0-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="a44c0-139">Zadejte platný klíč API společnosti HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a44c0-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="a44c0-140">Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.</span><span class="sxs-lookup"><span data-stu-id="a44c0-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="a44c0-141">Vyberte **Ověřit** k ověření konfigurace.</span><span class="sxs-lookup"><span data-stu-id="a44c0-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="a44c0-142">Po dokončení ověření vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="a44c0-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="a44c0-143">![Stránka konfigurace připojení pro HERE Technologies](media/enrichment-HERE-connection.png "Stránka konfigurace připojení pro HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="a44c0-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a44c0-144">Výsledky rozšíření</span><span class="sxs-lookup"><span data-stu-id="a44c0-144">Enrichment results</span></span>

<span data-ttu-id="a44c0-145">Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů.</span><span class="sxs-lookup"><span data-stu-id="a44c0-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a44c0-146">Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a44c0-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a44c0-147">Doba zpracování bude záviset na velikosti vašich zákaznických dat a dobách odezvy rozhraní API od HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a44c0-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="a44c0-148">Po dokončení procesu obohacení můžete zkontrolovat nově obohacené údaje o zákaznických profilech v **Moje rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="a44c0-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="a44c0-149">Dále najdete čas poslední aktualizace a počet obohacených profilů.</span><span class="sxs-lookup"><span data-stu-id="a44c0-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a44c0-150">Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.</span><span class="sxs-lookup"><span data-stu-id="a44c0-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a44c0-151">Další kroky</span><span class="sxs-lookup"><span data-stu-id="a44c0-151">Next steps</span></span>

<span data-ttu-id="a44c0-152">Stavte na svých obohacených zákaznických údajích.</span><span class="sxs-lookup"><span data-stu-id="a44c0-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a44c0-153">Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.</span><span class="sxs-lookup"><span data-stu-id="a44c0-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a44c0-154">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="a44c0-154">Data privacy and compliance</span></span>

<span data-ttu-id="a44c0-155">Když povolíte Dynamics 365 Customer Insights přenos dat společnosti HERE Technologies, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="a44c0-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a44c0-156">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost HERE Technologies splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="a44c0-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a44c0-157">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a44c0-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a44c0-158">Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a44c0-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
