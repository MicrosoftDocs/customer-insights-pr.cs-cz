---
title: Nové a aktualizované funkce
description: Informace o nových funkcích, vylepšeních a opravách chyb.
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: d06f8be114f558d7adadf2913107c5fd69686875
ms.sourcegitcommit: 9dd767051014e06d8d9f2f616e248573f24df4cb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/03/2022
ms.locfileid: "8843339"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novinky v řešení Dynamics 365 Customer Insights

S radostí představujeme naše nejnovější aktualizace! Tento článek shrnuje funkce Public Preview, rozšíření obecné dostupnosti a aktualizace funkcí. Chcete-li zobrazit dlouhodobé plány funkcí, projděte si [plány vydávání Dynamics 365 a Power Platform](/dynamics365/release-plans/).

Zavádíme aktualizace podle oblastí. Některé oblasti tedy budou disponovat funkcemi dříve než ostatní. Pokud není uvedeno jinak, nemusíte podnikat žádné kroky a my automaticky aktualizujeme aplikaci bez prostojů.

> [!TIP]
> Pokud chcete zasílat žádosti o funkce a návrhy na produkty a hlasovat o nich, přejděte na [portál pro nápady k aplikaci Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="may-2022-updates"></a>Aktualizace z května 2022

Aktualizace v květnu 2022 zahrnují nové funkce, upgrady výkonu a opravy chyb.

### <a name="updated-data-unification-experience"></a>Aktualizováno prostředí sjednocení dat

 Sjednocení dat vám umožňuje sjednotit kdysi nesourodé zdroje dat do jediné hlavní datové sady, která poskytuje jednotný pohled na tato data. Data mohou být sjednocena na jedné entitě nebo více entitách. Nejprve [vyberte entity a zdrojová pole](map-entities.md), [odeberte duplicitní záznamy](remove-duplicates.md), určete pravidla pro [podmínky shody](match-entities.md), a definujte, která [pole zahrnout do sjednocených profilů zákazníků](merge-entities.md).

Další informace získáte v [přehledu sjednocení dat](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Aktualizovaná domovská stránka v Customer Insights

**Domů** vás provede procesem konfigurace pro klíčové funkce a poskytuje přehled segmentů, měření a údajů o obohacení. Aktualizovali jsme prostředí, abychom na první pohled poskytovali relevantnější informace.

Další informace viz [Prozkoumání Customer Insights](home.md).

### <a name="track-usage-of-a-segment"></a>Sledování využití segmentu

Nyní můžete [sledovat použití segmentu](segments.md#track-usage-of-a-segment) v aplikacích založených na organizaci Dataverse, která je propojená s Customer Insights. U [segmentů Customer Insights používané v cestách zákazníků Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile) vás systém informuje o využití daného segmentu.

### <a name="export-to-criteo"></a>Export do Criteo

Criteo je online platforma, která uživatelům pomáhá spravovat digitální reklamu. Můžete exportovat segmenty jednotných zákaznických profilů pro generování kampaní, e-mailový marketing a využívání specifických skupin zákazníků pomocí služby Criteo.

Další informace naleznete v části [Export segmentů do Criteo (preview)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Propracovaná struktura dokumentace pro tvorbu prostředí

Znovu jsme navštívili dokumenty nápovědy týkající se vytváření a správy prostředí v Customer Insights. Články jsou nyní seskupeny pod uzlem Prostředí v obsahu. Restrukturalizované články poskytují více vodítek pro různé způsoby nastavení prostředí a mají jasnější strukturu. Pokud se chcete podělit o zpětnou vazbu, dejte nám vědět pomocí ovládacích prvků na konci článků nápovědy.

Další informace naleznete v tématu [Postup: Vytvoření nového prostředí](create-environment.md).

## <a name="april-2022-updates"></a>Aktualizace z dubna 2022

Aktualizace v dubnu 2022 zahrnují nové funkce, upgrady výkonu a opravy chyb.

### <a name="dun--bradstreet-enrichment-preview"></a>Vytvořte rozšíření Dun & Bradstreet (Preview)

Dun & Bradstreet poskytuje obchodní data, analýzy a statistiky pro podniky. Umožňuje zákazníkům s jednotnými profily zákazníků rozšiřovat data společností. Rozšíření obsahují atributy, jako je číslo DUNS, velikosti společnosti, místa, odvětví a další.

Více informací viz [Obohacení firemních profilů o Dun & Bradstreet (Preview)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Při vytváření nové míry definujte typ míry

Nyní můžete rozlišovat mezi opatřeními pro jednotlivé profily a opatřeními napříč celým vaším podnikáním. Zatímco obchodní měření se zobrazují na domovské stránce Customer Insights, měření zákazníků jsou vystavena v podrobných pohledech zákazníků.

Více informací získáte v části [Použití nástroje pro tvorbu míry k vytvoření měr od začátku](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Konsolidace dokumentace Customer Insights

Znovu jsme prošli naše články k dokumentaci a odstranili jsme zmínky o možnostech přehledů zapojení a schopnostech přehledů cílové skupiny. V budoucnu budeme důsledně odkazovat na název produktu Customer Insights, když budeme psát o základních funkcích aplikace. Tato změna také vede k významné restrukturalizaci obsahu, struktury URL a cest k souborům v základním úložišti dokumentace. Všechny vaše záložky nebo existující odkazy nadále fungují a přesměrovávají na aktualizované adresy URL.

Pokud nám chcete dát vědět, jak tuto změnu vnímáte nebo si všimnete, že něco nefunguje podle očekávání, řekněte nám to [odesláním zpětné vazby pro tuto stránku](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

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

Další informace viz [Povolení sdílení dat s Dataverse z vlastního úložiště Azure Data Lake Storage (Preview)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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