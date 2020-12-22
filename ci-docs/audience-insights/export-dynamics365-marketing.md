---
title: Export dat Customer Insights do Dynamics 365 Marketing
description: Naučte se, jak nakonfigurovat připojení k Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643765"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="5f8e3-103">Konektor pro Dynamics 365 Marketing (preview)</span><span class="sxs-lookup"><span data-stu-id="5f8e3-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="5f8e3-104">Použití [segmentů](segments.md) pro generování kampaní a kontaktování konkrétní skupiny zákazníků pomocí Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="5f8e3-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="5f8e3-105">Další informace získáte v tématu [Použití segmentů z Dynamics 365 Customer Insights s Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="5f8e3-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="5f8e3-106">Požadavek</span><span class="sxs-lookup"><span data-stu-id="5f8e3-106">Prerequisite</span></span>

<span data-ttu-id="5f8e3-107">Záznamy kontaktů [z Dynamics 365 Marketing ingestované pomocí Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="5f8e3-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="5f8e3-108">Nakonfigurujte konektor pro marketing</span><span class="sxs-lookup"><span data-stu-id="5f8e3-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="5f8e3-109">V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="5f8e3-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5f8e3-110">V **Dynamics 365 Marketing** vyberte **Založit**.</span><span class="sxs-lookup"><span data-stu-id="5f8e3-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="5f8e3-111">Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="5f8e3-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="5f8e3-112">Zadejte marketingovou adresu URL vaší organizace do pole **Adresa serveru**.</span><span class="sxs-lookup"><span data-stu-id="5f8e3-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="5f8e3-113">V sekci **Účet správce serveru** vyberte **Přihlásit se** a vyberte účet Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="5f8e3-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="5f8e3-114">Namapujte pole ID zákazníka na ID kontaktu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="5f8e3-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="5f8e3-115">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="5f8e3-115">Select **Next**.</span></span>

1. <span data-ttu-id="5f8e3-116">Vyberte jeden nebo více segmentů.</span><span class="sxs-lookup"><span data-stu-id="5f8e3-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="5f8e3-117">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="5f8e3-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5f8e3-118">Export dat</span><span class="sxs-lookup"><span data-stu-id="5f8e3-118">Export the data</span></span>

<span data-ttu-id="5f8e3-119">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5f8e3-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="5f8e3-120">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5f8e3-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
