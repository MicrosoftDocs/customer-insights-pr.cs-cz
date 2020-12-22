---
title: Export dat Customer Insights do služby DotDigital
description: Naučte se, jak nakonfigurovat připojení ke službě DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644440"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="fbdc8-103">Konektor pro DotDigital (Preview)</span><span class="sxs-lookup"><span data-stu-id="fbdc8-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="fbdc8-104">Exportujte segmenty sjednocených profilů zákazníků do adresářů DotDigital a použijte je pro kampaně, e-mailový marketing a vytváření segmentů zákazníků s pomocí služby DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="fbdc8-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="fbdc8-105">Prerequisites</span></span>

-   <span data-ttu-id="fbdc8-106">Máte [účet DotDigital](https://dotdigital.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fbdc8-107">Služba DotDigital obsahuje adresáře a odpovídající ID.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="fbdc8-108">ID najdete v adrese URL, když vyberete a otevřete adresář.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="fbdc8-109">Další informace viz [Adresáře DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="fbdc8-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="fbdc8-110">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="fbdc8-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="fbdc8-111">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="fbdc8-112">Připojení ke službě DotDigital</span><span class="sxs-lookup"><span data-stu-id="fbdc8-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="fbdc8-113">Přejděte na **Správce** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fbdc8-114">Pod **DotDigital** vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="fbdc8-115">Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Podokno konfigurace pro export do služby DotDigital.":::

1. <span data-ttu-id="fbdc8-117">Zadejte své **uživatelské jméno a heslo pro DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="fbdc8-118">Zadejte svoje **[ID adresáře DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="fbdc8-119">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fbdc8-120">Volbou **Připojit** inicializujte připojení ke službě DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="fbdc8-121">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="fbdc8-122">Vyberte **Další** pro konfiguraci exportu.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="fbdc8-123">Konfigurace konektoru</span><span class="sxs-lookup"><span data-stu-id="fbdc8-123">Configure the connector</span></span>

1. <span data-ttu-id="fbdc8-124">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="fbdc8-125">Stejné kroky opakujte pro další volitelná pole, například **Křestní jméno**, **Příjmení**, **Celé jméno**, **Pohlaví** a **PSČ**.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="fbdc8-126">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-126">Select the segments you want to export.</span></span> <span data-ttu-id="fbdc8-127">Do služby DotDigital můžete exportovat celkem až 1 milion zákaznických profilů.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="fbdc8-128">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="fbdc8-129">Export dat</span><span class="sxs-lookup"><span data-stu-id="fbdc8-129">Export the data</span></span>

<span data-ttu-id="fbdc8-130">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="fbdc8-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="fbdc8-131">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fbdc8-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fbdc8-132">Ve službě DotDigital nyní můžete najít své segmenty v [adresářích DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="fbdc8-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fbdc8-133">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="fbdc8-133">Known limitations</span></span>

- <span data-ttu-id="fbdc8-134">Až 1 milion profilů na jeden export do služby DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="fbdc8-135">Export do služby DotDigital je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="fbdc8-136">Export segmentů s celkem 1 milionem profilů může z důvodu omezení na straně poskytovatele trvat až 3 hodiny.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="fbdc8-137">Počet profilů, které můžete exportovat do služby DotDigital, závisí a je omezen na vaší smlouvě se společností DotDigital.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fbdc8-138">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="fbdc8-138">Data privacy and compliance</span></span>

<span data-ttu-id="fbdc8-139">Když pro Dynamics 365 Customer Insights povolíte přenos dat do služby DotDigital, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fbdc8-140">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost DotDigital splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="fbdc8-141">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fbdc8-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fbdc8-142">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fbdc8-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
