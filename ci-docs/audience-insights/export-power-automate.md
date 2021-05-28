---
title: Konektor Power Automate | Microsoft Docs
description: Vytváření toků v Microsoft Power Automate z Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976080"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="09900-103">Konektor Power Automate (preview)</span><span class="sxs-lookup"><span data-stu-id="09900-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="09900-104">Služba Power Automate podporuje automatické spouštění vybraných událostí při změně dat nebo přímou správu složitějších toků v [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="09900-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="09900-105">Triggery Power Automate</span><span class="sxs-lookup"><span data-stu-id="09900-105">Power Automate triggers</span></span>

<span data-ttu-id="09900-106">Pomocí triggerů můžete vytvářet cloudové toky a automatizovat opakující se úlohy, jako jsou oznámení nebo pokročilé akce.</span><span class="sxs-lookup"><span data-stu-id="09900-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="09900-107">Spustí se, když selže aktualizace zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="09900-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="09900-108">Spustí se, když uspěje aktualizace zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="09900-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="09900-109">Spustí se, když je v segmentu překročena prahová hodnota.</span><span class="sxs-lookup"><span data-stu-id="09900-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="09900-110">Trigger je omezen na překročení nad prahovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="09900-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="09900-111">Spustí se, když je v obchodní míře překročena prahová hodnota.</span><span class="sxs-lookup"><span data-stu-id="09900-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="09900-112">Jsou podporovány pouze firemní míry bez dimenze.</span><span class="sxs-lookup"><span data-stu-id="09900-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="09900-113">Trigger je omezen na překročení nad prahovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="09900-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="09900-114">Spustí se, když je dokončena úplná aktualizace (zdroje dat, segmenty, míry, ...).</span><span class="sxs-lookup"><span data-stu-id="09900-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="09900-115">Spustí se, když je dokončena aktualizace procesu sjednocení (mapování, spárování, sloučení).</span><span class="sxs-lookup"><span data-stu-id="09900-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="09900-116">[Konfigurace triggerů v Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="09900-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="09900-117">Akce Power Automate</span><span class="sxs-lookup"><span data-stu-id="09900-117">Power Automate actions</span></span>
<span data-ttu-id="09900-118">Konektor Power Automate poskytuje jiné akce než dostupné triggery.</span><span class="sxs-lookup"><span data-stu-id="09900-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="09900-119">Další informace naleznete v dokumentaci [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="09900-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="09900-120">Vytvoření toku Power Automate</span><span class="sxs-lookup"><span data-stu-id="09900-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="09900-121">V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="09900-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="09900-122">Na dlaždici **Power Automate** vyberte **Nastavit**.</span><span class="sxs-lookup"><span data-stu-id="09900-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="09900-123">V Power Automate se otevře konektor Customer Insights (Preview).</span><span class="sxs-lookup"><span data-stu-id="09900-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="09900-124">**Přihlaste se** k Power Automate.</span><span class="sxs-lookup"><span data-stu-id="09900-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="09900-125">Vyberte jeden z dostupných triggerů a do nového toku přidejte další kroky.</span><span class="sxs-lookup"><span data-stu-id="09900-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="09900-126">Další informace viz [Vytvoření cloudového toku v Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="09900-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="09900-127">Příklady použití toků:</span><span class="sxs-lookup"><span data-stu-id="09900-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="09900-128">Odeslání zprávy do kanálu Microsoft Teams, pokud selže aktualizace zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="09900-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="09900-129">Odeslání e-mailu vlastníkům dat po překročení prahové hodnoty v segmentu.</span><span class="sxs-lookup"><span data-stu-id="09900-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
