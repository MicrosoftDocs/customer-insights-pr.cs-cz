---
title: Správa neznámých profilů pomocí Customer Insights
description: Pracujte s neznámými profily zákazníků, které jsou vytvořeny a spravovány v Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776813"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Správa neznámých profilů pomocí Customer Insights

Online uživatelé internetu jsou často neidentifikovaní nebo anonymní. I ti nejvěrnější zákazníci se mohou zobrazovat jako „neznámí“, pokud nejsou přihlášeni na různých zařízeních. Pro mnoho značek jsou známí nebo ověření uživatelé v menšině navzdory rostoucím očekáváním zákazníků ohledně personalizace. Vzhledem k nejisté budoucnosti souborů cookie třetích stran pro dosažení personalizovaných prostředí je zásadní správa uživatelských preferencí na základě dat první strany.

Nezapomenutelná personalizace závisí na tom, jak dobře znáte svého zákazníka, a Customer Insights vám v tom pomáhá sledováním všech vašich zákazníků.  Na začátku cesty zákazníka nemusíte omezovat nebo zastavovat používání shromážděných dat. Customer Insights vám umožní přinést vlastní data k vytvoření zákaznických profilů neznámých uživatelů. Tyto profily pak můžete použít pro další akce, i když chybí kontaktní informace. Importujte data první strany ze zdrojů, jako jsou webové, mobilní nebo CRM systémy, do Customer Insights, čímž kontinuálně rozšíříte profily zákazníků. Po sjednocení více interakcí [změníte *neznámého* zákazníka na *známého*](unknown-to-known.md).

## <a name="sample-scenario"></a>Ukázkový scénář

Předpokládejme, že uživatel používá mobilní zařízení k procházení vašeho webu elektronického obchodu. Web přiřadí návštěvníkovi „mobile_guest123“ jako jedinečný identifikátor a vy začnete shromažďovat behaviorální aktivity na základě jeho online aktivity. Například které stránky navštívili, kolik času na těchto stránkách strávili nebo na které odkazy klikli. Neznáte jeho jméno ani e-mailovou adresu, ale tato data mohou značkám poskytnout srozumitelné informace o tomto konkrétním uživateli. Následně můžete tyto přehledy použít, až uživatel příště navštíví web. Zadejte dotaz na Customer Insights ohledně „mobile_guest123“, abyste získali seznam segmentů uživatele, například „organičtí zákazníci“, „mobilní předobjednávající zákazníci“, „zákazníci s vysokou hodnotou“ atd., nebo načtěte profil a vytvořte personalizovaná webová prostředí. Data můžete také exportovat do libovolného aktivačního systému a provést totéž.

## <a name="prerequisites"></a>Předpoklady

- Ingestování dat první strany do Customer Insights
- Každá entita má jedinečné ID, které je nastaveno jako primární klíč
- Každá entita s primárním klíčem pro personalizaci je sjednocena
- Systém pro správu obsahu webu umí používat rozhraní API (pro personalizaci webu na základě přímé komunikace s Customer Insights)

Následující tabulka ukazuje zjednodušený příklad, jak lze zachytit webové události s vysokou důležitostí.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|0|09-15-2022 9:00:00|abc123|CookieID1|Zobrazení produktů|
|2|09-18-2022 10:05:00|abc123|CookieID1|Zobrazení produktů|
|3|09-18-2022 10:10:00|abc123|CookieID1|Přidat do košíku|
|4|09-21-2022 09:05:00|abc123|CookieID1|Zobrazení produktů|

## <a name="data-ingestion"></a>Příjem dat

Další informace o dostupných možnostech ingestace dat naleznete v části [Připojení zdrojů dat](data-sources.md).

## <a name="data-unification"></a>Sjednocení dat

Další informace o sjednocení profilů zákazníků naleznete v části [Přehled sjednocení dat](data-unification.md).

## <a name="get-insights"></a>Získat přehledy

[Rozšiřte](enrichment-hub.md) svá data, sestavte [míry](measures.md) a vytvořte [segmenty](segments.md) pro další aktivaci.

Můžete například vytvořit segmenty neznámých uživatelů, kteří procházeli stejné produktové stránky, ale nedokončili objednávku.

## <a name="activation"></a>Aktivace

S daty v Customer Insights a přehledy připravenými k práci můžete Customer Insights použít k personalizaci:

1. Pomocí [rozhraní API protokolu OData](apis.md) načtěte členství v segmentu nebo profilu zákazníka Další příklady viz [Příklady dotazů OData pro rozhraní API Customer Insights](odata-examples.md).

1. [Exportujte](export-destinations.md) data do aktivačních systémů.

Příklad: Neznámý uživatel několikrát navštíví web a stránky produktů pro různé modely kožených bot. Díky těmto údajům dostupným v Customer Insights můžete neznámého uživatele zahrnout do segmentu osob, které se zajímají o kožené boty. Pomocí tohoto segmentu můžete dodat informace za účelem personalizace při tvorbě webu pro vracející se návštěvníky. Při další návštěvě web neznámého uživatele rozpozná a může mu nabídnout 10% kupón na kožené boty.

[!INCLUDE [footer-include](includes/footer-banner.md)]
