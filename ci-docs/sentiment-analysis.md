---
title: Analýza postoje pro názory zákazníků (Preview)
description: Naučte se používat model analýzy postoje v názorech zákazníků v Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: af1afd3eff8a795a9e199b1c1d411b79dc2841b4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055528"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analýza postoje na základě názorů zákazníků (Preview)

Dnešní zákazníci očekávají vysoce kvalitní produkty, služby a prostředí. Zejména zákazníci, kteří sdílejí své názory. Pro organizace je velmi náročné analyzovat rostoucí objem dat, aniž by utrpěla přesnost a nenarostly pracovní náklady. Dynamics 365 Customer Insights nabízí model analýzy postoje na základě názorů zákazníků, který organizacím umožňuje přesněji a s nižšími náklady analyzovat svá data.

Analýza postoje umožňuje syntetizovat postoje zákazníků a identifikovat obchodní aspekty jako příležitosti ke zlepšení. Tato funkce Customer Insights vám pomůže pochopit, co funguje dobře a co musíte zlepšit. Zaměřte se na nejrelevantnější oblasti s největším dopadem, abyste zlepšili dojem svých zákazníků. V konečném důsledku vám analýza může pomoci s vykonáním podnikatelských kroků, které povedou k vysoké spokojenosti a loajalitě zákazníků.

## <a name="overview"></a>Přehled

Funkce analýzy postoje generuje dva odvozené přehledy podle ID zákazníka. Skóre postoje (od -5 do 5) a seznam příslušných obchodních aspektů (oblastí podnikání) vám společně pomohou lépe porozumět názorům zákazníků. 

Tyto informace vám mohou pomoci dosáhnout následujících výsledků: 
- Získáte přehled o postojích zákazníků vůči značce nebo organizaci
- Identifikujete zákazníky s negativním postojem, na které zaměříte svou kampaň a zapojení, které optimalizujete pro vyšší návratnost  
- Identifikujete obchodní aspekty s problémy, na které poukážou zákazníci  
- Segmentujete zákazníky na základě jejich postoje, abyste mohli vést personalizované kampaně s cíleným prodejem, marketingem a podporou
- Optimalizujete obchodní operace zaměřením na oblasti zájmu nebo příležitosti zmíněné zákazníky
- Rozpoznáte obchodní aspekty, které fungují, a odměníte spokojené zákazníky prostřednictvím věrnostních a propagačních programů

Abychom zajistili, že výsledkům modelů můžete důvěřovat, poskytujeme transparentní informace o tom, jak se modely rozhodují. Získáte seznam slov, která měla vliv na rozhodnutí modelů při přiřazení určitého skóre postoje nebo obchodního aspektu ke komentářům s názory zákazníků.  

Používáme dva **modely zpracování přirozeného jazyka (NLP)**: První model přiřadí každému komentáři s názory skóre postoje. Druhý model přidruží každý názor ke všem vhodným obchodním aspektům. Modely jsou trénovány na veřejných datech ze zdrojů napříč sociálními médii, maloobchodem, restauracemi, spotřebním zbožím a automobilovým průmyslem.    
  
Předdefinované obchodní aspekty modelu, které jsou přidruženy k datům názorů, zahrnují následující položky:
-   Správa účtů
-   Pokladna a platba
-   Zákaznická podpora
-   Vyzvednutí v obchodě
-   Přeprava a vyzvednutí obalů
-   Předobjednání
-   Cena
-   Ochrana osobních údajů a zabezpečení
-   Propagační akce a odměny
-   Příjem a záruka
-   Vrácení výměnou a zrušení
-   Přesnost plnění
-   Kvalita webu/aplikace

> [!NOTE]
> V současné době podporujeme analýzu postoje na základě názorů zákazníků pouze v angličtině. Podpora dalších jazyků bude k dispozici v budoucnu. Pokud je odeslán názor v jiném jazyce, model bude stále vracet výsledky. Tyto výsledky však nebudou přesné. 

## <a name="prerequisites"></a>Předpoklady

