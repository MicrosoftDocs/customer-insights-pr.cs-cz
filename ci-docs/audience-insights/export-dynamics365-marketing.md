---
title: Export dat Customer Insights do Dynamics 365 Marketing
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759601"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="634f7-103">Použití segmentů v Dynamics 365 Marketing (Preview)</span><span class="sxs-lookup"><span data-stu-id="634f7-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="634f7-104">Použití [segmentů](segments.md) pro generování kampaní a kontaktování konkrétní skupiny zákazníků pomocí Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="634f7-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="634f7-105">Další informace získáte v tématu [Použití segmentů z Dynamics 365 Customer Insights s Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="634f7-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="634f7-106">Předpoklad pro propojení</span><span class="sxs-lookup"><span data-stu-id="634f7-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="634f7-107">Než budete moci exportovat segment z Customer Insights do aplikace Marketing, musí se v Dynamics 365 Marketing nacházet záznamy kontaktu.</span><span class="sxs-lookup"><span data-stu-id="634f7-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="634f7-108">Přečtěte si, jak ingestovat kontakty v [Dynamics 365 Marketing pomocí Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="634f7-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="634f7-109">Export segmentů z přehledů cílové skupiny do aplikace Marketing nevytvoří nové záznamy kontaktů v instancích aplikace Marketing.</span><span class="sxs-lookup"><span data-stu-id="634f7-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="634f7-110">Záznamy kontaktů z aplikace Marketing musí být zpracovány v přehledech cílové skupiny a použity jako zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="634f7-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="634f7-111">Než je možné segmenty exportovat, rovněž je třeba záznamy kontaktů zahrnout do sjednocené entity zákazníka, aby bylo možné mapovat ID zákazníků na ID kontaktů.</span><span class="sxs-lookup"><span data-stu-id="634f7-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="634f7-112">Nastavení propojení s aplikací Marketing</span><span class="sxs-lookup"><span data-stu-id="634f7-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="634f7-113">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="634f7-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="634f7-114">Vyberte **Přidat připojení** a zvolte **Dynamics 365 Marketing** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="634f7-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="634f7-115">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="634f7-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="634f7-116">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="634f7-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="634f7-117">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="634f7-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="634f7-118">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="634f7-118">Choose who can use this connection.</span></span> <span data-ttu-id="634f7-119">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="634f7-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="634f7-120">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="634f7-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="634f7-121">Zadejte marketingovou adresu URL vaší organizace do pole **Adresa serveru**.</span><span class="sxs-lookup"><span data-stu-id="634f7-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="634f7-122">V sekci **Účet správce serveru** vyberte **Přihlásit se** a vyberte účet Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="634f7-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="634f7-123">Namapujte pole ID zákazníka na ID kontaktu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="634f7-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="634f7-124">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="634f7-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="634f7-125">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="634f7-125">Configure an export</span></span>

<span data-ttu-id="634f7-126">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="634f7-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="634f7-127">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="634f7-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="634f7-128">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="634f7-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="634f7-129">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="634f7-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="634f7-130">V poli **Propojení pro export** vyberte propojení v části Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="634f7-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="634f7-131">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="634f7-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="634f7-132">Vyberte jeden nebo více segmentů.</span><span class="sxs-lookup"><span data-stu-id="634f7-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="634f7-133">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="634f7-133">Select **Save**.</span></span>

<span data-ttu-id="634f7-134">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="634f7-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="634f7-135">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="634f7-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="634f7-136">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="634f7-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
