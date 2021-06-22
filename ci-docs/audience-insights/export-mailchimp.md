---
title: Export dat Customer Insights do služby Mailchimp
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124219"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="2906e-103">Export segmentů do služby Mailchimp (preview)</span><span class="sxs-lookup"><span data-stu-id="2906e-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="2906e-104">Exportujte segmenty sjednocených profilů zákazníků do služby Mailchimp a vytvářejte bulletiny a e-mailové kampaně.</span><span class="sxs-lookup"><span data-stu-id="2906e-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="2906e-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="2906e-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="2906e-106">Máte [účet Mailchimp](https://mailchimp.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="2906e-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2906e-107">Služba Mailchimp obsahuje cílové skupiny a odpovídající ID.</span><span class="sxs-lookup"><span data-stu-id="2906e-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="2906e-108">Další informace viz [Cílové skupiny Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="2906e-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="2906e-109">Máte [konfigurované segmenty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="2906e-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="2906e-110">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="2906e-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2906e-111">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="2906e-111">Known limitations</span></span>

- <span data-ttu-id="2906e-112">Až 1 milion profilů na jeden export do služby Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="2906e-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="2906e-113">Export do služby Mailchimp je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="2906e-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="2906e-114">Export segmentů s 1 milionem profilů může trvat až tři hodiny.</span><span class="sxs-lookup"><span data-stu-id="2906e-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="2906e-115">Počet profilů, které můžete exportovat do služby Mailchimp, závisí a je omezen na vaší smlouvě se službou Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="2906e-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="2906e-116">Nastavení propojení s aplikací Mailchimp</span><span class="sxs-lookup"><span data-stu-id="2906e-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="2906e-117">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="2906e-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2906e-118">Vyberte **Přidat připojení** a zvolte **Mailchimp** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="2906e-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="2906e-119">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="2906e-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2906e-120">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="2906e-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2906e-121">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="2906e-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2906e-122">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="2906e-122">Choose who can use this connection.</span></span> <span data-ttu-id="2906e-123">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="2906e-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2906e-124">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2906e-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2906e-125">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="2906e-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2906e-126">K inicializaci propojení se službou Mailchimp vyberte **Připojit**.</span><span class="sxs-lookup"><span data-stu-id="2906e-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="2906e-127">Vyberte **Ověření pomocí Mailchimp** a zadejte své přihlašovací údaje ke službě Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="2906e-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="2906e-128">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2906e-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2906e-129">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="2906e-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="2906e-130">Konfigurace konektoru</span><span class="sxs-lookup"><span data-stu-id="2906e-130">Configure the connector</span></span>

<span data-ttu-id="2906e-131">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="2906e-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2906e-132">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2906e-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2906e-133">Přejděte na **Data**> **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="2906e-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="2906e-134">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="2906e-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2906e-135">V poli **propojení pro export** vyberte propojení v části Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="2906e-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="2906e-136">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="2906e-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2906e-137">Zadejte **[ID cílové skupiny Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="2906e-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="2906e-138">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="2906e-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="2906e-139">Volitelně můžete exportovat **křestní jméno** a **příjmení** pro vytvoření více přizpůsobených e-mailů.</span><span class="sxs-lookup"><span data-stu-id="2906e-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="2906e-140">Volbou **Přidat atribut** namapujte tato pole.</span><span class="sxs-lookup"><span data-stu-id="2906e-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="2906e-141">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="2906e-141">Select the segments you want to export.</span></span> <span data-ttu-id="2906e-142">Do služby Mailchimp můžete exportovat celkem až 1 milion zákaznických profilů.</span><span class="sxs-lookup"><span data-stu-id="2906e-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="2906e-143">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="2906e-143">Select **Save**.</span></span>

<span data-ttu-id="2906e-144">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="2906e-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2906e-145">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2906e-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2906e-146">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2906e-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2906e-147">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="2906e-147">Data privacy and compliance</span></span>

<span data-ttu-id="2906e-148">Když povolíte Dynamics 365 Customer Insights přenos dat do služby Mailchimp, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="2906e-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2906e-149">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Mailchimp splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="2906e-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2906e-150">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2906e-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2906e-151">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2906e-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
