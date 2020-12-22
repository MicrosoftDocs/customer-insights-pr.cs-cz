---
title: Rozšíření od třetí strany Experian
description: Obecné informace o rozšíření od třetí strany Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668798"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="0a77b-103">Obohaťte profily zákazníků o demografické údaje ze služby Experian (náhled)</span><span class="sxs-lookup"><span data-stu-id="0a77b-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="0a77b-104">Experian je světový lídr v oblasti spotřebitelských a obchodních úvěrových reportů a marketingových služeb.</span><span class="sxs-lookup"><span data-stu-id="0a77b-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="0a77b-105">Se službami obohacení dat společnosti Experian můžete získat hlubší porozumění svým zákazníkům obohacením profilů zákazníků o demografické údaje, jako je velikost domácnosti, příjem a další.</span><span class="sxs-lookup"><span data-stu-id="0a77b-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0a77b-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="0a77b-106">Prerequisites</span></span>

<span data-ttu-id="0a77b-107">Pro konfiguraci Experianu je třeba splnit následující předpoklady:</span><span class="sxs-lookup"><span data-stu-id="0a77b-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0a77b-108">Máte aktivní předplatné Experian.</span><span class="sxs-lookup"><span data-stu-id="0a77b-108">You have an active Experian subscription.</span></span> <span data-ttu-id="0a77b-109">Chcete-li získat předplatné, [kontaktujte Experian](https://www.experian.com/marketing-services/contact) přímo.</span><span class="sxs-lookup"><span data-stu-id="0a77b-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="0a77b-110">[Další informace o rozšiřování dat Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="0a77b-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="0a77b-111">Pro svůj účet Secure Transport (ST) s povoleným SSH, který pro vás vytvořil Experian, máte ID uživatele, ID strany a Číslo modelu.</span><span class="sxs-lookup"><span data-stu-id="0a77b-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="0a77b-112">V přehledech cílové skupiny máte oprávnění [Správce](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="0a77b-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="0a77b-113">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="0a77b-113">Configuration</span></span>

1. <span data-ttu-id="0a77b-114">Přejděte na **Data** > **Obohacení** a vyberte kartu **Objevit**.</span><span class="sxs-lookup"><span data-stu-id="0a77b-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="0a77b-115">Vyberte **Obohaťte moje data** na dlaždici Experian.</span><span class="sxs-lookup"><span data-stu-id="0a77b-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0a77b-116">![Dlaždice Experian](media/experian-tile.png "Dlaždice Experian")</span><span class="sxs-lookup"><span data-stu-id="0a77b-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="0a77b-117">Vyberte **Začít** a zadejte ID uživatele, ID strany a Číslo modelu pro váš účet Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="0a77b-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="0a77b-118">Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.</span><span class="sxs-lookup"><span data-stu-id="0a77b-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="0a77b-119">Potvrďte všechny vstupy výběrem **Použít**.</span><span class="sxs-lookup"><span data-stu-id="0a77b-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="0a77b-120">Mapování polí</span><span class="sxs-lookup"><span data-stu-id="0a77b-120">Map your fields</span></span>

1. <span data-ttu-id="0a77b-121">Vyberte **Přidat data** a vyberte klíčové identifikátory z **Jméno a adresa**, **E-mail** nebo **Telefon** k odeslání do Experian k vyřešení identity.</span><span class="sxs-lookup"><span data-stu-id="0a77b-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="0a77b-122">Další klíčové atributy identifikátoru odeslané do Experian pravděpodobně přinesou vyšší míru shody.</span><span class="sxs-lookup"><span data-stu-id="0a77b-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="0a77b-123">Vyberte **Další** a namapujte odpovídající atributy z vaší jednotné entity zákazníka pro vybraná pole klíčového identifikátoru.</span><span class="sxs-lookup"><span data-stu-id="0a77b-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="0a77b-124">Vyberte **Přidat atribut**, chcete-li mapovat libovolné další atributy, které byste chtěli odeslat do Experian.</span><span class="sxs-lookup"><span data-stu-id="0a77b-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="0a77b-125">Vyberte **Uložit** pro dokončení mapování pole.</span><span class="sxs-lookup"><span data-stu-id="0a77b-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0a77b-126">![Mapování polí Experian](media/experian-field-mapping.png "Mapování polí Experian")</span><span class="sxs-lookup"><span data-stu-id="0a77b-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="0a77b-127">Výsledky rozšíření</span><span class="sxs-lookup"><span data-stu-id="0a77b-127">Enrichment results</span></span>

<span data-ttu-id="0a77b-128">Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů.</span><span class="sxs-lookup"><span data-stu-id="0a77b-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="0a77b-129">Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0a77b-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0a77b-130">Doba zpracování bude záviset na velikosti vašich údajů o zákaznících a na procesech obohacování nastavených pro váš účet společností Experian.</span><span class="sxs-lookup"><span data-stu-id="0a77b-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="0a77b-131">Po dokončení procesu obohacení můžete zkontrolovat nově obohacené údaje o zákaznických profilech v **Moje rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="0a77b-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="0a77b-132">Dále najdete čas poslední aktualizace a počet obohacených profilů.</span><span class="sxs-lookup"><span data-stu-id="0a77b-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0a77b-133">Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.</span><span class="sxs-lookup"><span data-stu-id="0a77b-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0a77b-134">Další kroky</span><span class="sxs-lookup"><span data-stu-id="0a77b-134">Next steps</span></span>

<span data-ttu-id="0a77b-135">Stavte na svých obohacených zákaznických údajích.</span><span class="sxs-lookup"><span data-stu-id="0a77b-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0a77b-136">Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.</span><span class="sxs-lookup"><span data-stu-id="0a77b-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0a77b-137">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="0a77b-137">Data privacy and compliance</span></span>

<span data-ttu-id="0a77b-138">Když povolíte Dynamics 365 Customer Insights přenos dat společnosti Experian, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="0a77b-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0a77b-139">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Experian splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="0a77b-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0a77b-140">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0a77b-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0a77b-141">Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0a77b-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
