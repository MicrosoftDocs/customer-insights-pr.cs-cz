---
title: Data Customer Insights v Microsoft Dataverse
description: Používejte entity Customer Insights jako tabulky v Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 220e01a06711a5d35b8df09e265017a6d8fd0490
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650034"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Práce s daty Customer Insights v Microsoft Dataverse

Aplikace Customer Insights nabízí možnost zpřístupnění výstupních entit v [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Tato integrace umožňuje snadné sdílení dat a vlastní vývoj prostřednictvím přístupu s žádným nebo minimálním množstvím kódu. Výstupní entity budou k dispozici jako tabulky v Dataverse. Tyto tabulky umožňují nasazení scénářů typu [automatizované pracovní postupy prostřednictvím Power Automate](/power-automate/getting-started), [aplikací řízených modelem](/powerapps/maker/model-driven-apps/) a [aplikací plátna](/powerapps/maker/canvas-apps/) prostřednictvím Power Apps. Data můžete použít pro jakoukoli jinou aplikaci založenou na tabulkách Dataverse. Aktuální implementace podporuje hlavně vyhledávání, kde lze pro dané ID zákazníka načíst data z dostupných entit přehledů cílových skupin.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Připojení prostředí Dataverse k aplikaci Customer Insights

**Organizace se stávajícími prostředími Dataverse**

Organizace, které již používají Dataverse, mohou [použít jedno z jejich stávajících prostředí Dataverse](get-started-paid.md), když správce nastavuje přehledy cílové skupiny. Poskytnutím adresy URL prostředí Dataverse toto prostředí připojíte k novému prostředí přehledů cílové skupiny. Aby byl zajištěn co nejlepší výkon, musejí být prostředí Customer Insights a Dataverse hostována ve stejné oblasti.

Chcete-li připojit prostředí Dataverse, rozbalte při vytváření prostředí přehledů cílové skupiny uzel **Rozšířená nastavení**. Zadejte **adresu URL prostředí Microsoft Dataverse** a zaškrtněte políčko **Povolit sdílení dat**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt.":::

**Nová organizace**

Když vytvoříte novou organizaci při nastavování aplikace Customer Insights, automaticky získáte nové prostředí Dataverse.

> [!NOTE]
> Pokud vaše organizace již ve svém klientu používá Dataverse, je důležité si zapamatovat, že [tvorbu prostředí Dataverse řídí administrátor](/power-platform/admin/control-environment-creation.md). Pokud například nastavujete nové prostředí přehledů cílové skupiny pomocí vašeho účtu organizace a správce zakázal vytváření zkušebních prostředí Dataverse všem kromě správců, nemůžete vytvořit nové zkušební prostředí.
> 
> Zkušební prostředí Dataverse vytvořená v aplikaci Customer Insights mají úložiště o velikosti 3 GB, které se nezapočítává do celkové kapacity klienta. Placená předplatná získají oprávnění Dataverse o velikosti 15 GB pro databázi a 20 GB pro ukládání souborů.

## <a name="output-entities"></a>Výstupní entity

Některé výstupní entity z přehledů cílové skupiny jsou k dispozici jako tabulky v Dataverse. V následujících částech je popsáno očekávané schéma těchto tabulek.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obohacení](#enrichment)
- [Predikce](#prediction)


### <a name="customerprofile"></a>CustomerProfile

Tato tabulka obsahuje sjednocený profil zákazníka z Customer Insights. Schéma pro sjednocený profil zákazníka závisí na entitách a atributech použitých v procesu slučování. Schéma profilu zákazníka obvykle obsahuje podmnožinu atributů z [definice Common Data Model sloupce CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabulka AlternateKey obsahuje klíče entit, které se účastnily procesu sjednocení.

|Column  |Typ  |Popis  |
|---------|---------|---------|
|DataSourceName    |String         | Název zdroje dat. Příklad: `datasource5`        |
|EntityName        | String        | Název entity v přehledu cílové skupiny. Příklad: `contact1`        |
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
