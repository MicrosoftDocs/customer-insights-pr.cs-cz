---
title: Rozšíření firemních profilů od třetí strany Leadspace
description: Obecné informace o rozšíření od třetí strany Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269414"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="92f2e-103">Rozšíření profilů společnosti o Leadspace (náhled)</span><span class="sxs-lookup"><span data-stu-id="92f2e-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="92f2e-104">Leadspace je společnost zabývající se datovou vědou, která poskytuje B2B zákaznickou datovou platformu.</span><span class="sxs-lookup"><span data-stu-id="92f2e-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="92f2e-105">Umožňuje zákazníkům s jednotnými profily zákazníků rozšiřovat data společností.</span><span class="sxs-lookup"><span data-stu-id="92f2e-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="92f2e-106">Rozšíření zahrnuje dodatečné atributy, včetně velikosti společnosti, místa, odvětví a dalších.</span><span class="sxs-lookup"><span data-stu-id="92f2e-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="92f2e-107">Požadavky</span><span class="sxs-lookup"><span data-stu-id="92f2e-107">Prerequisites</span></span>

<span data-ttu-id="92f2e-108">Abyste mohli Leadspace konfigurovat, je třeba splnit následující předpoklady:</span><span class="sxs-lookup"><span data-stu-id="92f2e-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="92f2e-109">Máte aktivní licenci Leadspace a „časově neomezený klíč“ (označovaný jako **Token Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="92f2e-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="92f2e-110">Kontaktujte přímo [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) pro podrobnosti o jejich produktu.</span><span class="sxs-lookup"><span data-stu-id="92f2e-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="92f2e-111">Máte oprávnění pro [správu](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="92f2e-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="92f2e-112">Máte [sjednocené profily zákazníků](customer-profiles.md) pro společnosti.</span><span class="sxs-lookup"><span data-stu-id="92f2e-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="92f2e-113">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="92f2e-113">Configuration</span></span>

1. <span data-ttu-id="92f2e-114">V přehledech cílové skupiny přejděte na **Data** > **Rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="92f2e-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="92f2e-115">Vybrat **Rozšířit moje data** na dlaždici Leadspace.</span><span class="sxs-lookup"><span data-stu-id="92f2e-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot dlaždice Leadspace.":::

1. <span data-ttu-id="92f2e-117">Vyberte **Začít** a poté zadejte aktivní **Token Leadspace** (časově neomezený klíč).</span><span class="sxs-lookup"><span data-stu-id="92f2e-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="92f2e-118">Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.</span><span class="sxs-lookup"><span data-stu-id="92f2e-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="92f2e-119">Potvrďte oba vstupy výběrem **Připojit k Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="92f2e-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="92f2e-120">Vyberte **Mapovat data** a zvolte datovou sadu, kterou chcete rozšířit o firemní data od společnosti Leadspace.</span><span class="sxs-lookup"><span data-stu-id="92f2e-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="92f2e-121">Můžete vybrat entitu *Zákazník* k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.</span><span class="sxs-lookup"><span data-stu-id="92f2e-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Výběr mezi profilem zákazníka a rozšířením segmentu.":::

1. <span data-ttu-id="92f2e-123">Klikněte na **Další** a definujte, která pole z vašich sjednocených profilů by měla být použita k vyhledání odpovídajících firemních dat z Leadspace.</span><span class="sxs-lookup"><span data-stu-id="92f2e-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="92f2e-124">Pole **Název společnosti** je povinné.</span><span class="sxs-lookup"><span data-stu-id="92f2e-124">The **Name of company** field is required.</span></span> <span data-ttu-id="92f2e-125">Pro vyšší přesnost shody až do dvou dalších polí můžete přidat **Web společnosti** a **Umístění společnosti**.</span><span class="sxs-lookup"><span data-stu-id="92f2e-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Podokno mapování pole Leadspace.":::
   
1. <span data-ttu-id="92f2e-127">Vyberte **Použít** k dokončení mapování polí.</span><span class="sxs-lookup"><span data-stu-id="92f2e-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="92f2e-128">Vyberte **Spustit** pro rozšíření profilů společnosti.</span><span class="sxs-lookup"><span data-stu-id="92f2e-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="92f2e-129">Rychlost provedení rozšíření závisí na počtu sjednocených profilů zákazníků.</span><span class="sxs-lookup"><span data-stu-id="92f2e-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="92f2e-130">Výsledky rozšíření</span><span class="sxs-lookup"><span data-stu-id="92f2e-130">Enrichment results</span></span>

<span data-ttu-id="92f2e-131">Po aktualizaci rozšíření si můžete prohlédnout nově rozšířená firemní data v části [Moje rozšíření](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="92f2e-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="92f2e-132">Najdete čas poslední aktualizace a počet rozšířených profilů.</span><span class="sxs-lookup"><span data-stu-id="92f2e-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="92f2e-133">Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.</span><span class="sxs-lookup"><span data-stu-id="92f2e-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="92f2e-134">Další informace naleznete na webu [Rozhraní API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="92f2e-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="92f2e-135">Další kroky</span><span class="sxs-lookup"><span data-stu-id="92f2e-135">Next steps</span></span>

<span data-ttu-id="92f2e-136">Stavte na svých obohacených zákaznických údajích.</span><span class="sxs-lookup"><span data-stu-id="92f2e-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="92f2e-137">Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.</span><span class="sxs-lookup"><span data-stu-id="92f2e-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="92f2e-138">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="92f2e-138">Data privacy and compliance</span></span>

<span data-ttu-id="92f2e-139">Když povolíte Dynamics 365 Customer Insights přenos dat společnosti Leadspace, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="92f2e-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="92f2e-140">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Leadspace splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="92f2e-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="92f2e-141">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="92f2e-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="92f2e-142">Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="92f2e-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]