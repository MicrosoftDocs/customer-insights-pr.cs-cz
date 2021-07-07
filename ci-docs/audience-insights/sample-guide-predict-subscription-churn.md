---
title: Průvodce ukázkami predikce úbytku předplatných
description: Pomocí tohoto průvodce ukázkami můžete vyzkoušet dodávaný model predikce úbytku předplatných.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306295"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="9530c-103">Průvodce ukázkami (Preview) predikce úbytku předplatných</span><span class="sxs-lookup"><span data-stu-id="9530c-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="9530c-104">Provedeme vás příkladem predikce úbytku předplatných od začátku dokonce s využitím níže uvedených ukázkových dat.</span><span class="sxs-lookup"><span data-stu-id="9530c-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="9530c-105">Scénář</span><span class="sxs-lookup"><span data-stu-id="9530c-105">Scenario</span></span>

<span data-ttu-id="9530c-106">Contoso je společnost vyrábějící vysoce kvalitní kávu a kávovary, které prodávají prostřednictvím svého webu Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="9530c-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="9530c-107">Nedávno zavedla předplatné pro své zákazníky, aby mohli pravidelně dostávat kávu.</span><span class="sxs-lookup"><span data-stu-id="9530c-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="9530c-108">Jejím cílem je pochopit, kteří zákazníci s předplatným mohou v příštích několika měsících své předplatné zrušit.</span><span class="sxs-lookup"><span data-stu-id="9530c-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="9530c-109">Informace, který z jejích zákazníků bude **pravděpodobně ztracen**, jí může pomoci ušetřit marketingové prostředky tím, že se soustředí na jeho udržení.</span><span class="sxs-lookup"><span data-stu-id="9530c-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9530c-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="9530c-110">Prerequisites</span></span>

