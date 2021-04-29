---
title: Export údajů ze služby Customer Insights do služby Snapchat
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do služby Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760495"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="114df-103">Export seznamů segmentů do služby Snapchat (preview)</span><span class="sxs-lookup"><span data-stu-id="114df-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="114df-104">Exportujte segmenty sjednocených profilů zákazníků do služby Snapchat a použijte je pro reklamu.</span><span class="sxs-lookup"><span data-stu-id="114df-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="114df-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="114df-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="114df-106">Máte [účet Snapchat Business](https://business.snapchat.com/), [účet Snapchat Ads](https://ads.snapchat.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="114df-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="114df-107">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="114df-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="114df-108">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="114df-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="114df-109">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="114df-109">Known limitations</span></span>

- <span data-ttu-id="114df-110">Export do Snapchatu je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="114df-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="114df-111">Export až 1 milionu profilů do Snapchatu může trvat až 15 minut.</span><span class="sxs-lookup"><span data-stu-id="114df-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="114df-112">Nastavení propojení se Snapchatem</span><span class="sxs-lookup"><span data-stu-id="114df-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="114df-113">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="114df-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="114df-114">Vyberte **Přidat připojení** a zvolte **Snapchat** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="114df-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="114df-115">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="114df-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="114df-116">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="114df-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="114df-117">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="114df-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="114df-118">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="114df-118">Choose who can use this connection.</span></span> <span data-ttu-id="114df-119">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="114df-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="114df-120">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="114df-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="114df-121">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="114df-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="114df-122">K inicializaci propojení se službou Snapchat vyberte **Propojit**.</span><span class="sxs-lookup"><span data-stu-id="114df-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="114df-123">Vyberte **Ověření pomocí Snapchatu** a poskytněte své přihlašovací údaje pro Snapchat.</span><span class="sxs-lookup"><span data-stu-id="114df-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="114df-124">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="114df-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="114df-125">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="114df-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="114df-126">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="114df-126">Configure an export</span></span>

<span data-ttu-id="114df-127">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="114df-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="114df-128">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="114df-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="114df-129">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="114df-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="114df-130">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="114df-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="114df-131">V poli **propojení pro export** vyberte propojení v části Snapchat.</span><span class="sxs-lookup"><span data-stu-id="114df-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="114df-132">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="114df-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="114df-133">Zadejte [**ID cílové skupiny Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="114df-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="114df-134">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="114df-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="114df-135">Je nutné exportovat segmenty do Snapchatu.</span><span class="sxs-lookup"><span data-stu-id="114df-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="114df-136">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="114df-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="114df-137">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="114df-137">Select **Save**.</span></span>

<span data-ttu-id="114df-138">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="114df-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="114df-139">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="114df-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="114df-140">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="114df-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="114df-141">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="114df-141">Data privacy and compliance</span></span>

<span data-ttu-id="114df-142">Když povolíte Dynamics 365 Customer Insights k přenosu dat do Snapchatu, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="114df-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="114df-143">Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že Snapchat bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="114df-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="114df-144">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="114df-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="114df-145">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="114df-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
