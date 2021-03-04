---
title: Doplnění částečných dat pomocí predikcí
description: Pomocí predikcí můžete vyplnit neúplná zákaznická data.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268264"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="000c3-103">Doplňte své dílčí údaje pomocí predikcí</span><span class="sxs-lookup"><span data-stu-id="000c3-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="000c3-104">Předpovědi vám umožňují snadno vytvářet předpovídané hodnoty, které mohou zlepšit vaše porozumění zákazníkovi.</span><span class="sxs-lookup"><span data-stu-id="000c3-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="000c3-105">Na stránce **Analytické nástroje** > **Predikce** můžete volbou **Moje predikce** zobrazit predikce, které jste nakonfigurovali v jiných částech přehledů cílové skupiny, a umožnit vám je dále přizpůsobovat.</span><span class="sxs-lookup"><span data-stu-id="000c3-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="000c3-106">Tuto funkci nemůžete použít, pokud vaše prostředí používá úložiště Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="000c3-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="000c3-107">Funkce predikcí používá automatizované prostředky k vyhodnocování údajů a vytváření predikcí na základě těchto údajů, a proto má schopnost být použita jako metoda profilování, protože tento pojem je definován obecným nařízením o ochraně údajů („GDPR“).</span><span class="sxs-lookup"><span data-stu-id="000c3-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="000c3-108">Použití této funkce zákazníkem ke zpracování dat může podléhat GDPR nebo jiným zákonům nebo předpisům.</span><span class="sxs-lookup"><span data-stu-id="000c3-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="000c3-109">Zodpovídáte za to, že použití Dynamics 365 Customer Insights, včetně predikcí, je v souladu se všemi příslušnými zákony a předpisy, včetně zákonů týkajících se soukromí, osobních údajů, biometrických údajů, ochrany údajů a důvěrnosti komunikace.</span><span class="sxs-lookup"><span data-stu-id="000c3-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="000c3-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="000c3-110">Prerequisites</span></span>

