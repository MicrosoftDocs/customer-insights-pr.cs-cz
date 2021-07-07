---
title: Predikce celoživotní hodnoty zákazníka – ukázkový průvodce
description: Pomocí tohoto ukázkového průvodce můžete vyzkoušet model predikce celoživotní hodnoty zákazníka.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306341"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="15a5e-103">Predikce celoživotní hodnoty zákazníka (CLV) – ukázkový průvodce</span><span class="sxs-lookup"><span data-stu-id="15a5e-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="15a5e-104">Tento průvodce vás provede kompletním příkladem predikce celoživotní hodnoty zákazníka (CLV) v Customer Insights s využitím ukázkových dat.</span><span class="sxs-lookup"><span data-stu-id="15a5e-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="15a5e-105">Scénář</span><span class="sxs-lookup"><span data-stu-id="15a5e-105">Scenario</span></span>

<span data-ttu-id="15a5e-106">Contoso je společnost, která vyrábí vysoce kvalitní kávu a kávovary.</span><span class="sxs-lookup"><span data-stu-id="15a5e-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="15a5e-107">Své výrobky podávají prostřednictvím webu Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="15a5e-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="15a5e-108">Společnost chce znát hodnotu (výnos), kterou mohou její zákazníci generovat v příštích 12 měsících.</span><span class="sxs-lookup"><span data-stu-id="15a5e-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="15a5e-109">Znalost očekávané hodnoty jejich zákazníků v příštích 12 měsících jim pomůže nasměrovat jejich marketingové úsilí na zákazníky s vysokou důležitostí.</span><span class="sxs-lookup"><span data-stu-id="15a5e-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15a5e-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="15a5e-110">Prerequisites</span></span>

- <span data-ttu-id="15a5e-111">Alespoň [oprávnění přispěvatele](permissions.md) v přehledech cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="15a5e-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="15a5e-112">Doporučujeme implementovat následující kroky [v novém prostředí](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="15a5e-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="15a5e-113">Úkol 1 – Ingestace dat</span><span class="sxs-lookup"><span data-stu-id="15a5e-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="15a5e-114">Přečtěte si články [o příjmu dat](data-sources.md) a [importu zdrojů dat pomocí konektorů Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="15a5e-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="15a5e-115">Následující informace předpokládají, že jste se seznámili s ingestací dat obecně.</span><span class="sxs-lookup"><span data-stu-id="15a5e-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="15a5e-116">Ingestace zákaznických dat z platformy eCommerce</span><span class="sxs-lookup"><span data-stu-id="15a5e-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="15a5e-117">Vytvořte zdroj dat s názvem **eCommerce**, vyberte možnost importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="15a5e-118">Zadejte adresu URL pro kontakty eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="15a5e-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="15a5e-119">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="15a5e-120">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="15a5e-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="15a5e-121">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="15a5e-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="15a5e-122">**CreatedOn**: Datum/čas/pásmo</span><span class="sxs-lookup"><span data-stu-id="15a5e-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformace data narození na datum.":::

