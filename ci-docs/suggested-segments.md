---
title: Navrhované segmenty na základě měr (Preview)
description: Nechte strojové učení vyhledat nové a zajímavé segmenty na základě atributů zákazníků.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170949"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Navrhované segmenty na základě měr (Preview)

Objevte zajímavé segmenty svých zákazníků pomocí modelu AI. Tato funkce využívající strojové učení navrhuje segmenty na základě měr nebo atributů zákazníka. Může pomoci zlepšit vaše klíčové ukazatele výkonu (KPI) nebo lépe porozumět vlivu atributů v kontextu jiných atributů.

> [!NOTE]
> Funkce navrhovaných segmentů využívá automatizované prostředky k vyhodnocování dat a vytváření predikcí na základě těchto dat. Proto ji lze použít jako metodu profilování, jak je tento pojem definován obecným nařízením o ochraně osobních údajů („GDPR“). Vaše použití této funkce ke zpracování dat může podléhat GDPR nebo jiným zákonům či předpisům. Zodpovídáte za to, že použití Dynamics 365 Customer Insights, včetně této funkce, je v souladu se všemi příslušnými zákony a předpisy, včetně zákonů týkajících se soukromí, osobních údajů, biometrických údajů, ochrany údajů a důvěrnosti komunikace.

:::image type="content" source="media/suggested-segments.png" alt-text="Stránka s navrhovanými segmenty, která obsahuje podrobnosti o návrhu v postranním panelu.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Navrhované segmenty pro zlepšení vašich ukazatelů KPI

Pokud použijete [vytvořené míry](measures.md) pro sledování svých klíčových ukazatelů výkonu, vytvořením segmentů zobrazíte vlivy na klíčové ukazatele výkonu. Tyto informace můžete použít k vedení vysoce cílené kampaně.

Například sledujete míru s názvem *TotalSpendPerCustomer* (Celková útrata na zákazníka). Jako firma byste chtěli, aby toto číslo rostlo. Výběr míry jako primárního atributu umožňuje vybrat atributy, které chcete posoudit z hlediska vlivu. Řekněme *úroveň členství*, *období členství* a *povolání*. Aplikace Customer Insights pak může navrhnout segment, který vám řekne, kdo má největší vliv na tuto míru. Například *Účetní*, kteří jsou *zlatými* členy a kteří jsou ve styku s vaší firmou *alespoň pět let*, mají největší vliv na hodnotu *TotalSpendPerCustomer*. Pro každý návrh získáte odhadovanou velikost segmentu. Tyto informace můžete použít k vytvoření kampaní pro cílové publikum.

## <a name="understand-what-influences-a-customer-attribute"></a>Co ovlivňuje atribut zákazníka

Jako primární atribut můžete místo míry zvolit atribut zákazníka. Na základě vašeho výběru ovlivňujících atributů vytvoří model AI řadu návrhů, které ukazují, jak vybrané atributy ovlivňují primární atribut.

Například vyberete *Člen odměn (ano/ne)* jako primární atribut. *Udržení*, *Povolání* a *Počet lístků podpory* jsou nastaveny jako další ovlivňující atributy. Model AI by mohl navrhnout segmenty, které udávají, že členy odměn jsou většinou IT profesionálové s udržením přes dva roky. Další návrh by mohl zdůraznit, že účetní, kteří byli udrženi déle než jeden rok a mají méně než tři lístky podpory, jsou členy odměn.

## <a name="artificial-intelligence-usage"></a>Využití umělé inteligence

Pomocí primárního atributu a ovlivňujících atributů navrhuje algoritmus rozhodovacího stromu zajímavé segmenty. Návrhy jsou založeny na pravidlech nebo vzorech, které byly získány algoritmem AI. Jako návrhy jsou zobrazeny pouze segmenty, které se výrazně liší od průměrné populace. Porovnání s průměrnou populací je založeno na vybrané míře nebo primárním atributu.

### <a name="responsible-ai"></a>Zodpovědná AI

Navrhované segmenty umožňují vybrat atributy k vytvoření nových segmentů a zpracování vybraných dat. Při výběru atributů, včetně citlivých atributů, jako je rasa, sexuální orientace nebo pohlaví, musíte zajistit, abyste jste tato data mohli zpracovávat. Odpovídáte za dodržování veškerých zákonů platných pro vaši organizaci a za dodržování principů a zásad ochrany osobních údajů vaší organizace.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Různé výsledky pro primární atributy s kategorickými a číselnými hodnotami

