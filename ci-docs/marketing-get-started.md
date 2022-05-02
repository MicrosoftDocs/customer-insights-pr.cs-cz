---
title: Použijte jednotné profily v Dynamics 365 Marketing
description: Naučte se integrovat jednotné profily a segmenty s aplikací Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 45c59465771e4ad25ed36d5da1568e67b94cf994
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653720"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Práce s jednotnými profily zákazníků v Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) vylepšuje zkušenosti zákazníků a umožňuje vám organizovat personalizované cesty napříč všemi kontaktními body, abyste posílili vztahy a získali loajalitu. Aplikace Dynamics 365 Marketing bezproblémově spolupracuje s Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams a dalšími produkty a umožňuje vám činit rychlejší a lepší rozhodnutí s využitím výkonu dat a umělé inteligence.

Propojením dat Customer Insights s aplikací Marketing můžete:

- Cílit na jednotnné profily a segmenty zákazníků. To vám umožní zapojit každého zákazníka bez ohledu na umístění jeho dat.
- Založit dynamický obsah (například personalizované tokeny) v e-mailech, SMS a nabízených oznámeních v opatřeních, jako je věrnostní status, datum obnovení předplatného, nadřazený obchodní vztah nebo jakékoli jiné opatření, které jste zachytili v jednotném profilu Customer Insights.
- Načítat data z Marketingu do Customer Insights a kombinovat je s daty zákazníků z jiných zdrojů.
- Používat čištění dat Customer Insights, rozšíření a nástroje pro přibližné shody.


## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Používání bohatých zákaznických profilů v marketingu v reálném čase

Marketing v reálném čase umožňuje vytvářet [vlastní triggery](/dynamics365/marketing/real-time-marketing-custom-triggers), které spouštějí cesty zákazníků na základě jakékoli akce zákazníka. Čím více personalizovaná jsou vaše data, tím relevantnější a personalizovanější budou vaše cesty. Proto je kombinace aplikací Marketing a Customer Insights tak výkonná. Můžete [sjednotit data](data-unification.md) z libovolného zdroje a pak je použít k podpoře maximálně personalizovaných cest zákazníků.

Další informace: [Použití profilů a segmentů Customer Insights v marketingu v reálném čase](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Použití jednotných segmentů s odchozími cestami zákazníků

Customer Insights umožňuje zpřesnit data z mnoha zdrojů a kombinovat je do agregovaných segmentů zákazníků. [Propojením Customer Insights s odchozím marketingem](export-dynamics365-marketing.md) se tyto segmenty automaticky zobrazí *a* automaticky se aktualizují v návrháři cesta zákazníka.

Další informace: [Použití segmentů z Dynamics 365 Customer Insights s Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Stažení dat z vlastní Azure Data Lake Storage

Pokud chcete používat data Customer Insights spolu s aplikací Marketing, nejste omezeni na cloudové úložiště. Pokud už máte nastaven vlastní Azure Data Lake Storage, můžete se připojit pomocí Customer Insights a pak sdílet data s aplikací Marketing stejně jako u cloudového nastavení.

Další informace: [Povolení sdílení dat s Dataverse z vlastní Azure Data Lake Storage](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)