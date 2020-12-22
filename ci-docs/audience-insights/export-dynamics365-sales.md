---
title: Export dat Customer Insights do Dynamics 365 Sales
description: Naučte se, jak nakonfigurovat připojení k Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643810"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="49e9e-103">Konektor pro Dynamics 365 Sales (preview)</span><span class="sxs-lookup"><span data-stu-id="49e9e-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="49e9e-104">Aplikace Dynamics 365 Sales umožňuje na základě zákaznických dat vytvářet marketingové seznamy, sledovat pracovní postupy a rozesílat propagační akce.</span><span class="sxs-lookup"><span data-stu-id="49e9e-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="49e9e-105">Požadavek</span><span class="sxs-lookup"><span data-stu-id="49e9e-105">Prerequisite</span></span>

<span data-ttu-id="49e9e-106">Záznamy kontaktů [z Dynamics 365 Sales ingestované pomocí Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="49e9e-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="49e9e-107">Nakonfigurujte konektor pro Sales</span><span class="sxs-lookup"><span data-stu-id="49e9e-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="49e9e-108">V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="49e9e-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="49e9e-109">V **Dynamics 365 Sales** vyberte **Založit**.</span><span class="sxs-lookup"><span data-stu-id="49e9e-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="49e9e-110">Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="49e9e-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="49e9e-111">Zadejte adresu URL Sales vaší organizace do pole **Adresa serveru**.</span><span class="sxs-lookup"><span data-stu-id="49e9e-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="49e9e-112">V sekci **Účet správce serveru** vyberte **Přihlásit se** a vyberte účet Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="49e9e-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="49e9e-113">Namapujte pole ID zákazníka na ID kontaktu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="49e9e-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="49e9e-114">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="49e9e-114">Select **Next**.</span></span>

1. <span data-ttu-id="49e9e-115">Vyberte jeden nebo více segmentů.</span><span class="sxs-lookup"><span data-stu-id="49e9e-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="49e9e-116">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="49e9e-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="49e9e-117">Export dat</span><span class="sxs-lookup"><span data-stu-id="49e9e-117">Export the data</span></span>

<span data-ttu-id="49e9e-118">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="49e9e-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="49e9e-119">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="49e9e-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