<span data-ttu-id="000c3-111">Než bude vaše organizace moci používat funkci předpovědí, musí být splněny následující předpoklady:</span><span class="sxs-lookup"><span data-stu-id="000c3-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="000c3-112">Vaše organizace má instanci [vytvořenou v Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) a je ve stejné organizaci jako Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="000c3-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="000c3-113">Vaše prostředí je připojeno k vaší instanci Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="000c3-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="000c3-114">Pokud [vytváříte první prostředí](manage-environments.md), nakonfigurujte jej v dialogu **Vytvořit prostředí** a vyberete **Rozšířený**.</span><span class="sxs-lookup"><span data-stu-id="000c3-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="000c3-115">Pokud jste již vytvořili prostředí, přejděte na jeho nastavení a vyberte možnost **Pokročilý**.</span><span class="sxs-lookup"><span data-stu-id="000c3-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="000c3-116">Ať tak či onak, v sekci **Použití predikcí** přejděte na adresu URL instance Common Data Service, ke které chcete připojit své prostředí.</span><span class="sxs-lookup"><span data-stu-id="000c3-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="000c3-117">Vytvoření predikce v entitě Zákazník</span><span class="sxs-lookup"><span data-stu-id="000c3-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="000c3-118">V přehledech cílové skupiny přejděte na **Data** > **Entity**.</span><span class="sxs-lookup"><span data-stu-id="000c3-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="000c3-119">Vyberte entitu **Zákazník**.</span><span class="sxs-lookup"><span data-stu-id="000c3-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="000c3-120">V entitě **Zákazník: CustomerInsights** vyberte entitu na kartě **Pole**.</span><span class="sxs-lookup"><span data-stu-id="000c3-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="000c3-121">Vyhledejte název atributu, pro který chcete predikovat hodnoty, a vyberte ikonu **Přehled** ve sloupci **Souhrn**.</span><span class="sxs-lookup"><span data-stu-id="000c3-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="000c3-122">![Přehledová ikona](media/intelligence-overviewicon.png "Přehledová ikona")</span><span class="sxs-lookup"><span data-stu-id="000c3-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="000c3-123">Pokud pro váš atribut existuje vysoká míra chybějících hodnot, vyberte **Předpovědět chybějící hodnoty** a pokračujte tak ve své predikci.</span><span class="sxs-lookup"><span data-stu-id="000c3-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="000c3-124">![Přehledový stav se zobrazeným tlačítkem predikce chybějících hodnot](media/intelligence-overviewpredictmissingvalues.png "Přehledový stav se zobrazeným tlačítkem predikce chybějících hodnot")</span><span class="sxs-lookup"><span data-stu-id="000c3-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="000c3-125">Poskytněte **Zobrazované jméno** a **Název výstupní entity** pro výsledky predikce.</span><span class="sxs-lookup"><span data-stu-id="000c3-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="000c3-126">Předvyplněný seznam možností ukáže, kde můžete namapovat hodnoty na předpovídanou kategorii.</span><span class="sxs-lookup"><span data-stu-id="000c3-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="000c3-127">V takovém případě budou vaše jediné možnosti kategorie 0 nebo 1, protože mapují na pravdivou / nepravdivou nebo binární povahu predikce.</span><span class="sxs-lookup"><span data-stu-id="000c3-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="000c3-128">Ve sloupci Kategorie namapujte hodnoty polí, které chcete mít klasifikovány jako „0“ v konečné predikci, na „0“ ve sloupci Kategorie, a položky, které chcete v konečné predikci klasifikovat jako „1“, na „1“.</span><span class="sxs-lookup"><span data-stu-id="000c3-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="000c3-129">![Příklad zobrazení mapovaných hodnot polí do kategorií](media/intelligence-categorymapping.png "Příklad zobrazení mapovaných hodnot polí do kategorií")</span><span class="sxs-lookup"><span data-stu-id="000c3-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="000c3-130">Vyberte **Hotovo** a předpověď bude zpracována.</span><span class="sxs-lookup"><span data-stu-id="000c3-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="000c3-131">Zpracování bude nějakou dobu trvat, v závislosti na velikosti a složitosti dat.</span><span class="sxs-lookup"><span data-stu-id="000c3-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="000c3-132">Výsledky buduo k dispozici v nové entitě na základě **Název výstupní entity** předpovědi, kterou jste vytvořili.</span><span class="sxs-lookup"><span data-stu-id="000c3-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="000c3-133">Vytvořte předpověď při vytváření segmentu</span><span class="sxs-lookup"><span data-stu-id="000c3-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="000c3-134">Při vytváření segmentu je také možné předpovídat chybějící hodnoty pro konkrétní atribut volby.</span><span class="sxs-lookup"><span data-stu-id="000c3-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="000c3-135">Konkrétně, když rychle vytvoříte segment na základě své sjednocené entity zákazníka nebo entity Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="000c3-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="000c3-136">V rámci tohoto toku si vyberete konkrétní atribut, který bude základem vašeho segmentu, jako je spokojenost zákazníka nebo částka nákupu.</span><span class="sxs-lookup"><span data-stu-id="000c3-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="000c3-137">Po vytvoření segmentu systém navrhne metodu předpovídání chybějících hodnot pro tento atribut.</span><span class="sxs-lookup"><span data-stu-id="000c3-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="000c3-138">V přehledech cílové skupiny přejděte na **Segmenty** a vyberte dlaždici **Profily**.</span><span class="sxs-lookup"><span data-stu-id="000c3-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="000c3-139">Vyberte **Pole**, chcete-li vytvořit segment a vyberte **Operátor**, poté vyberte **Recenze**.</span><span class="sxs-lookup"><span data-stu-id="000c3-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="000c3-140">Poskytněte **Název** a **Zobrazované jméno** pro segment.</span><span class="sxs-lookup"><span data-stu-id="000c3-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="000c3-141">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="000c3-141">Select **Save**.</span></span>

5. <span data-ttu-id="000c3-142">Pokud segment, který jste vytvořili, obsahuje neúplná data ve zdrojovém poli, můžete předpovědět chybějící hodnoty.</span><span class="sxs-lookup"><span data-stu-id="000c3-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="000c3-143">![Tlačítko predikce](media/segments-predictoption.png "Tlačítko predikce")</span><span class="sxs-lookup"><span data-stu-id="000c3-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="000c3-144">Poskytněte **Zobrazované jméno** a **Název výstupní entity** pro výsledky predikce.</span><span class="sxs-lookup"><span data-stu-id="000c3-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="000c3-145">Vyberte **Hotovo**.</span><span class="sxs-lookup"><span data-stu-id="000c3-145">Select **Done**.</span></span> <span data-ttu-id="000c3-146">Vaše předpověď bude brzy vygenerována a bude k dispozici v nové entitě s názvem, který jste zadali pro **Název výstupní entity**.</span><span class="sxs-lookup"><span data-stu-id="000c3-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="000c3-147">Zobrazit předpověď</span><span class="sxs-lookup"><span data-stu-id="000c3-147">View a prediction</span></span>

