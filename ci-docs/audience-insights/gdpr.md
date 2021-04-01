---
title: Žádosti o práva subjektu údajů (DSR) v rámci GDPR | Microsoft Docs
description: Odpověď na žádosti subjektů údajů pro funkci přehledů cílové skupiny Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9c453c9b416bff0e6362a8ccf7ff534f4efa1e00
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597503"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="98555-103">Žádosti o práva subjektu údajů (DSR) v rámci GDPR</span><span class="sxs-lookup"><span data-stu-id="98555-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="98555-104">Odpověď na žádosti subjektů údajů o odstranění údajů v rámci GDPR pro funkci přehledů cílové skupiny Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="98555-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="98555-105">Právo na odstranění osobních údajů ze zákaznických údajů organizace je klíčovou ochranou podle obecného nařízení o ochraně osobních údajů (GDPR).</span><span class="sxs-lookup"><span data-stu-id="98555-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="98555-106">Odstranění osobních údajů zahrnuje odstranění všech osobních údajů a protokolů generovaných systémem, s výjimkou informací z protokolu auditu.</span><span class="sxs-lookup"><span data-stu-id="98555-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="98555-107">Správa požadavků na vymazání subjektu údajů</span><span class="sxs-lookup"><span data-stu-id="98555-107">Manage data subject delete requests</span></span>

<span data-ttu-id="98555-108">Přehledy cílové skupiny nabízí následující integrované prostředí k odstranění osobních údajů konkrétního zákazníka nebo uživatele:</span><span class="sxs-lookup"><span data-stu-id="98555-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="98555-109">**Správa požadavků na výmaz zákaznických dat**: Údaje o zákaznících v nástroji Customer Insights jsou přijímány z původních zdrojů dat mimo Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98555-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="98555-110">Všechny žádosti o odstranění GDPR musí být provedeny v původním zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="98555-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="98555-111">**Správa žádostí o odstranění údajů uživatele Customer Insights**: Data uživatelů jsou vytvářena v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98555-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="98555-112">Všechny žádosti o odstranění GDPR musí být provedeny v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98555-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="98555-113">Správa mazacích požadavků na zákaznická data</span><span class="sxs-lookup"><span data-stu-id="98555-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="98555-114">Správce Customer Insights může podle těchto kroků odebrat zákaznická data, která byla odstraněna ze zdroje dat:</span><span class="sxs-lookup"><span data-stu-id="98555-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="98555-115">Přihlaste se ke službě Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98555-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="98555-116">V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**</span><span class="sxs-lookup"><span data-stu-id="98555-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="98555-117">Pro každý zdroj dat v seznamu, který obsahuje odstraněná zákaznická data:</span><span class="sxs-lookup"><span data-stu-id="98555-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="98555-118">Vyberte (...) a poté volbu **Aktualizovat**.</span><span class="sxs-lookup"><span data-stu-id="98555-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="98555-119">Zkontrolujte stav zdroje dat ve volbě **Stav**.</span><span class="sxs-lookup"><span data-stu-id="98555-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="98555-120">Zaškrtnutí znamená, že aktualizace proběhla úspěšně.</span><span class="sxs-lookup"><span data-stu-id="98555-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="98555-121">Výstražný trojúhelník znamená, že se něco pokazilo.</span><span class="sxs-lookup"><span data-stu-id="98555-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="98555-122">Pokud se zobrazí výstražný trojúhelník, kontaktujte D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="98555-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="98555-123">![Správa požadavků na výmaz GDPR pro zákaznická data](media/gdpr-data-sources.png "Správa požadavků na výmaz GDPR pro zákaznická data")</span><span class="sxs-lookup"><span data-stu-id="98555-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="98555-124">Správa žádostí o odstranění údajů uživatele</span><span class="sxs-lookup"><span data-stu-id="98555-124">Manage delete requests for user data</span></span>

