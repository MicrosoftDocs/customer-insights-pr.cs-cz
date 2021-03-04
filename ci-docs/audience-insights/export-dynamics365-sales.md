---
title: Export dat Customer Insights do Dynamics 365 Sales
description: Naučte se, jak nakonfigurovat připojení k Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269000"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="cf6cd-103">Konektor pro Dynamics 365 Sales (preview)</span><span class="sxs-lookup"><span data-stu-id="cf6cd-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="cf6cd-104">Aplikace Dynamics 365 Sales umožňuje na základě zákaznických dat vytvářet marketingové seznamy, sledovat pracovní postupy a rozesílat propagační akce.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="cf6cd-105">Požadavek</span><span class="sxs-lookup"><span data-stu-id="cf6cd-105">Prerequisite</span></span>

1. <span data-ttu-id="cf6cd-106">Než budete moci exportovat segment z Customer Insights do aplikace Sales, musí se v Dynamics 365 Sales nacházet záznamy kontaktu.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="cf6cd-107">Přečtěte si, jak ingestovat kontakty v [Dynamics 365 Sales pomocí Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="cf6cd-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="cf6cd-108">Export segmentů z přehledů cílové skupiny do aplikace Sales nevytvoří nové záznamy kontaktů v instancích aplikace Sales.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="cf6cd-109">Záznamy kontaktů z aplikace Sales musí být zpracovány v přehledech cílové skupiny a použity jako zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="cf6cd-110">Než je možné segmenty exportovat, rovněž je třeba záznamy kontaktů zahrnout do sjednocené entity zákazníka, aby bylo možné mapovat ID zákazníků na ID kontaktů.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="cf6cd-111">Nakonfigurujte konektor pro Sales</span><span class="sxs-lookup"><span data-stu-id="cf6cd-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="cf6cd-112">V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cf6cd-113">V **Dynamics 365 Sales** vyberte **Založit**.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="cf6cd-114">Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="cf6cd-115">Zadejte adresu URL Sales vaší organizace do pole **Adresa serveru**.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="cf6cd-116">V sekci **Účet správce serveru** vyberte **Přihlásit se** a vyberte účet Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="cf6cd-117">Namapujte pole ID zákazníka na ID kontaktu Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="cf6cd-118">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-118">Select **Next**.</span></span>

1. <span data-ttu-id="cf6cd-119">Vyberte jeden nebo více segmentů.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="cf6cd-120">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="cf6cd-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="cf6cd-121">Export dat</span><span class="sxs-lookup"><span data-stu-id="cf6cd-121">Export the data</span></span>

<span data-ttu-id="cf6cd-122">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cf6cd-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="cf6cd-123">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cf6cd-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]