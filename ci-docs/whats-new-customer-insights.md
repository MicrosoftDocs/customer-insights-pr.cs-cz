---
title: Nové a připravované funkce
description: Informace o nových funkcích, vylepšeních a opravách chyb.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 25c6e2897d836854408871b2c74afa16ecba7435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645913"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novinky v řešení Dynamics 365 Customer Insights

S radostí představujeme naše nejnovější aktualizace! Tento článek shrnuje funkce Public Preview, rozšíření obecné dostupnosti a aktualizace funkcí. Chcete-li zobrazit dlouhodobé plány funkcí, projděte si [plány vydávání Dynamics 365 a Power Platform](/dynamics365/release-plans/).

Zavádíme aktualizace podle oblastí. Některé oblasti tedy budou disponovat funkcemi dříve než ostatní. Pokud není uvedeno jinak, nemusíte podnikat žádné kroky a my automaticky aktualizujeme aplikaci bez prostojů.

> [!TIP]
> Pokud chcete zasílat žádosti o funkce a návrhy na produkty a hlasovat o nich, přejděte na [portál pro nápady k aplikaci Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Aktualizace z března 2022

Aktualizace v březnu 2022 zahrnují nové funkce, upgrady výkonu a opravy chyb.

### <a name="liveramp-abilitec-enrichment-preview"></a>Rozšíření pomocí LiveRamp AbiliTec (Preview)

Společnost LiveRamp poskytuje rozlišení identity a konsolidaci zákaznických dat. Osobní identifikátory ve svých zákaznických datech můžete mapovat do grafu identity AbiliTec a přijímat ID AbiliTec. Tato ID pak můžete využít pro lepší sjednocení údajů o vašich zákaznících.

Více informací viz téma [Rozšíření profilů zákazníků daty identity z LiveRamp (Preview)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Uspořádání segmentů a měr pomocí značek a filtrů
Pokud vaše organizace udržuje mnoho segmentů nebo měr, někdy může být obtížné najít ten správný nebo správnou. Tato nová funkce umožňuje uspořádat seznamy pomocí značek a sloupců. Pomáhá rychle a snadno vyhledat data a přizpůsobit zobrazení.

Další informace najdete v tématu [Práce se značkami a sloupci](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Povolení sdílení dat s Dataverse při použití vlastního účtu úložiště

Pokud vaše prostředí používá Azure Data Lake Storage k uchovávání dat Customer Insights, sdílení dat s Microsoft Dataverse vyžaduje zvláštní konfiguraci.
Dříve bylo možné povolit sdílení dat s Dataverse, pouze když byla data uložena v našem spravovaném datovém jezeře. 

Další informace viz [Povolení sdílení dat s Dataverse z vlastního úložiště Azure Data Lake Storage (Preview)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Nové cíle exportu: Iterable a Braze

Pokračujeme v rozšiřování našeho ekosystému cílů exportu o nová připojení. Nyní můžete exportovat segmenty do platforem Iterable a Braze a používat jejich služby aktivace.

Další informace viz [Export segmentů do Iterable (Preview)](export-iterable.md) a [Export segmentů do Braze (Preview)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Vylepšení exportu do Marketo a Google Ads

Změna rozhraní API v připojených službách způsobila aktualizaci konektorů, aby fungovaly spolehlivě a hladce. Vydali jsme několik aktualizací exportu do služeb Marketo a Google Ads:

- Google Ads: Nová verze exportního konektoru Google Ads zjednodušuje ověřování a nyní umožňuje automaticky vytvářet nové cílové skupiny Google Ads. 
- Marketo: Nová verze exportního konektoru Marketo poskytuje podporu pro Marketo ID, což vám umožňuje vyhnout se duplicitě dat, aktualizovat stávající záznamy a vytvářet nové záznamy v Marketo. 


## <a name="february-2022-updates"></a>Aktualizace z února 2022

Aktualizace v únoru 2022 zahrnují nové funkce, upgrady výkonu a opravy chyb.

### <a name="general-availability-for-prediction-models"></a>Všeobecná dostupnost modelů predikce

Integrované modely predikce, včetně **úbytku předplatného**, **úbytku transakcí** a **hodnoty životnosti zákazníka (CLV)** budou obecně dostupné jako součást Customer Insights. 

Další informace naleznete v tématu [Přehled predikcí](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nový zdroj dat: Integrace s Azure Synapse Analytics (Preview)

Azure Synapse Analytics je podniková analytická služba, která urychluje čas potřebný k získání přehledů napříč datovými sklady a velkými datovými systémy.

Organizace, které již používají Azure Synapse Analytics, mohou tato data ingestovat do Customer Insights. 

Další informace najdete v tématu [Připojení ke zdroji dat Azure Synapse (Preview)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Rozšíření pomocí LiveRamp (Preview)

Společnost LiveRamp poskytuje rozlišení identity a konsolidaci zákaznických dat. Osobní identifikátory ve svých zákaznických datech můžete mapovat do grafu identity AbiliTec a přijímat ID AbiliTec. Tato ID pak můžete využít pro lepší sjednocení údajů o vašich zákaznících.

Více informací viz téma [Rozšíření profilů zákazníků daty identity z LiveRamp (Preview)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Rozšíření zdrojů dat (Preview)

Použijte data ze zdrojů, jako je Microsoft a další partneři, abyste rozšířili svá zákaznická data před jejich sjednocením. Rozšíření zdrojů dat pomáhají vytvářet vyšší úplnost a kvalitu dat, která může pomoci dosáhnout lepších výsledků, jakmile svá data sjednotíte.

Další informace najdete v tématu [Rozšíření zdrojů dat (Preview)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Změnit vlastníka prostředí

I když v Customer Insights může mít několik uživatelů oprávnění správce, vlastníkem prostředí je pouze jeden uživatel. Vylepšené prostředí vám umožňuje změnit vlastníky prostředí a nárokovat vlastnictví, pokud bývalý vlastník opustil organizaci. 

Více informací najdete v části [Změna vlastníka prostředí](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Proces přípravy dat uvádí důvod poškození u poškozených záznamů

Příprava dat nyní ukazuje důvod poškození pro všechna pole s poškozenými daty. Informace jsou poskytovány na úrovni jednotlivých záznamů pro snadnou identifikaci. 

Další informace: [Poškozené zdroje dat](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Konec fáze Preview pro funkce vykazování ve funkci přehledů zapojení

Verze Preview přehledů zapojení řešení Dynamics 365 Customer Insights skončila 15. února 2022.  
Tato změna znamená, že zkušební prostředí Customer Insights již nezahrnuje možnost vytvářet tryctýře ani jiné funkce vytváření sestav.

Zveme vás k prozkoumání a hodnocení mnoha dalších funkcí [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), platformy Microsoft Customer Data Platform (CDP).    
 
Po přechodnou dobu mají stávající účastníci verze Preview stále přístup k některým možnostem a funkcím Preview:

- Získejte kód pro instrumentaci webu nebo mobilní aplikace 
- Podívejte se na události a vlastnosti události 
- Vylepšete sjednocené profily pomocí ingestovaných a upřesněných událostí, abyste mohli využít plnou hodnotu svých zákaznických dat
  
Během přechodného období jsou zachycené události stále streamovány do připojeného Data Lake. Jakmile je tato funkce vypnuta, sdílení dat se zastaví a do připojeného úložiště nebudou odesílány žádné nové události.
Máte-li dotazy ke konci verze Preview této funkce, kontaktujte přímo tým pro svůj účet Microsoft. Váš obchodní tým vás bude informovat o nadcházejících vydáních. 

## <a name="january-2022-updates"></a>Aktualizace z ledna 2022

Aktualizace v lednu 2022 zahrnují nové funkce, upgrady výkonu a opravy chyb.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analýza postoje v názorech vašich zákazníků

Customer Insights poskytuje novou funkci založenou na umělé inteligenci, která syntetizuje sentiment zákazníků a identifikuje konkrétní obchodní aspekty jako příležitosti pro cílená zlepšení. Analýzou písemné zpětné vazby vašich zákazníků můžete získat přesné informace za nízkou cenu. Analýza zabarvení založená na modelech zpracování přirozeného jazyka (NLP), které generují dva odvozené přehledy pro každé ID zákazníka. Skóre zabarvení (od –5 do 5) a seznam použitelných obchodních aspektů. 

Více informací viz [Analýza zabarvení v názorech zákazníků (preview)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]