---
title: Export údajů ze služby Customer Insights do Sendinblue
description: Naučte se, jak nakonfigurovat propojení a exportovat ho do Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314592"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="a9adb-103">Export segmentů do Sendinblue (náhled)</span><span class="sxs-lookup"><span data-stu-id="a9adb-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="a9adb-104">Segmenty sjednocených profilů zákazníků exportujte pro účely generování kampaní, poskytování e-mailového marketingu a využívání konkrétních skupin zákazníků se Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="a9adb-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="a9adb-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="a9adb-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="a9adb-106">Máte [účet Sendinblue](https://www.sendinblue.com/) a odpovídající pověření správce.</span><span class="sxs-lookup"><span data-stu-id="a9adb-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a9adb-107">V Sendinblue existují seznamy a odpovídající ID.</span><span class="sxs-lookup"><span data-stu-id="a9adb-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="a9adb-108">Máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a9adb-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="a9adb-109">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="a9adb-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a9adb-110">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="a9adb-110">Known limitations</span></span>

- <span data-ttu-id="a9adb-111">Až 1 milion profilů na export do Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="a9adb-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="a9adb-112">Export do Sendinblue je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="a9adb-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="a9adb-113">Export segmentů s celkem 1 milionem profilů může trvat až 90 minut.</span><span class="sxs-lookup"><span data-stu-id="a9adb-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="a9adb-114">Počet profilů, které můžete exportovat do Sendinblue, závisí na vaší smlouvě se společností Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="a9adb-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="a9adb-115">Nastavení připojení se Sendinblue</span><span class="sxs-lookup"><span data-stu-id="a9adb-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="a9adb-116">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="a9adb-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a9adb-117">Vyberte **Přidat připojení** a zvolte **Sendinblue** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="a9adb-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="a9adb-118">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="a9adb-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a9adb-119">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="a9adb-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a9adb-120">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="a9adb-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a9adb-121">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="a9adb-121">Choose who can use this connection.</span></span> <span data-ttu-id="a9adb-122">Ve výchozím nastavení jsou to pouze správci.</span><span class="sxs-lookup"><span data-stu-id="a9adb-122">By default it's only administrators.</span></span> <span data-ttu-id="a9adb-123">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a9adb-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a9adb-124">Zadejte **[klíč API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="a9adb-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="a9adb-125">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů** a vyberte **Připojit** pro inicializaci připojení k Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="a9adb-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="a9adb-126">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a9adb-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a9adb-127">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="a9adb-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a9adb-128">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="a9adb-128">Configure an export</span></span>

<span data-ttu-id="a9adb-129">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="a9adb-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a9adb-130">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a9adb-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a9adb-131">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="a9adb-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a9adb-132">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="a9adb-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a9adb-133">V poli **Připojení pro export** zvolte připojení z části Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="a9adb-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="a9adb-134">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="a9adb-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a9adb-135">Zadejte **ID seznamu Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="a9adb-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="a9adb-136">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a9adb-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="a9adb-137">Volitelně můžete exportovat **křestní jméno**, **příjmení**, a **telefon** k vytvoření přizpůsobených e-mailů.</span><span class="sxs-lookup"><span data-stu-id="a9adb-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="a9adb-138">Volbou **Přidat atribut** namapujte tato pole.</span><span class="sxs-lookup"><span data-stu-id="a9adb-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="a9adb-139">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="a9adb-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="a9adb-140">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="a9adb-140">Select **Save**.</span></span>

<span data-ttu-id="a9adb-141">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="a9adb-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a9adb-142">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a9adb-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a9adb-143">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a9adb-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a9adb-144">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="a9adb-144">Data privacy and compliance</span></span>

<span data-ttu-id="a9adb-145">Když povolíte Dynamics 365 Customer Insights přenášet data do Sendinblue, povolíte tím přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="a9adb-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a9adb-146">Společnost Microsoft přenese takové údaje podle vašeho pokynu, ale vy jste zodpovědní za zajištění, že Sendinblue bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="a9adb-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a9adb-147">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a9adb-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a9adb-148">Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.</span><span class="sxs-lookup"><span data-stu-id="a9adb-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
