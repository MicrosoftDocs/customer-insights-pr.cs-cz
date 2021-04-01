---
title: Konektor Power Automate | Microsoft Docs
description: Vytváření toků v Microsoft Power Automate z Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597917"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="0c2ea-103">Konektor Power Automate (preview)</span><span class="sxs-lookup"><span data-stu-id="0c2ea-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="0c2ea-104">Služba Power Automate podporuje automatické spouštění vybraných událostí při změně dat nebo přímou správu složitějších toků v [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="0c2ea-105">Triggery Power Automate</span><span class="sxs-lookup"><span data-stu-id="0c2ea-105">Power Automate triggers</span></span>

<span data-ttu-id="0c2ea-106">Pomocí triggerů můžete vytvářet cloudové toky a automatizovat opakující se úlohy, jako jsou oznámení nebo pokročilé akce.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="0c2ea-107">Spustí se, když selže aktualizace zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="0c2ea-108">Spustí se, když uspěje aktualizace zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="0c2ea-109">Spustí se, když je v segmentu překročena prahová hodnota.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="0c2ea-110">Trigger je omezen na překročení nad prahovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="0c2ea-111">Spustí se, když je v obchodní míře překročena prahová hodnota.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="0c2ea-112">Trigger je omezen na překročení nad prahovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="0c2ea-113">Spustí se, když je dokončena úplná aktualizace (zdroje dat, segmenty, míry, ...).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="0c2ea-114">Spustí se, když je dokončena aktualizace procesu sjednocení (mapování, spárování, sloučení).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="0c2ea-115">[Konfigurace triggerů v Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="0c2ea-116">Akce Power Automate</span><span class="sxs-lookup"><span data-stu-id="0c2ea-116">Power Automate actions</span></span>
<span data-ttu-id="0c2ea-117">Konektor Power Automate poskytuje jiné akce než dostupné triggery.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="0c2ea-118">Další informace naleznete v dokumentaci [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="0c2ea-119">Vytvoření toku Power Automate</span><span class="sxs-lookup"><span data-stu-id="0c2ea-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="0c2ea-120">V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0c2ea-121">Na dlaždici **Power Automate** vyberte **Nastavit**.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="0c2ea-122">V Power Automate se otevře konektor Customer Insights (Preview).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="0c2ea-123">**Přihlaste se** k Power Automate.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="0c2ea-124">Vyberte jeden z dostupných triggerů a do nového toku přidejte další kroky.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="0c2ea-125">Další informace viz [Vytvoření cloudového toku v Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="0c2ea-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="0c2ea-126">Příklady použití toků:</span><span class="sxs-lookup"><span data-stu-id="0c2ea-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="0c2ea-127">Odeslání zprávy do kanálu Microsoft Teams, pokud selže aktualizace zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="0c2ea-128">Odeslání e-mailu vlastníkům dat po překročení prahové hodnoty v segmentu.</span><span class="sxs-lookup"><span data-stu-id="0c2ea-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]