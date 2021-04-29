---
title: Export dat Customer Insights do služby Autopilot
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760135"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="65e38-103">Export segmentů do Autopilot (náhled)</span><span class="sxs-lookup"><span data-stu-id="65e38-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="65e38-104">Exportujte segmenty sjednocených profilů zákazníků do služby Autopilot a použijte je pro e-mailový marketing ve službě Autopilot.</span><span class="sxs-lookup"><span data-stu-id="65e38-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="65e38-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="65e38-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="65e38-106">Máte [účet Autopilot](https://www.autopilothq.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="65e38-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="65e38-107">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="65e38-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="65e38-108">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="65e38-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="65e38-109">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="65e38-109">Known limitations</span></span>

- <span data-ttu-id="65e38-110">Do služby Autopilot můžete exportovat celkem až 100 000 profilů zákazníků.</span><span class="sxs-lookup"><span data-stu-id="65e38-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="65e38-111">Export do služby Autopilot je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="65e38-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="65e38-112">Export až 100 000 profilů do služby Autopilot může trvat až několik hodin.</span><span class="sxs-lookup"><span data-stu-id="65e38-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="65e38-113">Počet profilů, které můžete exportovat do služby Autopilot, závisí a je omezen na vaší smlouvě se službou Autopilot.</span><span class="sxs-lookup"><span data-stu-id="65e38-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="65e38-114">Nastavení propojení s aplikací Autopilot</span><span class="sxs-lookup"><span data-stu-id="65e38-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="65e38-115">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="65e38-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="65e38-116">Vyberte **Přidat připojení** a zvolte **Mailchimp** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="65e38-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="65e38-117">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="65e38-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="65e38-118">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="65e38-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="65e38-119">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="65e38-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="65e38-120">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="65e38-120">Choose who can use this connection.</span></span> <span data-ttu-id="65e38-121">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="65e38-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="65e38-122">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="65e38-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="65e38-123">Zadejte [klíč rozhraní API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="65e38-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="65e38-124">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="65e38-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="65e38-125">Volbou **Připojit** inicializujte připojení ke službě Autopilot.</span><span class="sxs-lookup"><span data-stu-id="65e38-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="65e38-126">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="65e38-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="65e38-127">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="65e38-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="65e38-128">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="65e38-128">Configure an export</span></span>

<span data-ttu-id="65e38-129">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="65e38-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="65e38-130">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="65e38-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="65e38-131">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="65e38-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="65e38-132">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="65e38-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="65e38-133">V poli **propojení pro export** vyberte propojení v části Autopilot.</span><span class="sxs-lookup"><span data-stu-id="65e38-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="65e38-134">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="65e38-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="65e38-135">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="65e38-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="65e38-136">Stejné kroky opakujte pro další volitelná pole, například **Křestní jméno**, **Příjmení**.</span><span class="sxs-lookup"><span data-stu-id="65e38-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="65e38-137">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="65e38-137">Select the segments you want to export.</span></span> <span data-ttu-id="65e38-138">Velice **doporučujeme neexportovat více než 100 000 profilů zákazníků** do služby Autopilot.</span><span class="sxs-lookup"><span data-stu-id="65e38-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="65e38-139">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="65e38-139">Select **Save**.</span></span>

<span data-ttu-id="65e38-140">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="65e38-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="65e38-141">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="65e38-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="65e38-142">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="65e38-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="65e38-143">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="65e38-143">Data privacy and compliance</span></span>

<span data-ttu-id="65e38-144">Když povolíte Dynamics 365 Customer Insights přenos dat do služby Autopilot, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="65e38-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="65e38-145">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Autopilot splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="65e38-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="65e38-146">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="65e38-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="65e38-147">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="65e38-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
