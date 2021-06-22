---
title: Export dat Customer Insights do služby Microsoft Advertising
description: Naučte se konfigurovat připojení a export do služby Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124468"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="5f42b-103">Export segmentů do služby Microsoft Advertising (preview)</span><span class="sxs-lookup"><span data-stu-id="5f42b-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="5f42b-104">Exportujte segmenty Customer Insights do služby Microsoft Advertising a vytvořte cílové skupiny shody zákazníků.</span><span class="sxs-lookup"><span data-stu-id="5f42b-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="5f42b-105">Tyto cílové skupiny používejte pro své reklamní kampaně.</span><span class="sxs-lookup"><span data-stu-id="5f42b-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5f42b-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="5f42b-106">Prerequisites</span></span>

-   <span data-ttu-id="5f42b-107">Máte [účet Microsoft Advertising](https://ads.microsoft.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="5f42b-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5f42b-108">Přijali jste podmínky použití shod zákazníků.</span><span class="sxs-lookup"><span data-stu-id="5f42b-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="5f42b-109">[Konfigurované segmenty](segments.md) v přehledech cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="5f42b-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5f42b-110">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole s e-mailovou adresou.</span><span class="sxs-lookup"><span data-stu-id="5f42b-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5f42b-111">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="5f42b-111">Known limitations</span></span>

- <span data-ttu-id="5f42b-112">Do Microsoft Advertising můžete exportovat až 500 tisíc profilů na export.</span><span class="sxs-lookup"><span data-stu-id="5f42b-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="5f42b-113">Export do Microsoft Advertising je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="5f42b-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="5f42b-114">Export až 500 tisíc profilů do Microsoft Advertising může trvat až 10 minut.</span><span class="sxs-lookup"><span data-stu-id="5f42b-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="5f42b-115">Nastavení propojení se službou Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="5f42b-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="5f42b-116">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="5f42b-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5f42b-117">Vyberte **Přidat připojení** a zvolte **Microsoft Advertising** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="5f42b-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="5f42b-118">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="5f42b-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5f42b-119">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="5f42b-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5f42b-120">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="5f42b-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5f42b-121">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="5f42b-121">Choose who can use this connection.</span></span> <span data-ttu-id="5f42b-122">Výchozí jsou správci.</span><span class="sxs-lookup"><span data-stu-id="5f42b-122">The default is administrators.</span></span> <span data-ttu-id="5f42b-123">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5f42b-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5f42b-124">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="5f42b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5f42b-125">K inicializaci propojení se službou Microsoft Advertising vyberte příkaz **Připojit**.</span><span class="sxs-lookup"><span data-stu-id="5f42b-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="5f42b-126">Vyberte **Ověření pomocí Microsoft Advertising** a zadejte své přihlašovací údaje pro Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="5f42b-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="5f42b-127">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5f42b-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5f42b-128">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="5f42b-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5f42b-129">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="5f42b-129">Configure an export</span></span>

<span data-ttu-id="5f42b-130">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="5f42b-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5f42b-131">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5f42b-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5f42b-132">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="5f42b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5f42b-133">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="5f42b-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5f42b-134">V poli **Připojení pro export** vyberte připojení v části Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="5f42b-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="5f42b-135">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="5f42b-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5f42b-136">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="5f42b-136">Select the segments to export.</span></span> <span data-ttu-id="5f42b-137">Cílové skupiny shody zákazníků ve službě Microsoft Advertising se automaticky vytvářejí s názvem segmentů vybraných pro export.</span><span class="sxs-lookup"><span data-stu-id="5f42b-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="5f42b-138">Výsledkem každého segmentu bude samostatná cílová skupina shody zákazníků.</span><span class="sxs-lookup"><span data-stu-id="5f42b-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="5f42b-139">Vložte své **ID zákazníka a ID účtu Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="5f42b-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="5f42b-140">ID zákazníka (`cid`) a ID účtu (`aid`) najdete v parametrech adresy URL, když jste přihlášeni do služby Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="5f42b-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="5f42b-141">V oddíle **Párování dat** vyberte v poli **E-mail** to pole sjednoceného profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="5f42b-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="5f42b-142">Je nutné exportovat segmenty do Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="5f42b-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="5f42b-143">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="5f42b-143">Select **Save**.</span></span>

<span data-ttu-id="5f42b-144">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="5f42b-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5f42b-145">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5f42b-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5f42b-146">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5f42b-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5f42b-147">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="5f42b-147">Data privacy and compliance</span></span>

<span data-ttu-id="5f42b-148">Když aplikaci Dynamics 365 Customer Insights povolíte přenos dat do Microsoft Advertising, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="5f42b-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5f42b-149">Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že Microsoft Advertising bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="5f42b-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5f42b-150">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5f42b-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="5f42b-151">Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.</span><span class="sxs-lookup"><span data-stu-id="5f42b-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
