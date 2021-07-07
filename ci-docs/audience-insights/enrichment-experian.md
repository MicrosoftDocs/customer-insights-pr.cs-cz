---
title: Obohacení pomocí obohacení třetí strany Experian
description: Obecné informace o obohacování třetí strany Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309812"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="a0877-103">Obohaťte profily zákazníků o demografické údaje z Experian (náhled)</span><span class="sxs-lookup"><span data-stu-id="a0877-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="a0877-104">Experian je světovým lídrem v oblasti reportingu spotřebitelských a obchodních úvěrů a marketingových služeb.</span><span class="sxs-lookup"><span data-stu-id="a0877-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="a0877-105">Se službami rozšiřování dat Experian můžete získat hlubší porozumění svým zákazníkům obohacením svých profilů zákazníků o demografické údaje, jako je velikost domácnosti, příjem atd.</span><span class="sxs-lookup"><span data-stu-id="a0877-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a0877-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="a0877-106">Prerequisites</span></span>

<span data-ttu-id="a0877-107">Abyste mohli konfigurovat Experian, je třeba splnit následující předpoklady:</span><span class="sxs-lookup"><span data-stu-id="a0877-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a0877-108">Musíte mít aktivní předplatné Experian.</span><span class="sxs-lookup"><span data-stu-id="a0877-108">You have an active Experian subscription.</span></span> <span data-ttu-id="a0877-109">Chcete-li získat předplatné, [kontaktujte Experian](https://www.experian.com/marketing-services/contact) přímo.</span><span class="sxs-lookup"><span data-stu-id="a0877-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="a0877-110">[Další informace o rozšiřování dat Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="a0877-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="a0877-111">Správce již nakonfiguroval připojení Experian *nebo* máte oprávnění [správce](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="a0877-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="a0877-112">Pro svůj účet Secure Transport (ST) s povoleným SSH potřebujete také ID uživatele, ID strany a Číslo modelu, které pro vás společnost Experian vytvořila.</span><span class="sxs-lookup"><span data-stu-id="a0877-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="a0877-113">Podporované země/oblasti</span><span class="sxs-lookup"><span data-stu-id="a0877-113">Supported countries/regions</span></span>

<span data-ttu-id="a0877-114">V současné době podporujeme rozšíření profilů zákazníků pouze ve Spojených státech.</span><span class="sxs-lookup"><span data-stu-id="a0877-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="a0877-115">Konfigurace rozšíření</span><span class="sxs-lookup"><span data-stu-id="a0877-115">Configure the enrichment</span></span>

1. <span data-ttu-id="a0877-116">Přejděte na **Data** > **Obohacení** a vyberte kartu **Objevit**.</span><span class="sxs-lookup"><span data-stu-id="a0877-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="a0877-117">Vyberte **Obohatit moje data** v dlaždici Experian.</span><span class="sxs-lookup"><span data-stu-id="a0877-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a0877-118">![Experian dlaždic](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="a0877-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="a0877-119">V rozevíracím seznamu vyberte [připojení](connections.md).</span><span class="sxs-lookup"><span data-stu-id="a0877-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="a0877-120">Pokud není k dispozici propojení , kontaktujte správce.</span><span class="sxs-lookup"><span data-stu-id="a0877-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="a0877-121">Pokud jste správce, můžete vytvořit připojení výběrem **Přidat připojení** a výběrem Experian z rozevíracího seznamu.</span><span class="sxs-lookup"><span data-stu-id="a0877-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="a0877-122">Vyberte **Připojit k Experian** pro potvrzení výběru připojení.</span><span class="sxs-lookup"><span data-stu-id="a0877-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="a0877-123">Vyberte **Další** a zvolte **Sadu dat zákazníka**, kterou chcete obohatit o demograficé údaje z Experian.</span><span class="sxs-lookup"><span data-stu-id="a0877-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="a0877-124">Můžete vybrat entitu **Zákazník** k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.</span><span class="sxs-lookup"><span data-stu-id="a0877-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot výběru sady zákaznických dat.":::

1. <span data-ttu-id="a0877-126">Vyberte **Další** a definujte, který typ polí z vašich sjednocených profilů se má použít k vyhledání odpovídajících demografických dat Experian.</span><span class="sxs-lookup"><span data-stu-id="a0877-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="a0877-127">Požaduje se alespoň jedno z polí **Jméno a adresa**, **Telefon** nebo **E-mail**.</span><span class="sxs-lookup"><span data-stu-id="a0877-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="a0877-128">Pro vyšší přesnost shody lze přidat až dvě další pole.</span><span class="sxs-lookup"><span data-stu-id="a0877-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="a0877-129">Tento výběr ovlivní mapovací pole, ke kterým máte přístup v dalším kroku.</span><span class="sxs-lookup"><span data-stu-id="a0877-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="a0877-130">Další klíčové atributy identifikátoru odeslané do Experian pravděpodobně přinesou vyšší míru shody.</span><span class="sxs-lookup"><span data-stu-id="a0877-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="a0877-131">Výběrem možnosti **Další** spusťte mapování polí.</span><span class="sxs-lookup"><span data-stu-id="a0877-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="a0877-132">Definujte, který typ polí z vašich sjednocených profilů se má použít k vyhledání odpovídajících demografických dat z Experian.</span><span class="sxs-lookup"><span data-stu-id="a0877-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="a0877-133">Povinná pole jsou označená.</span><span class="sxs-lookup"><span data-stu-id="a0877-133">Required fields are marked.</span></span>

1. <span data-ttu-id="a0877-134">Zadejte název rozšíření a název výstupní entity.</span><span class="sxs-lookup"><span data-stu-id="a0877-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="a0877-135">Po kontrole vašich voleb vyberte **Uložit rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="a0877-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="a0877-136">Konfigurace rolí připojení pro Experian</span><span class="sxs-lookup"><span data-stu-id="a0877-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="a0877-137">Abyste mohli konfigurovat propojení, musíte být správce.</span><span class="sxs-lookup"><span data-stu-id="a0877-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="a0877-138">Při konfiguraci obohacení vyberte **Přidat připojení** *nbo* jděte na **Správa** > **Připojení** a vyberte **Nastavit** v dlaždici Experian.</span><span class="sxs-lookup"><span data-stu-id="a0877-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="a0877-139">Vyberte **Začínáme**.</span><span class="sxs-lookup"><span data-stu-id="a0877-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="a0877-140">Do pole **Zobrazované jméno** zadejte jméno.</span><span class="sxs-lookup"><span data-stu-id="a0877-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="a0877-141">Zadejte platné ID uživatele, ID strany a Číslo modelu pro váš zabezpečený transportní účet Experian.</span><span class="sxs-lookup"><span data-stu-id="a0877-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="a0877-142">Zkontrolujte a poskytněte svůj souhlas s **ochranou osobních údajů a dodržováním předpisů** výběrem **souhlasím**.</span><span class="sxs-lookup"><span data-stu-id="a0877-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="a0877-143">Vyberte **Ověřit** k ověření konfigurace.</span><span class="sxs-lookup"><span data-stu-id="a0877-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="a0877-144">Po dokončení ověření vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="a0877-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Podokno konfigurace připojení Experian":::

## <a name="enrichment-results"></a><span data-ttu-id="a0877-146">Výsledky rozšíření</span><span class="sxs-lookup"><span data-stu-id="a0877-146">Enrichment results</span></span>

<span data-ttu-id="a0877-147">Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů.</span><span class="sxs-lookup"><span data-stu-id="a0877-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a0877-148">Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a0877-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a0877-149">Doba zpracování bude záviset na velikosti vašich údajů o zákaznících a na procesech obohacování nastavených pro váš účet Experian.</span><span class="sxs-lookup"><span data-stu-id="a0877-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="a0877-150">Po dokončení procesu obohacení můžete zkontrolovat nově obohacené údaje o zákaznických profilech v **Moje rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="a0877-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="a0877-151">Dále najdete čas poslední aktualizace a počet obohacených profilů.</span><span class="sxs-lookup"><span data-stu-id="a0877-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a0877-152">Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.</span><span class="sxs-lookup"><span data-stu-id="a0877-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a0877-153">Další kroky</span><span class="sxs-lookup"><span data-stu-id="a0877-153">Next steps</span></span>

<span data-ttu-id="a0877-154">Stavte na svých obohacených zákaznických údajích.</span><span class="sxs-lookup"><span data-stu-id="a0877-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a0877-155">Vytvořte [segmenty](segments.md) a [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům poskytli přizpůsobené prostředí.</span><span class="sxs-lookup"><span data-stu-id="a0877-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a0877-156">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="a0877-156">Data privacy and compliance</span></span>

<span data-ttu-id="a0877-157">Když povolíte Dynamics 365 Customer Insights přenášet data do Experian, povolíte tím přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="a0877-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a0877-158">Společnost Microsoft přenese takové údaje podle vašeho pokynu, ale vy jste zodpovědní za zajištění, že Experian bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="a0877-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a0877-159">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a0877-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a0877-160">Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a0877-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