Návrhy segmentů se liší, pokud jako primární atribut zvolíte číselný atribut nebo kategorický atribut. Hodnoty v kategorickém atributu obsahují dvě nebo více kategorií nebo typů. Číselný atribut obsahuje kvantitativní data a v určitém smyslu přestavuje míru.

S číselným atributem jako *roční příjem* nebo *období členství* jako primárním atributem systém navrhuje segmenty, které mají ve srovnání se všemi zákazníky vyšší nebo nižší průměrnou hodnotu číselného atributu.

Z kategorického atributu jako *spokojenost zákazníků* nastaveného jako primární atribut vyplynou navrhované segmenty, které mají vyšší nebo nižší procento zákazníků patřících do určité kategorie ve srovnání s procentem všech zákazníků patřících do stejné kategorie. Například, jako primární je vybrán atribut *spokojenost zákazníků*, který se skládá ze tří kategorií (*Nízká*, *Střední* a *Vysoká*). Pro každou kategorii budou navrženy segmenty, které mají vyšší nebo nižší procento zákazníků patřících do dané kategorie ve srovnání s podílem všech zákazníků ve stejné kategorii. Pokud má 22 % všech zákazníků *vysokou* spokojenost, pak budou pro tuto kategorii navrženy pouze segmenty, které mají vyšší či nižší podíl zákazníků s *vysokou* spokojeností ve srovnání s 22 %. Podobně budou navrženy segmenty pro každou z ostatních kategorií (*Nízká* a *Střední*), pokud jsou statisticky významné.

> [!NOTE]
> V současné době podporujeme pouze primární kategorické atributy, které mají až 10 kategorií. Chcete-li zobrazit návrhy segmentů na základě primárního atributu s více než 10 kategoriemi, doporučujeme seskupit některé z kategorií, abyste snížili počet kategorií na 10 nebo méně. Toto omezení se vztahuje pouze na primární atributy. Pro ovlivnění kategorických atributů aktuálně podporujeme maximálně 100 kategorií.

## <a name="generate-suggested-segments"></a>Generování doporučovaných segmentů

1. Přejděte na **Segmenty** a vyberte kartu **Návrhy (Preview)**.

1. Vyberte **Najít nové návrhy** a vyberte **Zlepšení míry/metriky**. Vyberte **Spustit**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Výběr zlepšení míry pro navrhované segmenty.":::

1. Jako primární atribut zvolte míru nebo atribut zákazníka a vyberte **Další**.

1. Vyberte ovlivňující atributy a vyberte **Spustit**.

   > [!TIP]
   > Výběr více ovlivňujících atributů zvyšuje šance na vyhodnocení, jak ovlivňují primární atribut. Nezahrnujte atributy, které nemají žádný vliv na primární atribut. Pokud jsou například všichni vaši zákazníci z konkrétní země, nezahrnujte atribut *země*, protože to nebude mít žádný dopad na výstup.

V závislosti na počtu profilů zákazníků a vybraných atributů může zpracování vybraných atributů trvat několik minut.

## <a name="manage-suggested-segments"></a>Správa doporučovaných segmentů

Jděte do sekce **Segmenty** a vyberte katu **Návrhy (Preview)**. V sekci **Návrhy segmentů založené na atributech** vyberte navrhovaný segment pro zobrazení dostupných akcí.

- **Zobrazte** podrobnosti navrhovaného segmentu a hodnoty atributů nebo pravidla, která se model AI naučil.
- Volbou **Uložit jako segment** uložíte návrh jako segment. Zobrazí se na kartě **Všechny segmenty** a může být [aktualizován, upraven nebo odstraněn](segments.md).
- Volbou **Upravit atributy** upravíte nakonfigurované atributy, které nahradí aktuální návrhy.
- Volbou **Aktualizovat návrhy** aktualizujete návrhy při zachování konfigurovaných atributů.

## <a name="limitations"></a>Omezení

1. Odhadovaná neshoda velikosti segmentu: Pokud zvolíte primární atribut, který obsahuje prázdné hodnoty, může to ovlivnit odhadovanou velikost segmentu v návrzích segmentů. Při ukládání takového segmentu se skutečná velikost segmentu může lišit od původního odhadu.

2. Primární atributy typu Boolean nefungují: V současné době podporujeme jako primární atribut pouze řetězcové a číselné typy dat.

3. Navrhované segmenty nejsou dostatečně odlišné: Mějte na paměti, že vybrané atributy a rozdělení hodnot těchto atributů ovlivňuje výsledky. Chcete-li dosáhnout různých výsledků, můžete změnit své ovlivňující atributy nebo dokonce svůj primární atribut.

[!INCLUDE [footer-include](includes/footer-banner.md)]