---
title: Predikce úbytku předplatitelů (obsahuje video)
description: Predikuje, zda hrozí odchod zákazníka, když přestane používat předplatné pro produkty nebo služby vaší společnosti.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 415cd5d675512b4f434998afaa8265c8e45c562b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646397"
---
# <a name="subscription-churn-prediction"></a>Predikce ukončení předplatného

Predikce odchodu předplatitelů pomáhá predikovat, zda hrozí odchod zákazníka, když přestane používat předplatné pro produkty nebo služby vaší společnosti. Novou predikci odchodu předplatitelů můžete vytvořit na stránce **Analytické nástroje** > **Predikce**. Volbou **Moje predikce** zobrazíte ostatní predikce, které jste vytvořili.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Vyzkoušejte kurz pro predikci úbytku předplatných s využitím ukázkových dat: [Průvodce ukázkami predikce úbytku předplatných](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Požadavky

- Alespoň [oprávnění Přispěvatel](permissions.md).
- Obchodní znalosti k pochopení toho, co znamená pro vaši firmu odchod zákazníků. Podporujeme definice časově závislých odchodů zákazníků, což znamená, že je zákazník považován za odchozího po uplynutí časového intervalu od konce jeho předplatného.
- Údaje o vašich předplatných a jejich historii:
    - Identifikátory pro rozlišování předplatných.
    - Identifikátory zákazníků pro párování předplatných s vašimi zákazníky.
    - Data událostí předplatných, která definují data zahájení, data ukončení a data, při kterých došlo k událostem předplatného.
    - Informace o předplatném pro definování, zda se jedná o opakující se předplatné a jak často se obnovuje.
    - Schéma sémantických dat pro předplatné vyžaduje následující informace:
        - **ID předplatného:** Jedinečný identifikátor předplatného.
        - **Datum ukončení předplatného:** Datum vypršení platnosti předplatného zákazníka.
        - **Datum zahájení předplatného:** Datum zahájení platnosti předplatného zákazníka.
        - **Datum transakce:** Datum změny předplatného. Například zákazník koupil nebo zrušil předplatné.
        - **Je to opakující se předplatné:** Logické pole pravda/nepravda, které určuje, zda bude odběr obnoven se stejným ID předplatného bez zásahu zákazníka.
        - **Frekvence opakování (v měsících):** U opakujících se předplatných je to období, po kterém bude předplatné obnoveno. Je vyjádřena v měsících. Například roční předplatné, které se automaticky obnovuje pro zákazníka z roku na rok, má hodnotu 12.
        - (Volitelně) **Částka předplatného:** Částka měny, kterou zákazník platí za obnovení předplatného. Může pomoci identifikovat vzory pro různé úrovně předplatného.
- Údaje o zákaznických aktivitách:
    - Identifikátory aktivit pro rozlišení aktivit stejného typu.
    - Identifikátory zákazníků pro mapování aktivit na vaše zákazníky.
    - Informace o aktivitě obsahující název a datum aktivity.
    - Schéma sémantických dat pro aktivity zákazníka zahrnuje:
        - **Primární klíč:** Jedinečný identifikátor aktivity. Například návštěva webové stránky nebo záznam o použití znázorňující, že zákazník sledoval epizodu televizního pořadu.
        - **Časové razítko:** Datum a čas události identifikovaný primárním klíčem.
        - **Událot:** Název události, kterou chcete použít. Například pole nazvané „AkceUživatele“ ve streamovací službě může mít hodnotu „Zobrazeno“.
        - **Podrobnosti:** Podrobné informace o akci. Například pole nazvané „NázevPořadu“ ve streamovací službě může mít hodnotu videa shlédnutého uživatelem.
- Navrhované vlastnosti dat:
    - Dostatečná historická data: Data předplatného alespoň pro dvojnásobek vybraného časového okna. Nejlépe dva až tři roky předplacených dat.
    - Stav předplatného: Data zahrnují aktivní a neaktivní předplatné pro každého zákazníka, takže na každé číslo zákazníka je více záznamů.
    - Počet zákazníků: Nejméně 10 zákaznických profilů, nejlépe více než 1 000 jedinečných zákazníků. Model selže s méně než 10 zákazníky a nedostatečnými historickými daty.
    - Úplnost údajů: Méně než 20% chybějících hodnot v datovém poli poskytnuté entity.
   
   > [!NOTE]
   > Budete potřebovat alespoň dva záznamy o aktivitách pro 50 % zákazníků, pro které chcete vypočítat jejich možný odchod.

## <a name="create-a-subscription-churn-prediction"></a>Vytvoření predikce odchodu předplatitelů

1. Přejděte na **Analytické nástroje** > **Předpovědi**.
1. Vyberte dlaždici **Model úbytku předplatného** a vyberte **Použít tento model**.
   > [!div class="mx-imgBorder"]
   > ![Dlaždice modelu odchodu předplatitelů s tlačítkem Použít tento model.](media/subscription-churn-usethismodel.PNG "Dlaždice modelu odchodu předplatitelů s tlačítkem Použít tento model")

### <a name="name-model"></a>Pojmenování modelu

1. Zadejte název modelu, abyste jej odlišili od ostatních modelů.
1. Zadejte název výstupní entity pouze pomocí písmen a číslic bez mezer. Jedná se o název, který bude používat entita modelu. Pak vyberte **Další**.

### <a name="define-customer-churn"></a>Definujte ztracené zákazníky

1. Zadejte počet dní pro **Dny od ukončení předplatného**, po jejichž uplynutí vaše firma považuje zákazníka za odchozího. Toto období je obvykle přizpůsobeno obchodním činnostem, jako jsou nabídky nebo jiné marketingové činnosti, které se snaží zabránit ztrátě zákazníka.
1. Zadejte hodnotu pro **Počet dní predikce odlivu zákazníků**, čímž nastavíte okno pro predikci odlivu zákazníků. Například predikujte rizika odlivu zákazníků během následujících 90 dnů, abyste mohli přizpůsobit svůj marketing pro jejich udržení. Předvídání rizika odchodu zákazníků na delší nebo kratší období může ztížit řešení faktorů ve vašem profilu rizika odchodu zákazníků, v závislosti na vašich konkrétních obchodních požadavcích. Pokračujte kliknutím na tlačítko **Další**.
   >[!TIP]
   > Kdykoliv můžete volbou **Uložit koncept** uložit predikci jako koncept. Koncept predikce najdete na kartě **Moje predikce**.

### <a name="add-required-data"></a>Přidejte požadovaná data

1. Zvolte **Přidat data** pro možnost **Historie předplatného** a vyberte entitu, která poskytuje informace o historii předplatného, jak je popsáno v [předpokladech](#prerequisites).
1. Pokud níže uvedená pole nejsou vyplněna, nakonfigurujte vztah mezi entitou historie předplatného a entitou zákazníka.
    1. Vyberte možnost **Entita historie předplatného**.
    1. Vyberte **Pole**, které identifikuje zákazníka v entitě historie předplatného. Musí se vztahovat k primárnímu ID zákazníka vaší entity zákazníka.
    1. Vyberte **entitu zákazníka**, která odpovídá vaší primární entitě zákazníka.
    1. Zadejte název, který popisuje daný vztah.
       > [!div class="mx-imgBorder"]
       > ![Stránka historie předplatného ukazující vytvoření vztahu k zákazníkovi.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Stránka historie předplatného ukazující vytvoření vztahu k zákazníkovi")
1. Vyberte **Další**.
1. Namapujte sémantická pole na atributy v rámci entity historie předplatného a vyberte **Uložit**. Pro popis polí se podívejte na [předpoklady](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Stránka historie předplatného, která zobrazuje sémantické atributy, které jsou mapovány na pole ve vybrané entitě historie předplatného.](media/subscription-churn-subscriptionhistorymapping.PNG "Stránka historie předplatného, která zobrazuje sémantické atributy, které jsou mapovány na pole ve vybrané entitě historie předplatného")
1. Zvolte **Přidat data** pro **Aktivity zákazníků** a vyberte entitu, která poskytuje informace o aktivitě zákazníka, jak je popsáno v předpokladech.
1. Vyberte typ aktivity, který odpovídá typu aktivity zákazníka, kterou konfigurujete.  Pokud nevidíte možnost odpovídající typu aktivity, kterou potřebujete, vyberte **Vytvořit novou** a zadejte název.
1. Budete muset nakonfigurovat vztah mezi vaší entitou aktivity zákazníka a entitou zákazníka.
    1. Vyberte pole, které identifikuje zákazníka v tabulce aktivit zákazníků a které lze přímo propojit s primárním ID zákazníka vaší entity zákazníka.
    1. Výběr entity zákazníka, která odpovídá vaší primární entitě zákazníka
    1. Zadejte název, který popisuje daný vztah.
1. Vyberte **Další**.
1. Namapujte sémantická pole na atributy v rámci entity aktivit zákazníka a vyberte **Uložit**. Pro popis polí se podívejte na [předpoklady](#prerequisites).
1. (Volitelné) Pokud máte nějaké další aktivity zákazníka, které chcete zahrnout, opakujte výše uvedené kroky.
   > [!div class="mx-imgBorder"]
   > ![Definujte vztah entity.](media/subscription-churn-customeractivitiesmapping.PNG "Stránka aktivit zákazníků, která zobrazuje sémantické atributy, které jsou mapovány na pole ve vybrané entitě aktivity zákazníka")
1. Vyberte **Další**.

### <a name="set-schedule-and-review-configuration"></a>Nastavení plánu a kontrola konfigurace

1. Nastavte frekvenci opětovného cvičení modelu. Toto nastavení je důležité pro aktualizaci přesnosti předpovědí při zpracování nových dat v Customer Insights. Většina podniků může provést opětovné cvičení modelu jednou za měsíc a mít predikce s dobrou přesností.
1. Vyberte **Další**.
1. Zkontrolujte konfiguraci. Výběrem možnosti **Upravit** pod zobrazenou hodnotou se můžete vrátit do libovolné části konfigurace predikce. Nebo můžete vybrat krok konfigurace z ukazatele průběhu.
1. Pokud jsou všechny hodnoty správně nakonfigurovány, volbou **Uložit a spustit** zahájíte proces predikce. Na kartě **Moje predikce** se zobrazuje stav vašich predikcí. Dokončení procesu může trvat několik hodin v závislosti na množství dat použitých v predikci.

## <a name="review-a-prediction-status-and-results"></a>Kontrola stavu a výsledků predikce

1. Jděte na kartu **Moje predikce** v umístění **Analytické nástroje** > **Predikce**.
   > [!div class="mx-imgBorder"]
   > ![Zobrazení stránky Moje predikce.](media/subscription-churn-mypredictions.PNG "Zobrazení stránky Moje predikce")
1. Vyberte předpověď, kterou chcete zkontrolovat.
   - **Název predikce:** Název predikce zadaný při jejím vytvoření.
   - **Typ predikce:** Typ modelu použitého pro predikci.
   - **Výstupní entita:** Název entity pro uložení výstupu predikce. Můžete najít entitu s tímto názvem v umístění **Data** > **Entity**.    
     Ve výstupní entitě *ChurnScore* je předpokládaná pravděpodobnost odchodu zákazníků a *IsChurn* je binární štítek založený na *ChurnScore* s prahovou hodnotou 0,5. Výchozí prahová hodnota nemusí ve vašem scénáři fungovat. [Vytvořte nový segment](segments.md#create-a-new-segment) s vaší preferovanou prahovou hodnotou.
   - **Predikované pole:** Toto pole je vyplněno pouze u některých typů predikcí a nepoužívá se při predikci odchodu předplatitelů.
   - **Stav:** Aktuální stav běhu predikce.
        - **Ve frontě:** Predikce aktuálně čeká na spuštění dalších procesů.
        - **Aktualizace:** Predikce je v současné době ve fázi zpracování „skóre“, během které vznikají výsledky, které jsou předány do výstupní entity.
        - **Selhání:** Predikce selhala. Další podrobnosti zobrazíte výběrem položky **Protokoly**.
        - **Úspěch:** Predikce byla úspěšná. Volbou **Zobrazit** pod svislými třemi tečkami zkontrolujete predikci.
   - **Upraveno:** Datum, kdy byla konfigurace predikce změněna.
   - **Poslední aktualizace:** Datum, kdy predikce aktualizovala výsledky ve výstupní entitě.
1. Vyberte svislé tři tečky vedle predikce, pro kterou chcete zkontrolovat výsledky, a vyberte **Zobrazit**.
   > [!div class="mx-imgBorder"]
   > ![Zobrazení možností v nabídce svislých třech teček pro predikci včetně úprav, aktualizace, zobrazení, protokolů a odstranění.](media/subscription-churn-verticalellipses.PNG "Zobrazení možností v nabídce svislých třech teček pro predikci včetně úprav, aktualizace, zobrazení, protokolů a odstranění")
1. Na stránce výsledků jsou tři primární sekce s daty:
    1. **Výkon cvičení modelu:** Skóre může být A, B nebo C. Toto skóre označuje výkon predikce a může vám pomoci při rozhodování o použití výsledků uložených ve výstupní entitě.
        - Skóre je stanoveno na základě následujících pravidel:
            - **A**, když model přesně predikoval alespoň 50 % celkových predikcí a když procento přesných predikcí odešlých zákazníků je nejméně o 10 % vyšší, než je historická průměrná míra odešlých zákazníků.
            - **B**, když model přesně predikoval alespoň 50 % celkových predikcí a když procento přesných predikcí odešlých zákazníků je maximálně o 10 % vyšší, než je historická průměrná míra odešlých zákazníků.
            - **C**, když model přesně predikoval méně než 50 % celkových predikcí nebo když procento přesných predikcí odešlých zákazníků je nižší, než historická průměrná míra odešlých zákazníků.
               > [!div class="mx-imgBorder"]
               > ![Zobrazení výsledku výkonu modelu.](media/subscription-churn-modelperformance.PNG "Zobrazení výsledku výkonu modelu")
    1. **Pravděpodobnost odchodu (počet zákazníků):** Skupiny zákazníků na základě jejich predikovaného rizika odchodu. Tato data vám mohou pomoci později, pokud chcete vytvořit segment zákazníků s vysokým rizikem odchodu. Takové segmenty pomáhají pochopit, kde by se pro členství v segmentech mělo nacházet vyřazení.
       > [!div class="mx-imgBorder"]
       > ![Graf znázorňující rozložení výsledných odchodů rozdělený do rozmezí od 0 do 100 %.](media/subscription-churn-resultdistribution.PNG "Graf znázorňující rozložení výsledných odchodů rozdělený do rozmezí od 0 do 100 %")
    1. **Nejvlivnější faktory:** Při vytváření predikce se bere v úvahu mnoho faktorů. Každý z faktorů má svou důležitost vypočítanou pro agregované predikce, které model vytváří. Tyto faktory můžete použít k ověření výsledků predikce. Nebo můžete tyto informace použít později při [vytváření segmentů](segments.md), které mohou pomoci ovlivnit riziko odchodů zákazníků.
       > [!div class="mx-imgBorder"]
       > ![Seznam zobrazující vlivné faktory a jejich význam při predikci výsledných odchodů.](media/subscription-churn-influentialfactors.PNG "Seznam zobrazující vlivné faktory a jejich význam při predikci výsledných odchodů")

## <a name="manage-predictions"></a>Správa predikcí

Predikce můžete optimalizovat, odstraňovat jejich problémy, aktualizovat nebo odstranit. Projděte si sestavu použitelnosti vstupních dat a zjistěte v ní, jak zajistit, aby predikce byla rychlejší a spolehlivější. Další informace naleznete v tématu [Správa predikcí](manage-predictions.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]