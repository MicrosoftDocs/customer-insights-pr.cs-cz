---
title: Export dat Customer Insights do služby SendGrid
description: Naučte se, jak nakonfigurovat připojení ke službě SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597273"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="ac00d-103">Konektor pro službu SendGrid (Preview)</span><span class="sxs-lookup"><span data-stu-id="ac00d-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="ac00d-104">Exportujte segmenty sjednocených profilů zákazníků do seznamů kontaktů SendGrid a použijte je pro kampaně a e-mailový marketing ve službě SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ac00d-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ac00d-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ac00d-105">Prerequisites</span></span>

-   <span data-ttu-id="ac00d-106">Máte [účet SendGrid](https://sendgrid.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="ac00d-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ac00d-107">Služba SendGrid obsahuje seznamy kontaktů a odpovídající ID.</span><span class="sxs-lookup"><span data-stu-id="ac00d-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="ac00d-108">Další informace viz [SendGrid – Správa kontaktů](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="ac00d-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="ac00d-109">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ac00d-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ac00d-110">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="ac00d-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="ac00d-111">Připojení k SendGrid</span><span class="sxs-lookup"><span data-stu-id="ac00d-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="ac00d-112">Přejděte na **Správce** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="ac00d-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ac00d-113">Pod **SendGrid** vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="ac00d-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="ac00d-114">Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="ac00d-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Podokno konfigurace exportu SendGrid.":::

1. <span data-ttu-id="ac00d-116">Zadejte **klíč rozhraní API SendGrid** [Klíč rozhraní API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="ac00d-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="ac00d-117">Zadejte své **[ID seznamu SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="ac00d-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="ac00d-118">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="ac00d-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ac00d-119">Volbou **Připojit** inicializujte připojení ke službě SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ac00d-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="ac00d-120">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ac00d-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ac00d-121">Vyberte **Další** pro konfiguraci exportu.</span><span class="sxs-lookup"><span data-stu-id="ac00d-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ac00d-122">Konfigurace konektoru</span><span class="sxs-lookup"><span data-stu-id="ac00d-122">Configure the connector</span></span>

1. <span data-ttu-id="ac00d-123">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="ac00d-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ac00d-124">Stejné kroky opakujte pro další volitelná pole, například **Křestní jméno**, **Příjmení**, **Země/oblast**, **Stát**, **Město** a **PSČ**.</span><span class="sxs-lookup"><span data-stu-id="ac00d-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="ac00d-125">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="ac00d-125">Select the segments you want to export.</span></span> <span data-ttu-id="ac00d-126">Velice **doporučujeme neexportovat více než 100 000 profilů zákazníků** do služby SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ac00d-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="ac00d-127">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="ac00d-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ac00d-128">Export dat</span><span class="sxs-lookup"><span data-stu-id="ac00d-128">Export the data</span></span>

<span data-ttu-id="ac00d-129">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ac00d-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ac00d-130">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ac00d-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ac00d-131">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="ac00d-131">Known limitations</span></span>

- <span data-ttu-id="ac00d-132">Maximálně 100 000 profilů, které lze odeslat do služby SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ac00d-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="ac00d-133">Export do služby SendGrid je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="ac00d-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="ac00d-134">Export až 100 000 profilů do služby SendGrid může trvat až několik hodin.</span><span class="sxs-lookup"><span data-stu-id="ac00d-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="ac00d-135">Počet profilů, které můžete exportovat do služby SendGrid, závisí a je omezen na vaší smlouvě se službou SendGrid.</span><span class="sxs-lookup"><span data-stu-id="ac00d-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ac00d-136">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="ac00d-136">Data privacy and compliance</span></span>

<span data-ttu-id="ac00d-137">Když povolíte Dynamics 365 Customer Insights přenos dat do služby SendGrid, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="ac00d-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ac00d-138">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost SendGrid splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="ac00d-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ac00d-139">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ac00d-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ac00d-140">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ac00d-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]