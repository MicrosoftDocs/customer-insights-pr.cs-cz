---
title: Export dat Customer Insights do služby DotDigital
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124403"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="a4077-103">Export segmentů do služby DotDigital (preview)</span><span class="sxs-lookup"><span data-stu-id="a4077-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="a4077-104">Exportujte segmenty sjednocených profilů zákazníků do adresářů DotDigital a použijte je pro kampaně, e-mailový marketing a vytváření segmentů zákazníků s pomocí služby DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a4077-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a4077-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="a4077-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="a4077-106">Máte [účet DotDigital](https://dotdigital.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="a4077-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a4077-107">Služba DotDigital obsahuje adresáře a odpovídající ID.</span><span class="sxs-lookup"><span data-stu-id="a4077-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="a4077-108">ID najdete v adrese URL, když vyberete a otevřete adresář.</span><span class="sxs-lookup"><span data-stu-id="a4077-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="a4077-109">Další informace viz [Adresáře DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="a4077-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="a4077-110">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a4077-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a4077-111">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="a4077-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a4077-112">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="a4077-112">Known limitations</span></span>

- <span data-ttu-id="a4077-113">Až 1 milion profilů na jeden export do služby DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a4077-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="a4077-114">Export do služby DotDigital je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="a4077-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="a4077-115">Export segmentů s celkem 1 milionem profilů může z důvodu omezení na straně poskytovatele trvat až 3 hodiny.</span><span class="sxs-lookup"><span data-stu-id="a4077-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="a4077-116">Počet profilů, které můžete exportovat do služby DotDigital, závisí a je omezen na vaší smlouvě se společností DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a4077-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="a4077-117">Nastavení propojení s aplikací DotDigital</span><span class="sxs-lookup"><span data-stu-id="a4077-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="a4077-118">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="a4077-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a4077-119">Vyberte **Přidat připojení** a zvolte **DotDigital** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="a4077-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="a4077-120">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="a4077-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a4077-121">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="a4077-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a4077-122">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="a4077-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a4077-123">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="a4077-123">Choose who can use this connection.</span></span> <span data-ttu-id="a4077-124">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="a4077-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a4077-125">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a4077-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a4077-126">Zadejte své **uživatelské jméno a heslo pro DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="a4077-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="a4077-127">Zadejte svoje **[ID adresáře DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="a4077-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="a4077-128">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="a4077-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a4077-129">Volbou **Připojit** inicializujte připojení ke službě DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a4077-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="a4077-130">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a4077-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a4077-131">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="a4077-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="a4077-132">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="a4077-132">Configure an export</span></span>

<span data-ttu-id="a4077-133">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="a4077-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a4077-134">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a4077-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a4077-135">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="a4077-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a4077-136">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="a4077-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a4077-137">V poli **propojení pro export** vyberte propojení v části DotDigital.</span><span class="sxs-lookup"><span data-stu-id="a4077-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="a4077-138">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="a4077-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="a4077-139">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="a4077-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a4077-140">Stejné kroky opakujte pro další volitelná pole, například **Křestní jméno**, **Příjmení**, **Celé jméno**, **Pohlaví** a **PSČ**.</span><span class="sxs-lookup"><span data-stu-id="a4077-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="a4077-141">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="a4077-141">Select the segments you want to export.</span></span> <span data-ttu-id="a4077-142">Do služby DotDigital můžete exportovat celkem až 1 milion zákaznických profilů.</span><span class="sxs-lookup"><span data-stu-id="a4077-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="a4077-143">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="a4077-143">Select **Save**.</span></span>

<span data-ttu-id="a4077-144">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="a4077-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a4077-145">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a4077-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a4077-146">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a4077-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="a4077-147">Ve službě DotDigital nyní můžete najít své segmenty v [adresářích DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="a4077-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a4077-148">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="a4077-148">Data privacy and compliance</span></span>

<span data-ttu-id="a4077-149">Když pro Dynamics 365 Customer Insights povolíte přenos dat do služby DotDigital, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="a4077-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a4077-150">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost DotDigital splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="a4077-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a4077-151">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a4077-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a4077-152">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a4077-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