<span data-ttu-id="98555-125">Správce Customer Insights může odstranit údaje o uživatelích Customer Insights podle těchto kroků:</span><span class="sxs-lookup"><span data-stu-id="98555-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="98555-126">Přihlaste se ke službě Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="98555-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="98555-127">V přehledech cílové skupiny přejděte na **Správa** > **Oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="98555-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="98555-128">Zaškrtněte políčko pro uživatele, kterého chcete smazat.</span><span class="sxs-lookup"><span data-stu-id="98555-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="98555-129">Vyberte **Odstranit**.</span><span class="sxs-lookup"><span data-stu-id="98555-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="98555-130">![Zpracování žádostí o odstranění údajů uživatele v rámci GDPR](media/gdpr-permissions.png "Zpracování žádostí o odstranění údajů uživatele v rámci GDPR")</span><span class="sxs-lookup"><span data-stu-id="98555-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="98555-131">Odpověď na žádosti subjektu údajů o export údajů v rámci GDPR</span><span class="sxs-lookup"><span data-stu-id="98555-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="98555-132">V rámci našeho závazku s vámi spolupracovat na vaší cestě k obecnému nařízení o ochraně údajů (GDPR) jsme vyvinuli dokumentaci, která vám pomůže s přípravou.</span><span class="sxs-lookup"><span data-stu-id="98555-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="98555-133">Tato dokumentace popisuje kroky, které můžete dnes podniknout k podpoře dodržování předpisů GDPR, když používáte přehledy cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="98555-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="98555-134">Spravujte žádosti o export a zobrazení</span><span class="sxs-lookup"><span data-stu-id="98555-134">Manage export and view requests</span></span>

<span data-ttu-id="98555-135">Právo na přenositelnost údajů umožňuje subjektům údajů požádat o kopii svých osobních údajů v elektronickém formátu (definovaném jako „strukturovaný, běžně používaný, strojově čitelný a interoperabilní formát“), který lze předat jinému správci údajů.</span><span class="sxs-lookup"><span data-stu-id="98555-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="98555-136">Export údajů zákazníka (správce klienta)</span><span class="sxs-lookup"><span data-stu-id="98555-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="98555-137">Správce klienta může exportovat údaje pomocí následujícího postupu:</span><span class="sxs-lookup"><span data-stu-id="98555-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="98555-138">Pošlete e-mail na adresu D365CI@microsoft.com a určete e-mailovou adresu zákazníka v žádosti.</span><span class="sxs-lookup"><span data-stu-id="98555-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="98555-139">Tým Customer Insights zašle e-mail na zaregistrovanou e-mailovou adresu klienta s žádostí o potvrzení exportu dat.</span><span class="sxs-lookup"><span data-stu-id="98555-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="98555-140">Potvrďte potvrzení pro export dat pro požadovaného zákazníka.</span><span class="sxs-lookup"><span data-stu-id="98555-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="98555-141">Exportovaná data obdržíte prostřednictvím e-mailové adresy správce klienta.</span><span class="sxs-lookup"><span data-stu-id="98555-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="98555-142">Export údajů uživatele (správce klienta)</span><span class="sxs-lookup"><span data-stu-id="98555-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="98555-143">Pošlete e-mail na adresu D365CI@microsoft.com a určete e-mailovou adresu uživatele v žádosti.</span><span class="sxs-lookup"><span data-stu-id="98555-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="98555-144">Tým Customer Insights zašle e-mail na zaregistrovanou e-mailovou adresu klienta s žádostí o potvrzení exportu dat.</span><span class="sxs-lookup"><span data-stu-id="98555-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="98555-145">Potvrďte potvrzení pro export dat pro požadovaného uživatele.</span><span class="sxs-lookup"><span data-stu-id="98555-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="98555-146">Exportovaná data obdržíte prostřednictvím e-mailové adresy správce klienta.</span><span class="sxs-lookup"><span data-stu-id="98555-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]