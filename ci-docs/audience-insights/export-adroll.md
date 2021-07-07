---
title: Export dat Customer Insights do AdRoll
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304802"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="f864e-103">Export segmentů do služby AdRoll (preview)</span><span class="sxs-lookup"><span data-stu-id="f864e-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="f864e-104">Exportujte segmenty sjednocených profilů zákazníků do služby AdRoll a použijte je pro reklamu.</span><span class="sxs-lookup"><span data-stu-id="f864e-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f864e-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="f864e-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f864e-106">Máte [účet AdRoll](https://www.adroll.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="f864e-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f864e-107">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f864e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f864e-108">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="f864e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f864e-109">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="f864e-109">Known limitations</span></span>

- <span data-ttu-id="f864e-110">Do AdRoll můžete exportovat až 250 000 záznamů současně.</span><span class="sxs-lookup"><span data-stu-id="f864e-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="f864e-111">Do AdRoll nelze exportovat segmenty s méně než 100 profily.</span><span class="sxs-lookup"><span data-stu-id="f864e-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="f864e-112">Export do služby Marketo je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="f864e-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="f864e-113">Export až 250 000 profilů do služby AdRoll může trvat až 10 minut.</span><span class="sxs-lookup"><span data-stu-id="f864e-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="f864e-114">Počet profilů, které můžete exportovat do služby AdRoll, závisí na vaší smlouvě se společností AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f864e-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="f864e-115">Nastavení propojení s AdRoll</span><span class="sxs-lookup"><span data-stu-id="f864e-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="f864e-116">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="f864e-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f864e-117">Vyberte **Přidat připojení** a zvolte **AdRoll** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="f864e-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="f864e-118">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="f864e-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f864e-119">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="f864e-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f864e-120">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="f864e-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f864e-121">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="f864e-121">Choose who can use this connection.</span></span> <span data-ttu-id="f864e-122">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="f864e-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f864e-123">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f864e-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f864e-124">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="f864e-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f864e-125">Volbou **Připojit** inicializujte připojení ke službě AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f864e-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="f864e-126">Vyberte **Ověření pomocí AdRoll** a zadejte své přihlašovací údaje správce k AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f864e-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="f864e-127">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f864e-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f864e-128">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="f864e-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f864e-129">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="f864e-129">Configure an export</span></span>

<span data-ttu-id="f864e-130">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="f864e-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f864e-131">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f864e-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f864e-132">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="f864e-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f864e-133">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="f864e-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f864e-134">V poli **propojení pro export** vyberte propojení v části AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f864e-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="f864e-135">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="f864e-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="f864e-136">Vložte své **ID inzerenta AdRoll**.</span><span class="sxs-lookup"><span data-stu-id="f864e-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="f864e-137">Další informace viz [Profily inzerentů AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="f864e-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="f864e-138">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="f864e-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f864e-139">Je nutné exportovat segmenty do služby AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f864e-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="f864e-140">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="f864e-140">Select the segments you want to export.</span></span> <span data-ttu-id="f864e-141">Vyberte segment s nejméně 100 členy.</span><span class="sxs-lookup"><span data-stu-id="f864e-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="f864e-142">Menší segmenty nelze exportovat.</span><span class="sxs-lookup"><span data-stu-id="f864e-142">You can't export smaller segments.</span></span> <span data-ttu-id="f864e-143">Maximální velikost segmentu k exportu je navíc 250 000 členů na export.</span><span class="sxs-lookup"><span data-stu-id="f864e-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="f864e-144">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="f864e-144">Select **Save**.</span></span>

<span data-ttu-id="f864e-145">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="f864e-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f864e-146">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f864e-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="f864e-147">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f864e-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f864e-148">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="f864e-148">Data privacy and compliance</span></span>

<span data-ttu-id="f864e-149">Když povolíte Dynamics 365 Customer Insights přenést data do služby AdRoll, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="f864e-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f864e-150">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba AdRoll splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="f864e-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f864e-151">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f864e-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="f864e-152">Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.</span><span class="sxs-lookup"><span data-stu-id="f864e-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
