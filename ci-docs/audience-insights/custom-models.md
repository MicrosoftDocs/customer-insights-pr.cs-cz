---
title: Vlastní modely strojové učení | Microsoft Docs
description: Práce s vlastními modely z řešení Azure Machine Learning v aplikaci Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 87fb517e9f0b380f9721f77470dceb3bcb7e5616
ms.sourcegitcommit: 55c00ea61c78db7b3b54894c01afb3246dff31c8
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2021
ms.locfileid: "5700660"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="a0925-103">Vlastní modely strojového učení</span><span class="sxs-lookup"><span data-stu-id="a0925-103">Custom machine learning models</span></span>

<span data-ttu-id="a0925-104">**Analytické nástroje** > **Vlastní modely** umožňuje spravovat pracovní postupy založené na modelech strojového učení Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="a0925-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="a0925-105">Pracovní postupy vám pomohou vybrat data, ze kterých chcete generovat přehledy, a namapovat výsledky na vaše sjednocená data o zákaznících.</span><span class="sxs-lookup"><span data-stu-id="a0925-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="a0925-106">Další informace o vytváření vlastních modelů ML najdete v tématu [Použití modelů založených na Azure Machine Learning](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="a0925-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="a0925-107">Zodpovědná AI</span><span class="sxs-lookup"><span data-stu-id="a0925-107">Responsible AI</span></span>

<span data-ttu-id="a0925-108">Predikce umožňují vytvářet lepší zákaznické prostředí, zlepšovat obchodní schopnosti a zdroje příjmů.</span><span class="sxs-lookup"><span data-stu-id="a0925-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="a0925-109">Důrazně doporučujeme, abyste vyvážili hodnotu své predikce s dopadem, který má, a možnými opatřeními proti předpojatosti zavedenými z etických důvodů.</span><span class="sxs-lookup"><span data-stu-id="a0925-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="a0925-110">Další informace, jak společnost Microsoft [přistupuje k zodpovědné AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="a0925-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="a0925-111">Můžete se také dozvědět o [technikách a procesech pro zodpovědné strojové učení](/azure/machine-learning/concept-responsible-ml) specifické pro Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="a0925-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a0925-112">Požadavky</span><span class="sxs-lookup"><span data-stu-id="a0925-112">Prerequisites</span></span>

- <span data-ttu-id="a0925-113">V současné době tato funkce podporuje webové služby publikované prostřednictvím [Machine Learning Studio (classic)](https://studio.azureml.net) a [dávkových kanálů Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="a0925-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="a0925-114">Abyste mohli používat tuto funkci, potřebujete účet úložiště Azure Data Lake Gen2 přidružený k vaší instanci Azure Studio.</span><span class="sxs-lookup"><span data-stu-id="a0925-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="a0925-115">Další informace viz [Vytvoření účtu úložiště Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="a0925-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="a0925-116">Pro pracovní prostory Azure Machine Learning s kanály potřebujete oprávnění vlastníka nebo správce přístupu uživatelů k pracovnímu prostoru Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="a0925-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a0925-117">Data se přenášejí mezi vašimi instancemi Customer Insights a vybranými webovými službami nebo kanály Azure v pracovním postupu.</span><span class="sxs-lookup"><span data-stu-id="a0925-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="a0925-118">Když přenášíte data do služby Azure, ujistěte se, že je služba nakonfigurovaná tak, aby zpracovávala data způsobem a umístěním nezbytným pro splnění jakýchkoli právních nebo regulačních požadavků na tato data pro vaši organizaci.</span><span class="sxs-lookup"><span data-stu-id="a0925-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="a0925-119">Přidání nového pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="a0925-119">Add a new workflow</span></span>

1. <span data-ttu-id="a0925-120">Přejděte na **Analytické nástroje** > **Vlastní modely** a vyberte **Nový pracovní postup**.</span><span class="sxs-lookup"><span data-stu-id="a0925-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="a0925-121">Zadejte rozpoznatelný název vlastního modelu do pole **Název**.</span><span class="sxs-lookup"><span data-stu-id="a0925-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a0925-122">![Snímek obrazovky podokna Nový pracovní postup](media/new-workflowv2.png "Snímek obrazovky podokna Nový pracovní postup")</span><span class="sxs-lookup"><span data-stu-id="a0925-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="a0925-123">Vyberte organizaci, která obsahuje webovou službu, v části **Klient, který obsahuje vaši webovou službu**.</span><span class="sxs-lookup"><span data-stu-id="a0925-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="a0925-124">Pokud je vaše předplatné Azure Machine Learning v jiném klientovi než Customer Insights, vyberte **Přihlásit** pomocí přihlašovacích údajů pro vybranou organizaci.</span><span class="sxs-lookup"><span data-stu-id="a0925-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="a0925-125">Vyberte **Pracovní prostory** přidružené k vaší webové službě.</span><span class="sxs-lookup"><span data-stu-id="a0925-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="a0925-126">Jsou zde uvedeny dvě sekce, jedna pro Azure Machine Learning v1 (Machine Learning Studio (classic)) a Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="a0925-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="a0925-127">Pokud si nejste jisti, který pracovní prostor je ten pravý pro vaši webovou službu Machine Learning Studio (classic), vyberte **Žádný**.</span><span class="sxs-lookup"><span data-stu-id="a0925-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="a0925-128">Zvolte webovou službu Machine Learning Studio (classic) nebo kanál Azure Machine Learning v rozevíracím seznamu **Webová služba obsahující váš model**.</span><span class="sxs-lookup"><span data-stu-id="a0925-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="a0925-129">Pak vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="a0925-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="a0925-130">Další informace o [publikování webové služby v Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="a0925-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="a0925-131">Další informace o [publikování kanálu v Azure Machine Learning pomocí návrháře](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) nebo [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="a0925-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="a0925-132">Váš kanál musí být publikován pod [koncovým bodem kanálu](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="a0925-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="a0925-133">Pro každou položku **Vstup webové služby** vyberte odpovídající **entitu** z přehledů cílové skupiny a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="a0925-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="a0925-134">Pracovní postup vlastního modelu použije heuristiku k mapování vstupních polí webové služby na atributy entity na základě názvu a datového typu pole.</span><span class="sxs-lookup"><span data-stu-id="a0925-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="a0925-135">Pokud pole webové služby nelze mapovat na entitu, zobrazí se chyba.</span><span class="sxs-lookup"><span data-stu-id="a0925-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a0925-136">![Konfigurace pracovního postupu](media/intelligence-screen2-updated.png "Konfigurace pracovního postupu")</span><span class="sxs-lookup"><span data-stu-id="a0925-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="a0925-137">V kroku **Výstupní parametry modelu** nastavte následující vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="a0925-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="a0925-138">Machine Learning Studio (classic)</span><span class="sxs-lookup"><span data-stu-id="a0925-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="a0925-139">Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky webové služby.</span><span class="sxs-lookup"><span data-stu-id="a0925-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="a0925-140">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="a0925-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="a0925-141">Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky kanálu.</span><span class="sxs-lookup"><span data-stu-id="a0925-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="a0925-142">Vyberte **Název parametru úložiště výstupních dat** vašeho dávkového kanálu z rozbalovací nabídky.</span><span class="sxs-lookup"><span data-stu-id="a0925-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="a0925-143">Vyberte **Název parametru výstupní cesty** vašeho dávkového kanálu z rozbalovací nabídky.</span><span class="sxs-lookup"><span data-stu-id="a0925-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="a0925-144">![Podokno výstupních parametrů modelu](media/intelligence-screen3-outputparameters.png "Podokno výstupních parametrů modelu")</span><span class="sxs-lookup"><span data-stu-id="a0925-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="a0925-145">Vyberte odpovídající atribut z rozevíracího seznamu **ID zákazníka ve výsledcích**, který identifikuje zákazníky, a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="a0925-145">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a0925-146">![Propojení výsledků v podokně údajů o zákaznících](media/intelligence-screen4-relatetocustomer.png "Propojení výsledků v podokně údajů o zákaznících")</span><span class="sxs-lookup"><span data-stu-id="a0925-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="a0925-147">Zobrazí se obrazovka **Pracovní postup uložen** s podrobnostmi o pracovním postupu.</span><span class="sxs-lookup"><span data-stu-id="a0925-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="a0925-148">Pokud jste nakonfigurovali pracovní postup pro kanál Azure Machine Learning, přehledy cílové skupiny se připojí k pracovnímu prostoru, který obsahuje kanál.</span><span class="sxs-lookup"><span data-stu-id="a0925-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="a0925-149">Přehledy cílové skupiny získají roli **Přispěvatel** v pracovním prostoru Azure.</span><span class="sxs-lookup"><span data-stu-id="a0925-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="a0925-150">Vyberte **Hotovo**.</span><span class="sxs-lookup"><span data-stu-id="a0925-150">Select **Done**.</span></span>

1. <span data-ttu-id="a0925-151">Nyní můžete spustit pracovní postup ze stránky **Vlastní modely**.</span><span class="sxs-lookup"><span data-stu-id="a0925-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="a0925-152">Úprava pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="a0925-152">Edit a workflow</span></span>

1. <span data-ttu-id="a0925-153">Na stránce **Vlastní modely** vyberte vertikální elipsu ve sloupci **Akce** vedle dříve vytvořeného pracovního postupu a vyberte **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="a0925-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="a0925-154">Rozpoznatelný název pracovního postupu můžete změnit v poli **Zobrazovaný název**, ale nemůžete změnit nakonfigurovanou webovou službu nebo kanál.</span><span class="sxs-lookup"><span data-stu-id="a0925-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="a0925-155">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="a0925-155">Select **Next**.</span></span>

1. <span data-ttu-id="a0925-156">Pro každou položku **Vstup webové služby** můžete změnit odpovídající **entitu** z přehledů cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="a0925-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="a0925-157">Pak vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="a0925-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="a0925-158">V kroku **Výstupní parametry modelu** nastavte následující vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="a0925-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="a0925-159">Machine Learning Studio (classic)</span><span class="sxs-lookup"><span data-stu-id="a0925-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="a0925-160">Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky webové služby.</span><span class="sxs-lookup"><span data-stu-id="a0925-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="a0925-161">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="a0925-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="a0925-162">Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky kanálu.</span><span class="sxs-lookup"><span data-stu-id="a0925-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="a0925-163">Vyberte **Název parametru úložiště výstupních dat** pro váš testovací kanál.</span><span class="sxs-lookup"><span data-stu-id="a0925-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="a0925-164">Vyberte **Název parametru výstupní cesty** pro váš testovací kanál.</span><span class="sxs-lookup"><span data-stu-id="a0925-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="a0925-165">Vyberte odpovídající atribut z rozevíracího seznamu **ID zákazníka ve výsledcích**, který identifikuje zákazníky, a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="a0925-165">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="a0925-166">Vyberte atribut z výstupu odvození s hodnotami podobnými sloupci ID zákazníka entity Zákazník.</span><span class="sxs-lookup"><span data-stu-id="a0925-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="a0925-167">Pokud takový sloupec chybí v datové sadě, vyberte atribut, který jednoznačně identifikuje řádek.</span><span class="sxs-lookup"><span data-stu-id="a0925-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="a0925-168">Spuštění pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="a0925-168">Run a workflow</span></span>

1. <span data-ttu-id="a0925-169">Na stránce **Vlastní modely** vyberte vertikální elipsu ve sloupci **Akce** vedle dříve vytvořeného pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="a0925-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="a0925-170">Vyberte **Spustit**.</span><span class="sxs-lookup"><span data-stu-id="a0925-170">Select **Run**.</span></span>

<span data-ttu-id="a0925-171">Váš pracovní postup se také spustí automaticky s každou plánovanou aktualizací.</span><span class="sxs-lookup"><span data-stu-id="a0925-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="a0925-172">Další informace o [nastavení plánovaných aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a0925-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="a0925-173">Odstranění pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="a0925-173">Delete a workflow</span></span>

1. <span data-ttu-id="a0925-174">Na stránce **Vlastní modely** vyberte vertikální elipsu ve sloupci **Akce** vedle dříve vytvořeného pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="a0925-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="a0925-175">Vyberte **Odstranit** a potvrďte požadavek na odstranění.</span><span class="sxs-lookup"><span data-stu-id="a0925-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="a0925-176">Váš pracovní postup bude odstraněn.</span><span class="sxs-lookup"><span data-stu-id="a0925-176">Your workflow will be deleted.</span></span> <span data-ttu-id="a0925-177">[Entita](entities.md), která byla vytvořena, když jste vytvořili pracovní postup, přetrvává, a lze ji zobrazit na stránce **Entity**.</span><span class="sxs-lookup"><span data-stu-id="a0925-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="a0925-178">Výsledky</span><span class="sxs-lookup"><span data-stu-id="a0925-178">Results</span></span>

<span data-ttu-id="a0925-179">Výsledky z pracovního postupu jsou uloženy v entitě nakonfigurované během fáze Výstupní parametry modelu.</span><span class="sxs-lookup"><span data-stu-id="a0925-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="a0925-180">K těmto datům máte přístup ze [stránky entit](entities.md) nebo [přes API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="a0925-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="a0925-181">Přístup přes API</span><span class="sxs-lookup"><span data-stu-id="a0925-181">API Access</span></span>

<span data-ttu-id="a0925-182">Aby dotaz OData získal data z entity vlastního modelu, použijte následující formát:</span><span class="sxs-lookup"><span data-stu-id="a0925-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="a0925-183">Místo `<your instance id>` zadejte ID prostředí Customer Insights, které najdete v adresním řádku svého prohlížeče při přístupu k Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a0925-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="a0925-184">Místo `<custom model output entity>` zadejte název entity, který jste zadali během kroku Výstupní parametry modelu při konfiguraci vlastního modelu.</span><span class="sxs-lookup"><span data-stu-id="a0925-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="a0925-185">Místo `<guid value>` zadejte ID zákazníka, pro kterého chcete získat přístup k záznamu.</span><span class="sxs-lookup"><span data-stu-id="a0925-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="a0925-186">Toto ID obvykle najdete na [stránce s profily zákazníků](customer-profiles.md) v poli CustomerID.</span><span class="sxs-lookup"><span data-stu-id="a0925-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a0925-187">Nejčastější dotazy</span><span class="sxs-lookup"><span data-stu-id="a0925-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="a0925-188">Proč nevidím svůj kanál při nastavování pracovního postupu vlastního modelu?</span><span class="sxs-lookup"><span data-stu-id="a0925-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="a0925-189">Tento problém je často způsoben problémem s konfigurací v kanálu.</span><span class="sxs-lookup"><span data-stu-id="a0925-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="a0925-190">Musí být [nakonfigurován vstupní parametr](azure-machine-learning-experiments.md#dataset-configuration) a [ výstupní datové úložiště a parametry cesty](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).</span><span class="sxs-lookup"><span data-stu-id="a0925-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="a0925-191">Co znamená chyba „Nepodařilo se uložit pracovní postup analytických nástrojů“?</span><span class="sxs-lookup"><span data-stu-id="a0925-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="a0925-192">Tato chybová zpráva se uživatelům obvykle zobrazí, pokud v pracovním prostoru nemají oprávnění vlastníka nebo správce přístupu uživatelů.</span><span class="sxs-lookup"><span data-stu-id="a0925-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="a0925-193">Uživatel potřebuje vyšší úroveň oprávnění, aby umožnil Customer Insights zpracovat pracovní postup jako službu, místo aby používal přihlašovací údaje uživatele pro další spuštění pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="a0925-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