- <span data-ttu-id="9530c-111">Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9530c-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="9530c-112">Doporučujeme implementovat následující kroky [v novém prostředí](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="9530c-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="9530c-113">Úkol 1 – Ingestace dat</span><span class="sxs-lookup"><span data-stu-id="9530c-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="9530c-114">Projděte si články [o příjmu (ingestaci) dat](data-sources.md) a [importu zdrojů dat pomocí konektorů Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9530c-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="9530c-115">Následující informace předpokládají, že jste se seznámili s ingestací dat obecně.</span><span class="sxs-lookup"><span data-stu-id="9530c-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="9530c-116">Ingestace zákaznických dat z platformy eCommerce</span><span class="sxs-lookup"><span data-stu-id="9530c-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="9530c-117">Vytvořte zdroj dat **eCommerce**, vyberte možnost importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9530c-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9530c-118">Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="9530c-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="9530c-119">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="9530c-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9530c-120">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="9530c-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="9530c-121">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="9530c-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9530c-122">**CreatedOn**: Datum/čas/pásmo</span><span class="sxs-lookup"><span data-stu-id="9530c-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformace data narození na datum.":::

1. <span data-ttu-id="9530c-124">V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="9530c-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="9530c-125">Uložte zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="9530c-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="9530c-126">Ingestace zákaznických dat z věrnostního schématu</span><span class="sxs-lookup"><span data-stu-id="9530c-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="9530c-127">Vytvořte zdroj dat **LoyaltyScheme**, vyberte možnost importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9530c-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9530c-128">Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="9530c-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="9530c-129">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="9530c-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9530c-130">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="9530c-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="9530c-131">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="9530c-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9530c-132">**RewardsPoints**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="9530c-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="9530c-133">**CreatedOn**: Datum/čas</span><span class="sxs-lookup"><span data-stu-id="9530c-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="9530c-134">V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="9530c-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="9530c-135">Uložte zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="9530c-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="9530c-136">Ingestace informací o předplatném</span><span class="sxs-lookup"><span data-stu-id="9530c-136">Ingest subscription information</span></span>

1. <span data-ttu-id="9530c-137">Vytvořte zdroj dat **SubscriptionHistory**, vyberte možnost importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9530c-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9530c-138">Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="9530c-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="9530c-139">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="9530c-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9530c-140">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="9530c-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="9530c-141">**SubscriptioID**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="9530c-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="9530c-142">**SubscriptionAmount**: Měna</span><span class="sxs-lookup"><span data-stu-id="9530c-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="9530c-143">**SubscriptionEndDate**: Datum/čas</span><span class="sxs-lookup"><span data-stu-id="9530c-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="9530c-144">**SubscriptionStartDate**: Datum/čas</span><span class="sxs-lookup"><span data-stu-id="9530c-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="9530c-145">**TransactionDate**: Datum/čas</span><span class="sxs-lookup"><span data-stu-id="9530c-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="9530c-146">**IsRecurring**: True/false (pravda/nepravda)</span><span class="sxs-lookup"><span data-stu-id="9530c-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="9530c-147">**Is_auto_renew**: True/false (Pravda/nepravda)</span><span class="sxs-lookup"><span data-stu-id="9530c-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="9530c-148">**RecurringFrequencyInMonths**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="9530c-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="9530c-149">V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="9530c-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="9530c-150">Uložte zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="9530c-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="9530c-151">Ingestace zákaznických dat z recenzí na webových stránkách</span><span class="sxs-lookup"><span data-stu-id="9530c-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="9530c-152">Vytvořte zdroj dat **Website**, vyberte možnost importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9530c-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9530c-153">Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="9530c-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="9530c-154">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="9530c-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9530c-155">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="9530c-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="9530c-156">**ReviewRating**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="9530c-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="9530c-157">**ReviewDate**: Datum</span><span class="sxs-lookup"><span data-stu-id="9530c-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="9530c-158">V poli „Název“ v pravém podokně přejmenujte svůj zdroj dat z **Query** na **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="9530c-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="9530c-159">Úkol 2 – Sjednocení dat</span><span class="sxs-lookup"><span data-stu-id="9530c-159">Task 2 - Data unification</span></span>

<span data-ttu-id="9530c-160">Po ingestaci dat nyní začínáme s procesem **Mapování, párování, sloučení** pro vytvoření sjednoceného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="9530c-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="9530c-161">Další informace naleznete v tématu [Sjednocení dat](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9530c-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="9530c-162">Mapovat</span><span class="sxs-lookup"><span data-stu-id="9530c-162">Map</span></span>

1. <span data-ttu-id="9530c-163">Po ingestaci dat namapujte kontakty z eCommerce a věrnostní data na běžné datové typy.</span><span class="sxs-lookup"><span data-stu-id="9530c-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="9530c-164">Přejděte na **Data** > **Sjednocení** > **Mapování**.</span><span class="sxs-lookup"><span data-stu-id="9530c-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="9530c-165">Vyberte entity, které představují profil zákazníka – **eCommerceContacts** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="9530c-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Sjednocení zdrojů dat eCommerce a věrnostních bodů.":::

1. <span data-ttu-id="9530c-167">Vyberte **ContactId** jako primární klíč pro **eCommerceContatcs** a **LoyaltyID** jako primární klíč pro **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="9530c-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Sjednocení LoyaltyId jako primární klíč.":::

### <a name="match"></a><span data-ttu-id="9530c-169">Párování</span><span class="sxs-lookup"><span data-stu-id="9530c-169">Match</span></span>

1. <span data-ttu-id="9530c-170">Přejděte na kartu **Párování** a vyberte **Nastavit pořadí**.</span><span class="sxs-lookup"><span data-stu-id="9530c-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="9530c-171">V **primárním** rozevíracím seznamu zvolte jako primární zdroj **eCommerceContacts : eCommerce** a zahrňte všechny záznamy.</span><span class="sxs-lookup"><span data-stu-id="9530c-171">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="9530c-172">V rozevíracím seznamu **Entita 2** vyberte **loyCustomers: LoyaltyScheme** a zahrňte všechny záznamy.</span><span class="sxs-lookup"><span data-stu-id="9530c-172">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Sjednocení párování dat eCommerce a věrnostních bodů.":::

1. <span data-ttu-id="9530c-174">Vyberte **Vytvořit nové pravidlo**</span><span class="sxs-lookup"><span data-stu-id="9530c-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="9530c-175">Přidejte svou první podmínku pomocí FullName.</span><span class="sxs-lookup"><span data-stu-id="9530c-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="9530c-176">Pro eCommerceContacts vyberte **Celé jméno** v rozevírací nabídce.</span><span class="sxs-lookup"><span data-stu-id="9530c-176">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="9530c-177">Pro loyCustomers vyberte **Celé jméno** v rozevírací nabídce.</span><span class="sxs-lookup"><span data-stu-id="9530c-177">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="9530c-178">Vyberte rozevírací seznam **Normalizovat** rozevírací seznam a vyberte **Typ (telefon, jméno, adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="9530c-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="9530c-179">Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="9530c-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="9530c-180">Zadejte jméno **Celé jméno, e-mail** pro nové pravidlo.</span><span class="sxs-lookup"><span data-stu-id="9530c-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="9530c-181">Přidejte druhou podmínku pro e-mailovou adresu výběrem **Přidat podmínku**</span><span class="sxs-lookup"><span data-stu-id="9530c-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="9530c-182">Pro entitu eCommerceContacts zvolte **EMail** v rozevírací nabídce.</span><span class="sxs-lookup"><span data-stu-id="9530c-182">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="9530c-183">Pro entitu loyCustomers zvolte **EMail** v rozevírací nabídce.</span><span class="sxs-lookup"><span data-stu-id="9530c-183">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="9530c-184">Ponechejte pole Noramlizovat prázdné.</span><span class="sxs-lookup"><span data-stu-id="9530c-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="9530c-185">Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="9530c-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Sjednocení pravidla párování pro jméno a e-mail.":::

7. <span data-ttu-id="9530c-187">Zvolte **Uložit** a **Spustit**.</span><span class="sxs-lookup"><span data-stu-id="9530c-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="9530c-188">Sloučení</span><span class="sxs-lookup"><span data-stu-id="9530c-188">Merge</span></span>

1. <span data-ttu-id="9530c-189">Přejděte na kartu **Sloučení**.</span><span class="sxs-lookup"><span data-stu-id="9530c-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="9530c-190">V **ContactId** pro entitu **loyCustomers** změňte zobrazované jméno na **ContactIdLOYALTY**, abyste jej odlišili od ingestovaných ID.</span><span class="sxs-lookup"><span data-stu-id="9530c-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Přejmenování contactid z věrnostního ID.":::

1. <span data-ttu-id="9530c-192">Volbami **Uložit** a **Spustit** zahájíte proces sloučení.</span><span class="sxs-lookup"><span data-stu-id="9530c-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="9530c-193">Úkol 3 – Konfigurace predikce úbytku předplatných</span><span class="sxs-lookup"><span data-stu-id="9530c-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="9530c-194">Se zavedenými sjednocenými profily zákazníků nyní můžeme spustit predikci úbytku předplatných.</span><span class="sxs-lookup"><span data-stu-id="9530c-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="9530c-195">Podrobné kroky najdete v části [Predikce úbytku předplatných (Preview)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="9530c-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="9530c-196">Přejděte na **Analytické nástroje** > **Prozkoumat** a vyberte **Model úbytku zákazníků**.</span><span class="sxs-lookup"><span data-stu-id="9530c-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="9530c-197">Vyberte možnost **Předplatné** a pak **Začít**.</span><span class="sxs-lookup"><span data-stu-id="9530c-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="9530c-198">Pojmenujte model **Předdefinovaná predikce úbytku předplatných** a výstupní entitu **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="9530c-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="9530c-199">Definujte dvě podmínky pro model úbytku:</span><span class="sxs-lookup"><span data-stu-id="9530c-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="9530c-200">**Dny od ukončení předplatného**: **alespoň 60** dnů.</span><span class="sxs-lookup"><span data-stu-id="9530c-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="9530c-201">Pokud zákazník neobnoví své předplatné během této doby po ukončení předplatného, pak se považuje za ztraceného.</span><span class="sxs-lookup"><span data-stu-id="9530c-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="9530c-202">**Definice úbytku**: **alespoň 93** dnů.</span><span class="sxs-lookup"><span data-stu-id="9530c-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="9530c-203">Doba trvání modelu predikuje, kteří zákazníci by mohli odejít.</span><span class="sxs-lookup"><span data-stu-id="9530c-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="9530c-204">Čím více hledíte do budoucnosti, tím méně jsou výsledky přesné.</span><span class="sxs-lookup"><span data-stu-id="9530c-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Výběr pák modelu Interval predikce a Definice úbytku.":::

1. <span data-ttu-id="9530c-206">Vyberte **Přidat požadovaná data** a vyberte **Přidat data** pro historii předplatného.</span><span class="sxs-lookup"><span data-stu-id="9530c-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="9530c-207">Přidejte entitu **Předplatné: SubscriptionHistory** entita a mapujte pole z eCommerce na odpovídající pole požadovaná modelem.</span><span class="sxs-lookup"><span data-stu-id="9530c-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="9530c-208">Přidejte se k entitě **Předplatné: SubscriptionHistory** s **eCommerceContacts: eCommerce**, pojmenujte vztah **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="9530c-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Připojení se k entitám eCommerce.":::

1. <span data-ttu-id="9530c-210">V části Aktivity zákazníka přidejte entitu **webReviews: Website** a mapujte pole z webReviews na odpovídající pole požadovaná modelem.</span><span class="sxs-lookup"><span data-stu-id="9530c-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="9530c-211">Primární klíč: ReviewId</span><span class="sxs-lookup"><span data-stu-id="9530c-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="9530c-212">Časové razítko: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="9530c-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="9530c-213">Událost: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="9530c-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="9530c-214">Nakonfigurujte aktivitu pro recenze webových stránek.</span><span class="sxs-lookup"><span data-stu-id="9530c-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="9530c-215">Vyberte aktivitu **Recenze** a připojte se k entitě **webReviews: Website** s **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="9530c-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="9530c-216">Vyberte **Další** pro nastavení plánu modelu.</span><span class="sxs-lookup"><span data-stu-id="9530c-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="9530c-217">Model musí pravidelně trénovat, aby se naučil nové vzory, když jsou přijímána nová data.</span><span class="sxs-lookup"><span data-stu-id="9530c-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="9530c-218">V tomto příkladu vyberte položku **Měsíčně**.</span><span class="sxs-lookup"><span data-stu-id="9530c-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="9530c-219">Po kontrole všech podrobností vyberte **Uložit a spustit**.</span><span class="sxs-lookup"><span data-stu-id="9530c-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="9530c-220">Úkol 4 – Kontrola výsledků modelu a vysvětlení</span><span class="sxs-lookup"><span data-stu-id="9530c-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="9530c-221">Nechte model dokončit cvičení a bodování dat.</span><span class="sxs-lookup"><span data-stu-id="9530c-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="9530c-222">Nyní si můžete prohlédnout vysvětlení modelu úbytku předplatných.</span><span class="sxs-lookup"><span data-stu-id="9530c-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="9530c-223">Další informace viz [Kontrola stavu a výsledků predikce](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="9530c-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="9530c-224">Úkol 5 – Vytvoření segmentu zákazníků s vysokým rizikem ztráty</span><span class="sxs-lookup"><span data-stu-id="9530c-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="9530c-225">Spuštěním produkčního modelu se vytvoří nová entita, ve které se můžete podívat **Data** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="9530c-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="9530c-226">Můžete vytvořit nový segment na základě entity vytvořené modelem.</span><span class="sxs-lookup"><span data-stu-id="9530c-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="9530c-227">Jděte na **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="9530c-227">Go to **Segments**.</span></span> <span data-ttu-id="9530c-228">Vyberte **Nový** a vyberte **Vytvořit z** > **Analytické nástroje**.</span><span class="sxs-lookup"><span data-stu-id="9530c-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Vytvoření segmentu s výstupem modelu.":::

1. <span data-ttu-id="9530c-230">Vyberte koncový bod **OOBSubscriptionChurnPrediction** a definujte segment:</span><span class="sxs-lookup"><span data-stu-id="9530c-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="9530c-231">Pole: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="9530c-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="9530c-232">Operátor: větší než</span><span class="sxs-lookup"><span data-stu-id="9530c-232">Operator: greater than</span></span>
   - <span data-ttu-id="9530c-233">Hodnota: 0,6</span><span class="sxs-lookup"><span data-stu-id="9530c-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nastavení segmentu úbytku předplatných.":::

<span data-ttu-id="9530c-235">Nyní máte segment, který se dynamicky aktualizuje a který identifikuje zákazníky s vysokým rizikem odchodu pro toto podnikání s předplatným.</span><span class="sxs-lookup"><span data-stu-id="9530c-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="9530c-236">Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9530c-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]