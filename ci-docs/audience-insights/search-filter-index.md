---
title: Hledání a filtrování profilů zákazníků
description: Rychle vyhledejte informace o sjednocených profilech zákazníků a filtrujte zadané atributy.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270058"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="64c30-103">Profily zákazníků: Prohledávání a filtrování indexu</span><span class="sxs-lookup"><span data-stu-id="64c30-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="64c30-104">Výsledkem sjednocení údajů o zákaznících je entita profilu zákazníka, která poskytuje jednotný pohled na vaši celkovou zákaznickou základnu.</span><span class="sxs-lookup"><span data-stu-id="64c30-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="64c30-105">Chcete-li rychle [najít informace o konkrétním zákazníkovi nebo skupině zákazníků](customer-profiles.md), můžete nakonfigurovat funkce **Vyhledávání** a **Filtr** na stránce **Zákazníci**.</span><span class="sxs-lookup"><span data-stu-id="64c30-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="64c30-106">Čtěte dále a dozvíte se, jak mohou správci upravovat atributy na stránce **Prohledávání a filtrování rejstříku**, které jsou uživatelům k dispozici pro vyhledávání a filtrování.</span><span class="sxs-lookup"><span data-stu-id="64c30-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="64c30-107">![Filtr hledání](media/search-filter.png "Filtr hledání")</span><span class="sxs-lookup"><span data-stu-id="64c30-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="64c30-108">Přidejte pole a zadejte atributy</span><span class="sxs-lookup"><span data-stu-id="64c30-108">Add fields and specify attributes</span></span>

<span data-ttu-id="64c30-109">Pokud poprvé definujete prohledatelné atributy jako správce, musíte nejprve definovat indexovaná pole.</span><span class="sxs-lookup"><span data-stu-id="64c30-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="64c30-110">Doporučujeme, abyste si vybrali všechny atributy, podle kterých mohou uživatelé na internetu vyhledávat a filtrovat zákazníky na stránce **Zákazníci**.</span><span class="sxs-lookup"><span data-stu-id="64c30-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="64c30-111">Můžete určit pouze atributy, které existují v entitě profilu zákazníka, kterou jste vytvořili během procesu sjednocení dat.</span><span class="sxs-lookup"><span data-stu-id="64c30-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="64c30-112">Otevřete stránku **Zákazníci** a vyberte **Index hledání a filtrování**.</span><span class="sxs-lookup"><span data-stu-id="64c30-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="64c30-113">Volbou **+ Přidat** určete indexovaná pole.</span><span class="sxs-lookup"><span data-stu-id="64c30-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="64c30-114">V seznamu vyberte atributy, které chcete přidat jako indexovaná pole.</span><span class="sxs-lookup"><span data-stu-id="64c30-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="64c30-115">Výběrem **Přidat** můžete vždy přidat další atributy.</span><span class="sxs-lookup"><span data-stu-id="64c30-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="64c30-116">Jakékoli vybrané atributy můžete také odstranit výběrem symbolu **Odstranit**.</span><span class="sxs-lookup"><span data-stu-id="64c30-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="64c30-117">Prozkoumejte tabulku Pole indexovaných zákazníků</span><span class="sxs-lookup"><span data-stu-id="64c30-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="64c30-118">Tabulka obsahuje následující informace.</span><span class="sxs-lookup"><span data-stu-id="64c30-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="64c30-119">**Název**: Představuje název atributu, jak je uveden v entitě profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="64c30-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="64c30-120">**Datový typ**: Určuje, zda je typ dat řetězec, číslo nebo datum.</span><span class="sxs-lookup"><span data-stu-id="64c30-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="64c30-121">**Zahrnuto do vyhledávání**: Určuje, zda lze tento atribut použít pro vyhledávání zákazníků na stránce **Zákazníci** pomocí pole **Vyhledávání**.</span><span class="sxs-lookup"><span data-stu-id="64c30-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="64c30-122">**Přidat filtr**: Ovládací prvek, který definuje, jak lze tento atribut použít pro filtrování na stránce **Zákazníci**.</span><span class="sxs-lookup"><span data-stu-id="64c30-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="64c30-123">Úpravy možností filtrování pro daný atribut</span><span class="sxs-lookup"><span data-stu-id="64c30-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="64c30-124">Nabídka **Filtr** na stránce **Zákazníci** může zahrnovat různý počet úrovní atributů (například různé věkové skupiny, podle kterých lze filtrovat zákazníky).</span><span class="sxs-lookup"><span data-stu-id="64c30-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="64c30-125">Vyberte **Přidat filtr** pro daný atribut na stránce **Hledat a filtrovat rejstřík**.</span><span class="sxs-lookup"><span data-stu-id="64c30-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="64c30-126">Můžete definovat počet výsledků a pořadí, ve kterém budou uspořádány.</span><span class="sxs-lookup"><span data-stu-id="64c30-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="64c30-127">V závislosti na datovém typu atributu se objeví jedno z následujících podoken.</span><span class="sxs-lookup"><span data-stu-id="64c30-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="64c30-128">Atributy typu řetězec: Zadejte počet požadovaných výsledků v podokně **Možnosti filtrování řetězců** a zásady řazení, podle kterých budou uspořádány.</span><span class="sxs-lookup"><span data-stu-id="64c30-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="64c30-129">Atributy typu číslo: Zadejte intervaly z podokna **Možnosti filtrování čísel** a zásady řazení, podle kterých budou uspořádány.</span><span class="sxs-lookup"><span data-stu-id="64c30-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="64c30-130">Atributy typu datum: Zadejte intervaly z podokna **Možnosti filtrování kalendářních dat** a zásady řazení, podle kterých budou uspořádány.</span><span class="sxs-lookup"><span data-stu-id="64c30-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="64c30-131">Výběrem možnosti **Uložit** se vaše změny uplatní.</span><span class="sxs-lookup"><span data-stu-id="64c30-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="64c30-132">Vyberte **Spustit**, jakmile budete připraveni použít svá nastavení.</span><span class="sxs-lookup"><span data-stu-id="64c30-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="64c30-133">Další kroky</span><span class="sxs-lookup"><span data-stu-id="64c30-133">Next steps</span></span>

<span data-ttu-id="64c30-134">Přejděte na stránku **Zákazníci** pro vyhledání profilů zákazníků nebo pomocí indexovaného pole zobrazte podmnožinu všech profilů zákazníků.</span><span class="sxs-lookup"><span data-stu-id="64c30-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]