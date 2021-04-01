---
title: Průvodce ukázkami predikce doporučení produktů
description: Pomocí tohoto průvodce ukázkami můžete vyzkoušet dodávaný model predikce doporučení produktů.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595265"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="c5eef-103">Průvodce ukázkami predikce doporučení produktů (Preview)</span><span class="sxs-lookup"><span data-stu-id="c5eef-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="c5eef-104">Provedeme vás příkladem predikce doporučení produktů od začátku dokonce s využitím níže uvedených ukázkových dat.</span><span class="sxs-lookup"><span data-stu-id="c5eef-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="c5eef-105">Scénář</span><span class="sxs-lookup"><span data-stu-id="c5eef-105">Scenario</span></span>

<span data-ttu-id="c5eef-106">Contoso je společnost, která vyrábí vysoce kvalitní kávu a kávovary, které prodává prostřednictvím svých webových stránek Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="c5eef-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="c5eef-107">Jejich cílem je pochopit, které produkty by měli doporučit svým vracejícím se zákazníkům.</span><span class="sxs-lookup"><span data-stu-id="c5eef-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="c5eef-108">Informovanost, u kterých zákazníků je **pravděpodobnější nákup**, jim může pomoci ušetřit marketingové úsilí zaměřením na konkrétní položky.</span><span class="sxs-lookup"><span data-stu-id="c5eef-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c5eef-109">Požadavky</span><span class="sxs-lookup"><span data-stu-id="c5eef-109">Prerequisites</span></span>

