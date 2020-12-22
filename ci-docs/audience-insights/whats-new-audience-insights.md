---
title: Nové a připravované funkce
description: Informace o nových funkcích, vylepšeních a opravách chyb.
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/30/2020
ms.locfileid: "4649996"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Co je nového ve funkci přehledů cílové skupiny Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

S radostí představujeme naše nejnovější aktualizace! Tento článek shrnuje funkce Public Preview, rozšíření obecné dostupnosti a aktualizace funkcí. Chcete-li zobrazit dlouhodobé plány funkcí, projděte si [plány vydávání Dynamics 365 a Power Platform](https://docs.microsoft.com/dynamics365/release-plans/).

Můžete se také podívat na následující video a dozvědět se více o plánovaných funkcích za posledních šest měsíců.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Zavádíme aktualizace podle oblastí. Některé oblasti tedy budou disponovat funkcemi dříve než ostatní. Pokud není uvedeno jinak, nemusíte podnikat žádné kroky a my automaticky aktualizujeme aplikaci bez prostojů.

> [!TIP]
> Pokud chcete zasílat žádosti o funkce a návrhy na produkty a hlasovat o nich, přejděte na [portál pro nápady k aplikaci Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2020-updates"></a>Aktualizace z listopadu 2020

Aktualizace v listopadu 2020 zahrnují několik funkcí, upgrady výkonu a opravy chyb.

### <a name="new-and-updated-features-in-november-2020"></a>Nové a aktualizované funkce v listopadu 2020

#### <a name="data-enrichment"></a>Rozšiřování dat

- **Zavedení vlastních dat rozšíření vlastním importem prostřednictvím protokolu SFTP (Secure File Transfer Protocol)**
  
  Vlastní import pomocí protokolu SFTP umožňuje importovat data rozšíření, která nemusí projít procesem sjednocení dat. Zjistěte více o vlastním importu prostřednictvím protokolu SFTP.

  Další informace viz [Rozšíření profilů zákazníků o vlastní data (Preview)](enrichment-SFTP-custom-import.md).
 
- **Rozšíření zákaznických dat o údaje o poloze od společnosti HERE Technologies**

  Se službami rozšíření dat HERE Technologies můžete dosáhnout přesnějšího porozumění polohy svých zákazníků normalizací adres, získáním zeměpisné šířky a délky atd. Zjistěte více o rozšíření od společnosti HERE Technologies.

  Další informace viz [Rozšíření profilů zákazníků od HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Sjednocení dat

- **Flexibilita umožňující profilování dat u vybraných entit a polí z vašeho účtu úložiště**

  Můžete určit, pro které datové entity a pole ze složky Common Data Model ve vašem účtu úložiště Azure Data Lake chcete povolit profilování dat jako součást procesu příjmu dat.

  Další informace viz [Připojení ke složce Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Rozšiřitelnost

- **Aktivace svých segmentů prostřednictvím služby Google Ads**

  Exportujte segmenty ze seznamu cílových skupin Google Ads a použijte tyto seznamy k inzerci ve službách Google Search, Google Display Network, YouTube a Gmail. Zjistěte více o aktivaci vašich segmentů prostřednictvím služby Google Ads.

  Další informace viz [Konektor pro Google Ads](export-google-ads.md).

- **Aktivace svých segmentů prostřednictvím služby Marketo**

  Exportujte segmenty do cílových skupin služby Marketo a použijte je pro automatizaci marketingu. Zjistěte více o aktivaci vašich segmentů prostřednictvím služby Marketo. 

  Další informace viz [Konektor pro Marketo](export-marketo.md).

- **Aktivace svých segmentů prostřednictvím služby DotDigital**

  Exportujte segmenty do služby DotDigital a použijte je pro marketingové účely. Zjistěte více o aktivaci vašich segmentů prostřednictvím služby DotDigital. 

  Další informace viz [Konektor pro DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Predikce

- **Predikce úbytku transakcí**

  Funkce predikce úbytku transakcí vám umožňuje bez pomoci datového vědce předpovědět pravděpodobnost, že zákazník přestane kupovat produkty nebo služby.  Pomocí skóre predikce můžete zkombinovat další informace o vašich zákaznících, jako je hodnota zákazníka, a vytvořit segmenty s vysokým rizikem odlivu zákazníků nebo se zákazníky s vysokou hodnotou. Tento segment slouží k přímému cílení na zákazníky prostřednictvím marketingových aktivit, zákaznické podpory a dalších scénářů ke snížení rizika odlivu zákazníků.
 
  Nakonfigurujte definici odlivu zákazníků jako časové okno specifické pro vaši firmu a definujte, kdy u zákazníků hrozí riziko odchodu. Například obchod s potravinami může považovat za rizikového zákazníka takového, který si nic nekoupil za posledních 30 dní.
 
  Jak budete pokračovat ve vytváření predikce, provedeme vás, jaká data jsou potřebná, a umožníme vám mapovat data o vaší firmě na pole potřebná k předpovědi odlivu vašich zákazníků. Můžete také nastavit plán opětovného trénování modelu na základě nových informací ve vašem systému, aby se přizpůsobil měnícím se obchodním okolnostem.
 
  Další informace viz [Predikce úbytku transakcí (Preview)](predict-transactional-churn.md).

#### <a name="system-administration"></a>správa systému,

- **Obnovit prostředí**

  Obnovení veškerého obsahu prostředí vybrané instance a nový začátek.

  Další informace najdete v článku [Obnovení existujícího prostředí](manage-environments.md#reset-an-existing-environment).


- **Připojení k účtu úložiště Azure Data Lake pomocí instančního objektu**

  Zápis datového výstupu a čtení dat z vašeho účtu úložiště pomocí instančního objektu Azure. Existující připojení k účtu úložiště mohou nadále používat klíč účtu. Nabízejí také možnost upgradu pro použití instančního objektu při postupu vpřed. Nová připojení budou založena na metodě ověřování instančního objektu pro váš účet úložiště.

  Další informace viz [Připojení k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure pro přehledy cílové skupiny](connect-service-principal.md).

## <a name="october-2020-updates"></a>Aktualizace říjen 2020

Aktualizace ze října 2020 zahrnují několik funkcí, upgrady výkonu a opravy chyb.

### <a name="new-and-updated-features-in-october-2020"></a>Nové a aktualizované funkce v říjnu 2020

#### <a name="extensibility"></a>Rozšiřitelnost

- **Export do služby Mailchimp**

Exportujte segmenty do existujících seznamů cílových skupin ve službě Mailchimp a poskytněte svým zákazníkům přizpůsobené e-mailové prostředí.

Další informace viz [Konektor pro Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Rozšiřování dat

- **Zrušení duplicit zdrojových záznamů v entitě Párování**

Určete pravidla zrušení duplicit u entit použitých v procesu párování k identifikaci duplicitních záznamů. Slučte je do jednoho záznamu a propojte všechny zdrojové záznamy s tímto sloučeným záznamem. Tento záznamu se zrušenou duplicitou bude poté použit v procesu párování mezi entitami.

Další informace viz [Definování zrušení duplicit v entitě párování](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>správa systému,

- **Orchestrace: Nová možnost aktualizace při sloučení**

Do dneška, když jste spustili proces sloučení, systém spustil všechny následné procesy, které závisí na sloučení a následných procesech. Nyní můžete ověřit výstup procesu sloučení (sjednocená entita zákazníka) před použitím v následném zpracování jako segmenty nebo míry.
Na stránce sloučení nyní můžete zvolit spuštění pouze kroku sloučení a spuštění pouze tohoto procesu. Chcete-li také aktualizovat všechny následné procesy, můžete zvolit sloučení a následné procesy. 

## <a name="september-2020-updates"></a>Aktualizace ze září 2020

Aktualizace ze září 2020 zahrnují několik funkcí, upgrady výkonu a opravy chyb.

### <a name="new-and-updated-features-in-september-2020"></a>Nové a aktualizované funkce ze září 2020

#### <a name="activities"></a>Aktivity

- **Inteligentní predikce sémantiky atributů**

Tato nová funkce predikuje sémantické typy vstupních atributů, které jsou předávány procesu sjednocení dat. Funkce využívá modely strojového učení, které zlepšují přesnost a šetří čas.

#### <a name="enrichments"></a>Rozšíření

- **Rozšíření demografických údajů od společnosti Experian**

Rozšíření demografických údajů od společnosti Experian je nyní k dispozici ve verzi Preview. Experian je světový lídr v oblasti spotřebitelských a obchodních úvěrových reportů a marketingových služeb. Se [službami rozšíření dat společnosti Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) můžete lépe porozumět svým zákazníkům díky rozšíření profilů zákazníků o demografické údaje, jako je velikost domácnosti, příjem a další.

Abyste mohli používat tuto funkci, musíte mít aktivní předplatné Experian.

Další informace viz [Rozšíření profilů zákazníků o demografické údaje společnosti Experian](enrichment-experian.md)


#### <a name="system-administration"></a>správa systému,

- **Podokno podrobností o úlohách**

Podokno podrobností o úlohách umožňuje zobrazit podrobnosti o úlohách spouštěných systémem. Je to užitečný způsob, jak identifikovat problémy s konfigurací a najít řešení.
Přečtením chybové zprávy zjistíte, jak řešit potenciální problémy.
 
- **Zpracování informací přidáno na další stránky**

Toto vylepšení přidává informace o stavu vašich entit na stránkách **Entity** a **Zákazníci**.
 
Na obou těchto stránkách navíc najdete podrobnosti o průběhu procesů a podrobnosti o úkolech.

- **Vylepšení stránky stavu systému**

Vylepšili jsme strukturu tabulky podrobností na stránce **Systém** > **Stav** při kontrole exportu dat.
 
Navíc chyby ve sloupci **Podrobnosti** jsou nyní podrobnější a použitelnější. 
 
- **Zrušení vrácení úlohy zpět do předchozího stavu**

Když zrušíte úlohu, například během procesu párování, vrátí se zpět do předchozího stavu. Například pokud byl proces párování dokončen včera a dnes jej zrušíte, vrátí se do včerejšího úspěšně dokončeného stavu.


## <a name="august-2020-updates"></a>Aktualizace ze srpna 2020

Aktualizace ze srpna 2020 zahrnují několik funkcí, upgrady výkonu a opravy chyb.

### <a name="new-and-updated-features-in-august-2020"></a>Nové a aktualizované funkce ze srpna 2020

#### <a name="data-unification"></a>Sjednocení dat

- **Vylepšené prostředí pro fázi mapy během sjednocení dat**

  Prostředí pro fázi mapy během procesu sjednocení dat vám umožní vybrat plynuleji vybrat entity, atributy a definovat sémantiku.

  Změny zahrnují:
  
  - méně potřebných interakcí pro přidání entit a polí,
  - vylepšené možnosti vyhledávání na stránce mapy,
  - vizuální a snadná identifikace navrhovaného typu pole.

#### <a name="enrichment"></a>Rozšíření

- **Rozšíření náklonností k zájmům dostupné pro další trhy**

  Rozšiřujeme dostupnost rozšíření náklonností k zájmům mimo USA na pět dalších trhů: Kanada, Austrálie, Velká Británie, Francie a Německo. S tímto rozšířením můžete rozšířit svá zákaznická data o další zájmy vztahující se na tyto trhy. Rovněž obohatíme profily vašich zákazníků na těchto trzích, použitím místních patentovaných dat z aplikace Microsoft Graph.
  Další informace viz [Obohacení profilů zákazníků afinitami značky a zájmů](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Aktualizace z července 2020

Aktualizace v červenci 2020 zahrnují několik funkcí, vylepšení výkonu a opravy chyb.

### <a name="new-and-updated-features-in-july-2020"></a>Nové a aktualizované funkce v červenci 2020

#### <a name="extensibility"></a>Rozšiřitelnost

- Trigger **Power Automate pro dokončení procesu sjednocení**

  Rozšířili jsme triggery pro Power Automate a umožňujeme vám vytvořit oznámení nebo akci po dokončení aktualizace procesu sjednocení (mapa, shoda, sloučení).    
  Další informace viz [Konektor Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Rozšíření

- **Příloha obohacení afinit ke značce dostupná na dalších trzích**

  Rozšiřujeme dostupnost obohacení afinit značky za hranice Spojených států na pět dalších trhů: Kanada, Austrálie, Spojené království, Francie a Německo. Tímto rozšířením můžete na těchto trzích obohatit své zákaznické údaje o místní značky. Rovněž obohatíme profily vašich zákazníků na těchto trzích, použitím místních patentovaných dat z aplikace Microsoft Graph.
  Další informace viz [Obohacení profilů zákazníků afinitami značky a zájmů](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Aktualizace z června 2020

Aktualizace v červnu 2020 zahrnují několik funkcí, vylepšení výkonu a opravy chyb.

### <a name="new-and-updated-features-in-june-2020"></a>Nové a aktualizované funkce v červnu 2020

#### <a name="enrichment"></a>Rozšíření

- **Rozšíření firemními údaji z Leadspace**
  
  Definujte pole ve sjednocených profilech zákazníků, které se používají k vyhledávání souvisejících dat společnosti z Leadspace. Po spuštění procesu obohacení jsou profily B2B obohaceny o další atributy, včetně velikosti společnosti, umístění, odvětví a dalších.    
  Tato spolupráce umožňuje zlepšit kvalitu vašich dat pomocí vstupů ze služeb třetích stran. K použití tohoto rozšíření potřebujete licenci od Leadspace pro přístup k jejím firemním datům B2B. Systém použije tuto licenci k průběžnému rozšiřování vašich dat.    
  Další informace viz [Obohacení profilů společnosti s Leadspace](enrichment-leadspace.md).

- **Stránka centra obohacení**

  Veškeré dostupné obohacení dat od poskytovatelů obohacování první a třetí strany se konfiguruje na stejném místě. Konfigurace rozšiřování dat je plynulý zážitek, který je spravován z běžného místa.    
  Další informace viz [rozšiřování pro profily zákazníků](enrichment-hub.md).

- **Samostatné rozšíření o značku a zájmovou afinitu**

  Afinity značky a zájmů jsou nyní k dispozici ve dvou nezávislých rozšířeních. Oddělená rozšíření poskytují flexibilitu při konfiguraci a správě individuálně v závislosti na vašich obchodních požadavcích nebo potřebách.    
  Další informace viz [Rozšíření profilů zákazníků afinitami značky a zájmů](enrichment-microsoft-graph.md)

#### <a name="extensibility"></a>Rozšiřitelnost

- **Adresy URL pro sjednocené aktivity v doplňku karty zákazníka Dynamics 365, na které lze klikat**

  Sjednocené aktivity v doplňku zákaznické karty nyní zobrazují klikatelné adresy URL, pokud byly takové adresy URL definovány během konfigurace aktivit.    
  Další informace najdete v tématu [Doplněk karty zákazníka](customer-card-add-in.md).

- **Afinity značky a zájmů dostupné v doplňku karty zákazníka Dynamics 365**

  Nový ovládací prvek doplňku karty zákazníka Dynamics 365 vám umožní ukázat rozšíření o značku a zájem o vaše kontakty v aplikacích Customer Engagement Dynamics 365.    
  Další informace najdete v tématu [Doplněk karty zákazníka](customer-card-add-in.md).

- **Další triggery Power Automate**

  Rozšířili jsme triggery Power Automate a přidali následující triggery:
  - Po dokončení automatického úplného obnovení (zdroje dat, sjednocení, segmenty, míry, export) si nechte zaslat oznámení nebo proveďte akci
  - Definujte práh pro obchodní opatření. Můžete například vytvořit oznámení, které bude odesláno po překročení definované prahové hodnoty. Trigger navíc přináší informace, které vám umožní vytvářet složitější pracovní postupy v Power Automate.    
  Další informace viz [Konektor Power Automate](export-power-automate.md)

- **Exportovat do programu Facebook Ads Manager**
  
  Tato funkce umožňuje exportovat segmenty do služby Facebook Ads Manager. Segmenty se exportují jako vlastní cílové skupiny, aby bylo možné používat sjednocené profily v marketingových kampaních a reklamách na Facebooku. Vlastní segmenty cílové skupiny lze také použít k vytváření kampaní na Instagramu prostřednictvím nástroje Facebook Ads Manager.    
  Další informace viz [Konektor pro Facebook Ads Manager](export-facebook.md).

#### <a name="predictions"></a>Predikce

- **Predikce ukončení předplatného**

  Postupujte podle řízené zkušenosti a vytvořte kanál predikce ztrát v oblastech předplatného, jako jsou cloudové služby, členství zákazníků a další sektory. 

  Funkce predikce ztrát předplatného vám umožňuje předvídat pravděpodobnost, že zákazník přestane používat produkty nebo služby založené na předplatném, aniž byste zapojili odborníka na data. Pomocí skóre predikce můžete kombinovat další informace o svých zákaznících a vytvářet segmenty s vysokým rizikem ztráty. S pomocí tohoto segmentu můžete přímo cílit na zákazníky v oblasti marketingu, podpory zákazníků a dalších scénářů, abyste snížili riziko odlivu konkrétních zákazníků, abyste zvýšili výnosy a snížili náklady.

  V rámci prostředí můžete definovat definici ztrát jako časové okno specifické pro vaši firmu. Například firma zabývající se streamováním videa, která má měsíční předplatné, může předpokládat, že zákazníka ztratí 15 dní poté, co vyprší jeho předplatné.

  Při pokračování v predikci vás provedeme potřebnými údaji a umožníme vám mapovat údaje o vaší firmě do polí potřebných k předvídání ztrát zákazníků. S tím, jak se mění obchodní informace, můžete také nastavit plán, aby se v systému aktualizovaly nové informace a přizpůsobily se měnícím se obchodním okolnostem.    
  Další informace viz [Predikce ukončení předplatného (náhled)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmenty

- **Najít podobné zákazníky**
  
  Najděte podobné zákazníky ve své zákaznické základně pomocí umělé inteligence. Model binární klasifikace strojové učení přiřazuje skóre podobnosti zákazníkům v rozšířeném segmentu. Skóre je založeno na podobnosti se zákazníky ve zdrojovém segmentu. V závislosti na skóre podobnosti se profily zákazníků přidávají do nově vytvořeného segmentu.

  V digitálním marketingu bývá někdy označováno jako modelování na základě podobnosti a používá model AI k nalezení zákazníků, kteří jsou podobní jinému segmentu vašich zákazníků, a to faktoringem dalších atributů. Umožňuje vám nejen vybrat atributy, ale také určit maximální počet zákazníků, kteří by měli být v tomto novém segmentu. Model AI poté vypočítá skóre podobnosti pro každého zákazníka na základě vybraných atributů a vyhledá zákazníky s vyšším průměrným skóre podobnosti. Výsledný segment bude zahrnovat zákazníky, kteří vypadají podobně jako zákazníci ve vašem původním segmentu.    
  Další informace naleznete v článku [Podobní zákazníci](find-similar-customer-segments.md).

- **Překrytí a diferenciátory segmentu**

  Překrývání segmentů vám umožní zjistit, kolik a kteří zákazníci jsou společní pro dva nebo více segmentů. Například to, jak se segment s vysokými výdaji překrývá se segmentem zákazníků s vysokou spokojeností, nebo jak se segment v oblasti zákazníků překrývá se segmentem zákazníků s nízkou spokojeností. Kromě toho můžete analyzovat, jak se překrývání mění na základě dalšího atributu podle vašeho výběru.

  Diferenciátory segmentů odhalují, co odlišuje jeden segment od zbytku vašich zákazníků nebo od jiného segmentu. Vše, co musíte udělat, je identifikovat segment a systém identifikuje atributy profilu a opatření, která odlišují segment ve formě seřazeného seznamu diferenciátorů - od nejsilnějšího diferenciátoru k nejslabšímu.    
  Další informace viz [Přehled segmentů (náhled)](segment-insights.md).

- **Životnost segmentu**
  
  Definujte plán pro aktivaci nebo deaktivaci segmentu.    
  Další informace získáte v tématu [Správa existujících segmentů](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Aktualizace z května 2020

Aktualizace v květnu 2020 zahrnují několik funkcí, vylepšení výkonu a opravy chyb.

### <a name="new-and-updated-features-in-may-2020"></a>Nové a aktualizované funkce v květnu 2020

#### <a name="data-ingestion"></a>Příjem dat

- **Příjem dat v reálném čase: zobrazení historie**

  Při použití našeho rozhraní API k přijímání aktualizací v reálném čase můžete zobrazit až 30 dnů agregované historie těchto aktualizací. Máte přístup k agregacím všech úspěšných nebo neúspěšných volání rozhraní API, včetně jejich výsledku, zdrojového systému a dalších užitečných metadat.    
  Další informace viz [Příjem dat v reálném čase](real-time-data-ingestion.md).

- **Příjem dat v reálném čase: aktualizace profilů**

  Toto rozšíření přijímání dat v reálném čase umožňuje během několika sekund zobrazit změny v konkrétních polích uživatelského profilu.    
  Kromě funkcí pro aktivity v reálném čase podporuje systém aktualizace polí profilů s nízkou latencí. Aktualizace polí profilů v reálném čase mají čas vypršení platnosti, a proto nenahrazují plánované aktualizace.    
  Další informace viz [Příjem dat v reálném čase](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Rozšiřitelnost

- **Aktualizovaná časová osa a stránkování v řešení Doplněk karty zákazníka**

  Časová osa řešení doplňku zákaznické karty odpovídá časové ose aktivit. Stránkování časové osy se zlepšilo a nyní zobrazuje až 50 aktivit najednou. Umožňuje také načítání dalších aktivit na časové ose.    
  Další informace najdete v tématu [Doplněk karty zákazníka](customer-card-add-in.md).

- **Mění se trigger Power Automate pro segmenty**

  Triggery pro Power Automate definují, z čeho můžete vytvořit tok. Nově přidaný trigger vám umožní definovat prahovou hodnotu pro segment. Můžete například vytvořit oznámení, které bude odesláno po překročení definované prahové hodnoty.    
  Další informace viz [Konektor Power Automate](export-power-automate.md).

- **Podpora více klientů pro vlastní modely**

  Nakonfigurujte pracovní postupy pro vlastní modely pomocí webové služby jiného klienta Azure Machine Learning. Při vytváření nového pracovního postupu pro vlastní modely se můžete přihlásit do klienta Azure Machine Learning. Tato funkce je doplňkem stávající funkce integrace s vaší vlastní webovou službou Azure Machine Learning.    
  Další informace viz [Vlastní modely strojového učení](custom-models.md).

#### <a name="segments"></a>Segmenty

- **Automatizace cesty entity**

  Při vytváření segmentu musí uživatelé definovat cestu k entitě. Tato funkce provede první krok k automatizaci definice cesty entity, takže se můžete soustředit na kritéria segmentace, která máte na mysli.    
  Pokud entita, podle které chcete segmentovat své zákazníky, přímo souvisí s entitou sjednoceného zákazníka, již nemusíte definovat cestu entity. Pokud však existuje více než jedna cesta k entitě, je třeba ji definovat ručně.

- **Akce na více segmentech**
  
  Uživatelé si mohou vybrat více segmentů a jedním kliknutím s nimi provádět akce, například je aktualizovat.    

- **Aktualizovat segmenty**

  Uživatelé mohou aktualizovat jediný segment nebo vybrat pouze segmenty, které chtějí aktualizovat.    

  
- **Vylepšení složených segmentů**

  Uživatelé mohou vytvářet, upravovat a odstraňovat segmenty založené na jiných segmentech. Například segment vytvořený na jiném segmentu, který byl vytvořen na třetím segmentu.    

- **Stránka se seznamem segmentů**

  Nový design stránky segmentů používá formát seznamu, který umožňuje zobrazit více segmentů najednou. Pro rychlé nalezení segmentů je přidáno vyhledávací pole. Uživatelé mohou nyní provádět akce, jako je stahování nebo odstraňování, na více segmentech najednou. Je zavedena nová funkce trendů pro rychlou identifikaci významných změn v segmentech.    
  Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).

#### <a name="system-administration"></a>správa systému,

- **Řešení Customer Insights dostupné v Microsoft Dynamics 365 Online Government**

  S více a více kanály pro interakce jsou údaje o občanech rozptýleny v nesčetných systémech, což vede ke skladování velkých objemů dat a roztříštěnému zobrazení informací o interakcích občanů. Bez úplného zobrazení interakcí každého občana napříč kanály je nemožné, aby se vlády modernizovaly v potřebném měřítku. Společnost Microsoft je odhodlána podporovat technologické potřeby vlády, aby udržovala krok s očekáváním občanů ohledně konzistence a pohotovosti.    
  S 1. vlnou vydání v r. 2020 bude Dynamics 365 Customer Insights k dispozici pro cloud komunity státní správy (GCC), což je prostředí vytvořené pro naplnění vyšších požadavků státních úřadů Spojených států na dodržování předpisů. Úřady získají sjednocené zobrazení občanů a využijí předdefinovanou umělou inteligenci k získávání poznatků, které zlepšují interakce, posilují zaměstnance a transformují komunity, a zároveň snižují složitost IT a splňují normy a bezpečnostní standardy Spojených států. Dynamics 365 Government splňuje náročné požadavky programu Federal Risk and Authorization Management Program (FedRAMP), což federálním úřadům Spojených států umožňuje využívat úspory nákladů a přísné zabezpečení cloudu Microsoft Cloud.

## <a name="april-2020-updates"></a>Aktualizace z dubna 2020

Aktualizace v dubnu 2020 zahrnují několik funkcí, vylepšení výkonu a opravy chyb.

### <a name="new-and-updated-features-in-april-2020"></a>Nové a aktualizované funkce v dubnu 2020

#### <a name="activities"></a>Aktivity

- **Mapování entity aktivity na standardní typ aktivity**
  
  Konfigurace aktivity a úložiště jsou v současné době založeny na statickém návrhu, který umožňuje jejich zobrazení na časové ose. Sémantický význam aktivit, které mají potenciál pro vícenásobné použití v případech v AI modelech, není v současné době plně využíván. Plánujeme zlepšit dynamiku časové osy aktivit na základě typu aktivity a lepšího sémantického porozumění aktivitám. Cílem této funkce je identifikovat typ aktivity, jak je definován ve schématu Common Data Model, pro každou přijatou aktivitu.
  Další informace najdete v tématu [Aktivity zákazníka](activities.md).

#### <a name="data-ingestion"></a>Příjem dat

- **Příjem dat v reálném čase: aktivity**
  
  Příjem dat v reálném čase poskytuje data okamžitě ke spotřebě, dokud následující naplánovaná aktualizace nevytáhne tato data ze zdroje dat.    
  Další informace viz [Příjem dat v reálném čase](real-time-data-ingestion.md).

- **Vylepšení přípravy dat**
  
  Další informace o datech přijatých v entitě. Pomocí souhrnu údajů můžete porozumět charakteristikám kvality dat, což může pomoci podniknout příslušné kroky.    
  Další informace naleznete v článku [Zkoumání dat entity](entities.md#exploring-a-specific-entitys-data).

- **Příjem analytických dat z Dynamics 365 pomocí Common Data Service**
  
  Common Data Service je k dispozici jako způsob vytváření zdrojů dat. Stávající zákazníci Dynamics 365 mohou přijímat analytické entity z Common Data Service do Customer Insights. Jeden zdroj dat může současně používat totéž spravované jezero Common Data Service v prostředí Customer Insights.    
  Další informace viz [Připojení k datům v datovém jezeru spravovaném systémem Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Rozšiřitelnost

- **Export do LiveRamp**

  Aktivujte data v LiveRamp® a propojte se s více než 500 platformami napříč digitálními, sociálními a televizními ekosystémy. Využijte svá data v LiveRamp k cílení, potlačení a personalizaci reklamních kampaní.    
  Další informace viz [Konektor LiveRamp&reg;](export-liveramp.md).

- **Doplněk Teams pro Customer Insights**
  
  Bot poskytuje možnosti vyhledávání pro jednotné profily zákazníků. Zobrazí kartu s až 15 poli z výsledného zákaznického profilu. Více shod vrátí seznam výsledků, kde si můžete vybrat profil.    
  Další informace viz [Robot Teams pro Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Míry

- **Stránka se seznamem měr**
  
  Vylepšení na stránce měr zahrnují podporu akcí pro jednu míru a pro více měr najednou. Kromě toho najdete vyhledávací pole pro rychlé vyhledání a sledování měr.    
  Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).

- **Vylepšení složených měr**
  
  Uživatelé mohou vytvářet, upravovat a odstraňovat míry založené na jiných mírách. Například míra vytvořená na jiné míře, která byla vytvořena na třetí míře.

#### <a name="segments"></a>Segmenty

- **Další operátor**
  
  Operátor množiny In umožňuje segmentaci zákazníků podle několika možných hodnot řetězce. Než byl tento operátor přidán, museli jste zkonstruovat takové segmenty s více podmínkami OR. Operátor množiny In vám to umožňuje s jedinou podmínkou.    
  Další informace najdete v tématu o [vytváření a správě segmentů](segments.md).

#### <a name="system-administration"></a>správa systému,

- **Kopírování nastavení konfigurace do nového prostředí**
  
  Zkopírujte svou konfiguraci z jednoho prostředí do jiného. Při vytváření nového prostředí můžete vybrat existující prostředí, ze kterého chcete kopírovat konfiguraci. V současné době podporujeme zdroje dat, sjednocení dat, vztahy, míry a segmenty, které mají být zkopírovány. Nekopírují se přihlašovací údaje zdroje dat a samotná data.    
  Další informace naleznete v tématu [Správa prostředí](manage-environments.md).
