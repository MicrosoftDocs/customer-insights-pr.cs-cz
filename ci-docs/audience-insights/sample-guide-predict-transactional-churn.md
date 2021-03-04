---
title: Průvodce ukázkami predikce úbytku transakcí
description: Pomocí tohoto průvodce ukázkami můžete vyzkoušet dodávaný model predikce úbytku transakcí.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 81540ad2f490cf566f031233543b3cb6aa838033
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269782"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="66278-103">Průvodce ukázkami predikce úbytku transakcí (Preview)</span><span class="sxs-lookup"><span data-stu-id="66278-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="66278-104">Tento průvodce vás provede příkladem predikce úbytku transakcí od začátku dokonce v Customer Insights s využitím níže uvedených ukázkových dat.</span><span class="sxs-lookup"><span data-stu-id="66278-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="66278-105">Všechna data použitá v tomto průvodci nejsou skutečná zákaznická data a jsou součástí datové sady Contoso v prostředí *Ukázka* v rámci vašeho předplatného Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="66278-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="66278-106">Scénář</span><span class="sxs-lookup"><span data-stu-id="66278-106">Scenario</span></span>

<span data-ttu-id="66278-107">Contoso je společnost, která vyrábí vysoce kvalitní kávu a kávovary, které prodává prostřednictvím svých webových stránek Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="66278-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="66278-108">Jejím cílem je vědět, kteří zákazníci, kteří obvykle nakupují její produkty pravidelně, přestanou být aktivními zákazníky v příštích 60 dnech.</span><span class="sxs-lookup"><span data-stu-id="66278-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="66278-109">Informace, který z jejích zákazníků bude **pravděpodobně ztracen**, jí může pomoci ušetřit marketingové prostředky tím, že se soustředí na jeho udržení.</span><span class="sxs-lookup"><span data-stu-id="66278-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66278-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="66278-110">Prerequisites</span></span>

- <span data-ttu-id="66278-111">Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="66278-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="66278-112">Doporučujeme implementovat následující kroky [v novém prostředí](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="66278-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="66278-113">Úkol 1 – Ingestace dat</span><span class="sxs-lookup"><span data-stu-id="66278-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="66278-114">Projděte si články [o příjmu (ingestaci) dat](data-sources.md) a [importu zdrojů dat pomocí konektorů Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="66278-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="66278-115">Následující informace předpokládají, že jste se seznámili s ingestací dat obecně.</span><span class="sxs-lookup"><span data-stu-id="66278-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="66278-116">Ingestace zákaznických dat z platformy eCommerce</span><span class="sxs-lookup"><span data-stu-id="66278-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="66278-117">Vytvořte zdroj dat **eCommerce**, vyberte možnost importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="66278-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="66278-118">Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="66278-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="66278-119">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="66278-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="66278-120">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="66278-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="66278-121">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="66278-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="66278-122">**CreatedOn**: Datum/čas/pásmo</span><span class="sxs-lookup"><span data-stu-id="66278-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="66278-123">![Transformace pole DateOfBirth na Date](media/ecommerce-dob-date.PNG "Transformace data narození na datum")</span><span class="sxs-lookup"><span data-stu-id="66278-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="66278-124">V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="66278-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="66278-125">Uložte zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="66278-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="66278-126">Ingestace dat online nákupu</span><span class="sxs-lookup"><span data-stu-id="66278-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="66278-127">Přidejte další datovou sadu do stejného zdroje dat **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="66278-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="66278-128">Znovu vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="66278-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="66278-129">Zadejte adresu URL pro data **Online nákupy** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="66278-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="66278-130">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="66278-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="66278-131">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="66278-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="66278-132">**PurchasedOn**: Datum/čas</span><span class="sxs-lookup"><span data-stu-id="66278-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="66278-133">**TotalPrice**: Měna</span><span class="sxs-lookup"><span data-stu-id="66278-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="66278-134">V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="66278-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="66278-135">Uložte zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="66278-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="66278-136">Ingestace zákaznických dat z věrnostního schématu</span><span class="sxs-lookup"><span data-stu-id="66278-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="66278-137">Vytvořte zdroj dat **LoyaltyScheme**, vyberte možnost importu a vyberte konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="66278-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="66278-138">Zadejte adresu URL pro kontakty eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="66278-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="66278-139">Během úpravy dat vyberte **Transformovat** a pak **Použít první řádek jako záhlaví**.</span><span class="sxs-lookup"><span data-stu-id="66278-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="66278-140">Aktualizujte datový typ pro sloupce uvedené níže:</span><span class="sxs-lookup"><span data-stu-id="66278-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="66278-141">**DateOfBirth**: Datum</span><span class="sxs-lookup"><span data-stu-id="66278-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="66278-142">**RewardsPoints**: Celé číslo</span><span class="sxs-lookup"><span data-stu-id="66278-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="66278-143">**CreatedOn**: Datum/čas</span><span class="sxs-lookup"><span data-stu-id="66278-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="66278-144">V poli **Název** v pravém podokně přejmenujte svůj zdroj dat z **Query** na **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="66278-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="66278-145">Uložte zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="66278-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="66278-146">Úkol 2 – Sjednocení dat</span><span class="sxs-lookup"><span data-stu-id="66278-146">Task 2 - Data unification</span></span>

