---
title: Export dat ze služby Customer Insights do Salesforce Marketing Cloud
description: Naučte se, jak nakonfigurovat propojení a exportovat ho do Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314591"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="a3f32-103">Export segmentů a dalších dat do Salesforce Marketing Cloud (náhled)</span><span class="sxs-lookup"><span data-stu-id="a3f32-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="a3f32-104">Využijte svá zákaznická data ve službě Salesforce Marketing Cloud jejich exportem prostřednictvím umístění SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="a3f32-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="a3f32-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="a3f32-105">Prerequisites for connection</span></span>

- <span data-ttu-id="a3f32-106">Dostupnost hostitele SFTP a odpovídajících pověření správce.</span><span class="sxs-lookup"><span data-stu-id="a3f32-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="a3f32-107">Jak nastavit umístění SFTP pro Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="a3f32-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="a3f32-108">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="a3f32-108">Known limitations</span></span>

- <span data-ttu-id="a3f32-109">Běh exportu závisí na výkonu vašeho systému.</span><span class="sxs-lookup"><span data-stu-id="a3f32-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="a3f32-110">Jako minimální konfiguraci vašeho serveru doporučujeme dvě jádra CPU a 1 GB paměti.</span><span class="sxs-lookup"><span data-stu-id="a3f32-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="a3f32-111">Export entit s až 100 miliony zákaznických profilů může při použití doporučené minimální konfigurace trvat 90 minut.</span><span class="sxs-lookup"><span data-stu-id="a3f32-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="a3f32-112">Nastavení připojení k Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="a3f32-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="a3f32-113">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="a3f32-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a3f32-114">Vyberte **Přidat připojení** a zvolte **Salesforce Marketing Cloud** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="a3f32-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="a3f32-115">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="a3f32-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a3f32-116">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="a3f32-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a3f32-117">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="a3f32-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a3f32-118">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="a3f32-118">Choose who can use this connection.</span></span> <span data-ttu-id="a3f32-119">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="a3f32-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a3f32-120">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a3f32-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a3f32-121">Zadejte **Uživatelské jméno**, **Heslo**, **Název hostitele** a **Složku pro export** pro váš účet SFTP.</span><span class="sxs-lookup"><span data-stu-id="a3f32-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="a3f32-122">Vyberte **Ověřit** pro otestování připojení.</span><span class="sxs-lookup"><span data-stu-id="a3f32-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="a3f32-123">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="a3f32-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a3f32-124">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="a3f32-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a3f32-125">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="a3f32-125">Configure an export</span></span>

<span data-ttu-id="a3f32-126">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="a3f32-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a3f32-127">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a3f32-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a3f32-128">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="a3f32-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a3f32-129">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="a3f32-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a3f32-130">V poli **propojení pro export** vyberte propojení v části SFTP.</span><span class="sxs-lookup"><span data-stu-id="a3f32-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="a3f32-131">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="a3f32-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a3f32-132">Vyberte, zda chcete exportovat data **komprimovaná jako gzip** nebo **rozbalená** a vyberte **oddělovač polí** pro exportované soubory.</span><span class="sxs-lookup"><span data-stu-id="a3f32-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="a3f32-133">Vyberte entity, například segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="a3f32-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a3f32-134">Každá vybraná entita bude při exportu rozdělena až na pět výstupních souborů.</span><span class="sxs-lookup"><span data-stu-id="a3f32-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="a3f32-135">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="a3f32-135">Select **Save**.</span></span>

<span data-ttu-id="a3f32-136">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="a3f32-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a3f32-137">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a3f32-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a3f32-138">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a3f32-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="a3f32-139">Import dat z umístění SFTP do Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="a3f32-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="a3f32-140">Vytvořte [datová rozšíření v Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) pro import datového souboru Customer Insights z umístění SFTP.</span><span class="sxs-lookup"><span data-stu-id="a3f32-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="a3f32-141">[Importujte data z umístění SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) do datového rozšíření Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="a3f32-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="a3f32-142">Nastavte automatizaci pro import dat do datových rozšíření.</span><span class="sxs-lookup"><span data-stu-id="a3f32-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="a3f32-143">Zjistěte více o [automatizaci přetažení souborů a plánované automatizaci](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="a3f32-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="a3f32-144">Definujte [automatizaci přetahování souborů](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) nebo [plánovanou automatizaci](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="a3f32-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="a3f32-145">Zde je příklad [automatizace se SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="a3f32-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a3f32-146">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="a3f32-146">Data privacy and compliance</span></span>

<span data-ttu-id="a3f32-147">Když povolíte Dynamics 365 Customer Insights přenos dat prostřednictvím protokolu SFTP, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="a3f32-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a3f32-148">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že cíl exportu splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="a3f32-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a3f32-149">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a3f32-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a3f32-150">Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.</span><span class="sxs-lookup"><span data-stu-id="a3f32-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
