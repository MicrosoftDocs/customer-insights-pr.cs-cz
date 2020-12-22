---
title: Vlastní modely strojové učení | Microsoft Docs
description: Práce s vlastními modely z řešení Azure Machine Learning v aplikaci Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668895"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="bb949-103">Vlastní modely strojového učení</span><span class="sxs-lookup"><span data-stu-id="bb949-103">Custom machine learning models</span></span>

<span data-ttu-id="bb949-104">**Analytické nástroje** > **Vlastní modely** umožňuje spravovat pracovní postupy založené na modelech strojového učení Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="bb949-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="bb949-105">Pracovní postupy vám pomohou vybrat data, ze kterých chcete generovat přehledy, a namapovat výsledky na vaše sjednocená data o zákaznících.</span><span class="sxs-lookup"><span data-stu-id="bb949-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="bb949-106">Další informace o vytváření vlastních modelů ML najdete v tématu [Použití modelů založených na Azure Machine Learning](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="bb949-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="bb949-107">Zodpovědná AI</span><span class="sxs-lookup"><span data-stu-id="bb949-107">Responsible AI</span></span>

<span data-ttu-id="bb949-108">Predikce umožňují vytvářet lepší zákaznické prostředí, zlepšovat obchodní schopnosti a zdroje příjmů.</span><span class="sxs-lookup"><span data-stu-id="bb949-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="bb949-109">Důrazně doporučujeme, abyste vyvážili hodnotu své predikce s dopadem, který má, a možnými opatřeními proti předpojatosti zavedenými z etických důvodů.</span><span class="sxs-lookup"><span data-stu-id="bb949-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="bb949-110">Další informace, jak společnost Microsoft [přistupuje k zodpovědné AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="bb949-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="bb949-111">Můžete se také dozvědět o [technikách a procesech pro zodpovědné strojové učení](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specifické pro Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="bb949-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb949-112">Požadavky</span><span class="sxs-lookup"><span data-stu-id="bb949-112">Prerequisites</span></span>

- <span data-ttu-id="bb949-113">V současné době tato funkce podporuje webové služby publikované prostřednictvím [Machine Learning Studio (classic)](https://studio.azureml.net) a [dávkových kanálů Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="bb949-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="bb949-114">Abyste mohli používat tuto funkci, potřebujete účet úložiště Azure Data Lake Gen2 přidružený k vaší instanci Azure Studio.</span><span class="sxs-lookup"><span data-stu-id="bb949-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="bb949-115">Další informace viz [Vytvoření účtu úložiště Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="bb949-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="bb949-116">Přidání nového pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="bb949-116">Add a new workflow</span></span>

1. <span data-ttu-id="bb949-117">Přejděte na **Analytické nástroje** > **Vlastní modely** a vyberte **Nový pracovní postup**.</span><span class="sxs-lookup"><span data-stu-id="bb949-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="bb949-118">Zadejte rozpoznatelný název vlastního modelu do pole **Název**.</span><span class="sxs-lookup"><span data-stu-id="bb949-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bb949-119">![Snímek obrazovky podokna Nový pracovní postup](media/new-workflowv2.png "Snímek obrazovky podokna Nový pracovní postup")</span><span class="sxs-lookup"><span data-stu-id="bb949-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="bb949-120">Vyberte organizaci, která obsahuje webovou službu, v části **Klient, který obsahuje vaši webovou službu**.</span><span class="sxs-lookup"><span data-stu-id="bb949-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="bb949-121">Pokud je vaše předplatné Azure Machine Learning v jiném klientovi než Customer Insights, vyberte **Přihlásit** pomocí přihlašovacích údajů pro vybranou organizaci.</span><span class="sxs-lookup"><span data-stu-id="bb949-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="bb949-122">Vyberte **Pracovní prostory** přidružené k vaší webové službě.</span><span class="sxs-lookup"><span data-stu-id="bb949-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="bb949-123">Jsou zde uvedeny dvě sekce, jedna pro Azure Machine Learning v1 (Machine Learning Studio (classic)) a Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="bb949-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="bb949-124">Pokud si nejste jisti, který pracovní prostor je ten pravý pro vaši webovou službu Machine Learning Studio (classic), vyberte **Žádný**.</span><span class="sxs-lookup"><span data-stu-id="bb949-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="bb949-125">Zvolte webovou službu Machine Learning Studio (classic) nebo kanál Azure Machine Learning v rozevíracím seznamu **Webová služba obsahující váš model**.</span><span class="sxs-lookup"><span data-stu-id="bb949-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="bb949-126">Pak vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="bb949-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="bb949-127">Další informace o [publikování webové služby v Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="bb949-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="bb949-128">Další informace o [publikování kanálu v Azure Machine Learning pomocí návrháře](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) nebo [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="bb949-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="bb949-129">Váš kanál musí být publikován pod [koncovým bodem kanálu](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="bb949-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="bb949-130">Pro každou položku **Vstup webové služby** vyberte odpovídající **entitu** z přehledů cílové skupiny a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="bb949-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bb949-131">![Konfigurace pracovního postupu](media/intelligence-screen2-updated.png "Konfigurace pracovního postupu")</span><span class="sxs-lookup"><span data-stu-id="bb949-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="bb949-132">V kroku **Výstupní parametry modelu** nastavte následující vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="bb949-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="bb949-133">Machine Learning Studio (classic)</span><span class="sxs-lookup"><span data-stu-id="bb949-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="bb949-134">Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky webové služby.</span><span class="sxs-lookup"><span data-stu-id="bb949-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="bb949-135">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="bb949-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="bb949-136">Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky kanálu.</span><span class="sxs-lookup"><span data-stu-id="bb949-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="bb949-137">Vyberte **Název parametru úložiště výstupních dat** vašeho dávkového kanálu z rozbalovací nabídky.</span><span class="sxs-lookup"><span data-stu-id="bb949-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="bb949-138">Vyberte **Název parametru výstupní cesty** vašeho dávkového kanálu z rozbalovací nabídky.</span><span class="sxs-lookup"><span data-stu-id="bb949-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="bb949-139">![Podokno výstupních parametrů modelu](media/intelligence-screen3-outputparameters.png "Podokno výstupních parametrů modelu")</span><span class="sxs-lookup"><span data-stu-id="bb949-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="bb949-140">Vyberte odpovídající atribut z rozevíracího seznamu **ID zákazníka ve výsledcích**, který identifikuje zákazníky, a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="bb949-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bb949-141">![Propojení výsledků v podokně údajů o zákaznících](media/intelligence-screen4-relatetocustomer.png "Propojení výsledků v podokně údajů o zákaznících")</span><span class="sxs-lookup"><span data-stu-id="bb949-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="bb949-142">Zobrazí se obrazovka **Pracovní postup uložen** s podrobnostmi o pracovním postupu.</span><span class="sxs-lookup"><span data-stu-id="bb949-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="bb949-143">Pokud jste nakonfigurovali pracovní postup pro kanál Azure Machine Learning, přehledy cílové skupiny se připojí k pracovnímu prostoru, který obsahuje kanál.</span><span class="sxs-lookup"><span data-stu-id="bb949-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="bb949-144">Přehledy cílové skupiny získají roli **Přispěvatel** v pracovním prostoru Azure.</span><span class="sxs-lookup"><span data-stu-id="bb949-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="bb949-145">Vyberte **Hotovo**.</span><span class="sxs-lookup"><span data-stu-id="bb949-145">Select **Done**.</span></span>

1. <span data-ttu-id="bb949-146">Nyní můžete spustit pracovní postup ze stránky **Vlastní modely**.</span><span class="sxs-lookup"><span data-stu-id="bb949-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="bb949-147">Úprava pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="bb949-147">Edit a workflow</span></span>

1. <span data-ttu-id="bb949-148">Na stránce **Vlastní modely** vyberte vertikální elipsu ve sloupci **Akce** vedle dříve vytvořeného pracovního postupu a vyberte **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="bb949-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="bb949-149">Rozpoznatelný název pracovního postupu můžete změnit v poli **Zobrazovaný název**, ale nemůžete změnit nakonfigurovanou webovou službu nebo kanál.</span><span class="sxs-lookup"><span data-stu-id="bb949-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="bb949-150">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="bb949-150">Select **Next**.</span></span>

1. <span data-ttu-id="bb949-151">Pro každou položku **Vstup webové služby** můžete změnit odpovídající **entitu** z přehledů cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="bb949-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="bb949-152">Pak vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="bb949-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="bb949-153">V kroku **Výstupní parametry modelu** nastavte následující vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="bb949-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="bb949-154">Machine Learning Studio (classic)</span><span class="sxs-lookup"><span data-stu-id="bb949-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="bb949-155">Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky webové služby.</span><span class="sxs-lookup"><span data-stu-id="bb949-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="bb949-156">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="bb949-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="bb949-157">Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky kanálu.</span><span class="sxs-lookup"><span data-stu-id="bb949-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="bb949-158">Vyberte **Název parametru úložiště výstupních dat** pro váš testovací kanál.</span><span class="sxs-lookup"><span data-stu-id="bb949-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="bb949-159">Vyberte **Název parametru výstupní cesty** pro váš testovací kanál.</span><span class="sxs-lookup"><span data-stu-id="bb949-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="bb949-160">Vyberte odpovídající atribut z rozevíracího seznamu **ID zákazníka ve výsledcích**, který identifikuje zákazníky, a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="bb949-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="bb949-161">Musíte vybrat atribut z výstupu odvození s hodnotami podobnými sloupci ID zákazníka entity Zákazník.</span><span class="sxs-lookup"><span data-stu-id="bb949-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="bb949-162">Pokud takový sloupec chybí v datové sadě, vyberte atribut, který jednoznačně identifikuje řádek.</span><span class="sxs-lookup"><span data-stu-id="bb949-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="bb949-163">Spuštění pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="bb949-163">Run a workflow</span></span>

1. <span data-ttu-id="bb949-164">Na stránce **Vlastní modely** vyberte vertikální elipsu ve sloupci **Akce** vedle dříve vytvořeného pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="bb949-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="bb949-165">Vyberte **Spustit**.</span><span class="sxs-lookup"><span data-stu-id="bb949-165">Select **Run**.</span></span>

<span data-ttu-id="bb949-166">Váš pracovní postup se také spustí automaticky s každou plánovanou aktualizací.</span><span class="sxs-lookup"><span data-stu-id="bb949-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="bb949-167">Další informace o [nastavení plánovaných aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bb949-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="bb949-168">Odstranění pracovního postupu</span><span class="sxs-lookup"><span data-stu-id="bb949-168">Delete a workflow</span></span>

1. <span data-ttu-id="bb949-169">Na stránce **Vlastní modely** vyberte vertikální elipsu ve sloupci **Akce** vedle dříve vytvořeného pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="bb949-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="bb949-170">Vyberte **Odstranit** a potvrďte požadavek na odstranění.</span><span class="sxs-lookup"><span data-stu-id="bb949-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="bb949-171">Váš pracovní postup bude odstraněn.</span><span class="sxs-lookup"><span data-stu-id="bb949-171">Your workflow will be deleted.</span></span> <span data-ttu-id="bb949-172">[Entita](entities.md), která byla vytvořena, když jste vytvořili pracovní postup, přetrvává, a lze ji zobrazit na stránce **Entity**.</span><span class="sxs-lookup"><span data-stu-id="bb949-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
