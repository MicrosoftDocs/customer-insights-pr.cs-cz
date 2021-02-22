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
# <a name="custom-machine-learning-models"></a>Vlastní modely strojového učení

**Analytické nástroje** > **Vlastní modely** umožňuje spravovat pracovní postupy založené na modelech strojového učení Azure Machine Learning. Pracovní postupy vám pomohou vybrat data, ze kterých chcete generovat přehledy, a namapovat výsledky na vaše sjednocená data o zákaznících. Další informace o vytváření vlastních modelů ML najdete v tématu [Použití modelů založených na Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Zodpovědná AI

Predikce umožňují vytvářet lepší zákaznické prostředí, zlepšovat obchodní schopnosti a zdroje příjmů. Důrazně doporučujeme, abyste vyvážili hodnotu své predikce s dopadem, který má, a možnými opatřeními proti předpojatosti zavedenými z etických důvodů. Další informace, jak společnost Microsoft [přistupuje k zodpovědné AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Můžete se také dozvědět o [technikách a procesech pro zodpovědné strojové učení](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specifické pro Azure Machine Learning.

## <a name="prerequisites"></a>Požadavky

- V současné době tato funkce podporuje webové služby publikované prostřednictvím [Machine Learning Studio (classic)](https://studio.azureml.net) a [dávkových kanálů Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Abyste mohli používat tuto funkci, potřebujete účet úložiště Azure Data Lake Gen2 přidružený k vaší instanci Azure Studio. Další informace viz [Vytvoření účtu úložiště Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Přidání nového pracovního postupu

1. Přejděte na **Analytické nástroje** > **Vlastní modely** a vyberte **Nový pracovní postup**.

1. Zadejte rozpoznatelný název vlastního modelu do pole **Název**.

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky podokna Nový pracovní postup](media/new-workflowv2.png "Snímek obrazovky podokna Nový pracovní postup")

1. Vyberte organizaci, která obsahuje webovou službu, v části **Klient, který obsahuje vaši webovou službu**.

1. Pokud je vaše předplatné Azure Machine Learning v jiném klientovi než Customer Insights, vyberte **Přihlásit** pomocí přihlašovacích údajů pro vybranou organizaci.

1. Vyberte **Pracovní prostory** přidružené k vaší webové službě. Jsou zde uvedeny dvě sekce, jedna pro Azure Machine Learning v1 (Machine Learning Studio (classic)) a Azure Machine Learning v2 (Azure Machine Learning). Pokud si nejste jisti, který pracovní prostor je ten pravý pro vaši webovou službu Machine Learning Studio (classic), vyberte **Žádný**.

1. Zvolte webovou službu Machine Learning Studio (classic) nebo kanál Azure Machine Learning v rozevíracím seznamu **Webová služba obsahující váš model**. Pak vyberte **Další**.
   - Další informace o [publikování webové služby v Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Další informace o [publikování kanálu v Azure Machine Learning pomocí návrháře](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) nebo [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). 
     > [!NOTE]
     > Váš kanál musí být publikován pod [koncovým bodem kanálu](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Pro každou položku **Vstup webové služby** vyberte odpovídající **entitu** z přehledů cílové skupiny a vyberte **Další**.

   > [!div class="mx-imgBorder"]
   > ![Konfigurace pracovního postupu](media/intelligence-screen2-updated.png "Konfigurace pracovního postupu")

1. V kroku **Výstupní parametry modelu** nastavte následující vlastnosti:
   - Machine Learning Studio (classic)
      1. Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky webové služby.
   - Azure Machine Learning
      1. Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky kanálu.
      1. Vyberte **Název parametru úložiště výstupních dat** vašeho dávkového kanálu z rozbalovací nabídky.
      1. Vyberte **Název parametru výstupní cesty** vašeho dávkového kanálu z rozbalovací nabídky.
      
      > [!div class="mx-imgBorder"]
      > ![Podokno výstupních parametrů modelu](media/intelligence-screen3-outputparameters.png "Podokno výstupních parametrů modelu")

1. Vyberte odpovídající atribut z rozevíracího seznamu **ID zákazníka ve výsledcích**, který identifikuje zákazníky, a vyberte **Uložit**.
   
   > [!div class="mx-imgBorder"]
   > ![Propojení výsledků v podokně údajů o zákaznících](media/intelligence-screen4-relatetocustomer.png "Propojení výsledků v podokně údajů o zákaznících")

1. Zobrazí se obrazovka **Pracovní postup uložen** s podrobnostmi o pracovním postupu.    
   Pokud jste nakonfigurovali pracovní postup pro kanál Azure Machine Learning, přehledy cílové skupiny se připojí k pracovnímu prostoru, který obsahuje kanál. Přehledy cílové skupiny získají roli **Přispěvatel** v pracovním prostoru Azure.

1. Vyberte **Hotovo**.

1. Nyní můžete spustit pracovní postup ze stránky **Vlastní modely**.

## <a name="edit-a-workflow"></a>Úprava pracovního postupu

1. Na stránce **Vlastní modely** vyberte vertikální elipsu ve sloupci **Akce** vedle dříve vytvořeného pracovního postupu a vyberte **Upravit**.

1. Rozpoznatelný název pracovního postupu můžete změnit v poli **Zobrazovaný název**, ale nemůžete změnit nakonfigurovanou webovou službu nebo kanál. Vyberte **Další**.

1. Pro každou položku **Vstup webové služby** můžete změnit odpovídající **entitu** z přehledů cílové skupiny. Pak vyberte **Další**.

1. V kroku **Výstupní parametry modelu** nastavte následující vlastnosti:
   - Machine Learning Studio (classic)
      1. Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky webové služby.
   - Azure Machine Learning
      1. Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky kanálu.
      1. Vyberte **Název parametru úložiště výstupních dat** pro váš testovací kanál.
      1. Vyberte **Název parametru výstupní cesty** pro váš testovací kanál.

1. Vyberte odpovídající atribut z rozevíracího seznamu **ID zákazníka ve výsledcích**, který identifikuje zákazníky, a vyberte **Uložit**.
   Musíte vybrat atribut z výstupu odvození s hodnotami podobnými sloupci ID zákazníka entity Zákazník. Pokud takový sloupec chybí v datové sadě, vyberte atribut, který jednoznačně identifikuje řádek.

## <a name="run-a-workflow"></a>Spuštění pracovního postupu

1. Na stránce **Vlastní modely** vyberte vertikální elipsu ve sloupci **Akce** vedle dříve vytvořeného pracovního postupu.

1. Vyberte **Spustit**.

Váš pracovní postup se také spustí automaticky s každou plánovanou aktualizací. Další informace o [nastavení plánovaných aktualizací](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Odstranění pracovního postupu

1. Na stránce **Vlastní modely** vyberte vertikální elipsu ve sloupci **Akce** vedle dříve vytvořeného pracovního postupu.

1. Vyberte **Odstranit** a potvrďte požadavek na odstranění.

Váš pracovní postup bude odstraněn. [Entita](entities.md), která byla vytvořena, když jste vytvořili pracovní postup, přetrvává, a lze ji zobrazit na stránce **Entity**.