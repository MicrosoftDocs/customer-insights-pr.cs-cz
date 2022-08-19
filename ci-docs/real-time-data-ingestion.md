---
title: Příjem dat v reálném čase (náhled)
description: Obecné informace o schopnostech v reálném čase v Customer Insights.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2652e0868f5cc514ab6df9c150a9183cf95ae589
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246100"
---
# <a name="real-time-data-ingestion-preview"></a>Příjem dat v reálném čase (náhled)

Díky funkcím téměř v reálném čase můžete během několika sekund vidět nejnovější interakce, které vaši zákazníci provedli s vašimi produkty nebo službami.

[Plánované aktualizace](schedule-refresh.md) zahrnují velké množství záznamů a několik složitých operací. Nejprve jsou data stažena ze zdroje dat. Dále jsou data sjednocena a poté obohacena o další informace. Každé spuštění tohoto procesu může trvat minuty až hodiny.

Tato funkce v reálném čase poskytuje data okamžitě ke spotřebě, dokud následující naplánovaná aktualizace nevytáhne tato data ze zdroje dat.

Aktualizace v reálném čase mají čas vypršení platnosti, po kterém již nepřepisují hodnotu ze zdroje dat:

- Aktualizace profilu bude zachována po dobu čtyř hodin
- Činnosti budou udržovány po dobu 30 dnů

Tyto hodnoty jsou parametry volání API, které můžete změnit. Jejich cílem je zajistit, aby vaše zdrojová data zůstala vaším důvěryhodným zdrojem. Pokud chcete, aby byly aktualizace v reálném čase uchovány déle, musíte je přidat do zdroje dat, aby se stáhly během příští plánované aktualizace.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Aktualizace sjednocených polí profilu zákazníka v reálném čase

Aktualizované profily se projeví v zobrazení zákaznické karty nebo v jakékoli jiné vizualizaci během několika sekund.

Protože operace v reálném čase probíhají po sjednocení dat, vztahují se pouze na sjednocené profily zákazníků. V důsledku toho nebudou změny profilu v reálném čase aktualizovat opatření, členství v segmentech ani obohacení.

### <a name="limitations"></a>Omezení

- Profily zákazníků lze aktualizovat, ale nelze je vytvářet ani odstraňovat.
- Export aktualizací v reálném čase do externích systémů, například Power BI, v tuto chvíli není možný.

## <a name="real-time-creation-of-activities"></a>Tvorba aktivit v reálném čase

Rozhraní API v reálném čase umožňuje publikovat novou aktivitu ze zdrojového systému (samostatný zdrojový záznam) ve sjednoceném profilu zákazníka. Nová aktivita bude k dispozici jako sjednocená aktivita na časové ose tohoto sjednoceného zákaznického profilu během několika sekund. Časovou osu můžete vidět v zobrazení zákaznické karty nebo v jakékoli jiné integraci časové osy, kterou jste nakonfigurovali.

> [!NOTE]
>
> - Aktivity jsou neměnné. Jakmile se jednou vytvoří, nezmění se.
> - V současné době se segmenty a měření na základě nové aktivity neaktualizují.
> - Aktivity přidané pouze prostřednictvím rozhraní API v reálném čase nejsou součástí exportu a nebudou se zobrazovat v PowerBI.

K rozhraní API v reálném čase se můžete připojit dvěma způsoby:

- [nepřímo](#connect-via-the-dynamics-365-customer-insights-connector), pomocí konektoru [Dynamics 365 Customer Insights](/connectors/customerinsights/)
- [přímo](#connect-directly-to-the-real-time-api), s kódem

Oba způsoby mají společné následující předpoklady:

- Prostředí Customer Insights
- Sjednocené profily zákazníka
- Nakonfigurované a spuštěné činnosti
- Oprávnění přispěvatele nebo správce k ověření vašeho účtu

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Připojení přes konektor Dynamics 365 Customer Insights

Rozhraní API v reálném čase může ingestovat data z vyhrazeného konektoru Power Platform, konektoru [Dynamics 365 Customer Insights](/connectors/customerinsights/), bez nutnosti zapisovat a nasazovat kód.    
Konektor může provádět stejné akce v reálném čase jako API. Pro prémiové konektory potřebujete platnou licenci. Další informace získáte v části [Nejčastější dotazy k licencování Power Apps a Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps a/nebo Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

Podrobnosti o vytváření toků viz [dokumentace Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Připojení se přímo k rozhraní API v reálném čase

Funkce v reálném čase můžete využít vytvořením vlastního kanálu a přímým připojením k rozhraní API v reálném čase.    
Aktivitu můžete zveřejnit ve formátu zdrojového systému nebo ve formátu UnifiedActivity. Formát získejte voláním rozhraní API /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Podrobnosti o tomto rozhraní API, včetně parametrů a odpovědí, najdete v sekci **EntityData** v části [Referenční informace o rozhraních API v Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Další informace naleznete v části [Práce s rozhraními API v Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Využití v reálném čase pomocí telemetrie

Získejte přehled o objemu požadavků na rozhraní API v reálném čase a informace o problémech, se kterými se systém může setkat. Můžete [přistupovat k telemetrii v reálném čase](system.md#view-api-usage). 


[!INCLUDE [footer-include](includes/footer-banner.md)]
