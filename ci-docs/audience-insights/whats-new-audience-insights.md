---
title: Nové a připravované funkce
description: Informace o nových funkcích, vylepšeních a opravách chyb.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988912"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Co je nového ve funkci přehledů cílové skupiny Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

S radostí představujeme naše nejnovější aktualizace! Tento článek shrnuje funkce Public Preview, rozšíření obecné dostupnosti a aktualizace funkcí. Chcete-li zobrazit dlouhodobé plány funkcí, projděte si [plány vydávání Dynamics 365 a Power Platform](/dynamics365/release-plans/).

Zavádíme aktualizace podle oblastí. Některé oblasti tedy budou disponovat funkcemi dříve než ostatní. Pokud není uvedeno jinak, nemusíte podnikat žádné kroky a my automaticky aktualizujeme aplikaci bez prostojů.

> [!TIP]
> Pokud chcete zasílat žádosti o funkce a návrhy na produkty a hlasovat o nich, přejděte na [portál pro nápady k aplikaci Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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

- **Export segmentů do služby RollWorks** Naše cíle exportu jsme rozšířili o RollWorks. Nyní můžete exportovat segmenty ze služby Customer Insights cílové skupině RollWorks a použít je jako základ pro vaši B2B reklamu.    
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

  Správci mohou kopírovat konfigurace prostředí do nového prostředí ve stejné organizaci. Tato funkce rozšiřuje funkci kopírování prostředí pro případy, kdy jsou použity zdroje dat založené na datovém jezeře Common Data Service nebo složce Common Data Model.

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