---
title: Segmenty navrhované strojovým učením
description: Nechte strojové učení vyhledat nové a zajímavé segmenty na základě atributů zákazníků.
ms.date: 02/01/2021
ms.reviewer: jimsonc
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 54655d57f4f0f723b497fe47891fd397ccb9dbf4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268218"
---
# <a name="suggested-segments-preview"></a>Navrhované segmenty (Preview)

Objevte zajímavé segmenty svých zákazníků pomocí modelu AI. Tato funkce využívající strojové učení navrhuje segmenty na základě měr nebo atributů zákazníka. Může pomoci zlepšit vaše ukazatele KPI nebo lépe porozumět vlivu atributů v kontextu jiných atributů. 

> [!NOTE]
> Funkce navrhovaných segmentů používá automatizované prostředky k vyhodnocení dat a vytváření predikcí na základě těchto dat, a proto může být použita jako metoda profilování, jak je tento pojem definován obecným nařízením o ochraně osobních údajů („GDPR“). Vaše použití této funkce ke zpracování dat může podléhat GDPR nebo jiným zákonům či předpisům. Zodpovídáte za to, že použití Dynamics 365 Customer Insights, včetně této funkce, je v souladu se všemi příslušnými zákony a předpisy, včetně zákonů týkajících se soukromí, osobních údajů, biometrických údajů, ochrany údajů a důvěrnosti komunikace.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Stránka Navrhované segmenty v Customer Insights zobrazující podrobnosti o návrhu v postranním panelu.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Navrhované segmenty pro zlepšení vašich ukazatelů KPI

Jako uživatel přehledů cílových skupin pravděpodobně máte řadu [vytvořených měr](measures.md), které pomáhají sledovat vaše klíčové ukazatele výkonu (KPI). Je důležité pochopit, jak určité atributy ovlivňují tento ukazatel KPI při vytváření segmentů a provádění vysoce cílené kampaně.   
Například sledujete míru s názvem *TotalSpendPerCustomer* (Celková útrata na zákazníka). Jako firma byste chtěli, aby toto číslo rostlo. Výběr míry jako primárního atributu vám umožní vybrat atributy, které chcete posoudit z hlediska vlivu. Řekněme *úroveň členství*, *období členství* a *povolání*. Aplikace Customer Insights pak může navrhnout segment, který vám řekne, kdo má největší vliv na tuto míru. Například *Účetní*, kteří jsou *zlatými* členy a kteří jsou ve styku s vaší firmou *alespoň pět let*, mají největší vliv na hodnotu *TotalSpendPerCustomer*. Pro každý návrh získáte odhadovanou velikost segmentu. Tyto informace můžete použít k vytvoření kampaní pro cílové publikum.

## <a name="understand-what-influences-a-customer-attribute"></a>Co ovlivňuje atribut zákazníka

Jako primární atribut můžete místo míry zvolit atribut zákazníka. Na základě vašeho výběru ovlivňujících atributů vytvoří model AI řadu návrhů, které ukazují, jak vybrané atributy ovlivňují primární atribut.   
Například vyberete *Člen odměn (ano/ne)* jako primární atribut. *Udržení*, *Povolání* a *Počet lístků podpory* jsou nastaveny jako další ovlivňující atributy. Model AI by mohl navrhnout segmenty, které udávají, že členy odměn jsou většinou IT profesionálové s udržením přes dva roky. Další návrh by mohl zdůraznit, že účetní, kteří byli udrženi déle než jeden rok a mají méně než tři lístky podpory, jsou členy odměn. 

## <a name="artificial-intelligence-usage"></a>Využití umělé inteligence

Pomocí primárního atributu a ovlivňujících atributů navrhuje algoritmus rozhodovacího stromu zajímavé segmenty. Návrhy jsou založeny na pravidlech nebo vzorech, které byly získány algoritmem AI. Jako návrhy jsou zobrazeny pouze segmenty, které se výrazně liší od průměrné populace. Porovnání s průměrnou populací je založeno na vybrané míře nebo primárním atributu.

### <a name="responsible-ai"></a>Zodpovědná AI

Navrhované segmenty vám umožňují vybrat atributy k vytvoření nových segmentů a zpracování vybraných dat. Při výběru atributů, včetně citlivých atributů, jako je rasa, sexuální orientace nebo pohlaví, musíte zajistit, abyste jste tato data mohli zpracovávat. Odpovídáte za dodržování veškerých zákonů platných pro vaši organizaci a za dodržování principů a zásad ochrany osobních údajů vaší organizace.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Různé výsledky pro primární atributy s kategorickými a číselnými hodnotami

Návrhy segmentů se liší, pokud jako primární atribut zvolíte číselný atribut nebo kategorický atribut. Hodnoty v kategorickém atributu obsahují dvě nebo více kategorií nebo typů. Číselný atribut obsahuje kvantitativní data a v určitém smyslu přestavuje míru.