<span data-ttu-id="66278-147">Po ingestaci dat nyní začínáme s procesem **Mapování, párování, sloučení** pro vytvoření sjednoceného profilu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="66278-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="66278-148">Další informace naleznete v tématu [Sjednocení dat](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="66278-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="66278-149">Mapovat</span><span class="sxs-lookup"><span data-stu-id="66278-149">Map</span></span>

1. <span data-ttu-id="66278-150">Po ingestaci dat namapujte kontakty z eCommerce a věrnostní data na běžné datové typy.</span><span class="sxs-lookup"><span data-stu-id="66278-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="66278-151">Přejděte na **Data** > **Sjednocení** > **Mapování**.</span><span class="sxs-lookup"><span data-stu-id="66278-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="66278-152">Vyberte entity, které představují profil zákazníka – **eCommerceContacts** a **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="66278-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Sjednocení zdrojů dat eCommerce a věrnostních bodů.":::

1. <span data-ttu-id="66278-154">Vyberte **ContactId** jako primární klíč pro **eCommerceContatcs** a **LoyaltyID** jako primární klíč pro **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="66278-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Sjednocení LoyaltyId jako primární klíč.":::

### <a name="match"></a><span data-ttu-id="66278-156">Shoda barev</span><span class="sxs-lookup"><span data-stu-id="66278-156">Match</span></span>

1. <span data-ttu-id="66278-157">Přejděte na kartu **Párování** a vyberte **Nastavit pořadí**.</span><span class="sxs-lookup"><span data-stu-id="66278-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="66278-158">V rozevíracím seznamu **Primární** vyberte **eCommerceContacts: eCommerce** jako primární zdroj a zahrňte všechny záznamy.</span><span class="sxs-lookup"><span data-stu-id="66278-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="66278-159">V rozevíracím seznamu **Entita 2** vyberte **loyCustomers: LoyaltyScheme** a zahrňte všechny záznamy.</span><span class="sxs-lookup"><span data-stu-id="66278-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Sjednocení párování dat eCommerce a věrnostních bodů.":::

1. <span data-ttu-id="66278-161">Vyberte **Vytvořit nové pravidlo**</span><span class="sxs-lookup"><span data-stu-id="66278-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="66278-162">Přidejte svou první podmínku pomocí FullName.</span><span class="sxs-lookup"><span data-stu-id="66278-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="66278-163">Pro eCommerceContacts vyberte **FullName** v rozbalovací nabídce.</span><span class="sxs-lookup"><span data-stu-id="66278-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="66278-164">Pro loyCustomers vyberte **FullName** v rozbalovací nabídce.</span><span class="sxs-lookup"><span data-stu-id="66278-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="66278-165">Vyberte rozevírací seznam **Normalizovat** rozevírací seznam a vyberte **Typ (telefon, jméno, adresa, ...)**.</span><span class="sxs-lookup"><span data-stu-id="66278-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="66278-166">Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="66278-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="66278-167">Zadejte jméno **Celé jméno, e-mail** pro nové pravidlo.</span><span class="sxs-lookup"><span data-stu-id="66278-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="66278-168">Přidejte druhou podmínku pro e-mailovou adresu výběrem **Přidat podmínku**</span><span class="sxs-lookup"><span data-stu-id="66278-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="66278-169">Pro entitu eCommerceContacts zvolte **EMail** v rozevíracím seznamu.</span><span class="sxs-lookup"><span data-stu-id="66278-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="66278-170">Pro entitu loyCustomers zvolte **EMail** v rozevíracím seznamu.</span><span class="sxs-lookup"><span data-stu-id="66278-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="66278-171">Ponechejte pole Noramlizovat prázdné.</span><span class="sxs-lookup"><span data-stu-id="66278-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="66278-172">Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.</span><span class="sxs-lookup"><span data-stu-id="66278-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Sjednocení pravidla párování pro jméno a e-mail.":::

7. <span data-ttu-id="66278-174">Zvolte **Uložit** a **Spustit**.</span><span class="sxs-lookup"><span data-stu-id="66278-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="66278-175">Sloučení</span><span class="sxs-lookup"><span data-stu-id="66278-175">Merge</span></span>

1. <span data-ttu-id="66278-176">Přejděte na kartu **Sloučení**.</span><span class="sxs-lookup"><span data-stu-id="66278-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="66278-177">V **ContactId** pro entitu **loyCustomers** změňte zobrazované jméno na **ContactIdLOYALTY**, abyste jej odlišili od ingestovaných ID.</span><span class="sxs-lookup"><span data-stu-id="66278-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Přejmenování contactid z věrnostního ID.":::

