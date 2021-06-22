---
title: Export údajů ze služby Customer Insights do služby Campaign Monitor
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124173"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="84fb5-103">Export segmentů do služby Campaign Monitor (preview)</span><span class="sxs-lookup"><span data-stu-id="84fb5-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="84fb5-104">Exportujte segmenty sjednocených profilů zákazníků do služby Campaign Monitor a použijte je pro marketingové aktivity.</span><span class="sxs-lookup"><span data-stu-id="84fb5-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="84fb5-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="84fb5-105">Prerequisites</span></span>

-   <span data-ttu-id="84fb5-106">Máte [účet Campaign Monitor](https://www.campaignmonitor.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="84fb5-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="84fb5-107">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="84fb5-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="84fb5-108">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="84fb5-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="84fb5-109">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="84fb5-109">Known limitations</span></span>

- <span data-ttu-id="84fb5-110">Můžete exportovat až 1 milion profilů na export do Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="84fb5-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="84fb5-111">Export do Campaign Monitor je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="84fb5-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="84fb5-112">Export až 1 milionu profilů do Campaign Monitor může trvat až 20 minut.</span><span class="sxs-lookup"><span data-stu-id="84fb5-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="84fb5-113">Počet profilů, které můžete exportovat do Campaign Monitor, závisí na vaší smlouvě s Campaign Monitor a je podle ní omezen.</span><span class="sxs-lookup"><span data-stu-id="84fb5-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="84fb5-114">Nastavení propojení s Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="84fb5-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="84fb5-115">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="84fb5-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="84fb5-116">Vyberte **Přidat připojení** a zvolte **Campaign Monitor** pro konfiguraci propojení .</span><span class="sxs-lookup"><span data-stu-id="84fb5-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="84fb5-117">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="84fb5-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="84fb5-118">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="84fb5-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="84fb5-119">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="84fb5-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="84fb5-120">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="84fb5-120">Choose who can use this connection.</span></span> <span data-ttu-id="84fb5-121">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="84fb5-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="84fb5-122">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="84fb5-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="84fb5-123">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="84fb5-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="84fb5-124">K inicializaci propojení se službou Campaign Monitor vyberte **Propojit**.</span><span class="sxs-lookup"><span data-stu-id="84fb5-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="84fb5-125">Vyberte **Ověření pomocí Campaign Monitor** a poskytněte své přihlašovací údaje pro Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="84fb5-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="84fb5-126">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="84fb5-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="84fb5-127">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="84fb5-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="84fb5-128">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="84fb5-128">Configure an export</span></span>

<span data-ttu-id="84fb5-129">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="84fb5-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="84fb5-130">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="84fb5-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="84fb5-131">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="84fb5-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="84fb5-132">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="84fb5-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="84fb5-133">V poli **propojení pro export** vyberte propojení v části Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="84fb5-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="84fb5-134">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="84fb5-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="84fb5-135">Zadejte [**ID seznamu Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="84fb5-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="84fb5-136">[Vygenerujte klíč API](https://www.campaignmonitor.com/api/getting-started/) z **Nastavení účtu** nejprve v nástroji Campaign Monitor pro zobrazení ID seznamu API.</span><span class="sxs-lookup"><span data-stu-id="84fb5-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="84fb5-137">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="84fb5-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="84fb5-138">Je nutné exportovat segmenty do Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="84fb5-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="84fb5-139">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="84fb5-139">Select **Save**.</span></span>

<span data-ttu-id="84fb5-140">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="84fb5-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="84fb5-141">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="84fb5-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="84fb5-142">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="84fb5-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="84fb5-143">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="84fb5-143">Data privacy and compliance</span></span>

<span data-ttu-id="84fb5-144">Když povolíte Dynamics 365 Customer Insights k přenosu dat do Campaign Monitor, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="84fb5-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="84fb5-145">Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že Campaign Monitor bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="84fb5-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="84fb5-146">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="84fb5-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="84fb5-147">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="84fb5-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
