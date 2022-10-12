---
title: Použití modelů založených na Azure Machine Learning
description: Použití modelů založených na Azure Machine Learning v Dynamics 365 Customer Insights.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609817"
---
# <a name="use-azure-machine-learning-based-models"></a>Použití modelů založených na Azure Machine Learning

Sjednocená data v Dynamics 365 Customer Insights jsou zdrojem pro vytváření modelů strojového učení, které mohou generovat další obchodní poznatky. Řešení Customer Insights je integrováno s Azure Machine Learning, abyste mohli používat vaše vlastní modely.

## <a name="prerequisites"></a>Požadavky

- Přístup k Customer Insights
- Aktivní předplatné Azure Enterprise
- [Sjednocené profily zákazníka](data-unification.md)
- [Export entit do úložiště Azure Blob](export-azure-blob-storage.md) nakonfigurován

## <a name="set-up-azure-machine-learning-workspace"></a>Nastavení pracovního prostoru Azure Machine Learning

1. V části zabývající se [vytvořením pracovního prostoru Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) najdete různé možnosti vytvoření pracovního prostoru. Pro nejlepší výkon vytvořte pracovní prostor v oblasti Azure, která je geograficky nejblíže vašemu prostředí Customer Insights.

1. Ke svému pracovnímu prostoru přistupujte prostřednictvím [Azure Machine Learning Studio](https://ml.azure.com/). Existuje několik [způsobů interakce](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) s vaším pracovním prostorem.

## <a name="work-with-azure-machine-learning-designer"></a>Práce s návrhářem Azure Machine Learning

Návrhář Azure Machine Learning poskytuje vizuální plátno, kde můžete přetahovat datové sady a moduly. Dávkový kanál vytvořený v návrháři lze integrovat do aplikace Customer Insights, pokud je odpovídajícím způsobem nakonfigurována. 

## <a name="working-with-azure-machine-learning-sdk"></a>Práce s Azure Machine Learning SDK

Datoví vědci a vývojáři AI používají [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) k vytvoření pracovních postupů strojového učení. V současné době nelze modely vytrénované pomocí SDK integrovat přímo s Customer Insights. Pro integraci s Customer Insights je vyžadován dávkový odvozovací kanál, který tento model spotřebovává.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Požadavky na dávkový kanál pro integraci s Customer Insights

### <a name="dataset-configuration"></a>Konfigurace datové sady

Vytváření datových sady pro použití dat entit z Customer Insights ve vašem dávkovém odvozovacím kanálu. Zaregistrujte tyto datové sady v pracovním prostoru. V současné době podporujeme pouze [tabulkové datové sady](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) ve formátu CSV. Parametrizujte datové sady, které odpovídají datům entity, jako parametr kanálu.

- Parametry datové sady v návrháři

  V návrháři otevřete **Výběr sloupců v datové sadě** a vyberte **Nastavit jako parametr kanálu**, kde zadáte název parametru.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Parametrizace datové sady v návrháři.":::

- Parametr datové sady v SDK (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Dávkový odvozovací kanál
  
- V návrháři tréninkový kanál použijte k vytvoření nebo aktualizaci odvozovacího kanálu. V současné době jsou podporovány pouze dávkové odvozovací kanály.

- Pomocí sady SDK publikujte kanál v koncovém bodě. V současné době se Customer Insights integruje s výchozím kanálem v koncovém bodu dávkového kanálu v pracovním prostoru Azure Machine Learning.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Import dat kanálu do Customer Insights

- Návrhář poskytuje [modul exportu dat](/azure/machine-learning/algorithm-module-reference/export-data), který umožňuje export výstupu kanálu do úložiště Azure. V současné době musí modul používat typ úložiště dat **Azure Blob Storage** a parametrizovat **Úložiště dat** a relativní **Cestu**. Customer Insights přepíše oba tyto parametry během provádění kanálu datovým úložištěm a cestou, která je pro produkt přístupná.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="Konfigurace modulu exportu dat.":::

- Při psaní výstupu odvození pomocí kódu můžete výstup odeslat na cestu v rámci *registrovaného datového úložiště* v pracovním prostoru. Pokud jsou cesta a datové úložiště parametrizovány v kanálu, aplikace Customer Insights bude moci číst a importovat výstup odvození. V současné době je podporován jeden tabulkový výstup ve formátu CSV. Cesta musí zahrnovat adresář a název souboru.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]