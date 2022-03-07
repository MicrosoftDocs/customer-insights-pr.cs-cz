---
title: Nové a připravované funkce
description: Informace o nových funkcích, vylepšeních a opravách chyb.
ms.date: 03/02/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 0e25ed4e4e25b130fda410d4ba1c78caded7f0f9
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088277"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Co je nového ve funkci přehledů cílové skupiny Dynamics 365 Customer Insights



S radostí představujeme naše nejnovější aktualizace! Tento článek shrnuje funkce Public Preview, rozšíření obecné dostupnosti a aktualizace funkcí. Chcete-li zobrazit dlouhodobé plány funkcí, projděte si [plány vydávání Dynamics 365 a Power Platform](/dynamics365/release-plans/).

Zavádíme aktualizace podle oblastí. Některé oblasti tedy budou disponovat funkcemi dříve než ostatní. Pokud není uvedeno jinak, nemusíte podnikat žádné kroky a my automaticky aktualizujeme aplikaci bez prostojů.

> [!TIP]
> Pokud chcete zasílat žádosti o funkce a návrhy na produkty a hlasovat o nich, přejděte na [portál pro nápady k aplikaci Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="january-2022-updates"></a>Aktualizace z ledna 2022

Aktualizace v lednu 2022 zahrnují nové funkce, upgrady výkonu a opravy chyb.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analýza postoje v názorech vašich zákazníků

Customer Insights poskytuje novou funkci založenou na umělé inteligenci, která syntetizuje sentiment zákazníků a identifikuje konkrétní obchodní aspekty jako příležitosti pro cílená zlepšení. Analýzou písemné zpětné vazby vašich zákazníků můžete získat přesné informace za nízkou cenu. Analýza zabarvení založená na modelech zpracování přirozeného jazyka (NLP), které generují dva odvozené přehledy pro každé ID zákazníka. Skóre zabarvení (od –5 do 5) a seznam použitelných obchodních aspektů. 

Více informací viz [Analýza zabarvení v názorech zákazníků (preview)](sentiment-analysis.md).


## <a name="december-2021-updates"></a>Aktualizace z prosince 2021

Aktualizace v prosinci 2021 zahrnují nové funkce, upgrady výkonu a opravy chyb.

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>Předávání protokolů Customer Insights do Azure Monitor

Customer Insights poskytuje přímou integraci s Azure Monitor. Tato funkce zahrnuje události auditu a provozní události. Protokoly prostředků Azure Monitor umožňují monitorovat a odesílat protokoly do Azure Storage, Azure Log Analytics nebo je streamovat do Azure Event Hubs.

Více informací najdete v tématu [Přesměrování protokolů v Dynamics 365 Customer Insights s Azure Monitor (Preview)](diagnostics.md).

### <a name="enrich-customer-profiles-with-engagement-data"></a>Rozšíření profilů zákazníků o data o zapojení

Pomocí dat z Microsoft Office 365 můžete rozšířit profily vašich zákaznických účtů o přehledy o zapojení prostřednictvím aplikací Office 365. Data o zapojení se skládají z aktivit e-mailů a schůzek, které jsou agregovány na úrovni účtu. Například počet e-mailů z obchodního účtu nebo počet schůzek s obchodním vztahem. Nejsou sdílena žádná data o jednotlivých uživatelích. Toto rozšíření je k dispozici pouze v následujících oblastech: Spojené království, Evropa, Severní Amerika.

Více informací viz téma [Rozšíření profilů zákazníků o data o zapojení (Preview)](enrichment-office.md).

### <a name="advanced-data-unification-features"></a>Pokročilé funkce sjednocení dat

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>Povolení zásad řešení konfliktů na úrovni jednotlivých atributů

Při deduplikaci záznamů zákazníků v rámci entity možná nebudete chtít, abyste jako vítěze museli vybrat úplný záznam. Nyní vám umožňujeme sloučit nejlepší pole z různých záznamů na základě pravidel pro každý atribut. Můžete se například rozhodnout zachovat nejnovější e-mail A nejúplnější adresu z různých záznamů. 

Nyní můžete definovat samostatná pravidla slučování pro jednotlivé atributy a zároveň deduplikovat a slučovat záznamy v rámci jedné entity. Dříve jsme vám umožňovali vybrat pouze jediné pravidlo sloučení (udržování záznamů na základě úplnosti dat aktuálnosti) a toto pravidlo bylo aplikováno na úrovni záznamu na všechny atributy. Toto není ideální v případě, kdy se některá data, která chcete zachovat, nacházejí v záznamu A a jiná dobrá data v záznamu B.

Další informace viz [Definování zrušení duplicit v entitě párování](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="custom-rules-for-matching"></a>Vlastní pravidla pro párování

Jsou chvíle, kdy potřebujete určit výjimku z obecných pravidel, aby se záznamy NEspárovaly. To se může stát, když více jednotlivců sdílí dostatek informací, takže je systém spáruje jako jednoho jednotlivce. Například dvojčata se stejným příjmením, žijící ve stejném městě a mající stejný datum narození.

Výjimky zajišťují, že nesprávné sjednocení dat lze řešit v pravidlech sjednocení. K pravidlu můžete přidat více výjimek.

Další informace najdete v části [Přidání výjimek do pravidla](match-entities.md#add-exceptions-to-a-rule).

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>Zadání dalších zásad řešení konfliktů a povolení seskupování atributů

Tato funkce umožňuje zacházet se skupinou polí jako s jednou jednotkou. Například když naše záznamy obsahují pole Adresa1, Adresa2, Město, Stát a PSČ. Pravděpodobně nechceme sloučit adresu2 do jiného záznamu kvůli tomu, že by to udělalo naše data úplnější.

Nyní můžete zkombinovat skupinu souvisejících polí a použít na skupinu jedinou zásadu sloučení. 

Více informací viz část [Kombinace skupiny polí](merge-entities.md#combine-a-group-of-fields).


## <a name="november-2021-updates"></a>Aktualizace z listopadu 2021

Aktualizace v listopadu 2021 zahrnují nové funkce, upgrady výkonu a opravy chyb.

### <a name="segment-membership-now-available-in-dataverse"></a>Nyní je v Dataverse dostupné členství v segmentu

Informace o členství v segmentu pro profily zákazníků jsou nyní dostupné v Dataverse spolu s profily a přehledy zákazníků. Akční aplikace a modelem řízené aplikace Dynamics 365 mohou tato data použít k vyhledání podrobností o členství v segmentu pro daného zákazníka.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Aktivity podporují podrobnosti na úrovni kontaktů pro obchodní účty

Nyní můžete konfigurovat, zobrazovat a filtrovat aktivity kontaktů na časových osách aktivit vašeho obchodního účtu, abyste lépe pochopili, které kontakty obchodního vztahu se účastnily konkrétních aktivit.

## <a name="october-2021-updates"></a>Aktualizace říjen 2021

Aktualizace v říjnu 2021 zahrnují nové funkce, upgrady výkonu a opravy chyb.

### <a name="b-to-b"></a>B2B

Od října 2021 můžete v Customer Insights pracovat s obchodními účty a jejich souvisejícími kontakty. Dříve byla aplikace většinou přizpůsobena individuálním spotřebitelům. Bylo aktualizováno několik oblastí funkcí, aby podporovaly scénáře B2B nad rámec nového typu prostředí. Přehled podporovaných funkcí B2B viz [Práce s obchodními účty v přehledech cílové skupiny](work-with-business-accounts.md).

Následující části zdůrazňují některé z klíčových oblastí, které byly přizpůsobeny podpoře obchodních účtů a individuálních spotřebitelů.

#### <a name="export-segments-based-on-business-accounts"></a>Export segmentů na základě obchodních účtů

Všechny exporty segmentů v přehledech cílových skupin jsou dostupné v kontextu obchodních účtů. Většina exportů segmentů vyžaduje zvláštní konfiguraci a [kontaktní informace promítnuté](segment-builder.md#create-a-new-segment) v podkladových segmentech, aby byly platné pro firemní účty. Další informace viz [Export segmentů](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>Použití exportu LinkedIn Ads s obchodními účty

Nyní je k dispozici export LinkedIn Ads pro cílení kontaktů a společností v kontextu obchodních účtů. Když vyberete cílení na společnost jako primární cíl exportu LinkedIn, můžete exportovat segmenty postavené na obchodních účtech, aniž byste museli projektovat kontaktní informace. Další informace najdete v dokumentech o [exportu LinkedIn Ads](export-linkedin-ads.md) a rozdílech mezi [cílením kontaktů](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) a [cílením společností](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Vytváření měr založených na obchodních účtech a jejich hierarchii

Tvůrce měr umožňuje vytvářet míry v obchodních účtech a volitelně používat informace o hierarchii. Informace o hierarchii shrnují výpočet měr napříč účtem a všemi souvisejícími podúčty. Můžete například vytvořit míry typu celkové výnosy pro každou skupinu obchodních účtů identifikovaných podle jejich hierarchie. Další informace viz [Definování a správa měr](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Vytváření segmentů založených na obchodních účtech a jejich hierarchii

Tvůrce segmentů umožňuje vytvářet segmenty obchodních účtů, které volitelně zahrnují kontaktní informace pro každý účet v segmentu. Pokud máte vytvořenou hierarchii účtu, při vytváření segmentu můžete použít informace o hierarchii účtu. Další informace naleznete v tématu [Vytvoření nového segmentu](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Udržení zákazníků v obchodních účtech pomocí podrobných přehledů o tendencích odlivu zákazníků

Model predikce ztracených zákazníků nyní podporuje také obchodní účty. Riziko odchodu můžete vyhodnotit nejen pro obchodní vztah, ale i pro kombinaci obchodního vztahu a kategorie produktů nebo služeb, které si od vás koupí. Tento přídavek vám pomůže pochopit, zda je pravděpodobnější, že od vás obchodní vztah přestane nakupovat obecně nebo jen v určité kategorii zboží nebo služeb. Pro další usnadnění tento model AI také uvádí důvody, proč je pravděpodobný odliv zákazníků pro tento obchodní vztah. Další informace viz [Predikce úbytku transakcí (Preview)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Zobrazení kontaktů obchodního účtu v zobrazení zákazníka

Pokud jsou obchodní účty namapovány na související účty, aplikace Customer Insights zobrazí tyto související kontakty jako součást zobrazení podrobností o zákazníkovi. Další informace viz [Profily zákazníků](customer-profiles.md).


## <a name="september-2021-updates"></a>Aktualizace ze září 2021

Aktualizace v září 2021 zahrnují nové funkce, upgrady výkonu a opravy chyb.

### <a name="activities"></a>Aktivity

- **Vylepšení časové osy aktivity** Rozšířili jsme filtry pro časovou osu aktivity na zákaznických profilech. Kromě toho můžete použít nový filtr pro filtrování podle typu aktivity a podle data. Data lze filtrovat za různých podmínek. Další informace získáte v části [Zobrazení časových os aktivit v zákaznických profilech](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Relace

- **Podpora vztahů více kroků** Při konfiguraci aktivit a definování vztahů mezi entitami použijte vztahy více kroků. Vztahy více kroků používají mezilehlou entitu k propojení dvou entit. Při konfiguraci aktivity můžete použít vztah více kroků k připojení entity aktivity k mezilehlé entitě a poté k entitě zákazníka. Můžete kombinovat vztahy více kroků se vztahy více cest. Další informace najdete v tématu [Vztah více kroků](relationships.md#multi-hop-relationship).

- **Podpora vztahů více cest** Při konfiguraci aktivit a definování vztahů mezi entitami použijte vztahy více cest. Vztahy více cest vztahují zdrojovou entitu k více než jedné entitě. Při konfiguraci aktivity můžete použít vztah více cest k připojení entity aktivity k více než jedné entitě zákazníka. Můžete kombinovat vztahy více cest se vztahy více kroků. Další informace najdete v tématu [Vztah více cest](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Aktualizace ze srpna 2021

Aktualizace v červenci a srpnu 2021 zahrnují novou funkci, upgrady výkonu a opravy chyb.

### <a name="extensibility"></a>Rozšiřitelnost

- **Export segmentů do Klaviyo** Rozšířili jsme naše [exportní destinace tak, aby zahrnovaly Klaviyo](export-klaviyo.md). Exporty můžete nyní segmentovat, aby bylo možné vytvářet kampaně, poskytovat e-mailový marketing a používat konkrétní skupiny zákazníků pomocí Klaviyo. 


## <a name="june-2021-updates"></a>Aktualizace z června 2021

Aktualizace v červnu 2021 zahrnují několik funkcí, vylepšení výkonu a opravy chyb.

### <a name="data-ingestion"></a>Příjem dat

- **Vylepšené aktualizace postupu sjednocení dat** Nyní můžete na stránce zobrazit podrobnější a vylepšené dynamické aktualizace stavu v krocích [procesu sjednocení dat](data-unification.md). Tato funkce vám umožňuje sledovat podrobný postup, porozumět toku procesů a podniknout kroky v případě, že jakýkoli krok vyžaduje pozornost.

### <a name="extensibility"></a>Rozšiřitelnost

- **Export segmentů a dalších data do Salesforce Marketing Cloud** Rozšířili jsme naše exportní destinace o [Marketingový cloud Salesforce](export-salesforce.md). Nyní můžete exportovat segmenty a další typy dat do Salesforce Marketing Cloud prostřednictvím značkového exportu SFTP. Import dat lze v Salesforce plně automatizovat a použít k vytváření efektivnějších marketingových kampaní.  
 
- **Export segmentů do ActiveCampaign** Rozšířili jsme naše exportní destinace tak, aby zahrnovaly [Aktivní kampaň](export-active-campaign.md). Exporty můžete nyní segmentovat, aby bylo možné generovat kampaně, poskytovat e-mailový marketing a využívat konkrétní skupiny zákazníků pomocí ActiveCampaign.
 
- **Export segmentů do Sendinblue** Rozšířili jsme naše exportní destinace tak, aby zahrnovaly [Sendinblue](export-sendinblue.md). Exporty můžete nyní segmentovat, aby bylo možné generovat kampaně, poskytovat e-mailový marketing a využívat konkrétní skupiny zákazníků pomocí Sendinblue.
 
### <a name="ux-updates"></a>Aktualizace UX 

- **Nová a vylepšená stránka Zákazníci a stránka s podrobnostmi o profilu** Stránky Zákazníci a stránky podrobností profilu jsme přepracovali, tak abychom zlepšili uživatelské prostředí a zlepšili výkon. Tyto změny vám umožňují prohlížet, třídit, vyhledávat a filtrovat zákazníky. V adrese URL jsou nyní zastoupeny filtry, které umožňují bezproblémové sdílení výsledků vyhledávání s ostatními uživateli. Výsledky vyhledávání lze také uložit jako segment.    
  Stránka podrobností pro profily zákazníků nyní seskupuje data v různých podsekcích, jako jsou demografická data, ID a další atributy profilu pro lepší čitelnost. Ostatní sekce na stránce podrobností profilu jsou nyní interaktivnější. Sekce aktivit například nyní umožňuje filtrování a třídění.


## <a name="may-2021-updates"></a>Aktualizace z května 2021

Aktualizace v květnu 2021 zahrnují několik funkcí, upgrady výkonu a opravy chyb.

### <a name="data-ingestion"></a>Příjem dat

- **Zobrazení nebo úprava metadat či definice entity při připojování dat z Azure Data Lake Storage** Nyní můžete zobrazit a upravit metadata nebo definici entity v přehledech cílové skupiny při připojování dat ze složky Common Data Model ve službě Azure Data Lake Storage. Tato funkce poskytuje zpětnou vazbu v reálném čase, ověření modelu a kontrolu chyb. Umožňuje vám bezproblémově upravovat soubory model.json i manifest.json.

### <a name="extensibility"></a>Rozšiřitelnost

- **Vylepšené exporty segmentů, vlastní plán a duplikace** Nyní můžete v seznamu [zobrazit všechny exporty pro konkrétní segment](export-destinations.md#view-exports-and-export-details). Toto nové zobrazení pomáhá řídit, jak se konkrétní segment používá, a přizpůsobit stávající nebo vytvořit nové exporty.    
  Můžete [definovat vlastní plány aktualizací](export-destinations.md#schedule-and-run-exports) pro jednotlivé exporty nebo několik exportů najednou. Doposud byly všechny exporty spouštěny s každou aktualizací systému.    
  Namísto vytváření nového exportu od začátku můžete začít na základě stávajícího a ušetřit tak čas.

- **Export segmentů do služby Microsoft Advertising** Naše cíle exportu jsme rozšířili o službu Microsoft Advertising. Vytvářejte cílové skupiny shody zákazníků v Microsoft Advertising pomocí jednotných dat profilu zákazníka a používejte tyto cílové skupiny pro své reklamní kampaně. Další informace najdete v článku [Export segmentů do Microsoft Advertising](export-microsoft-advertising.md).

- **Export segmentů do služby LinkedIn Ads** Rozšířili jsme naše cíle exportu tak, aby zahrnovaly reklamní službu LinkedIn Ads a umožnili vám odemknout cílení na kontakty i cílení na společnost prostřednictvím LinkedIn exportem dat vašich sjednocených profilů zákazníka. Další informace najdete v článku [Export segmentů do služby LinkedIn Ads](export-linkedin-ads.md).


- **Export segmentů do služby Omnisend** Naše cíle exportu jsme rozšířili o Omnisend. Pomocí segmentů vytvořených v přehledech cílových skupin můžete generovat kampaně, poskytovat e-mailový marketing a využívat konkrétní skupiny zákazníků pomocí služby Omnisend. Další informace najdete v článku [Export segmentů do služby Omnisend](export-omnisend.md).

### <a name="predictions"></a>Předpovědi

- **Sestava použitelnosti vstupních dat** Sestava použitelnosti vstupních dat poskytuje konsolidovaný pohled na chyby a varování, které mohou generovat vaše předpřipravené predikce. Poskytuje také doporučení, jak zlepšit výkon modelu.    
  Sestava je k dispozici poté, co model dokončí tréninkový proces. Je vytvořena pro každý model samostatně, bez ohledu na to, zda byl úspěšně dokončen nebo ne.
  V současné době je tato funkce k dispozici pouze pro model úbytku transakcí. Další informace najdete v článku [Sestava použitelnosti vstupních dat](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relace

- **Vizualizér vztahů** Zobrazení vizualizátoru vztahů vám umožňuje vidět všechny existující vztahy mezi entitami a jejich kardinalitu. Vztahy jsou nyní uspořádány do skupin: vytvořené uživatelem, systémové a zděděné vztahy. Zobrazení můžete také exportovat jako obrázek. Další informace popisuje článek [Zobrazení vztahů](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Aktualizace z dubna 2021

Aktualizace v dubnu 2021 zahrnují několik funkcí, upgrady výkonu a opravy chyb.

### <a name="data-unification"></a>Sjednocení dat
 
- **Vylepšené možnosti sloučení pro sjednocení dat**    
  
   Nyní máme vylepšené uživatelské prostředí v konfiguraci sloučení procesu sjednocení dat. Změny zahrnují intuitivní řazení sloučených polí a podrobné statistiky kombinovaných a jednoznačných polí.

- **Změna pořadí entit a konfigurace všech zdrojových záznamů do entity Zákazník**  
      
   Nyní můžete změnit pořadí a odebrat entity z existujícího plánu sjednocení v procesu sjednocení dat. Poskytuje flexibilitu pro změnu pořadí entit v procesu párování podle obchodních potřeb. Dále povolíme zahrnutí všech neshodných záznamů do konečné entity *Zákazník*, která jim umožňuje definovat definici datové sady jejich profilu zákazníka.

### <a name="enrichments"></a>Rozšíření

 - **Nové obohacení: Vylepšené adresy**    
  
   Jsme nadšeni, že můžeme představit nové obohacení pro vylepšení adres ve vašich zákaznických datech. Adresy ve vašich datech mohou být nestrukturované, neúplné nebo nesprávné. Tato funkce využívá modely společnosti Microsoft k normalizaci a obohacení vašich adres do formátu Common Data Model pro lepší přesnost a přehledy.
 
   Další informace viz [Obohacení profilů zákazníků o vylepšené adresy](enrichment-enhanced-addresses.md).

- **Řízená konfigurace pro obohacení**    
  
   Znovu jsme navštívili konfigurační prostředí pro obohacení pomocí jednoduchého, řízeného zážitku. Nyní máte jasný postup krok za krokem pro vytváření a úpravy obohacení.
 
   Kromě toho jsme oddělili konfiguraci připojení pro obohacení třetích stran, aby bylo možné použít stejné připojení pro více obohacení. Jenom správci mohou konfigurovat nová propojení, ale vytvořená propojení jsou k dispozici správcům i přispěvatelům.    

   Další informace najdete v článku [Přehled připojení](connections.md).

- **Více rozšíření stejného typu**    
  
   Nyní uživatelům umožňujeme vytvářet a spravovat více obohacení stejného typu. Například nyní můžete vytvořit dvě samostatná obohacení adres a obohatit tak dva různé segmenty zákazníků. Platí limity na to, kolik obohacení stejného typu lze vytvořit, a liší se v závislosti na typu obohacení.
  
   Další informace viz [rozšiřování pro profily zákazníků](enrichment-hub.md).

## <a name="march-2021-updates"></a>Aktualizace z března 2021

Aktualizace v březnu 2021 zahrnují několik funkcí, upgrady výkonu a opravy chyb.

### <a name="activities"></a>Aktivity

- **Průvodce aktivitou a sémantické typy**

   Vylepšili jsme a aktualizovali prostředí mapování aktivit, abychom vás mohli provést a zjednodušit vytváření mapování aktivit. V tomto novém prostředí získají uživatelé řízené prostředí, které jim pomůže dokončit každý krok procesu. V kroku mapování aktivity si uživatel kromě výběru z mnoha typů aktivit může zvolit sémantické mapování dat *Předplatné* a / nebo *SalesOrderLine* na standardní schémata odvětví, která lze použít pro následnou spotřebu.   

   Další informace najdete v tématu [Aktivity zákazníka](activities.md).

### <a name="data-ingestion"></a>Příjem dat

- **Připojení k místním zdrojům dat pomocí datových toků a bran Power Platform** S potěšením oznamujeme náhled datových toků a místního připojení Power Platform pomocí bran v Customer Insights s přidruženým prostředím Power Platform nebo Dataverse. Jakékoli nové zdroje dat vytvořené v prostředí Customer Insights s propojeným prostředím Dataverse ve výchozím nastavení přejde na datové toky Power Platform přinášející místní datové připojení a bohatou sadu konektorů a transformačních schopností.

### <a name="extensibility"></a>Rozšiřitelnost

- **Exporty organizované v propojeních a exportech** Změnili jsme název stránky **Exportovat cíle** na **Propojení** a přidali samostatnou stránku pro **Export**. V rámci této aktualizace převedeme existující export do dvojic propojení a export pomocí tohoto propojení. Správci nyní mají jasnější údaje o odchozích datech na serveru stránky **Propojení**. Všechny uživatelské role mají přístup na stránku **Exporty**, ale pouze správci mohou povolit přispěvatelům upravovat konkrétní exporty se sdílenými propojeními.     
  Další informace viz [Přehled propojení](connections.md) a [Přehled exportů](export-destinations.md).

- **Export segmentů do služby Campaign Monitor** Naše cíle exportu jsme rozšířili o Campaign Monitor. Nyní můžete exportovat segmenty ze služby Customer Insights do seznamů služby Campaign Monitor a použít je jako základ pro vaše marketingové kampaně.    
   Další informace naleznete v článku [Export dat do služby Campaign Monitor](export-campaign-monitor.md).

- **Export segmentů do služby Constant Contact** Naše cíle exportu jsme rozšířili o Constant Contact. Nyní můžete exportovat segmenty ze služby Customer Insights do seznamů služby Constant Contact a použít je jako základ pro vaše marketingové kampaně.   
   Další informace naleznete v článku [Export dat do služby Constant Contact](export-constant-contact.md).

- **Export segmentů do služby RollWorks** Naše cíle exportu jsme rozšířili o RollWorks. Nyní můžete exportovat segmenty z Customer Insights do cílových skupin RollWorks a použít je jako základ pro vaši B2B reklamu.    
   Další informace naleznete v článku [Export dat do služby RollWorks](export-rollworks.md).

- **Export segmentů do služby Snapchat** Naše cíle exportu jsme rozšířili o Snapchat. Nyní můžete exportovat segmenty ze služby Customer Insights cílové skupině Snapchat a použít je jako základ pro vaši reklamu.     
   Další informace naleznete v článku [Export dat do služby Snapchat](export-snapchat.md).

### <a name="predictions"></a>Předpovědi

- **V prediktivních doporučeních produktů používat filtry produktů** V našem modelu doporučení produktu jsme přidali možnost používat filtry produktů. Nyní můžete vytvořit predikci, která používá pouze podmnožinu vašich produktů.    
   Další informace viz [Konfigurace filtrů produktů](predict-product-recommendation.md#configure-product-filters).

- **Vytvořit segmenty z modelových predikcí** Přidali jsme rychlý způsob vytváření segmentů pomocí výsledků modelu predikce. Na stránce s výsledky modelu můžete snadno vytvořit nový segment výběrem nové volby **Vytvořit segment**.    
  Další informace viz [Vytvoření segmentu na základě modelu predikce](prediction-based-segment.md).

- **Vysvětlení doporučení produktu** Přidali jsme informace vysvětlující klíčové faktory naučené modelem AI pro generování doporučení produktů a míru, do jaké tyto faktory přispívají k doporučením produktu. Tyto informace se přidají na obrazovku s výsledky modelu.    
   Další informace viz [Kontrola stavu a výsledků predikce](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Aktualizace z února 2021

Aktualizace v únoru 2021 zahrnují několik funkcí, vylepšení výkonu a opravy chyb.

#### <a name="extensibility"></a>Rozšiřitelnost

- **Exportovat segmenty do aplikace AdRoll**

  Cíle exportu jsme rozšířili o službu AdRoll. Nyní můžete exportovat segmenty z Customer Insights do cílových skupin AdRoll a použít je jako základ pro vaši reklamu. Další informace viz [Konektor pro AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmenty
 
- **Vytvoření duplicitního segmentu**
  
  Chcete-li vytvořit nový segment na základě existujícího, můžete nyní duplikovat segment a upravit jej tak, abyste jej dále upřesnili. 

- **Přidání dalších atributů do segmentu**

  Nyní můžete do výstupu segmentu přidat atributy, i když nejsou součástí profilu zákazníka. Například můžete do segmentu přidat ID předplatného, i když je součástí entity předplatného, která má vztah M:1 s entitou zákazníka. Pokud atribut patří k entitě provázané s entitou zákazníka, můžete nyní tyto atributy zahrnout.  

#### <a name="predictions"></a>Předpovědi

- **Vytvoření prediktivního doporučení produktů**

  Pochopení, co zákazníci chtějí nakupovat, je jedním z prvních kroků potřebných ke zlepšení obchodních výnosů a budování loajality zákazníků prostřednictvím personalizace a zapojení. Doporučování produktů, které zákazníka nezajímají, může vytvořit stěnu mezi zákazníkem a vaším podnikem a v konečném důsledku omezit celkové potenciální výnosy a zážitek zákazníka. 

  Pomocí vlastních dat nyní můžete vytvářet predikce, jaké produkty si vaši zákazníci pravděpodobně v budoucnu koupí. Další informace viz [Predikce doporučení produktů](predict-product-recommendation.md).

#### <a name="system-administration"></a>správa systému,

- **Kopírování prostředí podporuje více typů zdrojů dat**

  Správci mohou kopírovat konfigurace prostředí do nového prostředí ve stejné organizaci. Tato funkce rozšiřuje funkce kopírovacího prostředí pro případy, kdy se používají zdroje dat založené na spravovaném datovém jezeře Microsoft Dataverse nebo složce Common Data Model.

## <a name="january-2021-updates"></a>Aktualizace z ledna 2021

Aktualizace v lednu 2021 zahrnují několik funkcí, vylepšení výkonu a opravy chyb.

#### <a name="extensibility"></a>Rozšiřitelnost

- **Rozšířená funkčnost a vylepšený výkon pro export SFTP** Nyní můžete exportovat všechny výstupní entity z Customer Insights do hostitele SFTP. Dříve byl export omezen na segmentové entity. Výkon exportu SFTP navíc umožňuje větší objem dat za kratší dobu, v závislosti na výkonu vašeho hostitele SFTP.    
  Další informace viz [Konektor pro SFTP (Preview)](export-sftp.md).  

#### <a name="segments"></a>Segmenty

- **Navrhované segmenty využívají strojové učení ke zlepšení metrik** Nový způsob objevování a vytváření segmentů. Systém používá model AI k navrhování segmentů, což může zlepšit ukazatel KPI (míru), který již sledujete. Ukazujeme rozsah vlivu atributů, které vyberete na míře nebo jiném primárním atributu. Tyto informace pomáhají najít potenciální segmenty, které představují příležitosti.    
  Další informace viz [Navrhované segmenty (Preview)](suggested-segments.md).

#### <a name="data-unification"></a>Sjednocení dat

- **Vylepšený prostředí párování** V oblasti sjednocení dat bylo aktualizováno prostředí párování. To vám umožňuje konfigurovat a zobrazovat pravidla párování, včetně podrobných statistik, které vám dále vysvětlí, jak párování funguje. Existují možnosti, jak zakázat pravidlo párování, takže již nebude aktivní při zachování konfigurace, pravidel párování při přetažení apod.
  Další informace najdete v tématu [Párování entit](match-entities.md).

- **Výstup odstraněných duplicit z procesu párování je k dispozici jako entita** Výstup procesu odstranění duplicit z procesu párování je nyní zapsán do samostatné entity pro další analýzu. Tato entita se skládá z polí použitých v procesu odstranění duplicit, vítězného záznamu a odpovídajících alternativních záznamů, které jsou sloučeny s vítězným záznamem.
  Další informace viz [Výstup odebraných duplicit jako entita](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>správa systému,

- **Bezproblémové sdílení dat s Microsoft Dataverse** Nyní můžete sdílet výstup Customer Insights s aplikacemi Microsoft Dataverse využívajícími službu Data Lake spravovanou Microsoft Dataverse. Jakmile přidružíte prostředí Dataverse k Customer Insights, budete moci povolit sdílení dat.
  Další informace naleznete v tématu [Správa prostředí](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]