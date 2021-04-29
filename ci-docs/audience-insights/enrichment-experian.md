---
title: Rozšíření od třetí strany Experian
description: Obecné informace o rozšíření od třetí strany Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896365"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="d0409-103">Obohaťte profily zákazníků o demografické údaje ze služby Experian (náhled)</span><span class="sxs-lookup"><span data-stu-id="d0409-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="d0409-104">Experian je světový lídr v oblasti spotřebitelských a obchodních úvěrových reportů a marketingových služeb.</span><span class="sxs-lookup"><span data-stu-id="d0409-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="d0409-105">Se službami obohacení dat společnosti Experian můžete získat hlubší porozumění svým zákazníkům obohacením profilů zákazníků o demografické údaje, jako je velikost domácnosti, příjem a další.</span><span class="sxs-lookup"><span data-stu-id="d0409-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d0409-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="d0409-106">Prerequisites</span></span>

<span data-ttu-id="d0409-107">Pro konfiguraci Experianu je třeba splnit následující předpoklady:</span><span class="sxs-lookup"><span data-stu-id="d0409-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d0409-108">Máte aktivní předplatné Experian.</span><span class="sxs-lookup"><span data-stu-id="d0409-108">You have an active Experian subscription.</span></span> <span data-ttu-id="d0409-109">Chcete-li získat předplatné, [kontaktujte Experian](https://www.experian.com/marketing-services/contact) přímo.</span><span class="sxs-lookup"><span data-stu-id="d0409-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="d0409-110">[Další informace o rozšiřování dat Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="d0409-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="d0409-111">Správce již nakonfiguroval připojení Experian *nebo* máte oprávnění [správce](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="d0409-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="d0409-112">Pro svůj účet Secure Transport (ST) s povoleným SSH, který pro vás společnost Experian vytvořila, potřebujete také ID uživatele, ID strany a číslo modelu.</span><span class="sxs-lookup"><span data-stu-id="d0409-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="d0409-113">Konfigurace rozšíření</span><span class="sxs-lookup"><span data-stu-id="d0409-113">Configure the enrichment</span></span>

1. <span data-ttu-id="d0409-114">Přejděte na **Data** > **Obohacení** a vyberte kartu **Objevit**.</span><span class="sxs-lookup"><span data-stu-id="d0409-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="d0409-115">Vyberte **Obohaťte moje data** na dlaždici Experian.</span><span class="sxs-lookup"><span data-stu-id="d0409-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d0409-116">![Dlaždice Experian](media/experian-tile.png "Dlaždice Experian")</span><span class="sxs-lookup"><span data-stu-id="d0409-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="d0409-117">V rozevíracím seznamu vyberte [propojení](connections.md).</span><span class="sxs-lookup"><span data-stu-id="d0409-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="d0409-118">Pokud není k dispozici propojení , kontaktujte správce.</span><span class="sxs-lookup"><span data-stu-id="d0409-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="d0409-119">Pokud jste správce, můžete vytvořit připojení výběrem možnosti **Přidat připojení** a volbou Experian z rozevíracího seznamu.</span><span class="sxs-lookup"><span data-stu-id="d0409-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="d0409-120">Výběr připojení potvrďte výběrem **Připojit k Experian**.</span><span class="sxs-lookup"><span data-stu-id="d0409-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="d0409-121">Vyberte **Další** a zvolte **datovou sadu zákazníka**, kterou chcete rozšířit o demografické údaje ze služby Experian.</span><span class="sxs-lookup"><span data-stu-id="d0409-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="d0409-122">Můžete vybrat entitu **Zákazník** k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.</span><span class="sxs-lookup"><span data-stu-id="d0409-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot výběru sady zákaznických dat.":::

1. <span data-ttu-id="d0409-124">Vyberte **Další** a definujte, který typ polí z vašich sjednocených profilů by se měla použít k vyhledání odpovídajících demografických údajů od Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d0409-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="d0409-125">Požaduje se alespoň jedno z polí **Jméno a adresa**, **Telefon** nebo **E-mail**.</span><span class="sxs-lookup"><span data-stu-id="d0409-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="d0409-126">Pro vyšší přesnost shody lze přidat až dvě další pole.</span><span class="sxs-lookup"><span data-stu-id="d0409-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="d0409-127">Tento výběr ovlivní mapovací pole, ke kterým máte přístup v dalším kroku.</span><span class="sxs-lookup"><span data-stu-id="d0409-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="d0409-128">Další klíčové atributy identifikátoru odeslané do Experian pravděpodobně přinesou vyšší míru shody.</span><span class="sxs-lookup"><span data-stu-id="d0409-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="d0409-129">Výběrem možnosti **Další** spusťte mapování polí.</span><span class="sxs-lookup"><span data-stu-id="d0409-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="d0409-130">Definujte, který typ polí z vašich sjednocených profilů by se měla použít k vyhledání odpovídajících demografických údajů od Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d0409-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="d0409-131">Povinná pole jsou označená.</span><span class="sxs-lookup"><span data-stu-id="d0409-131">Required fields are marked.</span></span>

1. <span data-ttu-id="d0409-132">Zadejte název rozšíření a název výstupní entity.</span><span class="sxs-lookup"><span data-stu-id="d0409-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="d0409-133">Po kontrole vašich voleb vyberte **Uložit rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="d0409-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="d0409-134">Konfigurace propojení pro Experian</span><span class="sxs-lookup"><span data-stu-id="d0409-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="d0409-135">Abyste mohli konfigurovat propojení, musíte být správce.</span><span class="sxs-lookup"><span data-stu-id="d0409-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="d0409-136">Při konfiguraci rozšíření vyberte **Přidat připojení** *nebo* přejděte na **Správce** > **Připojení** a v dlaždici Experian vyberte **Nastavit**.</span><span class="sxs-lookup"><span data-stu-id="d0409-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="d0409-137">Vyberte **Začínáme**.</span><span class="sxs-lookup"><span data-stu-id="d0409-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="d0409-138">Do pole **Zobrazované jméno** zadejte jméno.</span><span class="sxs-lookup"><span data-stu-id="d0409-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="d0409-139">Zadejte platné ID uživatele, ID strany a Číslo modelu pro účet zabezpečené přepravy Experian.</span><span class="sxs-lookup"><span data-stu-id="d0409-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="d0409-140">Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.</span><span class="sxs-lookup"><span data-stu-id="d0409-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="d0409-141">Vyberte **Ověřit** k ověření konfigurace.</span><span class="sxs-lookup"><span data-stu-id="d0409-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="d0409-142">Po dokončení ověření vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="d0409-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Podokno konfigurace připojení pro Experian":::

## <a name="enrichment-results"></a><span data-ttu-id="d0409-144">Výsledky rozšíření</span><span class="sxs-lookup"><span data-stu-id="d0409-144">Enrichment results</span></span>

<span data-ttu-id="d0409-145">Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů.</span><span class="sxs-lookup"><span data-stu-id="d0409-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="d0409-146">Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d0409-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d0409-147">Doba zpracování bude záviset na velikosti vašich údajů o zákaznících a na procesech obohacování nastavených pro váš účet společností Experian.</span><span class="sxs-lookup"><span data-stu-id="d0409-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="d0409-148">Po dokončení procesu obohacení můžete zkontrolovat nově obohacené údaje o zákaznických profilech v **Moje rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="d0409-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="d0409-149">Dále najdete čas poslední aktualizace a počet obohacených profilů.</span><span class="sxs-lookup"><span data-stu-id="d0409-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d0409-150">Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.</span><span class="sxs-lookup"><span data-stu-id="d0409-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d0409-151">Další kroky</span><span class="sxs-lookup"><span data-stu-id="d0409-151">Next steps</span></span>

<span data-ttu-id="d0409-152">Stavte na svých obohacených zákaznických údajích.</span><span class="sxs-lookup"><span data-stu-id="d0409-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d0409-153">Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.</span><span class="sxs-lookup"><span data-stu-id="d0409-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d0409-154">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="d0409-154">Data privacy and compliance</span></span>

<span data-ttu-id="d0409-155">Když povolíte Dynamics 365 Customer Insights přenos dat společnosti Experian, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="d0409-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d0409-156">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Experian splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="d0409-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d0409-157">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d0409-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d0409-158">Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d0409-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
