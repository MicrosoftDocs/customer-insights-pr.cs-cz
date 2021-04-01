---
title: Export dat Customer Insights do AdRoll
description: Naučte se, jak nakonfigurovat připojení k AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697066"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="c16cb-103">Konektor pro AdRoll (Preview)</span><span class="sxs-lookup"><span data-stu-id="c16cb-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="c16cb-104">Exportujte segmenty sjednocených profilů zákazníků do služby AdRoll a použijte je pro reklamu.</span><span class="sxs-lookup"><span data-stu-id="c16cb-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c16cb-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="c16cb-105">Prerequisites</span></span>

-   <span data-ttu-id="c16cb-106">Máte [účet AdRoll](https://www.adroll.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="c16cb-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c16cb-107">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c16cb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c16cb-108">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="c16cb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="c16cb-109">Připojit k AdRoll</span><span class="sxs-lookup"><span data-stu-id="c16cb-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="c16cb-110">Přejděte na **Správce** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="c16cb-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c16cb-111">Pod **AdRoll** vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="c16cb-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="c16cb-112">Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="c16cb-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfigurační podokno pro připojení služby AdRoll.":::

1. <span data-ttu-id="c16cb-114">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="c16cb-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c16cb-115">Volbou **Připojit** inicializujte připojení ke službě AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c16cb-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="c16cb-116">Vyberte **Ověření pomocí AdRoll** a zadejte své přihlašovací údaje správce k AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c16cb-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="c16cb-117">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c16cb-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c16cb-118">Vložte svoje **ID inzerenta AdRoll** [Inzerovatelný AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="c16cb-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="c16cb-119">Vyberte **Další** pro konfiguraci exportu.</span><span class="sxs-lookup"><span data-stu-id="c16cb-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c16cb-120">Konfigurace konektoru</span><span class="sxs-lookup"><span data-stu-id="c16cb-120">Configure the connector</span></span>

1. <span data-ttu-id="c16cb-121">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="c16cb-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c16cb-122">Je nutné exportovat segmenty do služby AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c16cb-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="c16cb-123">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="c16cb-123">Select the segments you want to export.</span></span> <span data-ttu-id="c16cb-124">Vyberte segment s nejméně 100 členy.</span><span class="sxs-lookup"><span data-stu-id="c16cb-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="c16cb-125">Menší segmenty nelze exportovat.</span><span class="sxs-lookup"><span data-stu-id="c16cb-125">You can't export smaller segments.</span></span> <span data-ttu-id="c16cb-126">Maximální velikost segmentu k exportu je navíc 250 000 členů na export.</span><span class="sxs-lookup"><span data-stu-id="c16cb-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="c16cb-127">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="c16cb-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c16cb-128">Export dat</span><span class="sxs-lookup"><span data-stu-id="c16cb-128">Export the data</span></span>

<span data-ttu-id="c16cb-129">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c16cb-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c16cb-130">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c16cb-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c16cb-131">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="c16cb-131">Known limitations</span></span>

- <span data-ttu-id="c16cb-132">Do služby AdRoll můžete exportovat maximálně 250 000 profilů na jeden export.</span><span class="sxs-lookup"><span data-stu-id="c16cb-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="c16cb-133">Do AdRoll nelze exportovat segmenty s méně než 100 profily.</span><span class="sxs-lookup"><span data-stu-id="c16cb-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="c16cb-134">Export do služby Marketo je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="c16cb-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="c16cb-135">Export až 250 000 profilů do služby AdRoll může trvat až 10 minut.</span><span class="sxs-lookup"><span data-stu-id="c16cb-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="c16cb-136">Počet profilů, které můžete exportovat do služby AdRoll, závisí a je omezen na vaší smlouvě se službou AdRoll.</span><span class="sxs-lookup"><span data-stu-id="c16cb-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c16cb-137">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="c16cb-137">Data privacy and compliance</span></span>

<span data-ttu-id="c16cb-138">Když povolíte Dynamics 365 Customer Insights přenést data do služby AdRoll, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="c16cb-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c16cb-139">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba AdRoll splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="c16cb-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c16cb-140">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c16cb-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="c16cb-141">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c16cb-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
