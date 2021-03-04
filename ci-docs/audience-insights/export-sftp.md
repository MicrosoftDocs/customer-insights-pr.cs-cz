---
title: Export dat Customer Insights do hostitelů SFTP
description: Naučte se, jak nakonfigurovat připojení k hostiteli SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267990"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="8e531-103">Konektor pro SFTP (preview)</span><span class="sxs-lookup"><span data-stu-id="8e531-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="8e531-104">Konektor SFTP umožňuje bezpečně exportovat vaše zákaznická data, která pak můžete používat v aplikacích třetích stran, do hostitele SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="8e531-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8e531-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="8e531-105">Prerequisites</span></span>

- <span data-ttu-id="8e531-106">Dostupnost hostitele SFTP a odpovídajících pověření.</span><span class="sxs-lookup"><span data-stu-id="8e531-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="8e531-107">Připojit k SFTP</span><span class="sxs-lookup"><span data-stu-id="8e531-107">Connect to SFTP</span></span>

1. <span data-ttu-id="8e531-108">Přejděte na **Správce** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="8e531-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8e531-109">V **SFTP** vyberte **Založit**</span><span class="sxs-lookup"><span data-stu-id="8e531-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="8e531-110">Zadejte rozpoznatelný název cíle do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="8e531-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8e531-111">Zadejte **Uživatelské jméno**, **Heslo**, **Název hostitele** a **Složku pro export** pro váš účet SFTP.</span><span class="sxs-lookup"><span data-stu-id="8e531-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="8e531-112">Vyberte **Ověřit** pro otestování připojení.</span><span class="sxs-lookup"><span data-stu-id="8e531-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="8e531-113">Po úspěšném ověření zvolte, zda chcete exportovat svá data **sbalená** nebo **rozbalená** a vyberte **oddělovač polí** pro exportované soubory.</span><span class="sxs-lookup"><span data-stu-id="8e531-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="8e531-114">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="8e531-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8e531-115">Vyberte **Další** pro spuštění konfigurace exportu.</span><span class="sxs-lookup"><span data-stu-id="8e531-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="8e531-116">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="8e531-116">Configure the export</span></span>

1. <span data-ttu-id="8e531-117">Vyberte entity, například segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="8e531-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8e531-118">Každá vybraná entita bude mít při exportu až pět výstupních souborů.</span><span class="sxs-lookup"><span data-stu-id="8e531-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="8e531-119">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="8e531-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8e531-120">Export dat</span><span class="sxs-lookup"><span data-stu-id="8e531-120">Export the data</span></span>

<span data-ttu-id="8e531-121">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8e531-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8e531-122">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8e531-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8e531-123">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="8e531-123">Known limitations</span></span>

- <span data-ttu-id="8e531-124">Běh exportu závisí na výkonu vašeho systému.</span><span class="sxs-lookup"><span data-stu-id="8e531-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="8e531-125">Jako minimální konfiguraci vašeho serveru doporučujeme dvě jádra CPU a 1 GB paměti.</span><span class="sxs-lookup"><span data-stu-id="8e531-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="8e531-126">Export entit s až 100 miliony zákaznických profilů může trvat 90 minut při použití doporučené minimální konfigurace dvou jader CPU a 1 GB paměti.</span><span class="sxs-lookup"><span data-stu-id="8e531-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8e531-127">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="8e531-127">Data privacy and compliance</span></span>

<span data-ttu-id="8e531-128">Když povolíte Dynamics 365 Customer Insights přenos dat prostřednictvím protokolu SFTP, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="8e531-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8e531-129">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že cíl exportu splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="8e531-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8e531-130">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8e531-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8e531-131">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8e531-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]