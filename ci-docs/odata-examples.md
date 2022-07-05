---
title: Příklady dotazů OData pro rozhraní API Customer Insights
description: Běžně používané příklady pro Open Data Protocol (OData) k dotazování rozhraní API Customer Insights za účelem kontroly dat.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54ba9f4e9baeb4b7021bb8c20a706bbb6eb1529f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081217"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Příklady dotazů OData pro rozhraní API Customer Insights

Open Data Protocol (OData) je protokol pro přístup k datům postavený na základních protokolech, jako je HTTP. Využívá běžně přijímané metodiky, jako je REST pro web. Existují různé druhy knihoven a nástrojů, které lze použít ke konzumaci služeb OData.

Tento článek uvádí některé často požadované vzorové dotazy, které vám pomohou s vytvářením vlastních implementací založených na [Rozhraní API Customer Insights](apis.md).

Ukázky dotazů musíte upravit, aby fungovaly v cílových prostředích: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}`, kde {instanceId} je GUID prostředí Customer Insights, na které se chcete dotazovat. [Operace ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) vám umožní najít {InstanceId}, k níž máte přístup.
- {CID}: GUID sjednoceného záznamu zákazníka. Příklad: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Identifikátor primárního klíče záznamu zákazníka ve zdroji dat. Příklad: `CNTID_1002`
- {DSname}: Řetězec s názvem entity zdroje dat, který se zpracovává v Customer Insights. Příklad: `Website_contacts`.
- {SegmentName}: Řetězec s názvem výstupní entity segmentu v Customer Insights. Příklad: `Male_under_40`.

## <a name="customer"></a>zákazníku

Následující tabulka obsahuje sadu vzorových dotazů pro entitu *Zákazník*.

|Typ dotazu |Příklad  | Poznámka:  |
|---------|---------|---------|
|ID jednoho zákazníka     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Alternativní klíč    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternativní klíče přetrvávají ve sjednocené entitě zákazníka       |
|Výběrem   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|v    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternativní klíč + v   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Vyhledávat  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Vrátí 10 nejlepších výsledků pro hledaný řetězec      |
|Členství v segmentu  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Vrátí přednastavený počet řádků z entity segmentace.      |

## <a name="unified-activity"></a>Sjednocená aktivita

Následující tabulka obsahuje sadu vzorových dotazů pro entitu *UnifiedActivity*.

|Typ dotazu |Příklad  | Poznámka:  |
|---------|---------|---------|
|Aktivita CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Vypisuje aktivity konkrétního profilu zákazníka |
|Časový rámec aktivity    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktivity zákaznického profilu v časovém rámci       |
|Typ aktivity    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktivita podle zobrazovaného jména     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Třídění aktivity    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Řazení aktivit ve vzestupném nebo sestupném pořadí       |
|Aktivita se rozšířila z členství v segmentu  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Další příklady

Následující tabulka obsahuje sadu vzorových dotazů pro ostatní entity.

|Typ dotazu |Příklad  | Poznámka:  |
|---------|---------|---------|
|Míry CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Obohacené značky CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Rozšířené zájmy CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-klauzule + Rozbalit     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Nepodporované dotazy OData

Customer Insights nepodporuje následující dotazy:

- `$filter` na přijatých zdrojových entitách. Dotazy $filter můžete spouštět pouze na systémové entity, které vytvoří Customer Insights.
- `$expand` z dotazu `$search`. Příklad: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` z `$select`, pokud je vybrána pouze podmnožina atributů. Příklad: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` obohacené značky nebo afinity zájmu pro daného zákazníka. Příklad: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Dotaz na výstupní entity predikčního modelu prostřednictvím alternativního klíče. Příklad: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