1. <span data-ttu-id="15a5e-124">V poli „Název“ v pravém podokně přejmenujte svůj zdroj dat z **Query** na **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="15a5e-125">**Uložte** zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="15a5e-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="15a5e-126">Ingestace dat online nákupu</span><span class="sxs-lookup"><span data-stu-id="15a5e-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="15a5e-127">Přidejte další datovou sadu do stejného zdroje dat **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="15a5e-128">Znovu vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="15a5e-129">Zadejte adresu URL pro data **Online nákupy** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="15a5e-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="15a5e-130">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="15a5e-131">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="15a5e-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="15a5e-132">**PurchasedOn**: Datum/čas</span><span class="sxs-lookup"><span data-stu-id="15a5e-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="15a5e-133">**TotalPrice**: Měna</span><span class="sxs-lookup"><span data-stu-id="15a5e-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="15a5e-134">V poli **Název** v postranním panelu přejmenujte svůj zdroj dat z **Query** na **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="15a5e-135">**Uložte** zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="15a5e-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="15a5e-136">Ingestace zákaznických dat z věrnostního schématu</span><span class="sxs-lookup"><span data-stu-id="15a5e-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="15a5e-137">Vytvořte zdroj dat **LoyaltyScheme**, vyberte možnost importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="15a5e-138">Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="15a5e-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="15a5e-139">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="15a5e-140">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="15a5e-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="15a5e-141">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="15a5e-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="15a5e-142">**RewardsPoints**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="15a5e-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="15a5e-143">**CreatedOn**: Datum/čas</span><span class="sxs-lookup"><span data-stu-id="15a5e-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="15a5e-144">V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="15a5e-145">**Uložte** zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="15a5e-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="15a5e-146">Ingestace zákaznických dat z recenzí na webových stránkách</span><span class="sxs-lookup"><span data-stu-id="15a5e-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="15a5e-147">Vytvořte zdroj dat **Website**, vyberte možnost importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="15a5e-148">Zadejte adresu URL pro kontakty eCommerce https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="15a5e-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="15a5e-149">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="15a5e-150">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="15a5e-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="15a5e-151">**ReviewRating**: Desetinné číslo</span><span class="sxs-lookup"><span data-stu-id="15a5e-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="15a5e-152">**ReviewDate**: Datum</span><span class="sxs-lookup"><span data-stu-id="15a5e-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="15a5e-153">V poli „Název“ v pravém podokně přejmenujte svůj zdroj dat z **Dotaz** na **Recenze**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="15a5e-154">**Uložte** zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="15a5e-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="15a5e-155">Úkol 2 – Sjednocení dat</span><span class="sxs-lookup"><span data-stu-id="15a5e-155">Task 2 - Data unification</span></span>

<span data-ttu-id="15a5e-156">Po příjmu dat nyní zahájíme proces sjednocení dat, abychom vytvořili jednotný profil zákazníka.</span><span class="sxs-lookup"><span data-stu-id="15a5e-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="15a5e-157">Další informace naleznete v tématu [Sjednocení dat](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="15a5e-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="15a5e-158">Mapovat</span><span class="sxs-lookup"><span data-stu-id="15a5e-158">Map</span></span>

1. <span data-ttu-id="15a5e-159">Po ingestaci dat namapujte kontakty z eCommerce a věrnostní data na běžné datové typy.</span><span class="sxs-lookup"><span data-stu-id="15a5e-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="15a5e-160">Přejděte na **Data** > **Sjednocení** > **Mapování**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="15a5e-161">Vyberte entity, které představují profil zákazníka – **eCommerceContacts** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="15a5e-162">Potom vyberte **Použít**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-162">Then, select **Apply**.</span></span>

   ![Sjednocení zdrojů dat eCommerce a věrnostních bodů.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="15a5e-164">Vyberte **ContactId** jako primární klíč pro **eCommerceContatcs** a **LoyaltyID** jako primární klíč pro **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Sjednocení LoyaltyId jako primární klíč.](media/unify-loyaltyid.png)

1. <span data-ttu-id="15a5e-166">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="15a5e-167">Párování</span><span class="sxs-lookup"><span data-stu-id="15a5e-167">Match</span></span>

1. <span data-ttu-id="15a5e-168">Přejděte na kartu **Párování** a vyberte **Nastavit pořadí**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="15a5e-169">V **primárním** rozevíracím seznamu zvolte jako primární zdroj **eCommerceContacts : eCommerce** a zahrňte všechny záznamy.</span><span class="sxs-lookup"><span data-stu-id="15a5e-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="15a5e-170">V rozevíracím seznamu **Entita 2** vyberte **loyCustomers: LoyaltyScheme** a zahrňte všechny záznamy.</span><span class="sxs-lookup"><span data-stu-id="15a5e-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Sjednocení párování dat eCommerce a věrnostních bodů.](media/unify-match-order.png)

1. <span data-ttu-id="15a5e-172">Vyberte položku **Přidat pravidlo**</span><span class="sxs-lookup"><span data-stu-id="15a5e-172">Select **Add rule**</span></span>

