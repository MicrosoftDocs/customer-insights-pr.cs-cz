---
title: Export dat Customer Insights do služby Marketo
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759813"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="c4ebc-103">Export segmentů do Marketo (náhled)</span><span class="sxs-lookup"><span data-stu-id="c4ebc-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="c4ebc-104">Exportem segmentů sjednocených profilů zákazníků můžete generovat kampaně, poskytovat e-mailový marketing a využívat konkrétní skupiny zákazníků pomocí služby Marketo.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="c4ebc-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="c4ebc-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="c4ebc-106">Máte [účet Marketo](https://login.marketo.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c4ebc-107">Služba Marketo obsahuje stávající seznamy a odpovídající ID.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="c4ebc-108">Další informace naleznete v [seznamech Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="c4ebc-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="c4ebc-109">Máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c4ebc-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="c4ebc-110">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c4ebc-111">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="c4ebc-111">Known limitations</span></span>

- <span data-ttu-id="c4ebc-112">Až 1 milion profilů na jeden export do služby Marketo.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="c4ebc-113">Export do služby Marketo je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="c4ebc-114">Export segmentů s celkem 1 milionem profilů může trvat až 3 hodiny.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="c4ebc-115">Počet profilů, které můžete exportovat do služby Marketo, závisí a je omezen na vaší smlouvě se službou Marketo.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="c4ebc-116">Nastavení propojení s aplikací Marketo</span><span class="sxs-lookup"><span data-stu-id="c4ebc-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="c4ebc-117">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c4ebc-118">Vyberte **Přidat připojení** a zvolte **Marketo** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="c4ebc-119">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c4ebc-120">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c4ebc-121">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c4ebc-122">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-122">Choose who can use this connection.</span></span> <span data-ttu-id="c4ebc-123">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c4ebc-124">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c4ebc-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c4ebc-125">Zadejte své **[ID klienta Marketo, tajný klíč klienta a název hostitele koncového bodu REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="c4ebc-126">Volbou **Souhlasím** potvrdíte **Ochranu osobních údajů a dodržování předpisů** a volbou **Připojit** inicializujete připojení ke službě Marketo.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="c4ebc-127">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c4ebc-128">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c4ebc-129">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="c4ebc-129">Configure an export</span></span>

<span data-ttu-id="c4ebc-130">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c4ebc-131">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c4ebc-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c4ebc-132">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c4ebc-133">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c4ebc-134">V poli **Propojení pro export** vyberte propojení v části Marketo.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="c4ebc-135">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c4ebc-136">Zadejte své **[ID seznamu Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="c4ebc-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="c4ebc-137">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="c4ebc-138">Volitelně můžete exportovat **křestní jméno**, **příjmení**, **město**, **stát** a **zemi/region** pro vytvoření více přizpůsobených e-mailů.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="c4ebc-139">Volbou **Přidat atribut** namapujte tato pole.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="c4ebc-140">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-140">Select the segments you want to export.</span></span> <span data-ttu-id="c4ebc-141">Do služby Marketo můžete exportovat celkem až 1 milion zákaznických profilů.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="c4ebc-142">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-142">Select **Save**.</span></span>

<span data-ttu-id="c4ebc-143">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c4ebc-144">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c4ebc-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c4ebc-145">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c4ebc-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="c4ebc-146">Ve službě Marketo nyní najdete své segmenty v části [Seznamy Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="c4ebc-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c4ebc-147">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="c4ebc-147">Data privacy and compliance</span></span>

<span data-ttu-id="c4ebc-148">Když povolíte Dynamics 365 Customer Insights přenos dat do služby Marketo, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c4ebc-149">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Marketo splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c4ebc-150">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c4ebc-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c4ebc-151">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c4ebc-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]