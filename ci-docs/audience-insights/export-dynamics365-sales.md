---
title: Export dat Customer Insights do Dynamics 365 Sales
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759583"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="2306c-103">Použití segmentů v Dynamics 365 Sales (Preview)</span><span class="sxs-lookup"><span data-stu-id="2306c-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="2306c-104">Aplikace Dynamics 365 Sales umožňuje na základě zákaznických dat vytvářet marketingové seznamy, sledovat pracovní postupy a rozesílat propagační akce.</span><span class="sxs-lookup"><span data-stu-id="2306c-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="2306c-105">Předpoklad pro připojení</span><span class="sxs-lookup"><span data-stu-id="2306c-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="2306c-106">Než budete moci exportovat segment z Customer Insights do aplikace Sales, musí se v Dynamics 365 Sales nacházet záznamy kontaktu.</span><span class="sxs-lookup"><span data-stu-id="2306c-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="2306c-107">Přečtěte si, jak ingestovat kontakty v [Dynamics 365 Sales pomocí Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="2306c-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="2306c-108">Export segmentů z přehledů cílové skupiny do aplikace Sales nevytvoří nové záznamy kontaktů v instancích aplikace Sales.</span><span class="sxs-lookup"><span data-stu-id="2306c-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="2306c-109">Záznamy kontaktů z aplikace Sales musí být zpracovány v přehledech cílové skupiny a použity jako zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="2306c-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="2306c-110">Než je možné segmenty exportovat, rovněž je třeba záznamy kontaktů zahrnout do sjednocené entity zákazníka, aby bylo možné mapovat ID zákazníků na ID kontaktů.</span><span class="sxs-lookup"><span data-stu-id="2306c-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="2306c-111">Nastavení propojení se Sales</span><span class="sxs-lookup"><span data-stu-id="2306c-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="2306c-112">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="2306c-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2306c-113">Vyberte **Přidat připojení** a zvolte **Dynamics 365 Sales** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="2306c-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="2306c-114">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="2306c-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2306c-115">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="2306c-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2306c-116">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="2306c-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2306c-117">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="2306c-117">Choose who can use this connection.</span></span> <span data-ttu-id="2306c-118">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="2306c-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2306c-119">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2306c-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2306c-120">Zadejte adresu URL Sales vaší organizace do pole **Adresa serveru**.</span><span class="sxs-lookup"><span data-stu-id="2306c-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="2306c-121">V sekci **Účet správce serveru** vyberte **Přihlásit se** a vyberte účet Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="2306c-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="2306c-122">Namapujte pole ID zákazníka na ID kontaktu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="2306c-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="2306c-123">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="2306c-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="2306c-124">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="2306c-124">Configure an export</span></span>

<span data-ttu-id="2306c-125">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="2306c-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2306c-126">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2306c-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2306c-127">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="2306c-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2306c-128">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="2306c-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2306c-129">V poli **propojení pro export** vyberte propojení v části Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="2306c-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="2306c-130">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="2306c-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2306c-131">Vyberte jeden nebo více segmentů.</span><span class="sxs-lookup"><span data-stu-id="2306c-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="2306c-132">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="2306c-132">Select **Save**</span></span>

<span data-ttu-id="2306c-133">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="2306c-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2306c-134">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2306c-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2306c-135">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2306c-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
