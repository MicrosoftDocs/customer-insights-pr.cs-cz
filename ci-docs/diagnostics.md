---
title: Přesměrování protokolů v Dynamics 365 Customer Insights s Azure Monitor (Preview)
description: Přečtěte si, jak odesílat protokoly do Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8c72df7054a682244215bbee54968d6aef4bbf59
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052645"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Přesměrování protokolů v Dynamics 365 Customer Insights s Azure Monitor (Preview)

Dynamics 365 Customer Insights poskytuje přímou integraci s Azure Monitor. Protokoly prostředků Azure Monitor umožňují monitorovat a odesílat protokoly do [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) nebo je streamovat do [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

Customer Insights odesílá následující protokoly událostí:

- **Událostí auditu**
  - **APIEvent** – umožňuje sledování změn prostřednictvím uživatelského rozhraní Dynamics 365 Customer Insights.
- **Provozní události**
  - **WorkflowEvent** – tento pracovní postup vám umožní nastavit [zdroje dat](data-sources.md), [sjednotit](data-unification.md) a [rozšířit](enrichment-hub.md) a nakonec [exportovat](export-destinations.md) data do jiných systémů. Všechny tyto kroky lze provést jednotlivě (například spustit jeden export). Může také běžet organizovaně (například obnova dat z datových zdrojů, která spustí proces sjednocení, který přitáhne obohacení a po dokončení exportuje data do jiného systému). Další informace viz [Schéma WorkflowEvent](#workflow-event-schema).
  - **APIEvent** – všechna volání rozhraní API do instance zákazníků do Dynamics 365 Customer Insights. Další informace viz [Schéma APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Nastavení diagnostiky

### <a name="prerequisites"></a>Předpoklady

Chcete -li konfigurovat diagnostiku v Customer Insights, musí být splněny následující předpoklady:

- Máte aktivní [předplatné Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Máte oprávnění [správce](permissions.md#admin) v Customer Insights.
- Máte roli **Přispěvatel** a **Správce přístupu uživatelů** v cílovém prostředku v Azure. Prostředkem může být účet Azure Data Lake Storage, centrum událostí Azure nebo pracovní prostor Azure Log Analytics. Další informace najdete v části [Přidání nebo odebrání přiřazení rolí Azure pomocí Azure Portal](/azure/role-based-access-control/role-assignments-portal). Toto oprávnění je nutné při konfiguraci diagnostických nastavení v Customer Insights. Po úspěšném nastavení je lze změnit.
- Splněny [požadavky na cíl](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) pro Azure Storage, centrum událostí Azure nebo Azure Log Analytics.
- Máte alespoň roli **Čtenář** ve skupině prostředků, do které prostředek patří.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Nastavení diagnostiky pomocí Azure Monitor

1. V Customer Insights volbou **Systém** > **Diagnostika** zobrazíte cíle diagnostiky nakonfigurované pro tuto instanci.

1. Vyberte **Přidat cíl**.

   > [!div class="mx-imgBorder"]
   > ![Připojení diagnostiky](media/diagnostics-pane.png "Připojení diagnostiky")

1. Do pole **Název cíle diagnostiky** zadejte název diagnostiky.

1. Vyberte **Klienta** předplatného Azure s cílovým prostředkem a vyberte **Přihlásit se**.

1. Vyberte **Typ prostředku** (účet úložiště, centrum událostí nebo analytika protokolů).

1. Pro cílový prostředek vyberte **Předplatné**.

1. Pro cílový prostředek vyberte **Skupina prostředků**.

1. Vyberte **Prostředek**.

1. Potvrďte prohlášení o **ochraně osobních údajů a dodržování předpisů**.

1. Volbou **Připojit k systému** se připojte k cílovému zdroji. Protokoly se začnou v cíli objevovat po 15 minutách, pokud je rozhraní API aktivní a generuje události.

### <a name="remove-a-destination"></a>Odebrání cíle

1. Přejděte na **Systém** > **Diagnostika**.

1. V seznamu vyberte cíl diagnostiky.

1. Ve sloupci **Akce** vyberte ikonu **Odstranit**.

1. Potvrzením odstranění zastavíte přesměrování protokolu. Prostředek v předplatném Azure nebude odstraněn. Volbou odkazu ve sloupci **Akce** můžete otevřít Azure Portal pro vybraný prostředek a odstranit jej tam.

## <a name="log-categories-and-event-schemas"></a>Kategorie protokolů a schémata událostí

V současné době jsou podporovány [události rozhraní API](apis.md) a události pracovního postupu a platí následující kategorie a schémata.
Schéma protokolu následuje [společné schéma Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorie

Customer Insights nabízí dvě kategorie:

- **Události auditu**: [Události rozhraní API](#api-event-schema) pro sledování změn konfigurace ve službě. Operace `POST|PUT|DELETE|PATCH` spadají do této kategorie.
- **Provozní události**: [Události rozhraní API](#api-event-schema) nebo [události pracovního postupu](#workflow-event-schema) generované při používání služby.  Například požadavky `GET` nebo události provedení pracovního postupu.

## <a name="configuration-on-the-destination-resource"></a>Konfigurace cílového prostředku

Na základě zvoleného typu prostředku se automaticky použijí následující kroky:

### <a name="storage-account"></a>Storage account

Instanční objekt Customer Insights získá oprávnění **Přispěvatel účtu úložiště** pro vybraný prostředek a vytvoří dva kontejnery pod vybraným prostorem názvů:

- `insight-logs-audit` obsahující **události auditu**
- `insight-logs-operational` obsahující **provozní události**

### <a name="event-hub"></a>Centrum událostí

Instanční objekt Customer Insights získá oprávnění **Vlastník dat Azure Event Hubs** pro vybraný prostředek a vytvoří dvě centra událostí pod vybraným prostorem názvů:

- `insight-logs-audit` obsahující **události auditu**
- `insight-logs-operational` obsahující **provozní události**

### <a name="log-analytics"></a>Log Analytics

Instanční objekt Customer Insights získá oprávnění **Přispěvatel Log Analytics** k prostředku. Protokoly budou dostupné v sekci **Protokoly** > **Tabulky** > **Správa protokolů** ve vybraném pracovním prostoru Log Analytics. Rozbalte řešení **Správa protokolů** a vyhledejte tabulky `CIEventsAudit` a `CIEventsOperational`.

- `CIEventsAudit` obsahující **události auditu**
- `CIEventsOperational` obsahující **provozní události**

V okně **Dotazy** rozbalte řešení **Audit** a vyhledejte vzorové dotazy poskytnuté při hledání `CIEvents`.

## <a name="event-schemas"></a>Schéma událostí

Události rozhraní API a události pracovního postupu mají společnou strukturu a podrobnosti, kde se liší, viz [schéma události rozhraní API](#api-event-schema) nebo [schéma události pracovního postupu](#workflow-event-schema).

### <a name="api-event-schema"></a>Schéma události rozhraní API

| Pole             | DataType  | Povinné/volitelné | Description       | Příklad        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Časové razítko | Požaduje se          | Časové razítko události (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Požaduje se          | ResourceId instance, která událost vyslala         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Požaduje se          | Název operace představované touto událostí.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Požaduje se          | Kategorie protokolu události. Buďto `Operational` nebo `Audit`. Všechny POST/PUT/PATCH/DELETE HTTP požadavky jsou označeny pomocí `Audit`, vše ostatní pomocí `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Požaduje se          | Stav události. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Volitelné          | Výsledný stav události. Pokud operace odpovídá volání REST API, je to stavový kód HTTP.        | `200`             |
| `durationMs`      | Dlouhé celé číslo      | Volitelné          | Doba trvání operace v milisekundách.     | `133`     |
| `callerIpAddress` | String    | Volitelné          | IP adresa volajícího, pokud operace odpovídá volání rozhraní API, které pochází z veřejně dostupné IP adresy.                                                 | `144.318.99.233`         |
| `identity`        | String    | Volitelné          | Objekt JSON popisující identitu uživatele nebo aplikace, která provedla operaci.       | Viz sekce [Identita](#identity-schema).     |  
| `properties`      | String    | Volitelné          | Objekt JSON s více vlastnostmi pro konkrétní kategorii událostí.      | Viz sekce [Vlastnosti](#api-properties-schema).    |
| `level`           | String    | Požaduje se          | Úroveň závažnosti události.    | `Informational`, `Warning`, `Error` nebo `Critical`.           |
| `uri`             | String    | Volitelné          | Absolutní identifikátor URI požadavku.    |               |

#### <a name="identity-schema"></a>Schéma identity

Objekt JSON `identity` má následující strukturu

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Pole                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Přiřazená role pro uživatele nebo aplikaci. Další informace naleznete viz [oprávnění uživatele](permissions.md).                                     |
| `Authorization.RequiredRoles` | Potřebné role k provedení operace. Role `Admin` může provádět všechny operace.                                                    |
| `Claims`                      | Deklarované identity webového tokenu JSON (JWT) uživatele nebo aplikace. Vlastnosti deklarace identity se liší podle organizace a konfigurace Azure Active Directory. |

#### <a name="api-properties-schema"></a>Schéma vlastností rozhraní API

[Události rozhraní API](apis.md) mají následující vlastnosti.

| Pole                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Vždy `ApiEvent` označující událost protokolu jako událost rozhraní API.                                                                 |
| `properties.userAgent`       | Agent prohlížeče odesílající požadavek nebo `unknown`.                                                                        |
| `properties.method`          | Metoda HTTP: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Relativní cesta požadavku.                                                                                          |
| `properties.origin`          | Identifikátor URI označující, odkud pochází načtení nebo `unknown`.                                                                  |
| `properties.operationStatus` | `Success` pro stavový kód HTTP < 400 <br> `ClientError` pro stavový kód HTTP < 500 <br> `Error` pro stav HTTP >= 500 |
| `properties.tenantId`        | ID organizace                                                                                                        |
| `properties.tenantName`      | Název organizace.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId volajícího.                                                                         |
| `properties.instanceId`      | `instanceId` pro Customer Insights                                                                                         |

### <a name="workflow-event-schema"></a>Schéma události pracovního postupu

Pracovní postup obsahuje několik kroků. [Ingestace zdrojů dat](data-sources.md), [sjednocení](data-unification.md), [rozšíření](enrichment-hub.md) a [export](export-destinations.md) dat. Všechny tyto kroky mohou běžet jednotlivě nebo orchestrovaně s následujícími procesy.

#### <a name="operation-types"></a>Typy operace

| OperationType     | Seskupit                                     |
| ----------------- | ----------------------------------------- |
| Příjem dat         | [Zdroje dat](data-sources.md)           |
| DataPreparation   | [Zdroje dat](data-sources.md)           |
| Mapovat               | [Sjednocení dat](data-unification.md)   |
| Párování             | [Sjednocení dat](data-unification.md)   |
| Sloučení             | [Sjednocení dat](data-unification.md)   |
| ProfileStore      | [Profily zákazníků](customer-profiles.md) |
| Vyhledávat            | [Profily zákazníků](customer-profiles.md) |
| Aktivita          | [Aktivity](activities.md)                  |
| AttributeMeasures | [Segmenty a míry](segments.md)      |
| EntityMeasures    | [Segmenty a míry](segments.md)      |
| Opatření          | [Segmenty a míry](segments.md)      |
| Segmentace      | [Segmenty a míry](segments.md)      |
| Rozšíření        | [Rozšíření](enrichment-hub.md)                                          |
| Analytické nástroje      | [Předpovědi](predictions-overview.md)                                          |
| AiBuilder         | [Předpovědi](predictions-overview.md)                                          |
| Přehledy          | [Předpovědi](predictions-overview.md)                                          |
| Export            | [Exporty](export-destinations.md)                                          |
| ModelManagement   | [Předpovědi](custom-models.md)                                           |
| Relace      | [Sjednocení dat](relationships.md)                                           |

#### <a name="field-description"></a>Popis pole

| Pole           | DataType  | Povinné/volitelné | Description                                                                                                                                                   | Příklad                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Časové razítko | Požaduje se          | Časové razítko události (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Požaduje se          | ResourceId instance, která událost vyslala.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Požaduje se          | Název operace představované touto událostí. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Viz [typy operací](#operation-types) pro referenci. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Požaduje se          | Kategorie protokolu události. Vždy `Operational` pro události pracovního postupu                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Požaduje se          | Stav události. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Dlouhé celé číslo      | Volitelné          | Doba trvání operace v milisekundách.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Volitelné          | Objekt JSON s více vlastnostmi pro konkrétní kategorii událostí.                                                                                        | Viz podsekce [vlastnosti pracovního postupu](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Požaduje se          | Úroveň závažnosti události.                                                                                                                                  | `Informational`, `Warning` nebo `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Schéma vlastností pracovního postupu

Události pracovního postupu mají následující vlastnosti.

| Pole              | Workflow | Úloha | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ano      | Ano  | Vždy `WorkflowEvent` označující událost jako událost pracovního postupu.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ano      | Ano  | Identifikátor běhu pracovního postupu. Všechny události pracovního postupu a úkolů v rámci provádění pracovního postupu mají stejné `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ano      | Ano  | Identifikátor operace, viz [Typy operací](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Ano      | No   | Pouze pracovní postup. Počet úloh, které aktivuje pracovní postup.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ano      | No   | Nepovinné. Pouze pracovní postup událostí. Azure Active Directory [objectId uživatele](/azure/marketplace/find-tenant-object-id#find-user-object-id), který spustil pracovní postup, viz také `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ano      | No   | `full` nebo `incremental` aktualizace.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ano      | No   | `OnDemand` nebo `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ano      | No   | `Running` nebo `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ano      | Ano  | Časové razítko UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ano      | Ano  | Časové razítko UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ano      | Ano  | Časové razítko UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ano      | Ano  | `instanceId` pro Customer Insights                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Ano  | - Jestliže OperationType = `Export`, identifikátor představuje guid pro konfiguraci exportu. <br> - Jestliže OperationType = `Enrichment`, jedná se o identifikátor guid rozšíření <br> - Jestliže OperationType = `Measures` a `Segmentation`, identifikátor je název entity. |
| `properties.friendlyName`                    | No       | Ano  | Uživatelsky přívětivý název exportu nebo zpracovávané entity.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ano  | Nepovinné. Chybová zpráva s více podrobnostmi.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ano  | Nepovinné. Pouze pro OperationType = `Export`. Identifikuje typ exportu. Další informace najdete v [přehledu exportu cílů](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ano  | Nepovinné. Pouze pro OperationType = `Export`. Obsahuje seznam konfigurovaných entit v exportu.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ano  | Nepovinné. Pouze pro OperationType = `Export`. Podrobná zpráva pro export.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ano  | Nepovinné. Pouze pro OperationType = `Segmentation`. Udává celkový počet členů segmentu.                                                                                                                                                    |