1. <span data-ttu-id="000c3-148">V přehledech cílové skupiny přejděte na **Analytické nástroje** > **Predikce** > **Moje predikce**.</span><span class="sxs-lookup"><span data-stu-id="000c3-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="000c3-149">Vyberte předpověď, kterou chcete zkontrolovat.</span><span class="sxs-lookup"><span data-stu-id="000c3-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="000c3-150">Vyberte elipsu ve sloupci **Akce** a zvolte **Zobrazit**.</span><span class="sxs-lookup"><span data-stu-id="000c3-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="000c3-151">Uvidíte několik datových bodů v zobrazení vaší predikce.</span><span class="sxs-lookup"><span data-stu-id="000c3-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="000c3-152">![Stránka predikce](media/intelligence-predictionsviewpage.png "Stránka predikce")</span><span class="sxs-lookup"><span data-stu-id="000c3-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="000c3-153">**Předvídané hodnoty** zobrazuje mapování, které jste vytvořili během fáze mapování Pole na Kategorie.</span><span class="sxs-lookup"><span data-stu-id="000c3-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="000c3-154">Zobrazí se hodnoty ve vašem datovém souboru, které byly mapovány do konkrétní kategorie.</span><span class="sxs-lookup"><span data-stu-id="000c3-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="000c3-155">-**Špičkové vlivy** jsou faktory v rámci vašeho datového souboru, které s největší pravděpodobností ovlivnily důvěru predikce, že vaše hodnota pole bude mapována na konkrétní kategorii.</span><span class="sxs-lookup"><span data-stu-id="000c3-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="000c3-156">**Výkon** označuje, jak se předpovědi dělají.</span><span class="sxs-lookup"><span data-stu-id="000c3-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="000c3-157">Další informace získáte kliknutím na odkaz.</span><span class="sxs-lookup"><span data-stu-id="000c3-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="000c3-158">**Náhled** ukazuje ukázky souboru výstupních dat z vaší predikce a pravděpodobnosti nebo naší důvěryhodnosti předpovídané hodnoty, kde 0 je nejistý a 1 je jistý.</span><span class="sxs-lookup"><span data-stu-id="000c3-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="000c3-159">Aktualizovat predikci</span><span class="sxs-lookup"><span data-stu-id="000c3-159">Update a prediction</span></span>

1. <span data-ttu-id="000c3-160">V přehledech cílové skupiny přejděte na **Analytické nástroje** > **Predikce** > **Moje predikce**.</span><span class="sxs-lookup"><span data-stu-id="000c3-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="000c3-161">Vyberte předpověď, kterou chcete aktualizovat, a vyberte ikonu **Aktualizovat**.</span><span class="sxs-lookup"><span data-stu-id="000c3-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="000c3-162">Predikce bude naplánována pro zpracování.</span><span class="sxs-lookup"><span data-stu-id="000c3-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="000c3-163">Můžete vidět čas, kdy byla naposledy aktualizována ve sloupci **Aktualizováno** na stránce **Předpovědi**.</span><span class="sxs-lookup"><span data-stu-id="000c3-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="000c3-164">Upravit předpověď</span><span class="sxs-lookup"><span data-stu-id="000c3-164">Edit a prediction</span></span>

