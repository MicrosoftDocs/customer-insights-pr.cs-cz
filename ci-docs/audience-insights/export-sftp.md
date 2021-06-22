---
title: Export dat Customer Insights do hostitelů SFTP
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do umístění SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124311"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a><span data-ttu-id="83906-103">Export segmentů a dalších dat do SFTP (preview)</span><span class="sxs-lookup"><span data-stu-id="83906-103">Export segments and other data to SFTP (preview)</span></span>

<span data-ttu-id="83906-104">Využijte svá zákaznická data v aplikacích třetích stran a exportujte je do umístění Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="83906-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="83906-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="83906-105">Prerequisites for connection</span></span>

- <span data-ttu-id="83906-106">Dostupnost hostitele SFTP a odpovídajících pověření.</span><span class="sxs-lookup"><span data-stu-id="83906-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="83906-107">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="83906-107">Known limitations</span></span>

- <span data-ttu-id="83906-108">Běh exportu závisí na výkonu vašeho systému.</span><span class="sxs-lookup"><span data-stu-id="83906-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="83906-109">Jako minimální konfiguraci vašeho serveru doporučujeme dvě jádra CPU a 1 GB paměti.</span><span class="sxs-lookup"><span data-stu-id="83906-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="83906-110">Export entit s až 100 miliony zákaznických profilů může trvat 90 minut při použití doporučené minimální konfigurace dvou jader CPU a 1 GB paměti.</span><span class="sxs-lookup"><span data-stu-id="83906-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="83906-111">Nastavení propojení k SFTP</span><span class="sxs-lookup"><span data-stu-id="83906-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="83906-112">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="83906-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="83906-113">Vyberte **Přidat připojení** a zvolte **SFTP** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="83906-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="83906-114">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="83906-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="83906-115">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="83906-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="83906-116">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="83906-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="83906-117">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="83906-117">Choose who can use this connection.</span></span> <span data-ttu-id="83906-118">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="83906-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="83906-119">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="83906-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="83906-120">Zadejte **Uživatelské jméno**, **Heslo**, **Název hostitele** a **Složku pro export** pro váš účet SFTP.</span><span class="sxs-lookup"><span data-stu-id="83906-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="83906-121">Vyberte **Ověřit** pro otestování připojení.</span><span class="sxs-lookup"><span data-stu-id="83906-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="83906-122">Vyberte, zda chcete exportovat data **komprimovaná jako gzip** nebo **rozbalená** a vyberte **oddělovač polí** pro exportované soubory.</span><span class="sxs-lookup"><span data-stu-id="83906-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="83906-123">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="83906-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="83906-124">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="83906-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="83906-125">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="83906-125">Configure an export</span></span>

<span data-ttu-id="83906-126">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="83906-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="83906-127">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="83906-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="83906-128">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="83906-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="83906-129">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="83906-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="83906-130">V poli **propojení pro export** vyberte propojení v části SFTP.</span><span class="sxs-lookup"><span data-stu-id="83906-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="83906-131">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="83906-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="83906-132">Vyberte entity, například segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="83906-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="83906-133">Každá vybraná entita bude při exportu rozdělena až na pět výstupních souborů.</span><span class="sxs-lookup"><span data-stu-id="83906-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="83906-134">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="83906-134">Select **Save**.</span></span>

<span data-ttu-id="83906-135">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="83906-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="83906-136">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="83906-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="83906-137">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="83906-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="83906-138">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="83906-138">Data privacy and compliance</span></span>

<span data-ttu-id="83906-139">Když povolíte Dynamics 365 Customer Insights přenos dat prostřednictvím protokolu SFTP, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="83906-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="83906-140">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že cíl exportu splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="83906-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="83906-141">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="83906-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="83906-142">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="83906-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
