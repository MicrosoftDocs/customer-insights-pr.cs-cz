---
title: Export dat Customer Insights do služby Autopilot
description: Naučte se, jak nakonfigurovat připojení ke službě Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269230"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="dbcea-103">Konektor pro službu Autopilot (Preview)</span><span class="sxs-lookup"><span data-stu-id="dbcea-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="dbcea-104">Exportujte segmenty sjednocených profilů zákazníků do služby Autopilot a použijte je pro e-mailový marketing ve službě Autopilot.</span><span class="sxs-lookup"><span data-stu-id="dbcea-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="dbcea-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="dbcea-105">Prerequisites</span></span>

-   <span data-ttu-id="dbcea-106">Máte [účet Autopilot](https://www.autopilothq.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="dbcea-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="dbcea-107">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="dbcea-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="dbcea-108">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="dbcea-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="dbcea-109">Připojení ke službě Autopilot</span><span class="sxs-lookup"><span data-stu-id="dbcea-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="dbcea-110">Přejděte na **Správce** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="dbcea-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dbcea-111">Pod **Autopilot** vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="dbcea-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="dbcea-112">Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="dbcea-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfigurační podokno pro připojení služby Autopilot.":::

1. <span data-ttu-id="dbcea-114">Zadejte svůj **klíč rozhraní API služby Autopilot** [Klíč rozhraní API služby Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="dbcea-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="dbcea-115">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="dbcea-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="dbcea-116">Volbou **Připojit** inicializujte připojení ke službě Autopilot.</span><span class="sxs-lookup"><span data-stu-id="dbcea-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="dbcea-117">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dbcea-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="dbcea-118">Vyberte **Další** pro konfiguraci exportu.</span><span class="sxs-lookup"><span data-stu-id="dbcea-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="dbcea-119">Konfigurace konektoru</span><span class="sxs-lookup"><span data-stu-id="dbcea-119">Configure the connector</span></span>

1. <span data-ttu-id="dbcea-120">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="dbcea-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="dbcea-121">Stejné kroky opakujte pro další volitelná pole, například **Křestní jméno**, **Příjmení**.</span><span class="sxs-lookup"><span data-stu-id="dbcea-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="dbcea-122">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="dbcea-122">Select the segments you want to export.</span></span> <span data-ttu-id="dbcea-123">Velice **doporučujeme neexportovat více než 100 000 profilů zákazníků** do služby Autopilot.</span><span class="sxs-lookup"><span data-stu-id="dbcea-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="dbcea-124">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="dbcea-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="dbcea-125">Export dat</span><span class="sxs-lookup"><span data-stu-id="dbcea-125">Export the data</span></span>

<span data-ttu-id="dbcea-126">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="dbcea-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="dbcea-127">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dbcea-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="dbcea-128">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="dbcea-128">Known limitations</span></span>

- <span data-ttu-id="dbcea-129">Do služby Autopilot můžete exportovat celkem až 100 000 profilů zákazníků.</span><span class="sxs-lookup"><span data-stu-id="dbcea-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="dbcea-130">Export do služby Autopilot je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="dbcea-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="dbcea-131">Export až 100 000 profilů do služby Autopilot může trvat až několik hodin.</span><span class="sxs-lookup"><span data-stu-id="dbcea-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="dbcea-132">Počet profilů, které můžete exportovat do služby Autopilot, závisí a je omezen na vaší smlouvě se službou Autopilot.</span><span class="sxs-lookup"><span data-stu-id="dbcea-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dbcea-133">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="dbcea-133">Data privacy and compliance</span></span>

<span data-ttu-id="dbcea-134">Když povolíte Dynamics 365 Customer Insights přenos dat do služby Autopilot, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="dbcea-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dbcea-135">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Autopilot splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="dbcea-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="dbcea-136">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dbcea-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dbcea-137">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dbcea-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]