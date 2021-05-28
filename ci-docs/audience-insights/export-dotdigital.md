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
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976838"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="ab84d-103">Export seznamů segmentů do služby DotDigital (preview)</span><span class="sxs-lookup"><span data-stu-id="ab84d-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="ab84d-104">Exportujte segmenty sjednocených profilů zákazníků do adresářů DotDigital a použijte je pro kampaně, e-mailový marketing a vytváření segmentů zákazníků s pomocí služby DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ab84d-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ab84d-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="ab84d-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ab84d-106">Máte [účet DotDigital](https://dotdigital.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="ab84d-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ab84d-107">Služba DotDigital obsahuje adresáře a odpovídající ID.</span><span class="sxs-lookup"><span data-stu-id="ab84d-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="ab84d-108">ID najdete v adrese URL, když vyberete a otevřete adresář.</span><span class="sxs-lookup"><span data-stu-id="ab84d-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="ab84d-109">Další informace viz [Adresáře DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ab84d-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="ab84d-110">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ab84d-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ab84d-111">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="ab84d-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ab84d-112">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="ab84d-112">Known limitations</span></span>

- <span data-ttu-id="ab84d-113">Až 1 milion profilů na jeden export do služby DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ab84d-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="ab84d-114">Export do služby DotDigital je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="ab84d-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="ab84d-115">Export segmentů s celkem 1 milionem profilů může z důvodu omezení na straně poskytovatele trvat až 3 hodiny.</span><span class="sxs-lookup"><span data-stu-id="ab84d-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="ab84d-116">Počet profilů, které můžete exportovat do služby DotDigital, závisí a je omezen na vaší smlouvě se společností DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ab84d-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="ab84d-117">Nastavení propojení s aplikací DotDigital</span><span class="sxs-lookup"><span data-stu-id="ab84d-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="ab84d-118">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="ab84d-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ab84d-119">Vyberte **Přidat připojení** a zvolte **DotDigital** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="ab84d-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="ab84d-120">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="ab84d-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ab84d-121">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="ab84d-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ab84d-122">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="ab84d-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ab84d-123">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="ab84d-123">Choose who can use this connection.</span></span> <span data-ttu-id="ab84d-124">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="ab84d-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ab84d-125">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ab84d-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ab84d-126">Zadejte své **uživatelské jméno a heslo pro DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="ab84d-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="ab84d-127">Zadejte svoje **[ID adresáře DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="ab84d-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="ab84d-128">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="ab84d-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ab84d-129">Volbou **Připojit** inicializujte připojení ke službě DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ab84d-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="ab84d-130">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ab84d-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ab84d-131">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="ab84d-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="ab84d-132">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="ab84d-132">Configure an export</span></span>

<span data-ttu-id="ab84d-133">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="ab84d-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ab84d-134">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ab84d-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ab84d-135">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="ab84d-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ab84d-136">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="ab84d-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ab84d-137">V poli **propojení pro export** vyberte propojení v části DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ab84d-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="ab84d-138">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="ab84d-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="ab84d-139">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="ab84d-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ab84d-140">Stejné kroky opakujte pro další volitelná pole, například **Křestní jméno**, **Příjmení**, **Celé jméno**, **Pohlaví** a **PSČ**.</span><span class="sxs-lookup"><span data-stu-id="ab84d-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="ab84d-141">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="ab84d-141">Select the segments you want to export.</span></span> <span data-ttu-id="ab84d-142">Do služby DotDigital můžete exportovat celkem až 1 milion zákaznických profilů.</span><span class="sxs-lookup"><span data-stu-id="ab84d-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="ab84d-143">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="ab84d-143">Select **Save**.</span></span>

<span data-ttu-id="ab84d-144">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="ab84d-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ab84d-145">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ab84d-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ab84d-146">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ab84d-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="ab84d-147">Ve službě DotDigital nyní můžete najít své segmenty v [adresářích DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ab84d-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ab84d-148">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="ab84d-148">Data privacy and compliance</span></span>

<span data-ttu-id="ab84d-149">Když pro Dynamics 365 Customer Insights povolíte přenos dat do služby DotDigital, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="ab84d-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ab84d-150">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost DotDigital splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="ab84d-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ab84d-151">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ab84d-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ab84d-152">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ab84d-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