S číselným atributem jako *roční příjem* nebo *období členství* jako primárním atributem systém navrhuje segmenty, které mají ve srovnání se všemi zákazníky vyšší nebo nižší průměrnou hodnotu číselného atributu.

Z kategorického atributu jako *spokojenost zákazníků* nastaveného jako primární atribut vyplynou navrhované segmenty, které mají vyšší nebo nižší procento zákazníků patřících do určité kategorie ve srovnání s procentem všech zákazníků patřících do stejné kategorie. Například, jako primární je vybrán atribut *spokojenost zákazníků*, který se skládá ze tří kategorií (*Nízká*, *Střední* a *Vysoká*). Pro každou kategorii budou navrženy segmenty, které mají výrazně vyšší nebo nižší procento zákazníků patřících do této kategorie ve srovnání s podílem všech zákazníků ve stejné kategorii. Pokud má 22 % všech zákazníků *vysokou* spokojenost, pak budou pro tuto kategorii navrženy pouze segmenty, které mají výrazně vyšší nebo nižší podíl zákazníků s *vysokou* spokojeností v porovnání s 22 %. Podobně budou navrženy segmenty pro každou z ostatních kategorií (*Nízká* a *Střední*), pokud jsou statisticky významné.

> [!NOTE]
> V současné době podporujeme pouze primární kategorické atributy, které mají až 10 kategorií. Chcete-li zobrazit návrhy segmentů na základě primárního atributu s více než 10 kategoriemi, doporučujeme seskupit některé z kategorií, abyste snížili počet kategorií na 10 nebo méně. Toto omezení se vztahuje pouze na primární atributy. Pro ovlivnění kategorických atributů aktuálně podporujeme maximálně 100 kategorií.

## <a name="generate-suggested-segments"></a>Generování doporučovaných segmentů

1. Jděte na **Segmenty**.

1. Vyberte kartu **Návrhy (preview)**.

1. Volbou **Získejte nové návrhy** spusťte průvodce.

1. Jako primární atribut uvolte míru nebo atribut zákazníka a vyberte **Další**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Výběr primárního atributu pro návrhy segmentů.":::

1. Vyberte ovlivňující atributy a vyberte **Uložit**.
   
   > [!TIP]
   > Výběr více ovlivňujících atributů zvyšuje šance na vyhodnocení, jak ovlivňují primární atribut. Nezahrnujte atributy, které nemají žádný vliv na primární atribut. Pokud jsou například všichni vaši zákazníci z konkrétní země, nezahrnujte atribut *země*, protože to nebude mít žádný dopad na výstup.

1. V závislosti na počtu profilů zákazníků a vybraných atributů může zpracování vybraných atributů trvat několik minut. 

## <a name="view-details-of-a-suggested-segment"></a>Zobrazení podrobností navrhovaného segmentu

Jakmile model AI vygeneruje návrhy, najdete je v seznamu **Segmenty** > **Návrhy (Preview)**.
 
Vyberte navrhovaný segment a prohlédněte si podrobnosti tohoto návrhu, včetně srovnání průměrné hodnoty a počtu členů segmentu. Můžete také zkontrolovat hodnoty atributů nebo pravidla, která se model AI naučil, aby navrhl vybraný segment.

## <a name="save-a-suggestion-as-a-segment"></a>Uložení návrhu jako segmentu

1. Jděte na **Segmenty** > **Návrhy (Preview)**.

1. Vyberte segment, který chcete uložit. 

1. V postranním panelu vyberte **Uložit jako segment**. 

1. Po uložení se segment zobrazí v seznamu segmentů na kartě **Všechny segmenty**. Nyní jej lze [aktualizovat, upravit nebo odstranit jako jakýkoli jiný segment](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Aktualizace nebo úprava sadu návrhů

1. Jděte na **Segmenty** > **Návrhy (Preview)**.

1. Volbou **Aktualizovat návrhy** aktualizujete návrhy při zachování konfigurovaných atributů. Nebo vyberte **Upravit atributy**, abyste upravili nakonfigurované atributy. Systém znovu spustí model AI, vygeneruje návrhy segmentů na základě nejnovějších dat a nahradí aktuální návrhy.

## <a name="limitations"></a>Omezení

1. Odhadovaná neshoda velikosti segmentu: Pokud zvolíte primární atribut, který obsahuje prázdné hodnoty, může to ovlivnit odhadovanou velikost segmentu v návrzích segmentů. Při ukládání takového segmentu se skutečná velikost segmentu může lišit od původního odhadu.
 
2. Primární atributy typu Boolean nefungují: V současné době podporujeme jako primární atribut pouze řetězcové a číselné typy dat.

3. Navrhované segmenty nejsou dostatečně odlišné: Mějte na paměti, že vybrané atributy a rozdělení hodnot těchto atributů ovlivňuje výsledky. Chcete-li dosáhnout různých výsledků, můžete změnit své ovlivňující atributy nebo dokonce svůj primární atribut.



[!INCLUDE[footer-include](../includes/footer-banner.md)]