1. <span data-ttu-id="15a5e-173">Přidejte svou první podmínku pomocí FullName.</span><span class="sxs-lookup"><span data-stu-id="15a5e-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="15a5e-174">Pro eCommerceContacts vyberte **Celé jméno** v rozevírací nabídce.</span><span class="sxs-lookup"><span data-stu-id="15a5e-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="15a5e-175">Pro loyCustomers vyberte **Celé jméno** v rozevírací nabídce.</span><span class="sxs-lookup"><span data-stu-id="15a5e-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="15a5e-176">Vyberte rozevírací seznam **Normalizovat** a zvolte **Typ (Telefon, Jméno, Adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="15a5e-177">Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="15a5e-178">Zadejte jméno **Celé jméno, e-mail** pro nové pravidlo.</span><span class="sxs-lookup"><span data-stu-id="15a5e-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="15a5e-179">Přidejte druhou podmínku pro e-mailovou adresu výběrem **Přidat podmínku**</span><span class="sxs-lookup"><span data-stu-id="15a5e-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="15a5e-180">Pro entitu eCommerceContacts zvolte **EMail** v rozevírací nabídce.</span><span class="sxs-lookup"><span data-stu-id="15a5e-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="15a5e-181">Pro entitu loyCustomers zvolte **EMail** v rozevírací nabídce.</span><span class="sxs-lookup"><span data-stu-id="15a5e-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="15a5e-182">Ponechejte pole Noramlizovat prázdné.</span><span class="sxs-lookup"><span data-stu-id="15a5e-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="15a5e-183">Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Sjednocení pravidla párování pro jméno a e-mail.](media/unify-match-rule.png)

1. <span data-ttu-id="15a5e-185">Vyberte **Hotovo**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-185">Select **Done**.</span></span>

1. <span data-ttu-id="15a5e-186">Zvolte **Uložit** a **Spustit**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="15a5e-187">Sloučení</span><span class="sxs-lookup"><span data-stu-id="15a5e-187">Merge</span></span>

1. <span data-ttu-id="15a5e-188">Přejděte na kartu **Sloučení**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="15a5e-189">V **ContactId** pro entitu **loyCustomers** změňte zobrazované jméno na **ContactIdLOYALTY**, abyste jej odlišili od ingestovaných ID.</span><span class="sxs-lookup"><span data-stu-id="15a5e-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Přejmenování contactid z věrnostního ID.](media/unify-merge-contactid.png)

