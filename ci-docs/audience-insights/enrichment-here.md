---
title: Rozšíření od třetí strany HERE Technologies
description: Obecné informace o rozšíření od třetí strany HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269506"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="3e1c4-103">Rozšíření profilů zákazníků od HERE Technologies (Preview)</span><span class="sxs-lookup"><span data-stu-id="3e1c4-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="3e1c4-104">HERE Technologies je společnost postavená na lokalizační platformě, která poskytuje data a služby týkající se umístění.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="3e1c4-105">Se službami rozšíření dat HERE Technologies můžete dosáhnout přesnějšího porozumění polohy svých zákazníků normalizací adres, získáním zeměpisné šířky a délky atd.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3e1c4-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="3e1c4-106">Prerequisites</span></span>

<span data-ttu-id="3e1c4-107">Chcete-li nakonfigurovat rozšíření společnosti HERE Technologies, musíte splnit následující předpoklady:</span><span class="sxs-lookup"><span data-stu-id="3e1c4-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3e1c4-108">Musíte mít aktivní předplatné HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="3e1c4-109">Chcete-li získat předplatné, můžete se [registrovat zde](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) nebo [kontaktujte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) přímo.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="3e1c4-110">Zjistěte více o HERE Technologies Location Enrichment.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="3e1c4-111">Máte klíč rozhraní API pro HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="3e1c4-112">Máte oprávnění pro [správu](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="3e1c4-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="3e1c4-113">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="3e1c4-113">Configuration</span></span>

1. <span data-ttu-id="3e1c4-114">Přejděte na **Data** > **Rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="3e1c4-115">Vyberte **Rozšířit moje data** na dlaždici HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3e1c4-116">![Dlaždice HERE Technologies](media/HERE-tile.png "Dlaždice HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="3e1c4-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="3e1c4-117">Zadejte aktivní **klíč rozhraní API pro HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="3e1c4-118">Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="3e1c4-119">Potvrďte oba vstupy výběrem **Připojit k HERE**.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="3e1c4-120">Vyberte **Přidat data** a zvolte **sadu zákaznických dat**, kterou chcete rozšířit o údaje o poloze od společnosti HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="3e1c4-121">Můžete vybrat entitu **Zákazník** k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Screenshot výběru sady zákaznických dat.":::

1. <span data-ttu-id="3e1c4-123">Zvolte, zda chcete mapovat pole na primární nebo sekundární adresu.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="3e1c4-124">Můžete zadat mapování polí pro obě adresy (například adresu domácnosti a adresu firmy) a profily pro obě adresy rozšířit samostatně.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="3e1c4-125">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-125">Select **Next**.</span></span>

1. <span data-ttu-id="3e1c4-126">Definujte, která pole z vašich sjednocených profilů se mají použít k vyhledání odpovídajících dat umístění od HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="3e1c4-127">Pole **Ulice 1** a **Poštovní směrovací číslo** jsou povinná pro vybranou primární a/nebo sekundární adresu.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="3e1c4-128">Pro vyšší přesnost shody lze přidat více polí.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3e1c4-129">![Stránka konfigurace rozšíření od HERE Technologies](media/enrichment-HERE-configuration.png "Stránka konfigurace rozšíření od HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="3e1c4-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="3e1c4-130">Vyberte **Použít** k dokončení mapování polí.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="3e1c4-131">Výsledky rozšíření</span><span class="sxs-lookup"><span data-stu-id="3e1c4-131">Enrichment results</span></span>

<span data-ttu-id="3e1c4-132">Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3e1c4-133">Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3e1c4-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3e1c4-134">Doba zpracování bude záviset na velikosti vašich zákaznických dat a dobách odezvy rozhraní API od HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="3e1c4-135">Po dokončení procesu obohacení můžete zkontrolovat nově obohacené údaje o zákaznických profilech v **Moje rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="3e1c4-136">Dále najdete čas poslední aktualizace a počet obohacených profilů.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3e1c4-137">Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3e1c4-138">Další kroky</span><span class="sxs-lookup"><span data-stu-id="3e1c4-138">Next steps</span></span>

<span data-ttu-id="3e1c4-139">Stavte na svých obohacených zákaznických údajích.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3e1c4-140">Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3e1c4-141">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="3e1c4-141">Data privacy and compliance</span></span>

<span data-ttu-id="3e1c4-142">Když povolíte Dynamics 365 Customer Insights přenos dat společnosti HERE Technologies, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3e1c4-143">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost HERE Technologies splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3e1c4-144">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3e1c4-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3e1c4-145">Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3e1c4-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]