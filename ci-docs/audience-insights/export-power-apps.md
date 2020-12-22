---
title: Konektor pro Power Apps
description: Propojení aplikací Power Apps a Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405353"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="da8f3-103">Konektor Microsoft Power Apps (preview)</span><span class="sxs-lookup"><span data-stu-id="da8f3-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="da8f3-104">Přeneste sjednocené zákaznické profily do svých přizpůsobených aplikací pomocí Power Apps.</span><span class="sxs-lookup"><span data-stu-id="da8f3-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="da8f3-105">Propojení aplikací Power Apps a Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="da8f3-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="da8f3-106">Customer Insights jsou jedním z mnoha [dostupných zdrojů dat v Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="da8f3-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="da8f3-107">V dokumentaci Power Apps najdete, jak [přidat datové připojení k aplikaci](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="da8f3-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="da8f3-108">Doporučujeme také zkontrolovat, [jak Power Apps používá delegování ke zpracování velkých datových sad v aplikacích plátna](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="da8f3-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="da8f3-109">Dostupné entity</span><span class="sxs-lookup"><span data-stu-id="da8f3-109">Available entities</span></span>

<span data-ttu-id="da8f3-110">Po přidání Customer Insights jako datového připojení si můžete v systému vybrat následující entity v Power Apps:</span><span class="sxs-lookup"><span data-stu-id="da8f3-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="da8f3-111">Zákazník: chcete-li použít data z [jednotného profilu zákazníka](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="da8f3-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="da8f3-112">Jednotná aktivita zákazníka: zobrazení [časové osy aktivity](activities.md) v aplikaci.</span><span class="sxs-lookup"><span data-stu-id="da8f3-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="da8f3-113">Omezení</span><span class="sxs-lookup"><span data-stu-id="da8f3-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="da8f3-114">Vyhledatelné entity</span><span class="sxs-lookup"><span data-stu-id="da8f3-114">Retrievable entities</span></span>

<span data-ttu-id="da8f3-115">Načíst můžete pouze entity **Zákazník**, **UnifiedActivity** a **Segmenty** prostřednictvím konektoru Power Apps.</span><span class="sxs-lookup"><span data-stu-id="da8f3-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="da8f3-116">Jsou zobrazeny další entity, protože podkladový konektor je podporuje prostřednictvím spouštěčů v Power Automate.</span><span class="sxs-lookup"><span data-stu-id="da8f3-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="da8f3-117">Delegování</span><span class="sxs-lookup"><span data-stu-id="da8f3-117">Delegation</span></span>

<span data-ttu-id="da8f3-118">Delegování funguje pro entitu zákazníka a entitu UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="da8f3-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="da8f3-119">Delegace pro entitu **Zákazník**: Chcete-li použít delegování pro tuto entitu, je třeba indexovat pole v části [Index hledání a filtrování](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="da8f3-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="da8f3-120">Delegace pro **UnifiedActivity**: Delegace pro tuto entitu funguje pouze pro pole **ActivityId** a **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="da8f3-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="da8f3-121">Další informace o delegování viz [Delegovatelné funkce a operace Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="da8f3-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="da8f3-122">Příklad ovládání galerie</span><span class="sxs-lookup"><span data-stu-id="da8f3-122">Example gallery control</span></span>

<span data-ttu-id="da8f3-123">Například přidáte profily zákazníků do [ovládacího prvku galerie](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="da8f3-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="da8f3-124">Přidat ovládací prvek **Galerie** do aplikace, kterou stavíte.</span><span class="sxs-lookup"><span data-stu-id="da8f3-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="da8f3-125">![Přidat prvek galerie](media/connector-powerapps9.png "Přidat prvek galerie")</span><span class="sxs-lookup"><span data-stu-id="da8f3-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="da8f3-126">Vyberte **Zákazník** jako zdroj dat pro položky.</span><span class="sxs-lookup"><span data-stu-id="da8f3-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="da8f3-127">![Vybrat zdroj dat](media/choose-datasource-powerapps.png "Vybrat zdroj dat")</span><span class="sxs-lookup"><span data-stu-id="da8f3-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="da8f3-128">Panel dat můžete změnit vpravo a vybrat pole pro entitu Zákazník, které se má zobrazit v galerii.</span><span class="sxs-lookup"><span data-stu-id="da8f3-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="da8f3-129">Chcete-li zobrazit libovolné pole od vybraného zákazníka v galerii, vyplňte vlastnost Text popisku: **{Name_of_the_gallery}.Vybrané.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="da8f3-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="da8f3-130">Příklad: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="da8f3-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="da8f3-131">Chcete-li zobrazit jednotnou časovou osu pro zákazníka, přidejte element Galerie a přidejte vlastnost Položky: **Filtr('SjednocenáAktivita', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="da8f3-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="da8f3-132">Příklad: Filtr('SjednocenáAktivita', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="da8f3-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
