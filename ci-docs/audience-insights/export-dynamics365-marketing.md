---
title: Export dat Customer Insights do Dynamics 365 Marketing
description: Naučte se, jak nakonfigurovat připojení k Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597595"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="404a4-103">Konektor pro Dynamics 365 Marketing (preview)</span><span class="sxs-lookup"><span data-stu-id="404a4-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="404a4-104">Použití [segmentů](segments.md) pro generování kampaní a kontaktování konkrétní skupiny zákazníků pomocí Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="404a4-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="404a4-105">Další informace získáte v tématu [Použití segmentů z Dynamics 365 Customer Insights s Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="404a4-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="404a4-106">Požadavek</span><span class="sxs-lookup"><span data-stu-id="404a4-106">Prerequisite</span></span>

- <span data-ttu-id="404a4-107">Než budete moci exportovat segment z Customer Insights do aplikace Marketing, musí se v Dynamics 365 Marketing nacházet záznamy kontaktu.</span><span class="sxs-lookup"><span data-stu-id="404a4-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="404a4-108">Přečtěte si, jak ingestovat kontakty v [Dynamics 365 Marketing pomocí Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="404a4-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="404a4-109">Export segmentů z přehledů cílové skupiny do aplikace Marketing nevytvoří nové záznamy kontaktů v instancích aplikace Marketing.</span><span class="sxs-lookup"><span data-stu-id="404a4-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="404a4-110">Záznamy kontaktů z aplikace Marketing musí být zpracovány v přehledech cílové skupiny a použity jako zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="404a4-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="404a4-111">Než je možné segmenty exportovat, rovněž je třeba záznamy kontaktů zahrnout do sjednocené entity zákazníka, aby bylo možné mapovat ID zákazníků na ID kontaktů.</span><span class="sxs-lookup"><span data-stu-id="404a4-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="404a4-112">Nakonfigurujte konektor pro marketing</span><span class="sxs-lookup"><span data-stu-id="404a4-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="404a4-113">V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="404a4-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="404a4-114">V **Dynamics 365 Marketing** vyberte **Založit**.</span><span class="sxs-lookup"><span data-stu-id="404a4-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="404a4-115">Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="404a4-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="404a4-116">Zadejte marketingovou adresu URL vaší organizace do pole **Adresa serveru**.</span><span class="sxs-lookup"><span data-stu-id="404a4-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="404a4-117">V sekci **Účet správce serveru** vyberte **Přihlásit se** a vyberte účet Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="404a4-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="404a4-118">Namapujte pole ID zákazníka na ID kontaktu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="404a4-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="404a4-119">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="404a4-119">Select **Next**.</span></span>

1. <span data-ttu-id="404a4-120">Vyberte jeden nebo více segmentů.</span><span class="sxs-lookup"><span data-stu-id="404a4-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="404a4-121">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="404a4-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="404a4-122">Export dat</span><span class="sxs-lookup"><span data-stu-id="404a4-122">Export the data</span></span>

<span data-ttu-id="404a4-123">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="404a4-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="404a4-124">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="404a4-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]