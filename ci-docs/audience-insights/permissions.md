---
title: Správa uživatelských oprávnění
description: Informace o oprávněních a rolích uživatele.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689212"
---
# <a name="user-permissions"></a><span data-ttu-id="1df19-103">Uživatelská oprávnění</span><span class="sxs-lookup"><span data-stu-id="1df19-103">User permissions</span></span>

<span data-ttu-id="1df19-104">Stránka **Oprávnění** je místo, kde nastavíte role a oprávnění pro používání přehledů cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="1df19-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="1df19-105">Abyste stránku mohli zobrazit, musíte mít oprávnění správce.</span><span class="sxs-lookup"><span data-stu-id="1df19-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="1df19-106">Chcete-li přejít na stránku oprávnění v přehledech cílové skupiny, přejděte na **Správa** > **Oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="1df19-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="1df19-107">Existují tři typy rolí:</span><span class="sxs-lookup"><span data-stu-id="1df19-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="1df19-108">Prohlížející</span><span class="sxs-lookup"><span data-stu-id="1df19-108">Viewer</span></span>

- <span data-ttu-id="1df19-109">Zkoumání přehledů a segmentů na stránkách **Domů** a **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="1df19-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="1df19-110">Prohledejte a filtrujte profily zákazníků pomocí stránky **Zákazníci**.</span><span class="sxs-lookup"><span data-stu-id="1df19-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="1df19-111">Pole musí být prohledávatelná.</span><span class="sxs-lookup"><span data-stu-id="1df19-111">Fields must be searchable.</span></span>
- <span data-ttu-id="1df19-112">Zobrazte a prozkoumejte stránku **Rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="1df19-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="1df19-113">Prozkoumejte a exportujte entity pomocí stránky **Entity**.</span><span class="sxs-lookup"><span data-stu-id="1df19-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="1df19-114">Zobrazení stavu systémových procesů pomocí stránky **Systém**.</span><span class="sxs-lookup"><span data-stu-id="1df19-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="1df19-115">Export segmentů ze stránky **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="1df19-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="1df19-116">Instalace a použití řídicího panelu **Power BI Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="1df19-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="1df19-117">Přispěvatel</span><span class="sxs-lookup"><span data-stu-id="1df19-117">Contributor</span></span>

- <span data-ttu-id="1df19-118">Všechna oprávnění, která má k dispozici Prohlížející.</span><span class="sxs-lookup"><span data-stu-id="1df19-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="1df19-119">Načtení a transformace dat pomocí stránky **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="1df19-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="1df19-120">Vyplnění sekcí *Sjednocení dat* (**Mapa**, **Párování** a **Sloučení**), jejichž výsledkem je entita sjednoceného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="1df19-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="1df19-121">Definice **Vztahů** a **Aktivit**.</span><span class="sxs-lookup"><span data-stu-id="1df19-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="1df19-122">Vytváření segmentů pomocí stránky **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="1df19-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="1df19-123">Vytvořte opatření na stránce **Opatření**.</span><span class="sxs-lookup"><span data-stu-id="1df19-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="1df19-124">Správa konfigurace a rozšíření zákaznických profilů ze stránky **Rozšíření** (pouze pro rozšíření první strany).</span><span class="sxs-lookup"><span data-stu-id="1df19-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="1df19-125">Správce</span><span class="sxs-lookup"><span data-stu-id="1df19-125">Administrator</span></span>

- <span data-ttu-id="1df19-126">Všechna oprávnění, která má k dispozici Přispěvatel.</span><span class="sxs-lookup"><span data-stu-id="1df19-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="1df19-127">Změna nastavení na stránce **Systém**, včetně pracovního jazyka a plánů aktualizace systémových procesů.</span><span class="sxs-lookup"><span data-stu-id="1df19-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="1df19-128">Zobrazení a přidání oprávnění pomocí stránky **Oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="1df19-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="1df19-129">Nastavení definic vyhledávání a filtrů pro stránku Zákazníci pomocí stránky **Index hledání a filtrování** (přístupné prostřednictvím stránky **Zákazníci**).</span><span class="sxs-lookup"><span data-stu-id="1df19-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="1df19-130">Definujte cíle segmentu Dynamics 365 Sales pomocí stránky **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="1df19-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="1df19-131">Správa konfigurace a rozšíření zákaznických profilů ze stránky **Rozšíření** (pro všechna rozšíření).</span><span class="sxs-lookup"><span data-stu-id="1df19-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="1df19-132">Nainstalujte a použijte **Doplněk zákaznické karty**.</span><span class="sxs-lookup"><span data-stu-id="1df19-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="1df19-133">Přidání a použiti **konektoru Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="1df19-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="1df19-134">Povolení využití [rozhraní API aplikace Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="1df19-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="1df19-135">Přiřazení oprávnění a rolí</span><span class="sxs-lookup"><span data-stu-id="1df19-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="1df19-136">V přehledech cílové skupiny přejděte na **Správa** > **Oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="1df19-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="1df19-137">Volbou **Přidat uživatele** otevřete podokno **Přidat/upravit oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="1df19-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="1df19-138">Pomocí pole **Vyhledávání** vyhledejte uživatele nebo skupinu Azure Active Directory, jejichž oprávnění chcete upravit.</span><span class="sxs-lookup"><span data-stu-id="1df19-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="1df19-139">Vyberte **Roli**, kterou chcete přiřadit tomuto uživateli nebo skupině.</span><span class="sxs-lookup"><span data-stu-id="1df19-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="1df19-140">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="1df19-140">Select **Save**.</span></span> <span data-ttu-id="1df19-141">Aktuální prostředí bude automaticky sdíleno s uživatelem nebo členy skupiny, jejichž oprávnění jste změnili.</span><span class="sxs-lookup"><span data-stu-id="1df19-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="1df19-142">Uživatelé mají přístup k aplikaci Customer Insights a vykonávají činnost dle své zadané role.</span><span class="sxs-lookup"><span data-stu-id="1df19-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="1df19-143">Zobrazit aktuální oprávnění</span><span class="sxs-lookup"><span data-stu-id="1df19-143">View current permissions</span></span>

<span data-ttu-id="1df19-144">V přehledech cílové skupiny přejděte na **Správce** > **Oprávnění**, kde zjistíte, která přiřazení rolí jsou aktuálně aktivní.</span><span class="sxs-lookup"><span data-stu-id="1df19-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="1df19-145">Sloupec **Typ** určuje jednoho uživatele, skupinu nebo aplikaci.</span><span class="sxs-lookup"><span data-stu-id="1df19-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="1df19-146">Systém podporuje jednotlivé uživatele a skupiny.</span><span class="sxs-lookup"><span data-stu-id="1df19-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="1df19-147">Role jsou určeny ve sloupci **Role**.</span><span class="sxs-lookup"><span data-stu-id="1df19-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="1df19-148">Výběrem některého nadpisu sloupce seřadíte výsledky podle hodnoty daného sloupce.</span><span class="sxs-lookup"><span data-stu-id="1df19-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="1df19-149">Pomocí **vyhledávacího** pole v horní části stránky vyhledejte konkrétní uživatele.</span><span class="sxs-lookup"><span data-stu-id="1df19-149">Use the **Search** field at the top of the page to locate specific users.</span></span>
