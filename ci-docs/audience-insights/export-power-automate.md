---
title: Konektor Power Automate | Microsoft Docs
description: Vytvářejte toky v Microsoft Power Automate z Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405351"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="520f6-103">Konektor Power Automate (preview)</span><span class="sxs-lookup"><span data-stu-id="520f6-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="520f6-104">Služba Power Automate podporuje automatické spouštění vybraných událostí při změně dat nebo přímou správu složitějších toků v [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="520f6-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="520f6-105">Triggery Power Automate</span><span class="sxs-lookup"><span data-stu-id="520f6-105">Power Automate triggers</span></span>

<span data-ttu-id="520f6-106">K automatizaci opakujících se úkolů, jako jsou oznámení nebo pokročilejší akce, můžete použít různé triggery, které vám umožní vytvářet toky.</span><span class="sxs-lookup"><span data-stu-id="520f6-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="520f6-107">Spustí se, když selže aktualizace zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="520f6-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="520f6-108">Spustí se, když uspěje aktualizace zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="520f6-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="520f6-109">Spustí se, když je v segmentu překročena prahová hodnota.</span><span class="sxs-lookup"><span data-stu-id="520f6-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="520f6-110">Trigger je omezen na překročení nad prahovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="520f6-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="520f6-111">Spustí se, když je v obchodní míře překročena prahová hodnota.</span><span class="sxs-lookup"><span data-stu-id="520f6-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="520f6-112">Trigger je omezen na překročení nad prahovou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="520f6-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="520f6-113">Spustí se, když je dokončena úplná aktualizace (zdroje dat, segmenty, míry, ...).</span><span class="sxs-lookup"><span data-stu-id="520f6-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="520f6-114">Spustí se, když je dokončena aktualizace procesu sjednocení (mapování, spárování, sloučení).</span><span class="sxs-lookup"><span data-stu-id="520f6-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="520f6-115">[Konfigurace triggerů v Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="520f6-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="520f6-116">Akce Power Automate</span><span class="sxs-lookup"><span data-stu-id="520f6-116">Power Automate actions</span></span>
<span data-ttu-id="520f6-117">Konektor Power Automate poskytuje jiné akce než dostupné triggery.</span><span class="sxs-lookup"><span data-stu-id="520f6-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="520f6-118">Další informace naleznete v dokumentaci [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="520f6-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="520f6-119">Vytvoření toku Power Automate v přehledech cílové skupiny</span><span class="sxs-lookup"><span data-stu-id="520f6-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="520f6-120">V přehledech cílové skupiny přejděte na **Správa** > **Systém**.</span><span class="sxs-lookup"><span data-stu-id="520f6-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="520f6-121">Na stránce **Systém** vyberte kartu **Stav**.</span><span class="sxs-lookup"><span data-stu-id="520f6-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="520f6-122">V sekci **Zdroje dat** vyberte **Toky** a vyberte **Vytvořte tok** z rozevíracího seznamu.</span><span class="sxs-lookup"><span data-stu-id="520f6-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="520f6-123">![Konektor Power Automate zobrazující Vytvořit akci toku](media/power-automate-connector-create-flow.png "Konektor Power Automate zobrazující akci Vytvořit toku")</span><span class="sxs-lookup"><span data-stu-id="520f6-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="520f6-124">V Power Automate vyberte jeden z dostupných spouštěčů a vytvořte si preferovaný tok.</span><span class="sxs-lookup"><span data-stu-id="520f6-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="520f6-125">Pokud vytváříte svůj první tok, musíte se nejprve autentizovat pomocí konektoru Power Automate.</span><span class="sxs-lookup"><span data-stu-id="520f6-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