- <span data-ttu-id="c5eef-110">Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c5eef-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="c5eef-111">Doporučujeme implementovat následující kroky [v novém prostředí](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="c5eef-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="c5eef-112">Úkol 1 – Ingestace dat</span><span class="sxs-lookup"><span data-stu-id="c5eef-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="c5eef-113">Projděte si články [o příjmu (ingestaci) dat](data-sources.md) a [importu zdrojů dat pomocí konektorů Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c5eef-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="c5eef-114">Následující informace předpokládají, že jste se seznámili s ingestací dat obecně.</span><span class="sxs-lookup"><span data-stu-id="c5eef-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="c5eef-115">Ingestace zákaznických dat z platformy eCommerce</span><span class="sxs-lookup"><span data-stu-id="c5eef-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="c5eef-116">Vytvořte zdroj dat **eCommerce**, vyberte možnost importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c5eef-117">Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="c5eef-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="c5eef-118">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c5eef-119">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="c5eef-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="c5eef-120">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="c5eef-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="c5eef-121">**CreatedOn**: Datum/čas/pásmo</span><span class="sxs-lookup"><span data-stu-id="c5eef-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformace data narození na datum.":::

5. <span data-ttu-id="c5eef-123">V poli „Název“ v pravém podokně přejmenujte svůj zdroj dat z **Query** na **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="c5eef-124">**Uložte** zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="c5eef-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="c5eef-125">Ingestace dat online nákupu</span><span class="sxs-lookup"><span data-stu-id="c5eef-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="c5eef-126">Přidejte další datovou sadu do stejného zdroje dat **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="c5eef-127">Znovu vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="c5eef-128">Zadejte adresu URL pro data **Online nákupy** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="c5eef-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="c5eef-129">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c5eef-130">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="c5eef-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="c5eef-131">**PurchasedOn**: Datum/čas</span><span class="sxs-lookup"><span data-stu-id="c5eef-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="c5eef-132">**TotalPrice**: Měna</span><span class="sxs-lookup"><span data-stu-id="c5eef-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="c5eef-133">V poli **Název** v postranním panelu přejmenujte svůj zdroj dat z **Query** na **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="c5eef-134">Uložte zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="c5eef-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="c5eef-135">Ingestace zákaznických dat z věrnostního schématu</span><span class="sxs-lookup"><span data-stu-id="c5eef-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="c5eef-136">Vytvořte zdroj dat **LoyaltyScheme**, vyberte možnost importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c5eef-137">Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="c5eef-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="c5eef-138">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c5eef-139">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="c5eef-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="c5eef-140">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="c5eef-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="c5eef-141">**RewardsPoints**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="c5eef-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="c5eef-142">**CreatedOn**: Datum/čas</span><span class="sxs-lookup"><span data-stu-id="c5eef-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="c5eef-143">V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="c5eef-144">Uložte zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="c5eef-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="c5eef-145">Úkol 2 – Sjednocení dat</span><span class="sxs-lookup"><span data-stu-id="c5eef-145">Task 2 - Data unification</span></span>

<span data-ttu-id="c5eef-146">Po ingestaci dat nyní začínáme s procesem **Mapování, párování, sloučení** pro vytvoření sjednoceného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="c5eef-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="c5eef-147">Další informace naleznete v tématu [Sjednocení dat](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="c5eef-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="c5eef-148">Mapovat</span><span class="sxs-lookup"><span data-stu-id="c5eef-148">Map</span></span>

1. <span data-ttu-id="c5eef-149">Po ingestaci dat namapujte kontakty z eCommerce a věrnostní data na běžné datové typy.</span><span class="sxs-lookup"><span data-stu-id="c5eef-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="c5eef-150">Přejděte na **Data** > **Sjednocení** > **Mapování**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="c5eef-151">Vyberte entity, které představují profil zákazníka – **eCommerceContacts** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![Sjednocení zdrojů dat eCommerce a věrnostních bodů.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="c5eef-153">Vyberte **ContactId** jako primární klíč pro **eCommerceContatcs** a **LoyaltyID** jako primární klíč pro **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Sjednocení LoyaltyId jako primární klíč.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="c5eef-155">Shoda barev</span><span class="sxs-lookup"><span data-stu-id="c5eef-155">Match</span></span>

1. <span data-ttu-id="c5eef-156">Přejděte na kartu **Párování** a vyberte **Nastavit pořadí**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="c5eef-157">V rozevíracím seznamu **Primární** vyberte **eCommerceContacts: eCommerce** jako primární zdroj a zahrňte všechny záznamy.</span><span class="sxs-lookup"><span data-stu-id="c5eef-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="c5eef-158">V rozevíracím seznamu **Entita 2** vyberte **loyCustomers: LoyaltyScheme** a zahrňte všechny záznamy.</span><span class="sxs-lookup"><span data-stu-id="c5eef-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Sjednocení párování dat eCommerce a věrnostních bodů.](media/unify-match-order.png)

4. <span data-ttu-id="c5eef-160">Vyberte **Vytvořit nové pravidlo**</span><span class="sxs-lookup"><span data-stu-id="c5eef-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="c5eef-161">Přidejte svou první podmínku pomocí FullName.</span><span class="sxs-lookup"><span data-stu-id="c5eef-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="c5eef-162">Pro eCommerceContacts vyberte **FullName** v rozbalovací nabídce.</span><span class="sxs-lookup"><span data-stu-id="c5eef-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="c5eef-163">Pro loyCustomers vyberte **FullName** v rozbalovací nabídce.</span><span class="sxs-lookup"><span data-stu-id="c5eef-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="c5eef-164">Vyberte rozevírací seznam **Normalizovat** rozevírací seznam a vyberte **Typ (telefon, jméno, adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="c5eef-165">Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="c5eef-166">Zadejte jméno **Celé jméno, e-mail** pro nové pravidlo.</span><span class="sxs-lookup"><span data-stu-id="c5eef-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="c5eef-167">Přidejte druhou podmínku pro e-mailovou adresu výběrem **Přidat podmínku**</span><span class="sxs-lookup"><span data-stu-id="c5eef-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="c5eef-168">Pro entitu eCommerceContacts zvolte **EMail** v rozevíracím seznamu.</span><span class="sxs-lookup"><span data-stu-id="c5eef-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="c5eef-169">Pro entitu loyCustomers zvolte **EMail** v rozevíracím seznamu.</span><span class="sxs-lookup"><span data-stu-id="c5eef-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="c5eef-170">Ponechejte pole Noramlizovat prázdné.</span><span class="sxs-lookup"><span data-stu-id="c5eef-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="c5eef-171">Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Sjednocení pravidla párování pro jméno a e-mail.](media/unify-match-rule.png)

7. <span data-ttu-id="c5eef-173">Zvolte **Uložit** a **Spustit**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="c5eef-174">Sloučení</span><span class="sxs-lookup"><span data-stu-id="c5eef-174">Merge</span></span>

1. <span data-ttu-id="c5eef-175">Přejděte na kartu **Sloučení**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="c5eef-176">V **ContactId** pro entitu **loyCustomers** změňte zobrazované jméno na **ContactIdLOYALTY**, abyste jej odlišili od ingestovaných ID.</span><span class="sxs-lookup"><span data-stu-id="c5eef-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Přejmenování contactid z věrnostního ID.](media/unify-merge-contactid.png)

1. <span data-ttu-id="c5eef-178">Volbami **Uložit** a **Spustit** zahájíte proces sloučení.</span><span class="sxs-lookup"><span data-stu-id="c5eef-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="c5eef-179">Úkol 3 – Konfigurace predikce doporučení produktů</span><span class="sxs-lookup"><span data-stu-id="c5eef-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="c5eef-180">Se zavedenými sjednocenými profily zákazníků nyní můžeme spustit predikci úbytku předplatných.</span><span class="sxs-lookup"><span data-stu-id="c5eef-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="c5eef-181">Přejděte na **Analytické nástroje** > **Predikce** a vyberte **Doporučení produktů**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="c5eef-182">Vyberte **Začínáme**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-182">Select **Get started**.</span></span>

1. <span data-ttu-id="c5eef-183">Pojmenujte model **Model predikce doporučení produktů OOB** a výstupní entitu **ModelPredikceDoporuceniProduktuOOB**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="c5eef-184">Definujte tři podmínky pro model:</span><span class="sxs-lookup"><span data-stu-id="c5eef-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="c5eef-185">**Počet produktů**: Nastavte tuto hodnotu na **5**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="c5eef-186">Toto nastavení definuje, kolik produktů chcete svým zákazníkům doporučit.</span><span class="sxs-lookup"><span data-stu-id="c5eef-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="c5eef-187">**Navrhovat produkty, které zákazníci nedávno zakoupili?**: Vyberte **Ano**, což znamená, že chcete do doporučení zahrnout produkty, které vaši zákazníci dříve zakoupili.</span><span class="sxs-lookup"><span data-stu-id="c5eef-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="c5eef-188">**Okno ohlédnutí:** Vyberte alespoň **365 dní**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="c5eef-189">Toto nastavení definuje, jak daleko do minulosti má model prozkoumat aktivitu zákazníka, aby ji použil jako zdroj pro doporučení.</span><span class="sxs-lookup"><span data-stu-id="c5eef-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Předvolby modelu pro model doporučení produktů.":::

1. <span data-ttu-id="c5eef-191">Vyberte **Požadovaná data** a vyberte **Přidat data** pro historii nákupů.</span><span class="sxs-lookup"><span data-stu-id="c5eef-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="c5eef-192">Přidejte entitu **eCommercePurchases : eCommerce** entita a mapujte pole z eCommerce na odpovídající pole požadovaná modelem.</span><span class="sxs-lookup"><span data-stu-id="c5eef-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="c5eef-193">Připojte se k entitě **eCommercePurchases: eCommerce** pomocí **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Připojení se k entitám eCommerce.](media/model-purchase-join.png)

1. <span data-ttu-id="c5eef-195">Vyberte **Další** pro nastavení plánu modelu.</span><span class="sxs-lookup"><span data-stu-id="c5eef-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="c5eef-196">Model musí pravidelně trénovat, aby se naučil nové vzory, když jsou přijímána nová data.</span><span class="sxs-lookup"><span data-stu-id="c5eef-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="c5eef-197">V tomto příkladu vyberte položku **Měsíčně**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="c5eef-198">Po kontrole všech podrobností vyberte **Uložit a spustit**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="c5eef-199">Úkol 4 – Kontrola výsledků modelu a vysvětlení</span><span class="sxs-lookup"><span data-stu-id="c5eef-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="c5eef-200">Nechte model dokončit cvičení a bodování dat.</span><span class="sxs-lookup"><span data-stu-id="c5eef-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="c5eef-201">Nyní si můžete prohlédnout vysvětlení modelu doporučení produktů.</span><span class="sxs-lookup"><span data-stu-id="c5eef-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="c5eef-202">Další informace viz [Kontrola stavu a výsledků predikce](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="c5eef-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="c5eef-203">Úkol 5 – Vytvoření segmentu často kupovaných produktů</span><span class="sxs-lookup"><span data-stu-id="c5eef-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="c5eef-204">Spuštěním produkčního modelu se vytvoří nová entita, ve které se můžete podívat **Data** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="c5eef-205">Můžete vytvořit nový segment na základě entity vytvořené modelem.</span><span class="sxs-lookup"><span data-stu-id="c5eef-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="c5eef-206">Jděte na **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-206">Go to **Segments**.</span></span> <span data-ttu-id="c5eef-207">Vyberte **Nový** a vyberte **Vytvořit z** > **Analytické nástroje**.</span><span class="sxs-lookup"><span data-stu-id="c5eef-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Vytvoření segmentu s výstupem modelu.](media/segment-intelligence.png)

1. <span data-ttu-id="c5eef-209">Vyberte koncový bod **ModelPredikceDoporuceniProduktuOOB** a definujte segment:</span><span class="sxs-lookup"><span data-stu-id="c5eef-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="c5eef-210">Pole: ProductID</span><span class="sxs-lookup"><span data-stu-id="c5eef-210">Field: ProductID</span></span>
   - <span data-ttu-id="c5eef-211">Operátor: Hodnota</span><span class="sxs-lookup"><span data-stu-id="c5eef-211">Operator: Value</span></span>
   - <span data-ttu-id="c5eef-212">Hodnota: Vyberte první tři ID produktů</span><span class="sxs-lookup"><span data-stu-id="c5eef-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Vytvoření segmentu z výsledků modelu.":::

<span data-ttu-id="c5eef-214">Nyní máte segment, který se dynamicky aktualizuje a který identifikuje zákazníky, kteří jsou ochotnější zakoupit tři nejdoporučovanější produkty.</span><span class="sxs-lookup"><span data-stu-id="c5eef-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="c5eef-215">Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c5eef-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]