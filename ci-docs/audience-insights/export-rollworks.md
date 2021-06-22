---
title: Export údajů ze služby Customer Insights do služby RollWorks
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do služby RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124081"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="2e6d4-103">Export segmentů do služby RollWorks (preview)</span><span class="sxs-lookup"><span data-stu-id="2e6d4-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="2e6d4-104">Exportujte segmenty sjednocených profilů zákazníků do služby RollWorks a použijte je pro reklamu.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="2e6d4-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="2e6d4-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="2e6d4-106">Máte [účet RollWorks](https://www.rollworks.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2e6d4-107">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="2e6d4-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2e6d4-108">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2e6d4-109">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="2e6d4-109">Known limitations</span></span>

- <span data-ttu-id="2e6d4-110">Můžete exportovat až 250 000 profilů na export do RollWorks.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="2e6d4-111">Do RollWorks nelze exportovat segmenty s méně než 100 profily.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="2e6d4-112">Export do RollWorks je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="2e6d4-113">Export až 250 000 profilů do RollWorks může trvat až 10 minut.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="2e6d4-114">Počet profilů, které můžete exportovat do RollWorks, závisí na vaší smlouvě s RollWorks a je podle ní omezen.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="2e6d4-115">Nastavení propojení s aplikací RollWorks</span><span class="sxs-lookup"><span data-stu-id="2e6d4-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="2e6d4-116">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2e6d4-117">Vyberte **Přidat připojení** a zvolte **RollWorks** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="2e6d4-118">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2e6d4-119">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2e6d4-120">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2e6d4-121">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-121">Choose who can use this connection.</span></span> <span data-ttu-id="2e6d4-122">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2e6d4-123">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2e6d4-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2e6d4-124">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2e6d4-125">K inicializaci propojení se službou RollWorks vyberte **Připojit**.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="2e6d4-126">Vyberte **Ověření pomocí RollWorks** a poskytněte své přihlašovací údaje pro RollWorks.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="2e6d4-127">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2e6d4-128">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2e6d4-129">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="2e6d4-129">Configure an export</span></span>

<span data-ttu-id="2e6d4-130">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2e6d4-131">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2e6d4-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2e6d4-132">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2e6d4-133">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2e6d4-134">V poli **propojení pro export** vyberte propojení v části RollWorks.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="2e6d4-135">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2e6d4-136">Zadejte **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="2e6d4-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="2e6d4-137">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2e6d4-138">Je nutné exportovat segmenty do RollWorks.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="2e6d4-139">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-139">Select the segments you want to export.</span></span> <span data-ttu-id="2e6d4-140">Vyberte segment s nejméně 100 členy.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="2e6d4-141">Menší segmenty nelze exportovat.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-141">You can't export smaller segments.</span></span> <span data-ttu-id="2e6d4-142">Maximální velikost segmentu k exportu je navíc 250 000 členů na export.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="2e6d4-143">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-143">Select **Save**.</span></span>

<span data-ttu-id="2e6d4-144">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2e6d4-145">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2e6d4-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2e6d4-146">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2e6d4-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2e6d4-147">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="2e6d4-147">Data privacy and compliance</span></span>

<span data-ttu-id="2e6d4-148">Když povolíte Dynamics 365 Customer Insights k přenosu dat do RollWorks, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2e6d4-149">Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že RollWorks bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2e6d4-150">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2e6d4-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="2e6d4-151">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2e6d4-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
