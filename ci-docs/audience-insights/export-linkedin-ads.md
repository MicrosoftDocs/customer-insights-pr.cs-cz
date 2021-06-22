---
title: Export údajů ze služby Customer Insights do služby LinkedIn Ads
description: Naučte se konfigurovat připojení a export do služby LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124470"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="bfdbf-103">Export segmentů do LinkedIn Ads (preview)</span><span class="sxs-lookup"><span data-stu-id="bfdbf-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="bfdbf-104">Exportujte segmenty sjednocených profilů zákazníků do reklam LinkedIn Ads a vytvořte spárované cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="bfdbf-105">Spárované cílové skupiny použijte k cílení na společnosti a kontakty.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bfdbf-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="bfdbf-106">Prerequisites</span></span>

-   <span data-ttu-id="bfdbf-107">Máte [účet LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bfdbf-108">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="bfdbf-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="bfdbf-109">Profily zákazníků v exportovaných segmentech obsahují pole s e-mailovou adresou.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bfdbf-110">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="bfdbf-110">Known limitations</span></span>

- <span data-ttu-id="bfdbf-111">Do LinkedIn Ads můžete exportovat až 100 000 profilů na export.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="bfdbf-112">Export do LinkedIn Ads je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="bfdbf-113">Export až 100 tisíc profilů do LinkedIn Ads může trvat až 10 minut.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="bfdbf-114">Nastavení připojení k LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="bfdbf-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="bfdbf-115">Ve statistikách cílové skupiny přejděte na **Správce** > **Připojení**.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bfdbf-116">Vyberte **Přidat připojení** a zvolte **LinkedIn Ads** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="bfdbf-117">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bfdbf-118">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bfdbf-119">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bfdbf-120">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-120">Choose who can use this connection.</span></span> <span data-ttu-id="bfdbf-121">Pokud neprovedete žádnou akci, výchozí budou administrátoři.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="bfdbf-122">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bfdbf-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bfdbf-123">Zadejte své [ID účtu LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="bfdbf-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="bfdbf-124">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bfdbf-125">K inicializaci propojení se službou Campaign Monitor vyberte **Propojit**.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="bfdbf-126">Vyberte **Ověření pomocí LinkedIn** a zadejte své přihlašovací údaje do aplikace LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="bfdbf-127">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bfdbf-128">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bfdbf-129">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="bfdbf-129">Configure an export</span></span>

<span data-ttu-id="bfdbf-130">Export můžete konfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="bfdbf-131">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bfdbf-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bfdbf-132">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bfdbf-133">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bfdbf-134">V poli **Připojení pro export** vyberte připojení v části LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="bfdbf-135">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bfdbf-136">Vyberte, zda chcete v LinkedIn exportovat data do [cílení kontaktů](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) nebo [cílení na společnost](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting).</span><span class="sxs-lookup"><span data-stu-id="bfdbf-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="bfdbf-137">V oddíle **Párování dat** vyberte pole sjednoceného profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="bfdbf-138">Je nutné exportovat segmenty do LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="bfdbf-139">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-139">Select the segments you want to export.</span></span> <span data-ttu-id="bfdbf-140">Spárované cílové skupiny v LinkedIn Campaign Manager se vytvoří automaticky s názvem segmentů, které jste vybrali k exportu.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="bfdbf-141">Výsledkem každého segmentu bude samostatná spárovaná cílová skupina.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="bfdbf-142">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-142">Select **Save**.</span></span>

<span data-ttu-id="bfdbf-143">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bfdbf-144">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bfdbf-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bfdbf-145">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bfdbf-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bfdbf-146">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="bfdbf-146">Data privacy and compliance</span></span>

<span data-ttu-id="bfdbf-147">Když aplikaci Dynamics 365 Customer Insights povolíte přenos dat do LinkedIn Ads, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bfdbf-148">Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že LinkedIn Ads bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="bfdbf-149">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bfdbf-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="bfdbf-150">Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.</span><span class="sxs-lookup"><span data-stu-id="bfdbf-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
