---
title: Rozšíření od třetí strany HERE Technologies
description: Obecné informace o rozšíření od třetí strany HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668670"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="725c9-103">Rozšíření profilů zákazníků od HERE Technologies (Preview)</span><span class="sxs-lookup"><span data-stu-id="725c9-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="725c9-104">HERE Technologies je společnost postavená na lokalizační platformě, která poskytuje data a služby týkající se umístění.</span><span class="sxs-lookup"><span data-stu-id="725c9-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="725c9-105">Se službami rozšíření dat HERE Technologies můžete dosáhnout přesnějšího porozumění polohy svých zákazníků normalizací adres, získáním zeměpisné šířky a délky atd.</span><span class="sxs-lookup"><span data-stu-id="725c9-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="725c9-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="725c9-106">Prerequisites</span></span>

<span data-ttu-id="725c9-107">Chcete-li nakonfigurovat rozšíření společnosti HERE Technologies, musíte splnit následující předpoklady:</span><span class="sxs-lookup"><span data-stu-id="725c9-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="725c9-108">Musíte mít aktivní předplatné HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="725c9-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="725c9-109">Chcete-li získat předplatné, můžete se [registrovat zde](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) nebo [kontaktujte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) přímo.</span><span class="sxs-lookup"><span data-stu-id="725c9-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="725c9-110">Zjistěte více o HERE Technologies Location Enrichment.</span><span class="sxs-lookup"><span data-stu-id="725c9-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="725c9-111">Máte klíč rozhraní API pro HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="725c9-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="725c9-112">Máte oprávnění pro [správu](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="725c9-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="725c9-113">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="725c9-113">Configuration</span></span>

1. <span data-ttu-id="725c9-114">Přejděte na **Data** > **Rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="725c9-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="725c9-115">Vyberte **Rozšířit moje data** na dlaždici HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="725c9-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="725c9-116">![Dlaždice HERE Technologies](media/HERE-tile.png "Dlaždice HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="725c9-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="725c9-117">Zadejte aktivní **klíč rozhraní API pro HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="725c9-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="725c9-118">Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.</span><span class="sxs-lookup"><span data-stu-id="725c9-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="725c9-119">Potvrďte oba vstupy výběrem **Připojit k HERE**.</span><span class="sxs-lookup"><span data-stu-id="725c9-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="725c9-120">Vyberte **Přidat data** a zvolte, zda chcete mapovat pole na primární nebo sekundární adresu.</span><span class="sxs-lookup"><span data-stu-id="725c9-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="725c9-121">Můžete zadat mapování polí pro obě adresy (například adresu domácnosti a adresu firmy) a profily pro obě adresy rozšířit samostatně.</span><span class="sxs-lookup"><span data-stu-id="725c9-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="725c9-122">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="725c9-122">Select **Next**.</span></span>

1. <span data-ttu-id="725c9-123">Definujte, která pole z vašich sjednocených profilů se mají použít k vyhledání odpovídajících dat umístění od HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="725c9-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="725c9-124">Pole **Ulice 1** a **Poštovní směrovací číslo** jsou povinná pro vybranou primární a/nebo sekundární adresu.</span><span class="sxs-lookup"><span data-stu-id="725c9-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="725c9-125">Pro vyšší přesnost shody lze přidat více polí.</span><span class="sxs-lookup"><span data-stu-id="725c9-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="725c9-126">![Stránka konfigurace rozšíření od HERE Technologies](media/enrichment-HERE-configuration.png "Stránka konfigurace rozšíření od HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="725c9-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="725c9-127">Vyberte **Použít** k dokončení mapování polí.</span><span class="sxs-lookup"><span data-stu-id="725c9-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="725c9-128">Výsledky rozšíření</span><span class="sxs-lookup"><span data-stu-id="725c9-128">Enrichment results</span></span>

<span data-ttu-id="725c9-129">Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů.</span><span class="sxs-lookup"><span data-stu-id="725c9-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="725c9-130">Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="725c9-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="725c9-131">Doba zpracování bude záviset na velikosti vašich zákaznických dat a dobách odezvy rozhraní API od HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="725c9-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="725c9-132">Po dokončení procesu obohacení můžete zkontrolovat nově obohacené údaje o zákaznických profilech v **Moje rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="725c9-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="725c9-133">Dále najdete čas poslední aktualizace a počet obohacených profilů.</span><span class="sxs-lookup"><span data-stu-id="725c9-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="725c9-134">Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.</span><span class="sxs-lookup"><span data-stu-id="725c9-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="725c9-135">Další kroky</span><span class="sxs-lookup"><span data-stu-id="725c9-135">Next steps</span></span>

<span data-ttu-id="725c9-136">Stavte na svých obohacených zákaznických údajích.</span><span class="sxs-lookup"><span data-stu-id="725c9-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="725c9-137">Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.</span><span class="sxs-lookup"><span data-stu-id="725c9-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="725c9-138">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="725c9-138">Data privacy and compliance</span></span>

<span data-ttu-id="725c9-139">Když povolíte Dynamics 365 Customer Insights přenos dat společnosti HERE Technologies, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="725c9-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="725c9-140">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost HERE Technologies splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="725c9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="725c9-141">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="725c9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="725c9-142">Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="725c9-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
