---
title: Export údajů ze služby Customer Insights do služby Omnisend
description: Naučte se konfigurovat připojení a export do služby Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124469"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="16b59-103">Export segmentů do Omnisend (preview)</span><span class="sxs-lookup"><span data-stu-id="16b59-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="16b59-104">Exportujte segmenty sjednocených profilů zákazníků do služby Omnisend a použijte je pro marketingové aktivity.</span><span class="sxs-lookup"><span data-stu-id="16b59-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="16b59-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="16b59-105">Prerequisites</span></span>

-   <span data-ttu-id="16b59-106">Máte [účet Omnisend](https://www.omnisend.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="16b59-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="16b59-107">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="16b59-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="16b59-108">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="16b59-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="16b59-109">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="16b59-109">Known limitations</span></span>

- <span data-ttu-id="16b59-110">Do Omnisend můžete exportovat až 1 milion profilů na export a jeho dokončení může trvat až 4 hodiny.</span><span class="sxs-lookup"><span data-stu-id="16b59-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="16b59-111">Export do Omnisend je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="16b59-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="16b59-112">Počet profilů, které můžete exportovat do Omnisend, závisí na vaší smlouvě se společností Omnisend.</span><span class="sxs-lookup"><span data-stu-id="16b59-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="16b59-113">Nastavení připojení ke službě Omnisend</span><span class="sxs-lookup"><span data-stu-id="16b59-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="16b59-114">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="16b59-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="16b59-115">Vyberte **Přidat připojení** a zvolte **Omnisend** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="16b59-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="16b59-116">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="16b59-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="16b59-117">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="16b59-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="16b59-118">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="16b59-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="16b59-119">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="16b59-119">Choose who can use this connection.</span></span> <span data-ttu-id="16b59-120">Ve výchozím nastavení jsou to pouze správci.</span><span class="sxs-lookup"><span data-stu-id="16b59-120">By default it's only administrators.</span></span> <span data-ttu-id="16b59-121">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="16b59-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="16b59-122">Zadejte svůj [klíč rozhraní API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="16b59-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="16b59-123">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="16b59-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="16b59-124">K inicializaci připojení ke službě Omnisend vyberte **Připojit**.</span><span class="sxs-lookup"><span data-stu-id="16b59-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="16b59-125">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="16b59-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="16b59-126">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="16b59-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="16b59-127">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="16b59-127">Configure an export</span></span>

<span data-ttu-id="16b59-128">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="16b59-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="16b59-129">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="16b59-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="16b59-130">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="16b59-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="16b59-131">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="16b59-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="16b59-132">V poli **Připojení pro export** vyberte připojení v části Omnisend.</span><span class="sxs-lookup"><span data-stu-id="16b59-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="16b59-133">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="16b59-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="16b59-134">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="16b59-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="16b59-135">Je nutné exportovat segmenty do služby Omnisend.</span><span class="sxs-lookup"><span data-stu-id="16b59-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="16b59-136">Volitelně můžete exportovat křestní jméno, příjmení, adresu, zemi/region, stát, město a PSČ, abyste vytvořili více přizpůsobené e-maily.</span><span class="sxs-lookup"><span data-stu-id="16b59-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="16b59-137">Volbou **Přidat atribut** namapujte tato pole.</span><span class="sxs-lookup"><span data-stu-id="16b59-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="16b59-138">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="16b59-138">Select **Save**.</span></span>

<span data-ttu-id="16b59-139">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="16b59-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="16b59-140">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="16b59-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="16b59-141">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="16b59-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="16b59-142">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="16b59-142">Data privacy and compliance</span></span>

<span data-ttu-id="16b59-143">Když aplikaci Dynamics 365 Customer Insights povolíte přenos dat do Omnisend, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="16b59-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="16b59-144">Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že Omnisend bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="16b59-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="16b59-145">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="16b59-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="16b59-146">Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.</span><span class="sxs-lookup"><span data-stu-id="16b59-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
