---
title: Vlastní modely strojové učení | Microsoft Docs
description: Práce s vlastními modely z řešení Azure Machine Learning v aplikaci Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609736"
---
# <a name="custom-machine-learning-models"></a>Vlastní modely strojového učení

> [!NOTE]
> Podpora pro Machine Learning Studio (klasické) skončí 31. srpna 2024. Do tohoto data vám doporučujeme přejít na [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning).
>
> Od 1. prosince 2021 nebudete moci vytvářet nové zdroje Machine Learning Studio (klasické). Do 31. srpna 2024 můžete nadále používat stávající zdroje Machine Learning Studio (klasické). Další informace viz [Migrace do Azure Machine Learning](/azure/machine-learning/migrate-overview).

Vlastní modely umožňují spravovat pracovní postupy založené na modelech Azure Machine Learning. Pracovní postupy vám pomohou vybrat data, ze kterých chcete generovat přehledy, a namapovat výsledky na vaše sjednocená data o zákaznících. Další informace o vytváření vlastních modelů ML najdete v tématu [Použití modelů založených na Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Předpoklady

- Webové služby publikované prostřednictvím [dávkových kanálů Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).
- Kanál musí být publikován pod [koncovým bodem kanálu](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- [Účet úložiště Azure Data Lake Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account) přidružený k vaší instanci Azure Studio.
- Pro pracovní prostory Azure Machine Learning s kanály oprávnění vlastníka nebo správce přístupu uživatelů k pracovnímu prostoru Azure Machine Learning.

  > [!NOTE]
  > Data se přenášejí mezi vašimi instancemi Customer Insights a vybranými webovými službami nebo kanály Azure v pracovním postupu. Když přenášíte data do služby Azure, ujistěte se, že je služba nakonfigurovaná tak, aby zpracovávala data způsobem a umístěním nezbytným pro splnění jakýchkoli právních nebo regulačních požadavků na tato data pro vaši organizaci.

## <a name="add-a-new-workflow"></a>Přidání nového pracovního postupu

1. Přejděte na **Analytické nástroje** > **Vlastní modely** a vyberte **Nový pracovní postup**.

1. Zadejte rozpoznatelný **název**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Screenshot podokna Nový pracovní postup.":::

1. Vyberte organizaci, která obsahuje webovou službu, v části **Klient, který obsahuje vaši webovou službu**.

1. Pokud je vaše předplatné Azure Machine Learning v jiném klientovi než Customer Insights, vyberte **Přihlásit** pomocí přihlašovacích údajů pro vybranou organizaci.

1. Vyberte **Pracovní prostory** přidružené k vaší webové službě.

1. Vyberte kanál Azure Machine Learning v rozevíracím seznamu **Webová služba obsahující váš model**. Pak vyberte **Další**.
   Další informace o [publikování kanálu v Azure Machine Learning pomocí návrháře](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) nebo [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Pro každou položku **Vstup webové služby** vyberte odpovídající **entitu** z Customer Insights. Pak vyberte **Další**.
   > [!NOTE]
   > Pracovní postup vlastního modelu použije heuristiku k mapování vstupních polí webové služby na atributy entity na základě názvu a datového typu pole. Pokud pole webové služby nelze mapovat na entitu, zobrazí se chyba.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Konfigurace pracovního postupu.":::

1. V kroku **Výstupní parametry modelu** nastavte následující vlastnosti:
   - **Název entity** pro výsledky výstupu kanálu
   - **Název parametru úložiště výstupních dat** hromadného kanálu
   - **Název parametru výstupní cesty** hromadného kanálu

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Podokno výstupních parametrů modelu.":::

1. Vyberte odpovídající atribut z **ID zákazníka ve výsledcích**, který identifikuje zákazníky, a pak vyberte **Uložit**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Propojení výsledků v podokně údajů o zákaznících.":::

   Zobrazí se obrazovka **Pracovní postup uložen** s podrobnostmi o pracovním postupu. Pokud jste nakonfigurovali pracovní postup pro kanál strojové učení Azure, Customer Insights se připojí k pracovnímu prostoru, který kanál obsahuje. Customer Insights dostanou a roli **Přispěvatel** v pracovním prostoru Azure.

1. Vyberte **Hotovo**. Zobrazí se stránka **Vlastní modely**.

1. Vyberte vertikální tři tečky (&vellip;) pro pracovní postup a poté vyberte **Spustit**. Váš pracovní postup se také spustí automaticky s každou [plánovanou aktualizací](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Správa existujícího pracovního postupu

Přejděte na **Analytické nástroje** > **Vlastní modely** pro zobrazení pracovních postupů, které jste vytvořili.

Výběrem pracovního postupu zobrazíte dostupné akce.

- **Úprava** pracovního postupu
- **Spuštění** pracovního postupu
- [**Odstranění**](#delete-a-workflow) pracovního postupu

### <a name="edit-a-workflow"></a>Úprava pracovního postupu

1. Přejděte na **Analytické nástroje** > **Vlastní modely**.

1. Vedle pracovního postupu, který chcete aktualizovat, vyberte vertikální tři tečky (&vellip;) a vyberte **Upravit**.

1. Změňte **Zobrazovaný název** v případě potřeby a vyberte **Další**.

1. Pro každou položku **Vstup webové služby** aktualizujte odpovídající **entitu** z Customer Insights, pokud je to potřeba. Pak vyberte **Další**.

1. V kroku **Výstupní parametry modelu** změňte následující:
   - **Název entity** pro výsledky výstupu kanálu
   - **Název parametru úložiště výstupních dat** hromadného kanálu
   - **Název parametru výstupní cesty** hromadného kanálu

1. Změňte odpovídající atribut z **ID zákazníka ve výsledcích** k identifikaci zákazníků. Vyberte atribut z výstupu odvození s hodnotami podobnými sloupci ID zákazníka entity Zákazník. Pokud takový sloupec chybí v datové sadě, vyberte atribut, který jednoznačně identifikuje řádek.

1. Vyberte **Uložit**.

### <a name="delete-a-workflow"></a>Odstranění pracovního postupu

1. Přejděte na **Analytické nástroje** > **Vlastní modely**.

1. Vedle pracovního postupu, který chcete odstranit, vyberte vertikální tři tečky (&vellip;) a vyberte **Odstranit**.

1. Odstranění potvrďte.

Váš pracovní postup bude odstraněn. [Entita](entities.md), která byla vytvořena, když jste vytvořili pracovní postup, přetrvává, a lze ji zobrazit na stránce **Data** > **Entity**.

## <a name="view-the-results"></a>Zobrazení výsledků

Výsledky z pracovního postupu jsou uloženy v názvu entity definovaném pro **Výstupní parametry modelu**. K těmto datům máte přístup ze [stránky **Data** > **Entity**](entities.md) nebo [přístup přes rozhraní API](apis.md).

### <a name="api-access"></a>Přístup přes API

Aby dotaz OData získal data z entity vlastního modelu, použijte následující formát:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Místo `<your instance id>` zadejte ID prostředí Customer Insights, které se zobrazí v adresním řádku svého prohlížeče při přístupu k Customer Insights.

1. Nahraďte `<custom model output entity>` za název entity, který jste zadali pro **Výstupní parametry modelu**.

1. Místo `<guid value>` zadejte ID zákazníka, pro kterého chcete získat přístup. Toto ID se zobrazuje na [stránce s profily zákazníků](customer-profiles.md) v poli CustomerID.

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

- Proč nevidím svůj kanál při nastavování pracovního postupu vlastního modelu?
  Tento problém je často způsoben problémem s konfigurací v kanálu. Musí být [nakonfigurován vstupní parametr](azure-machine-learning-experiments.md#dataset-configuration) a [ výstupní datové úložiště a parametry cesty](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).

- Co znamená chyba „Nepodařilo se uložit pracovní postup analytických nástrojů“? 
  Tato chybová zpráva se uživatelům obvykle zobrazí, pokud v pracovním prostoru nemají oprávnění vlastníka nebo správce přístupu uživatelů. Uživatel potřebuje vyšší úroveň oprávnění, aby umožnil Customer Insights zpracovat pracovní postup jako službu, místo aby používal přihlašovací údaje uživatele pro další spuštění pracovního postupu.

- Je podporován privátní koncový bod / privátní odkaz pro pracovní postup mého vlastního modelu?
  Customer Insights v současné době ve výchozím nastavení nepodporuje privátní koncový bod pro vlastní modely, ale je k dispozici ruční řešení. Další informace vám poskytne podpora.

## <a name="responsible-ai"></a>Zodpovědná AI

Predikce umožňují vytvářet lepší zákaznické prostředí, zlepšovat obchodní schopnosti a zdroje příjmů. Důrazně doporučujeme, abyste vyvážili hodnotu své predikce s dopadem, který má, a možnými opatřeními proti předpojatosti zavedenými z etických důvodů. Další informace, jak společnost Microsoft [přistupuje k zodpovědné AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Můžete se také dozvědět o [technikách a procesech pro zodpovědné strojové učení](/azure/machine-learning/concept-responsible-ml) specifické pro Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
