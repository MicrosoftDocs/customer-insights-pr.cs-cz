---
title: Experimenty v Azure Machine Learning
description: Použití modelů založených na Azure Machine Learning v Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267898"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="0d8ab-103">Použití modelů založených na Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="0d8ab-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="0d8ab-104">Sjednocená data v Dynamics 365 Customer Insights jsou zdrojem pro vytváření modelů strojového učení, které mohou generovat další obchodní poznatky.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="0d8ab-105">Customer Insights se integruje s řešeními Machine Learning Studio (classic) a Azure Machine Learning, abyste mohli používat své vlastní modely.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="0d8ab-106">Viz [Experimenty v Machine Learning Studio (classic)](machine-learning-studio-experiments.md), kde najdete příklady experimentů postavených na Machine Learning Studio (classic).</span><span class="sxs-lookup"><span data-stu-id="0d8ab-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0d8ab-107">Požadavky</span><span class="sxs-lookup"><span data-stu-id="0d8ab-107">Prerequisites</span></span>

- <span data-ttu-id="0d8ab-108">Přístup k Customer Insights</span><span class="sxs-lookup"><span data-stu-id="0d8ab-108">Access to Customer Insights</span></span>
- <span data-ttu-id="0d8ab-109">Aktivní předplatné Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="0d8ab-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="0d8ab-110">Sjednocené profily zákazníka</span><span class="sxs-lookup"><span data-stu-id="0d8ab-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="0d8ab-111">[Export entit do úložiště Azure Blob](export-azure-blob-storage.md) nakonfigurován</span><span class="sxs-lookup"><span data-stu-id="0d8ab-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="0d8ab-112">Nastavení pracovního prostoru Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="0d8ab-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="0d8ab-113">V části zabývající se [vytvořením pracovního prostoru Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) najdete různé možnosti vytvoření pracovního prostoru.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="0d8ab-114">Pro nejlepší výkon vytvořte pracovní prostor v oblasti Azure, která je geograficky nejblíže vašemu prostředí Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="0d8ab-115">Ke svému pracovnímu prostoru přistupujte prostřednictvím [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="0d8ab-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="0d8ab-116">Existuje několik [způsobů interakce](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) s vaším pracovním prostorem.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="0d8ab-117">Práce s návrhářem Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="0d8ab-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="0d8ab-118">Návrhář Azure Machine Learning poskytuje vizuální plátno, kam můžete přetahovat datové sady a moduly, podobně jako Machine Learning Studio (klasické řešení).</span><span class="sxs-lookup"><span data-stu-id="0d8ab-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="0d8ab-119">Dávkový kanál vytvořený v návrháři lze integrovat do aplikace Customer Insights, pokud je odpovídajícím způsobem nakonfigurována.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="0d8ab-120">Práce s Azure Machine Learning SDK</span><span class="sxs-lookup"><span data-stu-id="0d8ab-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="0d8ab-121">Datoví vědci a vývojáři AI používají [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) k vytvoření pracovních postupů strojového učení.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="0d8ab-122">V současné době nelze modely vytrénované pomocí SDK integrovat přímo s Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="0d8ab-123">Pro integraci s Customer Insights je vyžadován dávkový odvozovací kanál, který tento model spotřebovává.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="0d8ab-124">Požadavky na dávkový kanál pro integraci s Customer Insights</span><span class="sxs-lookup"><span data-stu-id="0d8ab-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="0d8ab-125">Konfigurace datové sady</span><span class="sxs-lookup"><span data-stu-id="0d8ab-125">Dataset Configuration</span></span>

<span data-ttu-id="0d8ab-126">Musíte vytvořit datové sady pro použití dat entit z Customer Insights ve vašem dávkovém odvozovacím kanálu.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="0d8ab-127">Tyto datové sady je třeba zaregistrovat v pracovním prostoru.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="0d8ab-128">V současné době podporujeme pouze [tabulkové datové sady](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) ve formátu CSV.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="0d8ab-129">Datové sady, které odpovídají datům entity, je třeba parametrizovat jako parametr kanálu.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="0d8ab-130">Parametry datové sady v návrháři</span><span class="sxs-lookup"><span data-stu-id="0d8ab-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="0d8ab-131">V návrháři otevřete **Výběr sloupců v datové sadě** a vyberte **Nastavit jako parametr kanálu**, kde zadáte název parametru.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="0d8ab-132">![Parametrizace datové sady v návrháři](media/intelligence-designer-dataset-parameters.png "Parametrizace datové sady v návrháři")</span><span class="sxs-lookup"><span data-stu-id="0d8ab-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="0d8ab-133">Parametr datové sady v SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="0d8ab-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="0d8ab-134">Dávkový odvozovací kanál</span><span class="sxs-lookup"><span data-stu-id="0d8ab-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="0d8ab-135">V návrháři lze tréninkový kanál použít k vytvoření nebo aktualizaci odvozovacího kanálu.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="0d8ab-136">V současné době jsou podporovány pouze dávkové odvozovací kanály.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="0d8ab-137">Pomocí sady SDK můžete publikovat kanál v koncovém bodě.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="0d8ab-138">V současné době se Customer Insights integruje s výchozím kanálem v koncovém bodu dávkového kanálu v pracovním prostoru Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="0d8ab-139">Import dat kanálu do Customer Insights</span><span class="sxs-lookup"><span data-stu-id="0d8ab-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="0d8ab-140">Návrhář poskytuje [modul exportu dat](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data), který umožňuje export výstupu kanálu do úložiště Azure.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="0d8ab-141">V současné době musí modul používat typ úložiště dat **Azure Blob Storage** a parametrizovat **Úložiště dat** a relativní **Cestu**.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="0d8ab-142">Customer Insights přepíše oba tyto parametry během provádění kanálu datovým úložištěm a cestou, která je pro produkt přístupná.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0d8ab-143">![Konfigurace modulu exportu dat](media/intelligence-designer-importdata.png "Konfigurace modulu exportu dat")</span><span class="sxs-lookup"><span data-stu-id="0d8ab-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="0d8ab-144">Při psaní výstupu odvození pomocí kódu můžete výstup odeslat na cestu v rámci *registrovaného datového úložiště* v pracovním prostoru.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="0d8ab-145">Pokud jsou cesta a datové úložiště parametrizovány v kanálu, aplikace Customer Insights bude moci číst a importovat výstup odvození.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="0d8ab-146">V současné době je podporován jeden tabulkový výstup ve formátu CSV.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="0d8ab-147">Cesta musí zahrnovat adresář a název souboru.</span><span class="sxs-lookup"><span data-stu-id="0d8ab-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]