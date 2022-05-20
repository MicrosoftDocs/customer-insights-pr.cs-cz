---
title: Data Customer Insights v Microsoft Dataverse
description: Používejte entity Customer Insights jako tabulky v Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741357"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Práce s daty Customer Insights v Microsoft Dataverse

Aplikace Customer Insights nabízí možnost zpřístupnění výstupních entit v [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Tato integrace umožňuje snadné sdílení dat a vlastní vývoj prostřednictvím přístupu s žádným nebo minimálním množstvím kódu. [Výstupní entity](#output-entities) jsou k dispozici jako tabulky v prostředí Dataverse. Data můžete použít pro jakoukoli jinou aplikaci založenou na tabulkách Dataverse. Tyto tabulky umožňují scénáře, jako jsou automatizované pracovní postupy prostřednictvím Power Automate nebo vytváření aplikací pomocí Power Apps. Současná implementace podporuje především vyhledávání, kde lze načíst data z dostupných entit Customer Insights pro dané ID zákazníka.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Připojení prostředí Dataverse k aplikaci Customer Insights

**Existující organizace**

Správci mohou nakonfigurovat aplikaci Customer Insights, aby [používala existující prostředí Dataverse](create-environment.md), když vytvoří prostředí Customer Insights. Poskytnutím adresy URL k prostředí Dataverse připojuje se k jejich novému prostředí Customer Insights. Prostředí Customer Insights a Dataverse musí být hostována ve stejné oblasti. 

Pokud nechcete použít existující prostředí Dataverse, systém vytvoří nové prostředí pro data Customer Insights ve vašem klientovi. 

> [!NOTE]
> Pokud vaše organizace již používá Dataverse ve svém kientovi, je důležité si to pamatovat, že [vytváření prostředí Dataverse řídí správce](/power-platform/admin/control-environment-creation). Pokud například nastavujete nové prostředí Customer Insights pomocí účtu organizace a správce zakázal vytváření zkušebního prostředí Dataverse pro všechny kromě administrátorů, nemůžete vytvořit nové zkušební prostředí.
> 
> Zkušební prostředí Dataverse vytvořená v aplikaci Customer Insights mají úložiště o velikosti 3 GB, které se nezapočítává do celkové kapacity klienta. Placená předplatná získají oprávnění Dataverse o velikosti 15 GB pro databázi a 20 GB pro ukládání souborů.

**Nová organizace**

Pokud při nastavování Customer Insights vytvoříte novou organizaci, systém za vás automaticky vytvoří nové prostředí Dataverse v této organizaci.

## <a name="output-entities"></a>Výstupní entity

Některé výstupní entity ze Customer Insights jsou dostupné jako tabulky v Dataverse. V následujících částech je popsáno očekávané schéma těchto tabulek.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obohacení](#enrichment)
- [Predikce](#prediction)
- [Členství v segmentu](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Tato tabulka obsahuje sjednocený profil zákazníka z Customer Insights. Schéma pro sjednocený zákaznický profil závisí na entitách a atributech použitých v procesu sjednocení dat. Schéma profilu zákazníka obvykle obsahuje podmnožinu atributů z [definice Common Data Model sloupce CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabulka AlternateKey obsahuje klíče entit, které se účastnily procesu sjednocení.

|Column  |Typ  |Popis  |
|---------|---------|---------|
|DataSourceName    |String         | Název zdroje dat. Příklad: `datasource5`        |
|EntityName        | String        | Název entity v Customer Insights. Příklad: `contact1`        |
|AlternateValue    |String         |Alternativní ID, které je namapováno na ID zákazníka. Příklad: `cntid_1078`         |
|KeyRing           | Víceřádkový text        | Hodnota JSON  </br> Ukázka: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | ID sjednoceného profilu zákazníka.         |
|AlternateKeyId     | GUID         |  Deterministický GUID AlternateKey založený na msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Ukázka: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Tato tabulka obsahuje aktivity uživatelů, které jsou k dispozici v Customer Insights.

| Column            | Typ        | Popis                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | ID profilu zákazníka                                                                      |
| ActivityId        | String      | Interní ID aktivity zákazníka (primární klíč)                                       |
| SourceEntityName  | String      | Název zdrojové entity                                                                |
| SourceActivityId  | String      | Primární klíč ze zdrojové entity                                                       |
| ActivityType      | String      | Typ sémantické aktivity nebo název vlastní aktivity                                        |
| ActivityTimeStamp | DATETIME    | Časové razítko aktivity                                                                      |
| Název             | String      | Nadpis nebo název aktivity                                                               |
| Popis       | String      | Popis aktivity                                                                     |
| Adresa URL               | String      | Odkaz na externí adresu URL specifickou pro aktivitu                                         |
| SemanticData      | Řetězec JSON | Zahrnuje seznam párů hodnot klíče pro pole sémantického mapování specifická pro typ aktivity |
| RangeIndex        | String      | Časové razítko Unix používané pro třídění časové osy aktivity a dotazů na rozsah platnosti |
| mydynci_unifiedactivityid   | GUID | Interní ID aktivity zákazníka (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Tato tabulka obsahuje výstupní data měr založených na atributech zákazníka.

| Column             | Typ             | Popis                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | ID profilu zákazníka        |
| Míry           | Řetězec JSON      | Zahrnuje seznam párů hodnot klíče pro název a hodnoty měr pro daného zákazníka | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID profilu zákazníka |


### <a name="enrichment"></a>Obohacení

Tato tabulka obsahuje výstup z procesu obohacování.

| Column               | Typ             |  Popis                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | ID profilu zákazníka                                 |
| EnrichmentProvider   | String           | Název poskytovatele pro obohacení                                  |
| EnrichmentType       | String           | Typ obohacení                                      |
| Hodnoty               | Řetězec JSON      | Seznam atributů vytvořených procesem obohacování |
| msdynci_enrichmentid | GUID             | Deterministický GUID generovaný z msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predikce

Tato tabulka obsahuje výstup z prognóz modelu.

| Column               | Typ        | Popis                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | ID profilu zákazníka                                  |
| ModelProvider        | String      | Název poskytovatele modelu                                      |
| Model                | String      | Název modelu                                                |
| Hodnoty               | Řetězec JSON | Seznam atributů vytvořených modelem |
| msdynci_predictionid | GUID        | Deterministický GUID generovaný z msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Členství v segmentu

Tato tabulka obsahuje informace o členství v segmentech profilů zákazníků.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID profilu zákazníka        |
| SegmentProvider      | String       | Aplikace, která publikuje segmenty.      |
| SegmentMembershipType | String       | Typ zákazníka, který toto členství v segmentu zaznamenává. Podporuje více typů, jako je zákazník, kontakt nebo obchodní vztah. Výchozí: Zákazník  |
| Segmenty       | Řetězec JSON  | Seznam jedinečných segmentů, jichž je profil zákazníka členem      |
| msdynci_identifier  | String   | Jedinečný identifikátor záznamu členství v segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | Identifikátor GUID      | Deterministický GUID generovaný z `msdynci_identifier`          |
