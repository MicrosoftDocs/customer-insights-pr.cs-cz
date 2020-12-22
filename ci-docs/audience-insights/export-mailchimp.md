---
title: Export dat Customer Insights do služby Mailchimp
description: Naučte se, jak nakonfigurovat připojení ke službě Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405357"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="7313a-103">Konektor pro službu Mailchimp (Preview)</span><span class="sxs-lookup"><span data-stu-id="7313a-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="7313a-104">Exportujte segmenty sjednocených profilů zákazníků do služby Mailchimp a vytvářejte bulletiny a e-mailové kampaně.</span><span class="sxs-lookup"><span data-stu-id="7313a-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7313a-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="7313a-105">Prerequisites</span></span>

-   <span data-ttu-id="7313a-106">Máte [účet Mailchimp](https://mailchimp.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="7313a-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7313a-107">Služba Mailchimp obsahuje cílové skupiny a odpovídající ID.</span><span class="sxs-lookup"><span data-stu-id="7313a-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="7313a-108">Další informace viz [Cílové skupiny Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="7313a-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="7313a-109">Máte [konfigurované segmenty](segments.md)</span><span class="sxs-lookup"><span data-stu-id="7313a-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="7313a-110">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="7313a-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="7313a-111">Připojit k Mailchimpu</span><span class="sxs-lookup"><span data-stu-id="7313a-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="7313a-112">Přejděte na **Správce** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="7313a-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7313a-113">Pod **Mailchimp** vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="7313a-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="7313a-114">Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="7313a-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7313a-115">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="7313a-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7313a-116">Zadejte své **[ID cílové skupiny Mailchimp](https://mailchimp.com/help/find-audience-id/)** a volbou **Připojit** inicializujte připojení ke službě Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7313a-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="7313a-117">Vyberte **Ověření pomocí Mailchimp** a zadejte své přihlašovací údaje ke službě Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7313a-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="7313a-118">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7313a-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Screenshot exportu pro připojení ke službě Mailchimp":::

1. <span data-ttu-id="7313a-120">Vyberte **Další** pro konfiguraci exportu.</span><span class="sxs-lookup"><span data-stu-id="7313a-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="7313a-121">Konfigurace konektoru</span><span class="sxs-lookup"><span data-stu-id="7313a-121">Configure the connector</span></span>

1. <span data-ttu-id="7313a-122">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="7313a-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="7313a-123">Volitelně můžete exportovat **Křestní jméno** a **Příjmení** jako další pole k vytvoření lépe přizpůsobených e-mailů.</span><span class="sxs-lookup"><span data-stu-id="7313a-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="7313a-124">Volbou **Přidat atribut** namapujte tato pole.</span><span class="sxs-lookup"><span data-stu-id="7313a-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="7313a-125">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="7313a-125">Select the segments you want to export.</span></span> <span data-ttu-id="7313a-126">Do služby Mailchimp můžete exportovat celkem až 1 milion zákaznických profilů.</span><span class="sxs-lookup"><span data-stu-id="7313a-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Výběr polí a segmentů pro export do služby Mailchimp":::

1. <span data-ttu-id="7313a-128">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="7313a-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7313a-129">Export dat</span><span class="sxs-lookup"><span data-stu-id="7313a-129">Export the data</span></span>

<span data-ttu-id="7313a-130">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7313a-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7313a-131">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7313a-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7313a-132">Ve službě Mailchimp nyní najdete své segmenty v části [Cílové skupiny Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="7313a-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7313a-133">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="7313a-133">Known limitations</span></span>

- <span data-ttu-id="7313a-134">Až 1 milion profilů na jeden export do služby Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7313a-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="7313a-135">Export do služby Mailchimp je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="7313a-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="7313a-136">Export segmentů s celkem 1 milionem profilů může z důvodu omezení na straně poskytovatele trvat až tři hodiny.</span><span class="sxs-lookup"><span data-stu-id="7313a-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="7313a-137">Počet profilů, které můžete exportovat do služby Mailchimp, závisí a je omezen na vaší smlouvě se službou Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="7313a-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7313a-138">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="7313a-138">Data privacy and compliance</span></span>

<span data-ttu-id="7313a-139">Když povolíte Dynamics 365 Customer Insights přenos dat do služby Mailchimp, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="7313a-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7313a-140">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Mailchimp splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="7313a-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7313a-141">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7313a-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7313a-142">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7313a-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
