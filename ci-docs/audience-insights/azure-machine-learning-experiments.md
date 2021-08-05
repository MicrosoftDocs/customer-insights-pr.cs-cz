---
title: Experimenty v Azure Machine Learning
description: Použití modelů založených na Azure Machine Learning v Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3f97e22687ae4f5536d492bac83bdf9c711e2c94
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554427"
---
# <a name="use-azure-machine-learning-based-models"></a>Použití modelů založených na Azure Machine Learning

Sjednocená data v Dynamics 365 Customer Insights jsou zdrojem pro vytváření modelů strojového učení, které mohou generovat další obchodní poznatky. Customer Insights se integruje s řešeními Machine Learning Studio (classic) a Azure Machine Learning, abyste mohli používat své vlastní modely. Viz [Experimenty v Machine Learning Studio (classic)](machine-learning-studio-experiments.md), kde najdete příklady experimentů postavených na Machine Learning Studio (classic). 

## <a name="prerequisites"></a>Požadavky

- Přístup k Customer Insights
- Aktivní předplatné Azure Enterprise
- [Sjednocené profily zákazníka](data-unification.md)
- [Export entit do úložiště Azure Blob](export-azure-blob-storage.md) nakonfigurován

## <a name="set-up-azure-machine-learning-workspace"></a>Nastavení pracovního prostoru Azure Machine Learning

1. V části zabývající se [vytvořením pracovního prostoru Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) najdete různé možnosti vytvoření pracovního prostoru. Pro nejlepší výkon vytvořte pracovní prostor v oblasti Azure, která je geograficky nejblíže vašemu prostředí Customer Insights.

1. Ke svému pracovnímu prostoru přistupujte prostřednictvím [Azure Machine Learning Studio](https://ml.azure.com/). Existuje několik [způsobů interakce](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) s vaším pracovním prostorem.

## <a name="work-with-azure-machine-learning-designer"></a>Práce s návrhářem Azure Machine Learning

Návrhář Azure Machine Learning poskytuje vizuální plátno, kam můžete přetahovat datové sady a moduly, podobně jako Machine Learning Studio (klasické řešení). Dávkový kanál vytvořený v návrháři lze integrovat do aplikace Customer Insights, pokud je odpovídajícím způsobem nakonfigurována. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Práce s Azure Machine Learning SDK

Datoví vědci a vývojáři AI používají [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) k vytvoření pracovních postupů strojového učení. V současné době nelze modely vytrénované pomocí SDK integrovat přímo s Customer Insights. Pro integraci s Customer Insights je vyžadován dávkový odvozovací kanál, který tento model spotřebovává.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Požadavky na dávkový kanál pro integraci s Customer Insights

### <a name="dataset-configuration"></a>Konfigurace datové sady

Musíte vytvořit datové sady pro použití dat entit z Customer Insights ve vašem dávkovém odvozovacím kanálu. Tyto datové sady je třeba zaregistrovat v pracovním prostoru. V současné době podporujeme pouze [tabulkové datové sady](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) ve formátu CSV. Datové sady, které odpovídají datům entity, je třeba parametrizovat jako parametr kanálu.
   
* Parametry datové sady v návrháři
   
     V návrháři otevřete **Výběr sloupců v datové sadě** a vyberte **Nastavit jako parametr kanálu**, kde zadáte název parametru.

     > [!div class="mx-imgBorder"]
     > ![Parametrizace datové sady v návrháři.](media/intelligence-designer-dataset-parameters.png "Parametrizace datové sady v návrháři")
   
* Parametr datové sady v SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Dávkový odvozovací kanál
  
* V návrháři lze tréninkový kanál použít k vytvoření nebo aktualizaci odvozovacího kanálu. V současné době jsou podporovány pouze dávkové odvozovací kanály.

* Pomocí sady SDK můžete publikovat kanál v koncovém bodě. V současné době se Customer Insights integruje s výchozím kanálem v koncovém bodu dávkového kanálu v pracovním prostoru Azure Machine Learning.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Import dat kanálu do Customer Insights

* Návrhář poskytuje [modul exportu dat](/azure/machine-learning/algorithm-module-reference/export-data), který umožňuje export výstupu kanálu do úložiště Azure. V současné době musí modul používat typ úložiště dat **Azure Blob Storage** a parametrizovat **Úložiště dat** a relativní **Cestu**. Customer Insights přepíše oba tyto parametry během provádění kanálu datovým úložištěm a cestou, která je pro produkt přístupná.
   > [!div class="mx-imgBorder"]
   > ![Konfigurace modulu exportu dat.](media/intelligence-designer-importdata.png "Konfigurace modulu exportu dat")
   
* Při psaní výstupu odvození pomocí kódu můžete výstup odeslat na cestu v rámci *registrovaného datového úložiště* v pracovním prostoru. Pokud jsou cesta a datové úložiště parametrizovány v kanálu, aplikace Customer Insights bude moci číst a importovat výstup odvození. V současné době je podporován jeden tabulkový výstup ve formátu CSV. Cesta musí zahrnovat adresář a název souboru.

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