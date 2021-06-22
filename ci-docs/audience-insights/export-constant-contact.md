---
title: Export údajů ze služby Customer Insights do služby Constant
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124265"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="e2487-103">Export segmentů do služby Constant Contact (preview)</span><span class="sxs-lookup"><span data-stu-id="e2487-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="e2487-104">Exportujte segmenty sjednocených profilů zákazníků do služby Constant Contact a použijte je pro marketingové aktivity.</span><span class="sxs-lookup"><span data-stu-id="e2487-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e2487-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="e2487-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e2487-106">Máte [účet Constant Contact](https://www.constantcontact.com/account-home) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="e2487-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e2487-107">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e2487-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e2487-108">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="e2487-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e2487-109">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="e2487-109">Known limitations</span></span>

- <span data-ttu-id="e2487-110">Můžete exportovat až 1 milion profilů na export do Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e2487-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="e2487-111">Export do Constant Contact je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="e2487-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="e2487-112">Export až 1 milionu profilů do Constant Contact může trvat až 1 hodinu.</span><span class="sxs-lookup"><span data-stu-id="e2487-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="e2487-113">Počet profilů, které můžete exportovat do Constant Contact, závisí na vaší smlouvě s Constant Contact a je podle ní omezen.</span><span class="sxs-lookup"><span data-stu-id="e2487-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="e2487-114">Nastavení propojení s Constant Contact</span><span class="sxs-lookup"><span data-stu-id="e2487-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="e2487-115">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="e2487-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e2487-116">Vyberte **Přidat připojení** a zvolte **Constant Contact** pro konfiguraci propojení .</span><span class="sxs-lookup"><span data-stu-id="e2487-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="e2487-117">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="e2487-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e2487-118">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="e2487-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e2487-119">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="e2487-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e2487-120">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="e2487-120">Choose who can use this connection.</span></span> <span data-ttu-id="e2487-121">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="e2487-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e2487-122">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e2487-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e2487-123">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="e2487-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e2487-124">K inicializaci propojení se službou Constant Contact vyberte **Propojit**.</span><span class="sxs-lookup"><span data-stu-id="e2487-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="e2487-125">Vyberte **Ověření pomocí AdRoll** a poskytněte své přihlašovací údaje pro Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e2487-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="e2487-126">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e2487-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e2487-127">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="e2487-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e2487-128">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="e2487-128">Configure an export</span></span>

<span data-ttu-id="e2487-129">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="e2487-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e2487-130">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e2487-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e2487-131">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="e2487-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e2487-132">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="e2487-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e2487-133">V poli **Připojení pro export** vyberte připojení v části Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e2487-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="e2487-134">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="e2487-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e2487-135">Zadejte [**ID seznamu Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="e2487-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="e2487-136">Otevřete seznam v Constant Contact a vyhledejte ID seznamu v adrese URL.</span><span class="sxs-lookup"><span data-stu-id="e2487-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="e2487-137">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="e2487-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e2487-138">Je nutné exportovat segmenty do Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e2487-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="e2487-139">Volitelně můžete exportovat Křestní jméno a Příjmení jako další pole k vytvoření lépe přizpůsobených e-mailů.</span><span class="sxs-lookup"><span data-stu-id="e2487-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="e2487-140">Volbou **Přidat atribut** namapujte tato pole.</span><span class="sxs-lookup"><span data-stu-id="e2487-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e2487-141">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="e2487-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e2487-142">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="e2487-142">Select **Save**.</span></span>

<span data-ttu-id="e2487-143">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="e2487-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e2487-144">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e2487-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e2487-145">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e2487-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e2487-146">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="e2487-146">Data privacy and compliance</span></span>

<span data-ttu-id="e2487-147">Když povolíte Dynamics 365 Customer Insights k přenosu dat do Constant Contact, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="e2487-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e2487-148">Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že Constant Contact bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="e2487-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e2487-149">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e2487-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e2487-150">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e2487-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
