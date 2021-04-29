---
title: Export dat Customer Insights do služby Google Ads
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759685"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="44be0-103">Export segmentů do Google Ads (náhled)</span><span class="sxs-lookup"><span data-stu-id="44be0-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="44be0-104">Exportujte segmenty sjednocených profilů zákazníků do seznamu cílových skupin Google Ads a použijte je k inzerci ve službách Google Search, Gmail, YouTube a Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="44be0-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="44be0-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="44be0-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="44be0-106">Máte [účet Google Ads](https://ads.google.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="44be0-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="44be0-107">Máte [schválený token vývojáře Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="44be0-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="44be0-108">Splňujete požadavky [Zásad pro vlastní seznamy zákazníků](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="44be0-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="44be0-109">Splňujete požadavky [velikosti remarketingového seznamu](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="44be0-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="44be0-110">Google Ads obsahuje cílové skupiny a odpovídající ID.</span><span class="sxs-lookup"><span data-stu-id="44be0-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="44be0-111">Další informace viz [Cílové skupiny Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="44be0-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="44be0-112">Máte [konfigurované segmenty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="44be0-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="44be0-113">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu, křestní jméno a příjmení</span><span class="sxs-lookup"><span data-stu-id="44be0-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="44be0-114">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="44be0-114">Known limitations</span></span>

- <span data-ttu-id="44be0-115">Až 1 milion profilů na jeden export do služby Google Ads.</span><span class="sxs-lookup"><span data-stu-id="44be0-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="44be0-116">Export do služby Google Ads je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="44be0-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="44be0-117">Export segmentů s celkem 1 milionem profilů může z důvodu omezení na straně poskytovatele trvat až 5 minut.</span><span class="sxs-lookup"><span data-stu-id="44be0-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="44be0-118">Spárování v Google Ads může trvat až 48 hodin.</span><span class="sxs-lookup"><span data-stu-id="44be0-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="44be0-119">Nastavení propojení ke Google Ads</span><span class="sxs-lookup"><span data-stu-id="44be0-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="44be0-120">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="44be0-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="44be0-121">Vyberte **Přidat připojení** a zvolte **Google Ads** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="44be0-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="44be0-122">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="44be0-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="44be0-123">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="44be0-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="44be0-124">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="44be0-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="44be0-125">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="44be0-125">Choose who can use this connection.</span></span> <span data-ttu-id="44be0-126">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="44be0-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="44be0-127">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="44be0-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="44be0-128">Zadejte své **[ID zákazníka Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="44be0-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="44be0-129">Zadete svůj **[token vývojáře schválený službou Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="44be0-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="44be0-130">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="44be0-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="44be0-131">Vyberte **Ověření pomocí Google Ads** a zadejte své přihlašovací údaje k Google Ads.</span><span class="sxs-lookup"><span data-stu-id="44be0-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="44be0-132">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="44be0-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="44be0-133">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="44be0-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="44be0-134">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="44be0-134">Configure an export</span></span>

<span data-ttu-id="44be0-135">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="44be0-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="44be0-136">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="44be0-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="44be0-137">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="44be0-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="44be0-138">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="44be0-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="44be0-139">V poli **propojení pro export** vyberte propojení v části Google Ads.</span><span class="sxs-lookup"><span data-stu-id="44be0-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="44be0-140">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="44be0-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="44be0-141">Zadejte své **[ID cílové skupiny Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** a volbou **Připojit** inicializujte připojení k Google Ads.</span><span class="sxs-lookup"><span data-stu-id="44be0-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="44be0-142">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="44be0-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="44be0-143">Stejné kroky opakujte pro pole **Křestní jméno** a **Příjmení**.</span><span class="sxs-lookup"><span data-stu-id="44be0-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="44be0-144">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="44be0-144">Select the segments you want to export.</span></span> <span data-ttu-id="44be0-145">Do Google Ads můžete exportovat celkem až 1 milion zákaznických profilů.</span><span class="sxs-lookup"><span data-stu-id="44be0-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="44be0-146">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="44be0-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="44be0-147">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="44be0-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="44be0-148">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="44be0-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="44be0-149">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="44be0-149">Data privacy and compliance</span></span>

<span data-ttu-id="44be0-150">Když povolíte Dynamics 365 Customer Insights přenos dat do služby Google Ads, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="44be0-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="44be0-151">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Google Ads splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="44be0-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="44be0-152">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="44be0-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="44be0-153">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="44be0-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
