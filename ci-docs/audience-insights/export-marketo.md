---
title: Export dat Customer Insights do služby Marketo
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059308"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="e0004-103">Export segmentů do Marketo (náhled)</span><span class="sxs-lookup"><span data-stu-id="e0004-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="e0004-104">Exportem segmentů sjednocených profilů zákazníků můžete generovat kampaně, poskytovat e-mailový marketing a využívat konkrétní skupiny zákazníků pomocí služby Marketo.</span><span class="sxs-lookup"><span data-stu-id="e0004-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e0004-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="e0004-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="e0004-106">Máte [účet Marketo](https://login.marketo.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="e0004-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e0004-107">Služba Marketo obsahuje stávající seznamy a odpovídající ID.</span><span class="sxs-lookup"><span data-stu-id="e0004-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="e0004-108">Další informace naleznete v [seznamech Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="e0004-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="e0004-109">Máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e0004-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="e0004-110">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="e0004-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e0004-111">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="e0004-111">Known limitations</span></span>

- <span data-ttu-id="e0004-112">Až 1 milion profilů na jeden export do služby Marketo.</span><span class="sxs-lookup"><span data-stu-id="e0004-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="e0004-113">Export do služby Marketo je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="e0004-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="e0004-114">Export segmentů s celkem 1 milionem profilů může trvat až 3 hodiny.</span><span class="sxs-lookup"><span data-stu-id="e0004-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="e0004-115">Počet profilů, které můžete exportovat do služby Marketo, závisí a je omezen na vaší smlouvě se službou Marketo.</span><span class="sxs-lookup"><span data-stu-id="e0004-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="e0004-116">Nastavení propojení s aplikací Marketo</span><span class="sxs-lookup"><span data-stu-id="e0004-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="e0004-117">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="e0004-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e0004-118">Vyberte **Přidat připojení** a zvolte **Marketo** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="e0004-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="e0004-119">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="e0004-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e0004-120">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="e0004-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e0004-121">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="e0004-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e0004-122">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="e0004-122">Choose who can use this connection.</span></span> <span data-ttu-id="e0004-123">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="e0004-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e0004-124">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e0004-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e0004-125">Zadejte své **[ID klienta Marketo, tajný klíč klienta a název hostitele koncového bodu REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="e0004-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="e0004-126">Koncový bod názvu hostitele REST je pouze název hostitele, bez `https://`.</span><span class="sxs-lookup"><span data-stu-id="e0004-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="e0004-127">Příklad: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="e0004-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="e0004-128">Volbou **Souhlasím** potvrdíte **Ochranu osobních údajů a dodržování předpisů** a volbou **Připojit** inicializujete připojení ke službě Marketo.</span><span class="sxs-lookup"><span data-stu-id="e0004-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="e0004-129">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e0004-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e0004-130">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="e0004-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e0004-131">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="e0004-131">Configure an export</span></span>

<span data-ttu-id="e0004-132">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="e0004-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e0004-133">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e0004-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e0004-134">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="e0004-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e0004-135">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="e0004-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e0004-136">V poli **Propojení pro export** vyberte propojení v části Marketo.</span><span class="sxs-lookup"><span data-stu-id="e0004-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="e0004-137">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="e0004-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e0004-138">Zadejte **[ID seznamu Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="e0004-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="e0004-139">ID seznamu je čistě číselná hodnota.</span><span class="sxs-lookup"><span data-stu-id="e0004-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="e0004-140">Například pokud je vaše ID seznamu Marketo ST12345A7, odstraňte znak před a za číslicemi a zadejte `12345`.</span><span class="sxs-lookup"><span data-stu-id="e0004-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="e0004-141">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="e0004-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e0004-142">Volitelně můžete exportovat **křestní jméno**, **příjmení**, **město**, **stát** a **zemi/region** pro vytvoření více přizpůsobených e-mailů.</span><span class="sxs-lookup"><span data-stu-id="e0004-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="e0004-143">Volbou **Přidat atribut** namapujte tato pole.</span><span class="sxs-lookup"><span data-stu-id="e0004-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e0004-144">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="e0004-144">Select the segments you want to export.</span></span> <span data-ttu-id="e0004-145">Do služby Marketo můžete exportovat celkem až 1 milion zákaznických profilů.</span><span class="sxs-lookup"><span data-stu-id="e0004-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="e0004-146">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="e0004-146">Select **Save**.</span></span>

<span data-ttu-id="e0004-147">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="e0004-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e0004-148">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e0004-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e0004-149">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e0004-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="e0004-150">Ve službě Marketo nyní najdete své segmenty v části [Seznamy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="e0004-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e0004-151">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="e0004-151">Data privacy and compliance</span></span>

<span data-ttu-id="e0004-152">Když povolíte Dynamics 365 Customer Insights přenos dat do služby Marketo, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="e0004-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e0004-153">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Marketo splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="e0004-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e0004-154">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e0004-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e0004-155">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e0004-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