1. <span data-ttu-id="15a5e-191">Vyberte **Uložit** a **Spustit sloučení a podřízené procesy**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="15a5e-192">Úkol 3 - Konfigurace predikce celoživotní hodnoty zákazníka</span><span class="sxs-lookup"><span data-stu-id="15a5e-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="15a5e-193">Se zavedenými sjednocenými profily zákazníků nyní můžeme spustit predikci celoživotní hodnoty zákazníka.</span><span class="sxs-lookup"><span data-stu-id="15a5e-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="15a5e-194">Podrobné kroky najdete v části [Predikce celoživotní hodnoty zákazníka (preview)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="15a5e-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="15a5e-195">Přejděte do nabídky **Analytické nástroje**  > **Predikce** a vyberte **Model celoživotní hodnoty zákazníka**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="15a5e-196">Projděte si informace v bočním podokně a vyberte položku **Začínáme**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="15a5e-197">Modelu dejte název **OOB eCommerce CLV Prediction** a výstupní entitě název **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="15a5e-198">Definujte předvolby modelu pro model CLV:</span><span class="sxs-lookup"><span data-stu-id="15a5e-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="15a5e-199">**Časové období předpovědi**: **12 měsíců nebo 1 rok**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="15a5e-200">Toto nastavení definuje, jak daleko do budoucnosti lze předpovědět celoživotní hodnotu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="15a5e-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="15a5e-201">**Aktivní zákazníci**: Určete, co pro vaši firmu znamená aktivní zákazník.</span><span class="sxs-lookup"><span data-stu-id="15a5e-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="15a5e-202">Nastavte historický časový rámec, ve kterém zákazník musel mít alespoň jednu transakci, aby mohl být považován za aktivního.</span><span class="sxs-lookup"><span data-stu-id="15a5e-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="15a5e-203">Model bude predikovat CLV pouze pro aktivní zákazníky.</span><span class="sxs-lookup"><span data-stu-id="15a5e-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="15a5e-204">Vyberte si, zda necháte model vypočítat časové období na základě historických údajů o transakcích, nebo zda zadáte konkrétní časový rámec.</span><span class="sxs-lookup"><span data-stu-id="15a5e-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="15a5e-205">V této ukázkové příručce **necháme model vypočítat interval nákupu**, což je výchozí možnost.</span><span class="sxs-lookup"><span data-stu-id="15a5e-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="15a5e-206">**Zákazníci s vysokou důležitostí** : Definujte zákazníky s vysokou důležitostí jako percentil nejlépe platících zákazníků.</span><span class="sxs-lookup"><span data-stu-id="15a5e-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="15a5e-207">Model používá tento vstup k vytváření výsledků, které odpovídají vaší obchodní definici zákazníků s vysokou důležitostí.</span><span class="sxs-lookup"><span data-stu-id="15a5e-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="15a5e-208">Můžete nechat model definovat zákazníky s vysokou důležitostí.</span><span class="sxs-lookup"><span data-stu-id="15a5e-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="15a5e-209">Používá heuristické pravidlo, které odvozuje percentil.</span><span class="sxs-lookup"><span data-stu-id="15a5e-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="15a5e-210">Můžete také definovat zákazníky s vysokou důležitostí jako percentil nejlépe platících budoucích zákazníků.</span><span class="sxs-lookup"><span data-stu-id="15a5e-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="15a5e-211">V této ukázkové příručce ručně definujeme zákazníky s vysokou důležitostí jako **nejlepších 30% aktivně platících zákazníků** a poté vyberte možnost **Další**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Předvolby v asistovaném prostředí pro model CLV.":::

1. <span data-ttu-id="15a5e-213">V kroku **Požadovaná data** vyberte **Přidat data** a zadejte údaje o historii transakcí.</span><span class="sxs-lookup"><span data-stu-id="15a5e-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="15a5e-214">Přidejte entitu **eCommercePurchases : eCommerce** a mapujte atributy, které model vyžaduje:</span><span class="sxs-lookup"><span data-stu-id="15a5e-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="15a5e-215">ID transakce: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="15a5e-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="15a5e-216">Datum transakce: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="15a5e-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="15a5e-217">Částka transakce: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="15a5e-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="15a5e-218">ID produktu: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="15a5e-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="15a5e-219">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-219">Select **Next**.</span></span>

1. <span data-ttu-id="15a5e-220">Nastavte vztah mezi entitami **eCommercePurchases : eCommerce** a **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="15a5e-221">Krok **Další údaje (volitelné)** umožňuje přidat více údajů o aktivitě zákazníka.</span><span class="sxs-lookup"><span data-stu-id="15a5e-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="15a5e-222">Tato data mohou pomoci získat více informací o interakcích zákazníků s vaší firmou, což může přispět k CLV.</span><span class="sxs-lookup"><span data-stu-id="15a5e-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="15a5e-223">Přidání klíčových interakcí zákazníků, jako jsou webové protokoly, protokoly služeb zákazníkům nebo historie programu odměn, může zlepšit přesnost predikcí.</span><span class="sxs-lookup"><span data-stu-id="15a5e-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="15a5e-224">Vyberte položku **Přidat data** a zadejte více údajů o aktivitě zákazníka.</span><span class="sxs-lookup"><span data-stu-id="15a5e-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="15a5e-225">Přidejte entitu aktivity zákazníka a namapujte její názvy polí na odpovídající pole vyžadovaná modelem:</span><span class="sxs-lookup"><span data-stu-id="15a5e-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="15a5e-226">Entita aktivity zákazníka: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="15a5e-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="15a5e-227">Primární klíč: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="15a5e-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="15a5e-228">Časové razítko: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="15a5e-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="15a5e-229">Událost (název aktivity): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="15a5e-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="15a5e-230">Podrobnosti (částka nebo hodnota): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="15a5e-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="15a5e-231">Vyberte položku **Další** a konfigurujte aktivitu a vztah mezi daty transakce a daty zákazníka:</span><span class="sxs-lookup"><span data-stu-id="15a5e-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="15a5e-232">Typ aktivity: Zvolte stávající</span><span class="sxs-lookup"><span data-stu-id="15a5e-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="15a5e-233">Popisek aktivity: Review</span><span class="sxs-lookup"><span data-stu-id="15a5e-233">Activity label: Review</span></span>
   - <span data-ttu-id="15a5e-234">Odpovídající popisek: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="15a5e-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="15a5e-235">Entita zákazníka: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="15a5e-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="15a5e-236">Vztah: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="15a5e-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="15a5e-237">Vyberte **Další** pro nastavení plánu modelu.</span><span class="sxs-lookup"><span data-stu-id="15a5e-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="15a5e-238">Model potřebuje pravidelně trénovat, aby se naučil nové vzorce, když jsou přijímána nová data.</span><span class="sxs-lookup"><span data-stu-id="15a5e-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="15a5e-239">V tomto příkladu zvolte **Měsíční**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="15a5e-240">Po kontrole všech podrobností vyberte **Uložit a spustit**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="15a5e-241">Úkol 4 – Kontrola výsledků modelu a vysvětlení</span><span class="sxs-lookup"><span data-stu-id="15a5e-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="15a5e-242">Nechte model dokončit cvičení a bodování dat.</span><span class="sxs-lookup"><span data-stu-id="15a5e-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="15a5e-243">Dále si můžete prohlédnout výsledky a vysvětlení modelu CLV.</span><span class="sxs-lookup"><span data-stu-id="15a5e-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="15a5e-244">Další informace viz [Kontrola stavu a výsledků predikce](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="15a5e-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="15a5e-245">Úkol 5 - Vytvoření segmentu zákazníků s vysokou důležitostí</span><span class="sxs-lookup"><span data-stu-id="15a5e-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="15a5e-246">Spuštěním modelu se vytvoří nová entita, která je uvedena na stránce **Data** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="15a5e-247">Můžete vytvořit nový segment zákazníků na základě entity vytvořené modelem.</span><span class="sxs-lookup"><span data-stu-id="15a5e-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="15a5e-248">Jděte na **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="15a5e-249">Vyberte **Nový** a vyberte **Vytvořit z** > **Analytické nástroje**.</span><span class="sxs-lookup"><span data-stu-id="15a5e-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Vytvoření segmentu s výstupem modelu.](media/segment-intelligence.png)

1. <span data-ttu-id="15a5e-251">Vyberte entitu **OOBeCommerceCLVPrediction** a definujte segment:</span><span class="sxs-lookup"><span data-stu-id="15a5e-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="15a5e-252">Pole: CLVScore</span><span class="sxs-lookup"><span data-stu-id="15a5e-252">Field: CLVScore</span></span>
  - <span data-ttu-id="15a5e-253">Operátor: větší než</span><span class="sxs-lookup"><span data-stu-id="15a5e-253">Operator: greater than</span></span>
  - <span data-ttu-id="15a5e-254">Hodnota: 1500</span><span class="sxs-lookup"><span data-stu-id="15a5e-254">Value: 1500</span></span>

1. <span data-ttu-id="15a5e-255">Vyberte **Zkontrolovat** a **Uložit** segment.</span><span class="sxs-lookup"><span data-stu-id="15a5e-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="15a5e-256">Nyní máte segment, který identifikuje zákazníky, u nichž se předpokládá, že v příštích 12 měsících vygenerují více než 1500 USD výnosů.</span><span class="sxs-lookup"><span data-stu-id="15a5e-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="15a5e-257">Tento segment se dynamicky aktualizuje, pokud je přijímáno více dat.</span><span class="sxs-lookup"><span data-stu-id="15a5e-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="15a5e-258">Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).</span><span class="sxs-lookup"><span data-stu-id="15a5e-258">For more information, see [Create and manage segments](segments.md).</span></span>
