---
title: Zobrazení profilů zákazníků
description: Získejte kombinované zobrazení sjednocených údajů o zákaznících.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 433e6ceda0ec7827bd672cff40f895d7719561df
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896319"
---
# <a name="customer-profiles"></a><span data-ttu-id="abf94-103">Profily zákazníků</span><span class="sxs-lookup"><span data-stu-id="abf94-103">Customer profiles</span></span>

<span data-ttu-id="abf94-104">Stránka **Zákazníci** obsahuje kombinované zobrazení vašich zákazníků na základě dat profilů získaných ze [všech zdrojů dat](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="abf94-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="abf94-105">Profily zákazníků jsou k dispozici, jakmile [vytvoříte sjednocenou entitu zákazníka](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="abf94-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="abf94-106">Ujistěte se, že jste dokončili proces sjednocení dat, abyste získali lepší přehled o svých zákaznících.</span><span class="sxs-lookup"><span data-stu-id="abf94-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="abf94-107">Tato stránka také umožňuje vyhledávat zákazníky.</span><span class="sxs-lookup"><span data-stu-id="abf94-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="abf94-108">Zákazníci mohou být jednotlivci nebo organizace (náhled).</span><span class="sxs-lookup"><span data-stu-id="abf94-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="abf94-109">Každý profil zákazníka nebo organizace je reprezentován dlaždicí.</span><span class="sxs-lookup"><span data-stu-id="abf94-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="abf94-110">Výběrem dlaždice zobrazíte další informace o konkrétním zákazníkovi nebo organizaci.</span><span class="sxs-lookup"><span data-stu-id="abf94-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="abf94-111">Chcete-li zobrazit další záznamy, použijte ovládací prvky stránkování ve spodní části stránky.</span><span class="sxs-lookup"><span data-stu-id="abf94-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="abf94-112">![Zákaznické profily B2C](media/profiles-customers.png "Zákaznické profily B2C")</span><span class="sxs-lookup"><span data-stu-id="abf94-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="abf94-113">Organizace (Náhled)</span><span class="sxs-lookup"><span data-stu-id="abf94-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="abf94-114">![Zákaznické profily B2B](media/profile-customers-b2b.png "Zákaznické profily B2B")</span><span class="sxs-lookup"><span data-stu-id="abf94-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="abf94-115">Pokud nevidíte dlaždice, když vyberete **Zákazníci** v navigaci, musí váš správce [definovat alespoň jeden prohledávatelný atribut](search-filter-index.md) v **Hledat a filtrovat index**.</span><span class="sxs-lookup"><span data-stu-id="abf94-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="abf94-116">Hledat zákazníky</span><span class="sxs-lookup"><span data-stu-id="abf94-116">Search for customers</span></span>

<span data-ttu-id="abf94-117">Vyhledejte zákazníky zadáním jména nebo jiného atributu do vyhledávacího pole.</span><span class="sxs-lookup"><span data-stu-id="abf94-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="abf94-118">Hledání funguje pouze v rámci entity Profil zákazníka vytvořené během procesu sjednocení dat.</span><span class="sxs-lookup"><span data-stu-id="abf94-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="abf94-119">Jako správce můžete konfigurovat prohledávatelné atributy pomocí stránky **Hledat a filtrovat rejstřík**.</span><span class="sxs-lookup"><span data-stu-id="abf94-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="abf94-120">Další informace získáte v tématu [Správa vyhledávání a filtrování rejstříku](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="abf94-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="abf94-121">Filtrování zákazníků</span><span class="sxs-lookup"><span data-stu-id="abf94-121">Filter customers</span></span>

<span data-ttu-id="abf94-122">Zákazníky můžete filtrovat podle polí entity Zákaznický profil.</span><span class="sxs-lookup"><span data-stu-id="abf94-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="abf94-123">Podobně jako při vyhledávání bude muset správce nejprve definovat pole jako filtrovatelná pomocí stránky **Hledat a filtrovat rejstřík**.</span><span class="sxs-lookup"><span data-stu-id="abf94-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="abf94-124">Vyberte **Filtr** na stránce **Zákazníci**.</span><span class="sxs-lookup"><span data-stu-id="abf94-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="abf94-125">Zaškrtněte políčka vedle atributů, podle kterých chcete zákazníky filtrovat.</span><span class="sxs-lookup"><span data-stu-id="abf94-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="abf94-126">![Profily zákazníků](media/profiles-customers3.png "Profily zákazníků")</span><span class="sxs-lookup"><span data-stu-id="abf94-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="abf94-127">Odeberte filtry volbou **Vymazat filtry** na stránce **Zákazníci**.</span><span class="sxs-lookup"><span data-stu-id="abf94-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="abf94-128">Stránka podrobností zákazníka</span><span class="sxs-lookup"><span data-stu-id="abf94-128">Customer details page</span></span>

<span data-ttu-id="abf94-129">Vyberte některou z dlaždic zákazníků a otevřete **stránku podrobností zákazníka**.</span><span class="sxs-lookup"><span data-stu-id="abf94-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="abf94-130">Toto zobrazení obsahuje jednotné informace o vybraném zákazníkovi.</span><span class="sxs-lookup"><span data-stu-id="abf94-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="abf94-131">Podrobnosti o zákazníkovi zahrnují následující:</span><span class="sxs-lookup"><span data-stu-id="abf94-131">Customer details include:</span></span>

-   <span data-ttu-id="abf94-132">**Dlaždice profilu zákazníka:** Tato dlaždice zobrazuje různé hodnoty z entity sjednoceného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="abf94-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="abf94-133">Tyto podrobnosti mohou zahrnovat e-mailovou adresu, jméno, město atd.</span><span class="sxs-lookup"><span data-stu-id="abf94-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="abf94-134">**Potenciální zájmy, potenciální značky:** Ukazuje, zda jste nakonfigurovali rozšíření první strany.</span><span class="sxs-lookup"><span data-stu-id="abf94-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="abf94-135">Představuje potenciální zájmy a oblíbenost značek, které může mít zákazník s profilem podobným tomuto zákazníkovi.</span><span class="sxs-lookup"><span data-stu-id="abf94-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="abf94-136">Další informace viz [Rozšíření profilů zákazníků afinitami značky a zájmů](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="abf94-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

-   <span data-ttu-id="abf94-137">**Míry:** Ukazuje, zda jste nakonfigurovali jednu nebo více měr atributů zákazníka.</span><span class="sxs-lookup"><span data-stu-id="abf94-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="abf94-138">Zahrnují vypočítané klíčové ukazatele výkonu ohledně vašich zákazníků na úrovni jednotlivých zákazníků.</span><span class="sxs-lookup"><span data-stu-id="abf94-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="abf94-139">Další informace viz [Definování a správa měr](measures.md).</span><span class="sxs-lookup"><span data-stu-id="abf94-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="abf94-140">**Časová osa aktivit:** Ukazuje, zda máte konfigurovány aktivity.</span><span class="sxs-lookup"><span data-stu-id="abf94-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="abf94-141">Zobrazení časové osy obsahuje chronologicky seřazené aktivity tohoto zákazníka, počínaje nejnovější aktivitou.</span><span class="sxs-lookup"><span data-stu-id="abf94-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="abf94-142">Další informace najdete v tématu [Aktivity zákazníka](activities.md).</span><span class="sxs-lookup"><span data-stu-id="abf94-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="abf94-143">Volbou **Zpět k zákazníkům** se vrátíte na stránku pro vyhledávání zákazníků.</span><span class="sxs-lookup"><span data-stu-id="abf94-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="abf94-144">Další kroky</span><span class="sxs-lookup"><span data-stu-id="abf94-144">Next steps</span></span>

<span data-ttu-id="abf94-145">[Přidejte další zdroje dat](data-sources.md) nebo [vytvořte segmenty zákazníků](segments.md).</span><span class="sxs-lookup"><span data-stu-id="abf94-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]