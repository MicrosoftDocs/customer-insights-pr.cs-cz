---
title: Analýza postoje pro názory zákazníků (Preview)
description: Naučte se používat model analýzy postoje v názorech zákazníků v Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610453"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analýza postoje na základě názorů zákazníků (Preview)

Analýza postoje umožňuje syntetizovat postoje zákazníků a identifikovat obchodní aspekty jako příležitosti ke zlepšení. Tato funkce Customer Insights vám pomůže pochopit, co funguje dobře a co musíte zlepšit. Může vám pomoci s vykonáním podnikatelských kroků, které povedou k vysoké spokojenosti a loajalitě zákazníků.

## <a name="overview"></a>Přehled

Funkce analýzy postoje generuje dva odvozené přehledy podle ID zákazníka. Skóre postoje (od −5 do 5) a seznam příslušných obchodních aspektů (oblastí podnikání), které vám společně pomohou lépe porozumět názorům zákazníků.

Tato analýza vám pomůže:
- Získáte přehled o postojích zákazníků vůči značce nebo organizaci
- Identifikujete zákazníky s negativním postojem, na které zaměříte svou kampaň a zapojení, které optimalizujete pro vyšší návratnost  
- Identifikujete obchodní aspekty s problémy, na které poukážou zákazníci  
- Segmentujete zákazníky na základě jejich postoje, abyste mohli vést personalizované kampaně s cíleným prodejem, marketingem a podporou
- Optimalizujete obchodní operace zaměřením na oblasti zájmu nebo příležitosti zmíněné zákazníky
- Rozpoznáte obchodní aspekty, které fungují, a odměníte spokojené zákazníky prostřednictvím věrnostních a propagačních programů

Model poskytuje seznam slov, která měla vliv na rozhodnutí modelu při přiřazení určitého skóre postoje nebo obchodního aspektu ke komentářům s názory zákazníků.  

Používáme dva **modely zpracování přirozeného jazyka (NLP)**: První model přiřadí každému komentáři s názory skóre postoje. Druhý model přidruží každý názor ke všem vhodným obchodním aspektům. Modely jsou trénovány na veřejných datech ze zdrojů napříč sociálními médii, maloobchodem, restauracemi, spotřebním zbožím a automobilovým průmyslem.
  
Předdefinované obchodní aspekty modelu, které jsou přidruženy k datům názorů, zahrnují následující položky:
- Správa účtů
- Pokladna a platba
- Zákaznická podpora
- Vyzvednutí v obchodě
- Přeprava a vyzvednutí obalů
- Předobjednání
- Cena
- Ochrana osobních údajů a zabezpečení
- Propagační akce a odměny
- Příjem a záruka
- Vrácení výměnou a zrušení
- Přesnost plnění
- Kvalita webu/aplikace

> [!NOTE]
> V současné době podporujeme analýzu postoje na základě názorů zákazníků pouze v angličtině. Podpora dalších jazyků bude k dispozici v budoucnu. Pokud je odeslán názor v jiném jazyce, model bude stále vracet výsledky. Tyto výsledky však nebudou přesné.

## <a name="prerequisites"></a>Předpoklady

