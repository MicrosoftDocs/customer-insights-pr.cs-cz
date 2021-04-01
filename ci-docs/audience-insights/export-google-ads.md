---
title: Export dat Customer Insights do služby Google Ads
description: Naučte se, jak nakonfigurovat připojení ke službě Google Ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598239"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="92fa2-103">Konektor pro Google Ads (Preview)</span><span class="sxs-lookup"><span data-stu-id="92fa2-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="92fa2-104">Exportujte segmenty sjednocených profilů zákazníků do seznamu cílových skupin Google Ads a použijte je k inzerci ve službách Google Search, Gmail, YouTube a Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="92fa2-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="92fa2-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="92fa2-105">Prerequisites</span></span>

-   <span data-ttu-id="92fa2-106">Máte [účet Google Ads](https://ads.google.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="92fa2-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="92fa2-107">Google Ads obsahuje cílové skupiny a odpovídající ID.</span><span class="sxs-lookup"><span data-stu-id="92fa2-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="92fa2-108">Další informace viz [Cílové skupiny Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="92fa2-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="92fa2-109">Máte [konfigurované segmenty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="92fa2-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="92fa2-110">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu, křestní jméno a příjmení</span><span class="sxs-lookup"><span data-stu-id="92fa2-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="92fa2-111">Připojit ke Google Ads</span><span class="sxs-lookup"><span data-stu-id="92fa2-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="92fa2-112">Přejděte na **Správce** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="92fa2-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="92fa2-113">Pod **Google Ads** vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="92fa2-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="92fa2-114">Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="92fa2-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="92fa2-115">Zadejte své **[ID zákazníka Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="92fa2-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="92fa2-116">Zadete svůj **[token vývojáře schválený službou Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="92fa2-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="92fa2-117">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="92fa2-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="92fa2-118">Zadejte své **[ID cílové skupiny Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** a volbou **Připojit** inicializujte připojení k Google Ads.</span><span class="sxs-lookup"><span data-stu-id="92fa2-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="92fa2-119">Vyberte **Ověření pomocí Google Ads** a zadejte své přihlašovací údaje k Google Ads.</span><span class="sxs-lookup"><span data-stu-id="92fa2-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="92fa2-120">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="92fa2-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Screenshot exportu pro připojení Google Ads":::

1. <span data-ttu-id="92fa2-122">Vyberte **Další** pro konfiguraci exportu.</span><span class="sxs-lookup"><span data-stu-id="92fa2-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="92fa2-123">Konfigurace konektoru</span><span class="sxs-lookup"><span data-stu-id="92fa2-123">Configure the connector</span></span>

1. <span data-ttu-id="92fa2-124">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="92fa2-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="92fa2-125">Stejné kroky opakujte pro pole **Křestní jméno** a **Příjmení**.</span><span class="sxs-lookup"><span data-stu-id="92fa2-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="92fa2-126">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="92fa2-126">Select the segments you want to export.</span></span> <span data-ttu-id="92fa2-127">Do Google Ads můžete exportovat celkem až 1 milion zákaznických profilů.</span><span class="sxs-lookup"><span data-stu-id="92fa2-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="92fa2-128">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="92fa2-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="92fa2-129">Export dat</span><span class="sxs-lookup"><span data-stu-id="92fa2-129">Export the data</span></span>

<span data-ttu-id="92fa2-130">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="92fa2-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="92fa2-131">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="92fa2-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="92fa2-132">V Google Ads nyní najdete své segmenty v části [Cílové skupiny Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="92fa2-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="92fa2-133">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="92fa2-133">Known limitations</span></span>

- <span data-ttu-id="92fa2-134">Až 1 milion profilů na jeden export do služby Google Ads.</span><span class="sxs-lookup"><span data-stu-id="92fa2-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="92fa2-135">Export do služby Google Ads je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="92fa2-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="92fa2-136">Export segmentů s celkem 1 milionem profilů může z důvodu omezení na straně poskytovatele trvat až 5 minut.</span><span class="sxs-lookup"><span data-stu-id="92fa2-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="92fa2-137">Spárování v Google Ads může trvat až 48 hodin.</span><span class="sxs-lookup"><span data-stu-id="92fa2-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="92fa2-138">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="92fa2-138">Data privacy and compliance</span></span>

<span data-ttu-id="92fa2-139">Když povolíte Dynamics 365 Customer Insights přenos dat do služby Google Ads, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="92fa2-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="92fa2-140">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Google Ads splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="92fa2-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="92fa2-141">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="92fa2-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="92fa2-142">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="92fa2-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]