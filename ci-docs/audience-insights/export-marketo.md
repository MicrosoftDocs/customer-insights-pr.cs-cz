---
title: Export dat Customer Insights do služby Marketo
description: Naučte se, jak nakonfigurovat připojení ke službě Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267073"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="81ea6-103">Konektor pro službu Marketo (Preview)</span><span class="sxs-lookup"><span data-stu-id="81ea6-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="81ea6-104">Exportem segmentů sjednocených profilů zákazníků můžete generovat kampaně, poskytovat e-mailový marketing a využívat konkrétní skupiny zákazníků pomocí služby Marketo.</span><span class="sxs-lookup"><span data-stu-id="81ea6-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="81ea6-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="81ea6-105">Prerequisites</span></span>

-   <span data-ttu-id="81ea6-106">Máte [účet Marketo](https://login.marketo.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="81ea6-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="81ea6-107">Služba Marketo obsahuje stávající seznamy a odpovídající ID.</span><span class="sxs-lookup"><span data-stu-id="81ea6-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="81ea6-108">Další informace naleznete v [seznamech Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="81ea6-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="81ea6-109">Máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="81ea6-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="81ea6-110">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="81ea6-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="81ea6-111">Připojení ke službě Marketo</span><span class="sxs-lookup"><span data-stu-id="81ea6-111">Connect to Marketo</span></span>

1. <span data-ttu-id="81ea6-112">Přejděte na **Správce** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="81ea6-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="81ea6-113">Pod **Marketo** vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="81ea6-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="81ea6-114">Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="81ea6-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="81ea6-115">Zadejte své **[ID klienta Marketo, tajný klíč klienta a název hostitele koncového bodu REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="81ea6-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="81ea6-116">Zadejte své **[ID seznamu Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="81ea6-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="81ea6-117">Volbou **Souhlasím** potvrdíte **Ochranu osobních údajů a dodržování předpisů** a volbou **Připojit** inicializujete připojení ke službě Marketo.</span><span class="sxs-lookup"><span data-stu-id="81ea6-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="81ea6-118">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="81ea6-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Screenshot exportu pro připojení ke službě Marketo":::

1. <span data-ttu-id="81ea6-120">Vyberte **Další** pro konfiguraci exportu.</span><span class="sxs-lookup"><span data-stu-id="81ea6-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="81ea6-121">Konfigurace konektoru</span><span class="sxs-lookup"><span data-stu-id="81ea6-121">Configure the connector</span></span>

1. <span data-ttu-id="81ea6-122">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="81ea6-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="81ea6-123">Volitelně můžete exportovat **Křestní jméno**, **Příjmení**, **Město**, **Stát** a **Oblast/zemi** jako další pole k vytvoření lépe přizpůsobených e-mailů.</span><span class="sxs-lookup"><span data-stu-id="81ea6-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="81ea6-124">Volbou **Přidat atribut** namapujte tato pole.</span><span class="sxs-lookup"><span data-stu-id="81ea6-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="81ea6-125">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="81ea6-125">Select the segments you want to export.</span></span> <span data-ttu-id="81ea6-126">Do služby Marketo můžete exportovat celkem až 1 milion zákaznických profilů.</span><span class="sxs-lookup"><span data-stu-id="81ea6-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Výběr polí a segmentů pro export do služby Marketo":::

1. <span data-ttu-id="81ea6-128">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="81ea6-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="81ea6-129">Export dat</span><span class="sxs-lookup"><span data-stu-id="81ea6-129">Export the data</span></span>

<span data-ttu-id="81ea6-130">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="81ea6-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="81ea6-131">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="81ea6-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="81ea6-132">Ve službě Marketo nyní najdete své segmenty v části [Seznamy Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="81ea6-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="81ea6-133">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="81ea6-133">Known limitations</span></span>

- <span data-ttu-id="81ea6-134">Až 1 milion profilů na jeden export do služby Marketo.</span><span class="sxs-lookup"><span data-stu-id="81ea6-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="81ea6-135">Export do služby Marketo je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="81ea6-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="81ea6-136">Export segmentů s celkem 1 milionem profilů může trvat až 3 hodiny.</span><span class="sxs-lookup"><span data-stu-id="81ea6-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="81ea6-137">Počet profilů, které můžete exportovat do služby Marketo, závisí a je omezen na vaší smlouvě se službou Marketo.</span><span class="sxs-lookup"><span data-stu-id="81ea6-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="81ea6-138">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="81ea6-138">Data privacy and compliance</span></span>

<span data-ttu-id="81ea6-139">Když povolíte Dynamics 365 Customer Insights přenos dat do služby Marketo, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="81ea6-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="81ea6-140">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Marketo splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="81ea6-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="81ea6-141">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="81ea6-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="81ea6-142">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="81ea6-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]