<span data-ttu-id="000c3-165">Po vytvoření predikce můžete model v mátroji AI Builder přizpůsobit a zvýšit tak efektivitu svého modelu.</span><span class="sxs-lookup"><span data-stu-id="000c3-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="000c3-166">V přehledech cílové skupiny přejděte na **Analytické nástroje** > **Predikce** > **Moje predikce**.</span><span class="sxs-lookup"><span data-stu-id="000c3-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="000c3-167">Vyberte předpověď, kterou chcete upravit.</span><span class="sxs-lookup"><span data-stu-id="000c3-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="000c3-168">Vyberte elipsu ve sloupci **Akce** a zvolte **Zobrazit**.</span><span class="sxs-lookup"><span data-stu-id="000c3-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="000c3-169">Vyberte **Přizpůsobit v nástroji AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="000c3-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="000c3-170">Aktualizujte svůj model v nástroji AI Builder.</span><span class="sxs-lookup"><span data-stu-id="000c3-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="000c3-171">[Další informace o správě modelů v nástroji AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="000c3-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="000c3-172">Příští spuštění vaší predikce použije aktualizovaný model, který jste vytvořili.</span><span class="sxs-lookup"><span data-stu-id="000c3-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="000c3-173">Nové modely vytvořené v nástroji AI Builder se nezobrazí v přehledech cílové skupiny, pokud nebyly vytvořeny ve výše uvedených prostředích.</span><span class="sxs-lookup"><span data-stu-id="000c3-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="000c3-174">Odeberte předpověď</span><span class="sxs-lookup"><span data-stu-id="000c3-174">Remove a prediction</span></span>

1. <span data-ttu-id="000c3-175">V přehledech cílové skupiny přejděte na **Analytické nástroje** > **Predikce** > **Moje predikce**.</span><span class="sxs-lookup"><span data-stu-id="000c3-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="000c3-176">Vyberte předpověď, kterou chcete odstranit.</span><span class="sxs-lookup"><span data-stu-id="000c3-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="000c3-177">Vyberte elipsu ve sloupci **Akce** a zvolte **Odstranit**.</span><span class="sxs-lookup"><span data-stu-id="000c3-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="000c3-178">Potvrďte odstranění.</span><span class="sxs-lookup"><span data-stu-id="000c3-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="000c3-179">Řešení problémů</span><span class="sxs-lookup"><span data-stu-id="000c3-179">Troubleshooting</span></span>

<span data-ttu-id="000c3-180">Pokud nemůžete dokončit připojení procesu Common Data Service kvůli chybě, můžete zkusit proces dokončit ručně.</span><span class="sxs-lookup"><span data-stu-id="000c3-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="000c3-181">V procesu připojení se mohou vyskytnout dva známé problémy:</span><span class="sxs-lookup"><span data-stu-id="000c3-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="000c3-182">Řešení Doplněk karty zákazníka není nainstalováno.</span><span class="sxs-lookup"><span data-stu-id="000c3-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="000c3-183">Vyplňte pokyny k [instalaci a konfiguraci řešení](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="000c3-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="000c3-184">Oprávnění k aplikaci nejsou udělena.</span><span class="sxs-lookup"><span data-stu-id="000c3-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="000c3-185">Přejděte na [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="000c3-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="000c3-186">Vyberte **Prostředí**.</span><span class="sxs-lookup"><span data-stu-id="000c3-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="000c3-187">Vyberte tlačítko se třemi vedle prostředí, do kterého chcete přidat oprávnění, a vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="000c3-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="000c3-188">Rozbalte **Uživatelé + oprávnění** a vyberte **Uživatelé**.</span><span class="sxs-lookup"><span data-stu-id="000c3-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="000c3-189">Vyberte **+ Nový** a vyberte **Uživatel**.</span><span class="sxs-lookup"><span data-stu-id="000c3-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="000c3-190">Vyberte možnost **Uživatel aplikace**, pokud ještě není vybrána, a zadejte následující informace:</span><span class="sxs-lookup"><span data-stu-id="000c3-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="000c3-191">**Uživatelské jméno:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="000c3-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="000c3-192">**ID aplikace:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="000c3-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="000c3-193">**Jméno:** Customer</span><span class="sxs-lookup"><span data-stu-id="000c3-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="000c3-194">**Příjmení:** Insights</span><span class="sxs-lookup"><span data-stu-id="000c3-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="000c3-195">**Primární e-mail:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="000c3-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="000c3-196">Zvolte **Uložit a zavřít**.</span><span class="sxs-lookup"><span data-stu-id="000c3-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="000c3-197">Vyberte uživatele, kterého jste právě vytvořili.</span><span class="sxs-lookup"><span data-stu-id="000c3-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="000c3-198">Na horním panelu nabídek zvolte **Spravovat role**.</span><span class="sxs-lookup"><span data-stu-id="000c3-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="000c3-199">Vyberte **Správce systému**, poté vyberte **OK**.</span><span class="sxs-lookup"><span data-stu-id="000c3-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]