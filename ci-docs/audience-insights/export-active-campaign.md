---
title: Export údajů ze služby Customer Insights do ActiveCampaign
description: Naučte se, jak nakonfigurovat propojení a exportovat ho do ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314593"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="ce83b-103">Export segmentů do ActiveCampaign (náhled)</span><span class="sxs-lookup"><span data-stu-id="ce83b-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="ce83b-104">Exportujte segmenty sjednocených profilů zákazníků do ActiveCampaign a použijte je pro marketingové aktivity.</span><span class="sxs-lookup"><span data-stu-id="ce83b-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ce83b-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ce83b-105">Prerequisites</span></span>

-   <span data-ttu-id="ce83b-106">Máte [účet ActiveCampaign](https://www.activecampaign.com/) a odpovídající pověření správce.</span><span class="sxs-lookup"><span data-stu-id="ce83b-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ce83b-107">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ce83b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ce83b-108">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole s e-mailovou adresou.</span><span class="sxs-lookup"><span data-stu-id="ce83b-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ce83b-109">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="ce83b-109">Known limitations</span></span>

- <span data-ttu-id="ce83b-110">Do aplikace ActiveCampaign můžete exportovat až 1 milion profilů na jeden export a dokončení může trvat až 90 minut.</span><span class="sxs-lookup"><span data-stu-id="ce83b-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="ce83b-111">Export do ActiveCampaign je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="ce83b-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="ce83b-112">Počet profilů, které můžete exportovat do služby ActiveCampaign, závisí na vaší smlouvě se společností ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="ce83b-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="ce83b-113">Můžete nastavit propojení řešení s ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="ce83b-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="ce83b-114">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="ce83b-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ce83b-115">Vyberte **Přidat připojení** a zvolte **ActiveCampaign** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="ce83b-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="ce83b-116">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="ce83b-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ce83b-117">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="ce83b-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ce83b-118">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="ce83b-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ce83b-119">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="ce83b-119">Choose who can use this connection.</span></span> <span data-ttu-id="ce83b-120">Ve výchozím nastavení jsou to pouze správci.</span><span class="sxs-lookup"><span data-stu-id="ce83b-120">By default, it's only administrators.</span></span> <span data-ttu-id="ce83b-121">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ce83b-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ce83b-122">Zadejte [Klíč API ActiveCampaign a název hostitele koncového bodu REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="ce83b-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="ce83b-123">Koncový bod názvu hostitele REST je pouze název hostitele, bez https://.</span><span class="sxs-lookup"><span data-stu-id="ce83b-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="ce83b-124">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="ce83b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ce83b-125">Vyberte **Připojit** k inicializaci připojení k ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="ce83b-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="ce83b-126">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ce83b-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ce83b-127">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="ce83b-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ce83b-128">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="ce83b-128">Configure an export</span></span>

<span data-ttu-id="ce83b-129">Export můžete konfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="ce83b-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="ce83b-130">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ce83b-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ce83b-131">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="ce83b-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ce83b-132">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="ce83b-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ce83b-133">V poli **Připojení pro export** zvolte připojení z části ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="ce83b-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="ce83b-134">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="ce83b-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ce83b-135">Zadejte [**ID seznamu ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="ce83b-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="ce83b-136">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="ce83b-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ce83b-137">Je potřeba pro export segmentů do ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="ce83b-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="ce83b-138">Volitelně můžete exportovat křestní jméno, příjmení, a telefon a vytvářet více přizpůsobené e-maily.</span><span class="sxs-lookup"><span data-stu-id="ce83b-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="ce83b-139">Volbou Přidat atribut namapujte tato pole.</span><span class="sxs-lookup"><span data-stu-id="ce83b-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="ce83b-140">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="ce83b-140">Select **Save**.</span></span>

<span data-ttu-id="ce83b-141">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="ce83b-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ce83b-142">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ce83b-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ce83b-143">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ce83b-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ce83b-144">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="ce83b-144">Data privacy and compliance</span></span>

<span data-ttu-id="ce83b-145">Když povolíte Dynamics 365 Customer Insights přenášet data do ActiveCampaign, povolíte tím přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="ce83b-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ce83b-146">Společnost Microsoft přenese takové údaje podle vašeho pokynu, ale vy jste zodpovědní za zajištění, že ActiveCampaign bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="ce83b-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ce83b-147">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ce83b-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ce83b-148">Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.</span><span class="sxs-lookup"><span data-stu-id="ce83b-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
