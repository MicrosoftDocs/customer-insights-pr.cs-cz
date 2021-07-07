---
title: Rozšíření firemních profilů od třetí strany Leadspace
description: Obecné informace o rozšíření od třetí strany Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305194"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="738d1-103">Rozšíření profilů společnosti o Leadspace (náhled)</span><span class="sxs-lookup"><span data-stu-id="738d1-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="738d1-104">Leadspace je společnost zabývající se datovou vědou, která poskytuje B2B zákaznickou datovou platformu.</span><span class="sxs-lookup"><span data-stu-id="738d1-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="738d1-105">Umožňuje zákazníkům s jednotnými profily zákazníků rozšiřovat data společností.</span><span class="sxs-lookup"><span data-stu-id="738d1-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="738d1-106">Rozšíření zahrnuje další atributy, jako je velikost společnosti, místa, odvětví a další.</span><span class="sxs-lookup"><span data-stu-id="738d1-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="738d1-107">Požadavky</span><span class="sxs-lookup"><span data-stu-id="738d1-107">Prerequisites</span></span>

<span data-ttu-id="738d1-108">Abyste mohli Leadspace konfigurovat, je třeba splnit následující předpoklady:</span><span class="sxs-lookup"><span data-stu-id="738d1-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="738d1-109">Máte aktivní licenci Leadspace.</span><span class="sxs-lookup"><span data-stu-id="738d1-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="738d1-110">Máte [sjednocené profily zákazníků](customer-profiles.md) pro společnosti.</span><span class="sxs-lookup"><span data-stu-id="738d1-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="738d1-111">propojení Leadspace již bylo nakonfigurováno správcem nebo máte oprávnění [správce](permissions.md#administrator) a "trvalý klíč" (označovaný jako **Token Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="738d1-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="738d1-112">Informace o produktu si zjistěte přímo u společnosti [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/).</span><span class="sxs-lookup"><span data-stu-id="738d1-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="738d1-113">Konfigurace rozšíření</span><span class="sxs-lookup"><span data-stu-id="738d1-113">Configure the enrichment</span></span>

1. <span data-ttu-id="738d1-114">V přehledech cílové skupiny přejděte na **Data** > **Rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="738d1-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="738d1-115">Vyberte **Rozšířit moje data** v dlaždici Leadspace a vyberte **Začít**.</span><span class="sxs-lookup"><span data-stu-id="738d1-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot dlaždice Leadspace.":::

1. <span data-ttu-id="738d1-117">V rozevíracím seznamu vyberte [připojení](connections.md).</span><span class="sxs-lookup"><span data-stu-id="738d1-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="738d1-118">Pokud není k dispozici propojení , kontaktujte správce.</span><span class="sxs-lookup"><span data-stu-id="738d1-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="738d1-119">Pokud jste správce, můžete vytvořit propojení výběrem možnosti **Přidat propojení** a **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="738d1-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="738d1-120">propojení potvrďte výběrem **Připojit k Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="738d1-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="738d1-121">Vyberte **Další** a zvolte **datovou sadu zákazníka**, kterou chcete rozšířit o firemní data ze služby Leadspace.</span><span class="sxs-lookup"><span data-stu-id="738d1-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="738d1-122">Můžete vybrat entitu **Zákazník** k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.</span><span class="sxs-lookup"><span data-stu-id="738d1-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Screenshot výběru sady zákaznických dat.":::

1. <span data-ttu-id="738d1-124">Vyberte **Další** a definujte, která pole z vašich sjednocených profilů se použijí k vyhledání odpovídajících firemních dat z Leadspace.</span><span class="sxs-lookup"><span data-stu-id="738d1-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="738d1-125">Pole **Název společnosti** je povinné.</span><span class="sxs-lookup"><span data-stu-id="738d1-125">The **Name of company** field is required.</span></span> <span data-ttu-id="738d1-126">Pro vyšší přesnost shody až do dvou dalších polí můžete přidat **Web společnosti** a **Umístění společnosti**.</span><span class="sxs-lookup"><span data-stu-id="738d1-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Podokno mapování pole Leadspace.":::

1. <span data-ttu-id="738d1-128">Výběrem možnosti **Další** dokončete mapování polí.</span><span class="sxs-lookup"><span data-stu-id="738d1-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="738d1-129">Zadejte název rozšíření a po přezkoumání vašich voleb vyberte **Uložit rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="738d1-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="738d1-130">Konfigurace propojení pro Leadspace</span><span class="sxs-lookup"><span data-stu-id="738d1-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="738d1-131">Abyste mohli konfigurovat propojení, musíte být správce.</span><span class="sxs-lookup"><span data-stu-id="738d1-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="738d1-132">Při konfiguraci rozšíření vyberte **Přidat připojení** *nebo* přejděte na **Správce** > **Připojení** a v dlaždici Leadspace vyberte **Nastavit**.</span><span class="sxs-lookup"><span data-stu-id="738d1-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="738d1-133">Vyberte **Začínáme**.</span><span class="sxs-lookup"><span data-stu-id="738d1-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="738d1-134">Do pole **Zobrazované jméno** zadejte jméno.</span><span class="sxs-lookup"><span data-stu-id="738d1-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="738d1-135">Zadejte platný token Leadspace.</span><span class="sxs-lookup"><span data-stu-id="738d1-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="738d1-136">Zkontrolujte a poskytněte svůj souhlas s **ochranou osobních údajů a dodržováním předpisů** výběrem **souhlasím**.</span><span class="sxs-lookup"><span data-stu-id="738d1-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="738d1-137">Vyberte **Ověřit** k ověření konfigurace.</span><span class="sxs-lookup"><span data-stu-id="738d1-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="738d1-138">Po dokončení ověření vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="738d1-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stránka konfigurace propojení pro Leadspace":::

## <a name="enrichment-results"></a><span data-ttu-id="738d1-140">Výsledky rozšíření</span><span class="sxs-lookup"><span data-stu-id="738d1-140">Enrichment results</span></span>

<span data-ttu-id="738d1-141">Po aktualizaci rozšíření si můžete prohlédnout nově rozšířená firemní data v části [Moje rozšíření](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="738d1-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="738d1-142">Najdete čas poslední aktualizace a počet rozšířených profilů.</span><span class="sxs-lookup"><span data-stu-id="738d1-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="738d1-143">Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.</span><span class="sxs-lookup"><span data-stu-id="738d1-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="738d1-144">Další informace naleznete na webu [Rozhraní API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="738d1-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="738d1-145">Další kroky</span><span class="sxs-lookup"><span data-stu-id="738d1-145">Next steps</span></span>

<span data-ttu-id="738d1-146">Stavte na svých obohacených zákaznických údajích.</span><span class="sxs-lookup"><span data-stu-id="738d1-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="738d1-147">Vytvořte [segmenty](segments.md) a [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům poskytli přizpůsobené prostředí.</span><span class="sxs-lookup"><span data-stu-id="738d1-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="738d1-148">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="738d1-148">Data privacy and compliance</span></span>

<span data-ttu-id="738d1-149">Když povolíte Dynamics 365 Customer Insights přenos dat společnosti Leadspace, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="738d1-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="738d1-150">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Leadspace splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="738d1-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="738d1-151">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="738d1-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="738d1-152">Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="738d1-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
