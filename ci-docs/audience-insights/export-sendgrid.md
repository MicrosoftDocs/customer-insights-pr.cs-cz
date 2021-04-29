---
title: Export dat Customer Insights do služby SendGrid
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759757"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="059cc-103">Export segmentů do SendGrid (náhled)</span><span class="sxs-lookup"><span data-stu-id="059cc-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="059cc-104">Exportujte segmenty sjednocených profilů zákazníků do seznamů kontaktů SendGrid a použijte je pro kampaně a e-mailový marketing ve službě SendGrid.</span><span class="sxs-lookup"><span data-stu-id="059cc-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="059cc-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="059cc-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="059cc-106">Máte [účet SendGrid](https://sendgrid.com/) a odpovídající přihlašovací údaje správce.</span><span class="sxs-lookup"><span data-stu-id="059cc-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="059cc-107">Služba SendGrid obsahuje seznamy kontaktů a odpovídající ID.</span><span class="sxs-lookup"><span data-stu-id="059cc-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="059cc-108">Další informace viz [SendGrid – Správa kontaktů](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="059cc-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="059cc-109">V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).</span><span class="sxs-lookup"><span data-stu-id="059cc-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="059cc-110">Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.</span><span class="sxs-lookup"><span data-stu-id="059cc-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="059cc-111">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="059cc-111">Known limitations</span></span>

- <span data-ttu-id="059cc-112">Maximálně 100 000 profilů, které lze odeslat do služby SendGrid.</span><span class="sxs-lookup"><span data-stu-id="059cc-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="059cc-113">Export do služby SendGrid je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="059cc-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="059cc-114">Export až 100 000 profilů do služby SendGrid může trvat až několik hodin.</span><span class="sxs-lookup"><span data-stu-id="059cc-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="059cc-115">Počet profilů, které můžete exportovat do služby SendGrid, závisí a je omezen na vaší smlouvě se službou SendGrid.</span><span class="sxs-lookup"><span data-stu-id="059cc-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="059cc-116">Nastavení propojení se SendGrid</span><span class="sxs-lookup"><span data-stu-id="059cc-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="059cc-117">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="059cc-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="059cc-118">Vyberte **Přidat připojení** a zvolte **SendGrid** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="059cc-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="059cc-119">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="059cc-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="059cc-120">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="059cc-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="059cc-121">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="059cc-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="059cc-122">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="059cc-122">Choose who can use this connection.</span></span> <span data-ttu-id="059cc-123">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="059cc-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="059cc-124">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="059cc-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="059cc-125">Zadejte **klíč rozhraní API SendGrid** [Klíč rozhraní API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="059cc-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="059cc-126">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="059cc-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="059cc-127">Volbou **Připojit** inicializujte připojení ke službě SendGrid.</span><span class="sxs-lookup"><span data-stu-id="059cc-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="059cc-128">Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="059cc-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="059cc-129">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="059cc-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="059cc-130">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="059cc-130">Configure an export</span></span>

<span data-ttu-id="059cc-131">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="059cc-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="059cc-132">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="059cc-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="059cc-133">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="059cc-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="059cc-134">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="059cc-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="059cc-135">V poli **Propojení pro export** vyberte propojení v části SendGrid.</span><span class="sxs-lookup"><span data-stu-id="059cc-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="059cc-136">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="059cc-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="059cc-137">Zadejte své **[ID seznamu SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="059cc-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="059cc-138">V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="059cc-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="059cc-139">Stejné kroky opakujte pro další volitelná pole, například **Křestní jméno**, **Příjmení**, **Země/oblast**, **Stát**, **Město** a **PSČ**.</span><span class="sxs-lookup"><span data-stu-id="059cc-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="059cc-140">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="059cc-140">Select the segments you want to export.</span></span> <span data-ttu-id="059cc-141">Velice **doporučujeme neexportovat více než 100 000 profilů zákazníků** do služby SendGrid.</span><span class="sxs-lookup"><span data-stu-id="059cc-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="059cc-142">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="059cc-142">Select **Save**.</span></span>

<span data-ttu-id="059cc-143">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="059cc-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="059cc-144">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="059cc-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="059cc-145">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="059cc-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="059cc-146">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="059cc-146">Data privacy and compliance</span></span>

<span data-ttu-id="059cc-147">Když povolíte Dynamics 365 Customer Insights přenos dat do služby SendGrid, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="059cc-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="059cc-148">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost SendGrid splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="059cc-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="059cc-149">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="059cc-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="059cc-150">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="059cc-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]