1. <span data-ttu-id="66278-179">Volbami **Uložit** a **Spustit** zahájíte proces sloučení.</span><span class="sxs-lookup"><span data-stu-id="66278-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="66278-180">Úkol 3 – Konfigurace predikce úbytku transakcí</span><span class="sxs-lookup"><span data-stu-id="66278-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="66278-181">Se zavedenými sjednocenými profily zákazníků nyní můžeme spustit predikci úbytku předplatných.</span><span class="sxs-lookup"><span data-stu-id="66278-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="66278-182">Podrobné kroky najdete v části [Predikce úbytku předplatných (Preview)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="66278-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="66278-183">Přejděte na **Analytické nástroje** > **Prozkoumat** a vyberte **Model úbytku zákazníků**.</span><span class="sxs-lookup"><span data-stu-id="66278-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="66278-184">Vyberte možnost **Transakce** a pak **Začít**.</span><span class="sxs-lookup"><span data-stu-id="66278-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="66278-185">Pojmenujte model **Předdefinovaná predikce úbytku transakcí eCommerce** a výstupní entitu **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="66278-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="66278-186">Definujte dvě podmínky pro model úbytku:</span><span class="sxs-lookup"><span data-stu-id="66278-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="66278-187">**Interval predikce**: **alespoň 60** dnů.</span><span class="sxs-lookup"><span data-stu-id="66278-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="66278-188">Toto nastavení definuje, jak daleko do budoucna chceme předvídat úbytek zákazníků.</span><span class="sxs-lookup"><span data-stu-id="66278-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="66278-189">**Definice úbytku**: **alespoň 60** dnů.</span><span class="sxs-lookup"><span data-stu-id="66278-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="66278-190">Doba bez nákupu, po které je zákazník považován za ztraceného.</span><span class="sxs-lookup"><span data-stu-id="66278-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Výběr pák modelu Interval predikce a Definice úbytku.":::

1. <span data-ttu-id="66278-192">Vyberte **Historie nákupů (povinné)** a vyberte **Přidat data** pro historii nákupů.</span><span class="sxs-lookup"><span data-stu-id="66278-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="66278-193">Přidejte entitu **eCommercePurchases : eCommerce** entita a mapujte pole z eCommerce na odpovídající pole požadovaná modelem.</span><span class="sxs-lookup"><span data-stu-id="66278-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="66278-194">Připojte se k entitě **eCommercePurchases: eCommerce** pomocí **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="66278-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Připojení se k entitám eCommerce.":::

1. <span data-ttu-id="66278-196">Vyberte **Další** pro nastavení plánu modelu.</span><span class="sxs-lookup"><span data-stu-id="66278-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="66278-197">Model musí pravidelně trénovat, aby se naučil nové vzory, když jsou přijímána nová data.</span><span class="sxs-lookup"><span data-stu-id="66278-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="66278-198">V tomto příkladu vyberte položku **Měsíčně**.</span><span class="sxs-lookup"><span data-stu-id="66278-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="66278-199">Po kontrole všech podrobností vyberte **Uložit a spustit**.</span><span class="sxs-lookup"><span data-stu-id="66278-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="66278-200">Úkol 4 – Kontrola výsledků modelu a vysvětlení</span><span class="sxs-lookup"><span data-stu-id="66278-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="66278-201">Nechte model dokončit cvičení a bodování dat.</span><span class="sxs-lookup"><span data-stu-id="66278-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="66278-202">Nyní si můžete prohlédnout vysvětlení modelu úbytku předplatných.</span><span class="sxs-lookup"><span data-stu-id="66278-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="66278-203">Další informace viz [Kontrola stavu a výsledků predikce](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="66278-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="66278-204">Úkol 5 – Vytvoření segmentu zákazníků s vysokým rizikem ztráty</span><span class="sxs-lookup"><span data-stu-id="66278-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="66278-205">Spuštěním produkčního modelu se vytvoří nová entita, ve které se můžete podívat **Data** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="66278-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="66278-206">Můžete vytvořit nový segment na základě entity vytvořené modelem.</span><span class="sxs-lookup"><span data-stu-id="66278-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="66278-207">Jděte na **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="66278-207">Go to **Segments**.</span></span> <span data-ttu-id="66278-208">Vyberte **Nový** a vyberte **Vytvořit z** > **Analytické nástroje**.</span><span class="sxs-lookup"><span data-stu-id="66278-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Vytvoření segmentu s výstupem modelu.":::

1. <span data-ttu-id="66278-210">Vyberte koncový bod **OOBSubscriptionChurnPrediction** a definujte segment:</span><span class="sxs-lookup"><span data-stu-id="66278-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="66278-211">Pole: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="66278-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="66278-212">Operátor: větší než</span><span class="sxs-lookup"><span data-stu-id="66278-212">Operator: greater than</span></span>
   - <span data-ttu-id="66278-213">Hodnota: 0,6</span><span class="sxs-lookup"><span data-stu-id="66278-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nastavení segmentu úbytku předplatných.":::

<span data-ttu-id="66278-215">Nyní máte segment, který se dynamicky aktualizuje a který identifikuje zákazníky s vysokým rizikem odchodu pro toto podnikání s předplatným.</span><span class="sxs-lookup"><span data-stu-id="66278-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="66278-216">Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).</span><span class="sxs-lookup"><span data-stu-id="66278-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]