Analýza postoje je založena na datech názorů ve formě textu, která prošla [procesem sjednocení dat](data-unification.md). Vřele vám doporučujeme předem [nakonfigurovat své entity dat názorů jako entity aktivit sémantického typu](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (typ názorů). 

Pro konfiguraci modelu analýzy postoje potřebujete minimálně [oprávnění přispěvatele](permissions.md).

Customer Insights dokáže zpracovat až 10 milionů záznamů názorů při jednom běhu modelu. Model umí analyzovat komentáře s názory až do 128 slov. Pokud je komentář s názory delší, analýza vezme v úvahu pouze prvních 128 slov.

### <a name="data-requirements"></a>Požadavky na data
  
Potřebujete následující atributy dat:
- Jednotné ID zákazníka (UCID) pro párování datových záznamů textových názorů s jednotlivými zákazníky. Toto ID získáte [procesem sjednocení dat](data-unification.md).
- ID zpětné vazby
- Časové razítko názorů
- Text zpětné vazby   

> [!TIP]
> Analýza postoje vyžaduje názory zákazníků v textové formě. Aktuálně lze konfigurovat pouze jednu entitu zpětné vazby. Pokud existuje více entit zpětné vazby, ještě před příjmem dat je můžete sjednotit v Power Query.

## <a name="configure-a-sentiment-analysis"></a>Konfigurace analýzy postoje 

1. V části Customer Insights přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na dlaždici **Analýza postoje zákazníků** vyberte **Použít model**.

1. V podokně **Analýza postoje zákazníků (Preview)** vyberte **Začít**.

1. V kroku **Název modelu** zadejte **Název** vaší analýzy. 

1. Zadejte **Název výstupní entity obchodního aspektu** a **Název výstupní entity skóre postoje** a poté vyberte **Další**.

1. V kroku **Požadovaná data** vyberte možnost **Přidat data**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Tok Přidat data v modelu analýzy postoje.":::

1. V podokně **Přidání dat** vyberte ze seznamu sémantický typ **Názory**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Krok konfigurace s výběrem aktivit Názory pro analýzu postoje.":::

1. Vyberte aktivity, které použít pro tuto analýzu postoje, a pak vyberte **Další**.
 
1. Namapujte atributy ve vašich datech na atributy modelu. Volbou **Uložit** použijte svůj výběr. 

1. Zobrazí se stav mapování dat. Pokračujte kliknutím na tlačítko **Další**. 

1. V kroku **Kontrola podrobností modelu** ověřte konfiguraci své analýzy postoje. Do kterékoli části konfigurace predikce se lze vrátit. Volbou **Uložit a spustit** spustíte analýzu. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Kontrolní krok modelu postoje zobrazující všechny nakonfigurované položky.":::

1. Volbou **Hotovo** opustíte konfigurační prostředí. Dokončení procesu může trvat několik hodin v závislosti na množství použitých dat. 

## <a name="review-analysis-status"></a>Kontrola stavu analýzy

1.  Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**.
2.  Vyberte předpověď, kterou chcete zkontrolovat.
- **Název predikce**: Název predikce poskytnutý při jeho vytvoření.
- **Typ predikce**: Typ modelu použitého pro predikci.
- **Výstupní entita**: Název entity pro uložení výstupu predikce. Přejděte na **Data** > **Entity**, chcete-li vyhledat entitu s tímto názvem.
- **Predikované pole**: Toto pole je vyplněno pouze pro některé typy predikcí a nepoužívá se v predikci hodnoty životnosti zákazníka.
- **Stav**: Stav spuštění predikce.
  - **Ve frontě**: Predikce čeká na dokončení dalších procesů.
  - **Aktualizace**: Predikce právě běží, aby vytvářela výsledky, které budou přenášeny do výstupní entity.
  - **Selhání**: Spuštění predikce selhalo. Podívejte se do protokolů pro další podrobnosti.
  - **Úspěch**: Predikce byla úspěšná. Vyberte Zobrazení pod svislými elipsami, abyste zkontrolovali výsledky predikce.
- **Upraveno**: Datum, kdy byla konfigurace predikce změněna.
- **Poslední aktualizace**: Datum, kdy predikce aktualizovala výsledky ve výstupní entitě.

## <a name="manage-sentiment-analysis"></a>Správa analýzy postoje

Predikce můžete optimalizovat, aktualizovat, odstraňovat nebo řešit jejich potíže. Projděte si sestavu použitelnosti vstupních dat a zjistěte v ní, jak zajistit, aby predikce byla rychlejší a spolehlivější. Další informace naleznete v tématu [Správa predikcí](manage-predictions.md).

## <a name="review-analysis-results"></a>Kontrola výsledků analýzy
 
1. Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**. 
1. Vyberte název predikce, jejíž výsledky chcete zkontrolovat. V tomto případě vyberte analýzu postoje, kterou chcete zkontrolovat. 

### <a name="summary-tab"></a>Karta Souhrn

Na stránce s výsledky jsou čtyři primární části dat. 

- **Průměrné skóre postoje**: Pomáhá vám porozumět celkovému postoji všech zákazníků. Skóre postojů jsou seskupena do tří kategorií: 
  1.    Záporný (-5 > 2)
  2.    Neutrální: (-1 > 1)
  3.    Kladný (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizuální reprezentace celkového postoje zákazníků.":::

- **Rozdělení zákazníků podle skóre postoje**: Zákazníci jsou rozděleni do záporných, neutrálních a kladných skupin na základě jejich skóre postoje. Umístěním ukazatele myši na sloupce v histogramu zobrazíte počet zákazníků a průměrné skóre postoje v každé skupině. Tato data vám mohou pomoci [vytvářet segmenty zákazníků](segments.md) na základě jejich skóre postoje.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Pruhový graf znázorňující postoje zákazníků napříč třemi skupinami postojů.":::

- **Průměrné skóre postoje v průběhu času**: Postoj zákazníka se může v průběhu času měnit. Poskytujeme trendy postojů vašich zákazníků v časovém rozmezí vašich dat. Toto zobrazení vám pomůže změřit vliv sezónních akcí, uvádění produktů na trh nebo jiných časově omezených vlivů na postoje zákazníků. Prohlédněte si graf výběrem roku, který vás zajímá, z rozevírací nabídky. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Historický graf se skórem postoje v průběhu času znázorněným jako čára.":::
 
- **Postoj napříč obchodními aspekty**: Tato tabulka uvádí průměrný postoj napříč obchodními aspekty. Pomůže vám odhadnout, které aspekty vašeho podnikání již uspokojují zákazníky a které aspekty vyžadují více pozornosti. Záznamy názorů, které nejsou v souladu s žádným z podporovaných obchodních aspektů, jsou zařazeny do kategorie **Ostatní**. Tabulka je standardně řazena abecedně. Řazení můžete upravit výběrem záhlaví tabulky.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Seznam obchodních aspektů s přidruženou hodnotou postoje a počtem zákazníků, kteří je zmiňují.":::
 
  Výběrem názvu obchodního aspektu zobrazíte další informace, jak je obchodní aspekt identifikován modelem. Toto podokno obsahuje dvě části: 

  - **Vlivná slova**: Zobrazuje hlavní slova, která ovlivnila identifikaci obchodního aspektu modelem AI v názorech zákazníků. 
    **Zobrazit urážlivá slova**: Umožňuje zahrnout urážlivá slova do seznamu z původních dat názorů zákazníků. Ve výchozím nastavení je tato funkce vypnuta.  Maskování urážlivých slov používá model AI a nemusí detekovat všechna urážlivá slova. I nadále iterujeme a trénujeme klasifikátor pro optimální výkon. Pokud objevíte urážlivé slovo, které nebylo filtrováno podle očekávání, dejte nám vědět. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Seznam vlivných slov s přepínačem pro zobrazení nebo skrytí urážlivých slov.":::
 
  - **Ukázky zpětné vazby**: Zobrazuje samotné záznamy názorů ve vašich datech. Slova jsou barevně odlišena podle jejich vlivu na identifikaci obchodního aspektu. 


### <a name="influential-words-analysis-tab"></a>Karta Analýza vlivných slov

Existují tři sekce dodatečných informací, které vysvětlují, jak funguje model postoje.
  
1. **Hlavní slova přispívající k pozitivnímu postoji**: Zobrazuje hlavní slova, která ovlivnila identifikaci pozitivního postoje modelem AI v názorech zákazníků.  
2. **Hlavní slova přispívající k zápornému postoji**: Zobrazuje hlavní slova, která ovlivnila identifikaci záporného postoje modelem AI v názorech zákazníků.  
3. **Ukázky zpětné vazby**: Zobrazuje samotné záznamy názorů, jeden s negativním postojem a druhý s pozitivním postojem. Slova v záznamech názorů jsou zvýrazněna podle jejich příspěvku k přiřazenému skóre postoje. Slova, která přispívají ke skóre pozitivního postoje, jsou zvýrazněna zeleně. Slova přispívající k zápornému skóre jsou zvýrazněna červeně.
   Volbou **Zobrazit více** načtete více ukázek zpětné vazby, které poskytují více informací a kontextu, jak model postoje funguje.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Příklady analýzy postoje na základě názorů zákazníků.":::
 
**Zobrazit urážlivá slova**: Umožňuje zahrnout urážlivá slova do seznamu z původních dat názorů zákazníků. Ve výchozím nastavení je tato funkce vypnuta.  Maskování urážlivých slov používá model AI a nemusí detekovat všechna urážlivá slova. I nadále iterujeme a trénujeme klasifikátor pro optimální výkon. Pokud objevíte urážlivé slovo, které nebylo filtrováno podle očekávání, dejte nám vědět. 

## <a name="act-on-analysis-results"></a>Práce s výsledky analýzy

V horní části stránky s výsledky modelu můžete snadno začít vytvářet nové segmenty zákazníků ze stránky s výsledky analýzy postoje volbou **Vytvořit segmenty**.

:::image type="content" source="media/create-segment-model.png" alt-text="Panel příkazů s možnostmi pro modely predikce.":::
 
## <a name="potential-bias"></a>Potenciální odchylka

Stejně jako u každé funkce, která využívá prediktivní umělou inteligenci, byste si měli být vědomi možné odchylky dat, která používáte k predikci postoje zákazníků. Pokud například shromažďujete názory pouze digitálně, můžete minout názory zákazníků, kteří s vámi primárně obchodují osobně, což může ovlivnit výstup funkce.

Vzhledem k tomu, že tato funkce využívá automatizované prostředky k vyhodnocování dat a vytváření predikcí na základě těchto údajů, lze ji proto použít jako metodu profilování, jak je tento pojem definován obecným nařízením o ochraně osobních údajů („GDPR“). Vaše použití této funkce ke zpracování dat může podléhat GDPR nebo jiným zákonům či předpisům. Zodpovídáte za to, že používání aplikace Dynamics 365 Customer Insights, včetně analýzy postoje, je v souladu se všemi platnými zákony a předpisy, včetně zákonů týkajících se soukromí, osobních údajů, biometrických údajů, ochrany dat a důvěrnosti komunikace.

[!INCLUDE [footer-include](includes/footer-banner.md)]

