---
title: Vlastní modely strojové učení | Microsoft Docs
description: Práce s vlastními modely z řešení Azure Machine Learning v aplikaci Dynamics 365 Customer Insights.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: a44d1f2c00c90de3ed5a9425e3a197e109cb28e0
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800412"
---
# <a name="custom-machine-learning-models"></a>Vlastní modely strojového učení

> [!NOTE]
> Podpora pro Machine Learning Studio (klasické) skončí 31. srpna 2024. Do tohoto data vám doporučujeme přejít na [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning).
>
> Od 1. prosince 2021 nebudete moci vytvářet nové zdroje Machine Learning Studio (klasické). Do 31. srpna 2024 můžete nadále používat stávající zdroje Machine Learning Studio (klasické). Další informace viz [Migrace do Azure Machine Learning](/azure/machine-learning/migrate-overview).


**Analytické nástroje** > **Vlastní modely** umožňuje spravovat pracovní postupy založené na modelech strojového učení Azure Machine Learning. Pracovní postupy vám pomohou vybrat data, ze kterých chcete generovat přehledy, a namapovat výsledky na vaše sjednocená data o zákaznících. Další informace o vytváření vlastních modelů ML najdete v tématu [Použití modelů založených na Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Zodpovědná AI

Predikce umožňují vytvářet lepší zákaznické prostředí, zlepšovat obchodní schopnosti a zdroje příjmů. Důrazně doporučujeme, abyste vyvážili hodnotu své predikce s dopadem, který má, a možnými opatřeními proti předpojatosti zavedenými z etických důvodů. Další informace, jak společnost Microsoft [přistupuje k zodpovědné AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Můžete se také dozvědět o [technikách a procesech pro zodpovědné strojové učení](/azure/machine-learning/concept-responsible-ml) specifické pro Azure Machine Learning.

## <a name="prerequisites"></a>Předpoklady

- Tato funkce podporuje webové služby publikované prostřednictvím [dávkových kanálů Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).

- Abyste mohli používat tuto funkci, potřebujete účet úložiště Azure Data Lake Gen2 přidružený k vaší instanci Azure Studio. Další informace viz [Vytvoření účtu úložiště Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Pro pracovní prostory Azure Machine Learning s kanály potřebujete oprávnění vlastníka nebo správce přístupu uživatelů k pracovnímu prostoru Azure Machine Learning.

   > [!NOTE]
   > Data se přenášejí mezi vašimi instancemi Customer Insights a vybranými webovými službami nebo kanály Azure v pracovním postupu. Když přenášíte data do služby Azure, ujistěte se, že je služba nakonfigurovaná tak, aby zpracovávala data způsobem a umístěním nezbytným pro splnění jakýchkoli právních nebo regulačních požadavků na tato data pro vaši organizaci.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>Přidání nového pracovního postupu

1. Přejděte na **Analytické nástroje** > **Vlastní modely** a vyberte **Nový pracovní postup**.

1. Zadejte rozpoznatelný název vlastního modelu do pole **Název**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot podokna Nový pracovní postup.](media/new-workflowv2.png "Snímek obrazovky podokna Nový pracovní postup")

1. Vyberte organizaci, která obsahuje webovou službu, v části **Klient, který obsahuje vaši webovou službu**.

1. Pokud je vaše předplatné Azure Machine Learning v jiném klientovi než Customer Insights, vyberte **Přihlásit** pomocí přihlašovacích údajů pro vybranou organizaci.

1. Vyberte **Pracovní prostory** přidružené k vaší webové službě. 

1. Vyberte kanál Azure Machine Learning v rozevíracím seznamu **Webová služba obsahující váš model**. Pak vyberte **Další**.    
   Další informace o [publikování kanálu v Azure Machine Learning pomocí návrháře](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) nebo [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Váš kanál musí být publikován pod [koncovým bodem kanálu](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Pro každou položku **Vstup webové služby** vyberte odpovídající **entitu** z Customer Insights a vyberte **Další**.
   > [!NOTE]
   > Pracovní postup vlastního modelu použije heuristiku k mapování vstupních polí webové služby na atributy entity na základě názvu a datového typu pole. Pokud pole webové služby nelze mapovat na entitu, zobrazí se chyba.

   > [!div class="mx-imgBorder"]
   > ![Konfigurace pracovního postupu.](media/intelligence-screen2-updated.png "Konfigurace pracovního postupu")

1. V kroku **Výstupní parametry modelu** nastavte následující vlastnosti:
      1. Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky kanálu.
      1. Vyberte **Název parametru úložiště výstupních dat** vašeho dávkového kanálu z rozbalovací nabídky.
      1. Vyberte **Název parametru výstupní cesty** vašeho dávkového kanálu z rozbalovací nabídky.

      > [!div class="mx-imgBorder"]
      > ![Podokno výstupních parametrů modelu.](media/intelligence-screen3-outputparameters.png "Podokno výstupních parametrů modelu")

1. Vyberte odpovídající atribut z rozevíracího seznamu **D zákazníka ve výsledcích**, který identifikuje zákazníky, a pak vyberte **Uložit**.

   > [!div class="mx-imgBorder"]
   > ![Propojení výsledků v podokně údajů o zákaznících.](media/intelligence-screen4-relatetocustomer.png "Propojení výsledků v podokně údajů o zákaznících")

1. Zobrazí se obrazovka **Pracovní postup uložen** s podrobnostmi o pracovním postupu.    
   Pokud jste nakonfigurovali pracovní postup pro kanál strojové učení Azure, Customer Insights se připojí k pracovnímu prostoru, který kanál obsahuje. Customer Insights dostanou a roli **Přispěvatel** v pracovním prostoru Azure.

1. Vyberte **Hotovo**.

1. Nyní můžete spustit pracovní postup ze stránky **Vlastní modely**.

## <a name="edit-a-workflow"></a>Úprava pracovního postupu

1. Na stránce **Vlastní modely** vyberte vertikální tři tečky (&vellip;) ve sloupci **Akce** vedle dříve vytvořeného pracovního postupu a vyberte **Upravit**.

1. Rozpoznatelný název pracovního postupu můžete změnit v poli **Zobrazovaný název**, ale nemůžete změnit nakonfigurovanou webovou službu nebo kanál. Vyberte **Další**.

1. Pro každou položku **Vstup webové služby** můžete aktualizovat odpovídající **entitu** z Customer Insights. Pak vyberte **Další**.

1. V kroku **Výstupní parametry modelu** nastavte následující vlastnosti:
      1. Zadejte **Název entity** výstupu, kam mají směřovat výstupní výsledky kanálu.
      1. Vyberte **Název parametru úložiště výstupních dat** pro váš testovací kanál.
      1. Vyberte **Název parametru výstupní cesty** pro váš testovací kanál.

1. Vyberte odpovídající atribut z rozevíracího seznamu **D zákazníka ve výsledcích**, který identifikuje zákazníky, a pak vyberte **Uložit**.
   Vyberte atribut z výstupu odvození s hodnotami podobnými sloupci ID zákazníka entity Zákazník. Pokud takový sloupec chybí v datové sadě, vyberte atribut, který jednoznačně identifikuje řádek.

## <a name="run-a-workflow"></a>Spuštění pracovního postupu

1. Na stránce **Vlastní modely** vyberte vertikální tři tečky (&vellip;) ve sloupci **Akce** vedle dříve vytvořeného pracovního postupu.

1. Vyberte **Spustit**.

Váš pracovní postup se také spustí automaticky s každou plánovanou aktualizací. Další informace o [nastavení plánovaných aktualizací](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Odstranění pracovního postupu

1. Na stránce **Vlastní modely** vyberte vertikální tři tečky (&vellip;) ve sloupci **Akce** vedle dříve vytvořeného pracovního postupu.

1. Vyberte **Odstranit** a potvrďte požadavek na odstranění.

Váš pracovní postup bude odstraněn. [Entita](entities.md), která byla vytvořena, když jste vytvořili pracovní postup, přetrvává, a lze ji zobrazit na stránce **Entity**.

## <a name="results"></a>Výsledky

Výsledky z pracovního postupu jsou uloženy v entitě nakonfigurované během fáze Výstupní parametry modelu. K těmto datům máte přístup ze [stránky entit](entities.md) nebo [přes API](apis.md).

### <a name="api-access"></a>Přístup přes API

Aby dotaz OData získal data z entity vlastního modelu, použijte následující formát:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Místo `<your instance id>` zadejte ID prostředí Customer Insights, které najdete v adresním řádku svého prohlížeče při přístupu k Customer Insights.

1. Místo `<custom model output entity>` zadejte název entity, který jste zadali během kroku Výstupní parametry modelu při konfiguraci vlastního modelu.

1. Místo `<guid value>` zadejte ID zákazníka, pro kterého chcete získat přístup k záznamu. Toto ID obvykle najdete na [stránce s profily zákazníků](customer-profiles.md) v poli CustomerID.

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

- Proč nevidím svůj kanál při nastavování pracovního postupu vlastního modelu?    
  Tento problém je často způsoben problémem s konfigurací v kanálu. Musí být [nakonfigurován vstupní parametr](azure-machine-learning-experiments.md#dataset-configuration) a [ výstupní datové úložiště a parametry cesty](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).

- Co znamená chyba „Nepodařilo se uložit pracovní postup analytických nástrojů“?    
  Tato chybová zpráva se uživatelům obvykle zobrazí, pokud v pracovním prostoru nemají oprávnění vlastníka nebo správce přístupu uživatelů. Uživatel potřebuje vyšší úroveň oprávnění, aby umožnil Customer Insights zpracovat pracovní postup jako službu, místo aby používal přihlašovací údaje uživatele pro další spuštění pracovního postupu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