- Alespoň [oprávnění Přispěvatel](permissions.md)
- [Sjednocená](data-unification.md) data textové zpětné vazby. Vřele vám doporučujeme [nakonfigurovat své entity dat názorů jako entity aktivit sémantického typu](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (typ názorů).
- Sjednocené ID zákazníka (UCID) ze sjednocení dat pro párování datových záznamů textových názorů s jednotlivými zákazníky.
- ID zpětné vazby
- Časové razítko názorů
- Text zpětné vazby

Customer Insights dokáže zpracovat až 10 milionů záznamů názorů při jednom běhu modelu. Model umí analyzovat komentáře s názory až do 128 slov. Pokud je komentář s názory delší, analýza vezme v úvahu pouze prvních 128 slov.

> [!NOTE]
> Lze konfigurovat pouze jednu entitu zpětné vazby. Pokud existuje více entit zpětné vazby, zkombinujte je před příjmem dat v Power Query.

## <a name="configure-a-sentiment-analysis"></a>Konfigurace analýzy postoje

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Vytvořit** vyberte **Použít model** na dlaždici **Analýza postoje zákazníků (Preview)**.

1. Vyberte **Začínáme**.

1. Analýzu **pojmenujte** a zadejte **Název výstupní entity obchodního aspektu** a **Název výstupní entity skóre postoje**.

1. Vyberte **Další**.

1. Vyberte **Přidat data** pro **Zpětná vazba zákazníka**.

1. Vyberte typ sémantické aktivity **Zpětná vazba**, který obsahuje data zpětné vazby. Pokud aktivita nebyla nastavena, vyberte **zde** a vytvořte ji.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Krok konfigurace s výběrem aktivit Názory pro analýzu postoje.":::

1. Vyberte aktivity, které použít pro tuto analýzu postoje, a pak vyberte **Další**.

1. Namapujte atributy ve vašich datech na atributy modelu. 

1. Vyberte **Uložit**.

1. Vyberte **Další**. Krok **Zkontrolovat a spustit** zobrazuje souhrn konfigurace a poskytuje možnost provést změny před vytvořením analýzy.

1. Vyberte **Upravit** na kterémkoli z kroků ke kontrole a provedení jakýchkoli změn.

1. Pokud jste spokojení se svými výběry, volbou **Uložit a spustit** spusťte model. Vyberte **Hotovo**. Karta **Moje předpovědi** se zobrazí při vytváření predikce. Dokončení procesu může trvat několik hodin v závislosti na množství dat použitých v predikci.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Zobrazení výsledků analýzy

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Moje predikce** vyberte predikci, kterou chcete zobrazit.

Existují dvě karty výsledků.

### <a name="sumary-tab"></a>Karta Souhrn

Na stránce s výsledky jsou čtyři primární části dat.

- **Průměrné skóre postoje**: Skóre postoje pomáhá porozumět celkovému postoji všech zákazníků.
  - **Negativní** (−5 > 2)
  - **Neutrální** (−1 > 1)
  - **Kladný** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizuální reprezentace celkového postoje zákazníků.":::

- **Rozdělení zákazníků podle skóre postoje**: Zákazníci jsou rozděleni do záporných, neutrálních a kladných skupin na základě jejich skóre postoje. Umístěním ukazatele myši na sloupce v histogramu zobrazíte počet zákazníků a průměrné skóre postoje v každé skupině. Tato data vám mohou pomoci [vytvářet segmenty zákazníků](prediction-based-segment.md) na základě jejich skóre postoje.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Pruhový graf znázorňující postoje zákazníků napříč třemi skupinami postojů.":::

- **Průměrné skóre postoje v průběhu času**: Postoj zákazníka se může v průběhu času měnit. Poskytujeme trendy postojů vašich zákazníků v časovém rozmezí vašich dat. Toto zobrazení vám pomůže změřit vliv sezónních akcí, uvádění produktů na trh nebo jiných časově omezených vlivů na postoje zákazníků. Prohlédněte si graf výběrem roku, který vás zajímá, z rozevírací nabídky.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Historický graf se skórem postoje v průběhu času znázorněným jako čára.":::

- **Postoj napříč obchodními aspekty**: Průměrný postoj napříč obchodními aspekty vám pomůže odhadnout, které aspekty vašeho podnikání již uspokojují zákazníky nebo vyžadují více pozornosti. Záznamy názorů, které nejsou v souladu s žádným z podporovaných obchodních aspektů, jsou zařazeny do kategorie **Ostatní**. Seřaďte data výběrem libovolného sloupce.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Seznam obchodních aspektů s přidruženou hodnotou postoje a počtem zákazníků, kteří je zmiňují.":::

  Výběrem názvu obchodního aspektu zobrazíte, jak je obchodní aspekt identifikován modelem:

  - **Vlivná slova**: Hlavní slova, která ovlivnila identifikaci obchodního aspektu modelem AI v názorech zákazníků.
    **Zobrazit urážlivá slova**: Umožňuje zahrnout urážlivá slova do seznamu z původních dat názorů zákazníků. Ve výchozím nastavení je tato funkce vypnuta.  Maskování urážlivých slov používá model AI a nemusí detekovat všechna urážlivá slova. Pokud objevíte urážlivé slovo, které nebylo filtrováno podle očekávání, dejte nám vědět.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Seznam vlivných slov s přepínačem pro zobrazení nebo skrytí urážlivých slov.":::

  - **Ukázky zpětné vazby**: Samotné záznamy názorů ve vašich datech. Slova jsou barevně odlišena podle jejich vlivu na identifikaci obchodního aspektu.

### <a name="influential-words-analysis-tab"></a>Karta Analýza vlivných slov

Existují tři sekce dodatečných informací, které vysvětlují, jak funguje model postoje.
  
- **Hlavní slova přispívající k pozitivnímu postoji**: Hlavní slova, která ovlivnila identifikaci pozitivního postoje modelem AI v názorech zákazníků.  

- **Hlavní slova přispívající k zápornému postoji**: Hlavní slova, která ovlivnila identifikaci záporného postoje modelem AI v názorech zákazníků.

- **Ukázky zpětné vazby**: Samotné záznamy názorů, jeden s negativním postojem a druhý s pozitivním postojem. Slova v záznamech názorů jsou zvýrazněna podle jejich příspěvku k přiřazenému skóre postoje. Slova, která přispívají ke skóre pozitivního postoje, jsou zvýrazněna zeleně. Slova přispívající k zápornému skóre jsou zvýrazněna červeně.
   Výběrem možnosti **Zobrazit další** načtete další ukázky zpětné vazby.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Příklady analýzy postoje na základě názorů zákazníků.":::

**Zobrazit urážlivá slova**: Umožňuje zahrnout urážlivá slova do seznamu z původních dat názorů zákazníků. Ve výchozím nastavení je tato funkce vypnuta.  Maskování urážlivých slov používá model AI a nemusí detekovat všechna urážlivá slova. Pokud objevíte urážlivé slovo, které nebylo filtrováno podle očekávání, dejte nám vědět.

## <a name="act-on-analysis-results"></a>Práce s výsledky analýzy

V horní části stránky s výsledky modelu můžete začít vytvářet nové segmenty zákazníků ze stránky s výsledky analýzy postoje volbou **Vytvořit segmenty**.

## <a name="potential-bias"></a>Potenciální odchylka

Stejně jako u každé funkce, která využívá prediktivní umělou inteligenci, možné být odchylka dat, která používáte k predikci postoje zákazníků. Pokud například shromažďujete názory pouze digitálně, můžete minout názory zákazníků, kteří s vámi primárně obchodují osobně, což může ovlivnit výstup funkce.

Vzhledem k tomu, že tato funkce využívá automatizované prostředky k vyhodnocování dat a vytváření predikcí na základě těchto údajů, lze ji proto použít jako metodu profilování, jak je tento pojem definován obecným nařízením o ochraně osobních údajů („GDPR“). Vaše použití této funkce ke zpracování dat může podléhat GDPR nebo jiným zákonům či předpisům. Zodpovídáte za to, že používání aplikace Dynamics 365 Customer Insights, včetně analýzy postoje, je v souladu se všemi platnými zákony a předpisy, včetně zákonů týkajících se soukromí, osobních údajů, biometrických údajů, ochrany dat a důvěrnosti komunikace.

[!INCLUDE [footer-include](includes/footer-banner.md)]

