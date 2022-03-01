---
title: Predikce doporučení produktů
description: Predikujte produkty, které si zákazník pravděpodobně zakoupí nebo s nimž bude interagovat.
ms.date: 09/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: a75a245bc721d65643fa78d46f2be52291595a5a
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494531"
---
# <a name="product-recommendation-prediction-preview"></a>Predikce doporučení produktů (Preview)

Model doporučení produktů vytváří sady prediktivních doporučení produktů. Doporučení jsou založena na předchozím nákupním chování a zákaznících s podobnými nákupními vzory. Nové predikce doporučení produktů můžete vytvořit na stránce **Analytické nástroje** > **Predikce**. Volbou **Moje predikce** zobrazíte ostatní predikce, které jste vytvořili.

Doporučení produktů mohou podléhat místním zákonům a předpisům a očekáváním zákazníků, které model na základě svého sestavení nezohledňuje.  Jako uživatel této prediktivní schopnosti **musíte před doručením vašim zákazníkům zkontrolovat doporučení** k zajištění, že dodržujete všechny příslušné zákony nebo předpisy a očekávání zákazníků ohledně toho, co můžete doporučit. 

Kromě toho vám výstup tohoto modelu poskytne doporučení založená na ID produktu. Váš doručovací mechanismus bude muset namapovat předpokládaná ID produktu na vhodný obsah pro vaše zákazníky, aby zohledňoval lokalizaci, obsah obrázku a další obsah nebo chování specifické pro firmy.

## <a name="sample-guide"></a>Průvodce ukázkami

Pokud máte zájem o vyzkoušení této funkce, ale nemáte data k splnění níže uvedených požadavků, můžete [vytvořit ukázkovou implementaci](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Požadavky

- Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.

- Obchodní znalosti, abyste rozuměli různým typům produktů pro vaše podnikání a jak s nimi zákazníci interagují. Podporujeme doporučení produktů, které si vaši zákazníci dříve zakoupili, nebo doporučení pro nové produkty.

- Údaje o transakcích a nákupech a jejich historie:
    - Identifikátory transakcí k rozlišení nákupů nebo transakcí.
    - Identifikátory zákazníků pro mapování transakcí na vaše zákazníky.
    - Data událostí, kdy došlo k transakcím.
    - Informace o ID produktu pro transakci.
    - (Volitelné) Datová entita katalogu produktů pro použití filtru produktu.
    - (Volitelně) Zda je transakce vratka nebo ne.
    - Schéma sémantických dat vyžaduje následující informace:
        - **ID transakce:** Jedinečný identifikátor nákupu nebo transakce.
        - **Datum transakce:** Datum nákupu nebo transakce.
        - **Hodnota transakce:** Číselná hodnota nákupu nebo transakce.
        - **Jedinečné ID produktu:** ID zakoupeného produktu nebo služby, pokud jsou vaše data na úrovni řádkové položky.
        - (Volitelný) **Nákup nebo vrácení:** Logické pole, kde hodnota *skutečný* identifikuje, že transakce byla vrácená. Pokud nejsou poskytnuty údaje o nákupu nebo vrácení, model **Hodnota transakce** je záporná, použijeme tyto informace také k odvození návratnosti.
- Navrhované vlastnosti dat:
    - Dostatečné historické údaje: Nejméně jeden rok transakčních údajů, nejlépe dva až tři roky, aby zahrnovaly určitou sezónnost.
    - Vícenásobné nákupy na zákazníka: Tři nebo více transakcí na ID zákazníka
    - Počet zákazníků: Nejméně 100 zákazníků, nejlépe více než 10 000 jedinečných zákazníků. Model selže s méně než 100 zákazníky.

> [!NOTE]
> - Model vyžaduje historii transakcí vašich zákazníků. Definice transakce je poměrně flexibilní. Jakákoli data, která popisují interakci uživatele a produktu, mohou fungovat jako vstup. Například nákup produktu, absolvování kurzu nebo účast na události.
> - Aktuálně lze konfigurovat pouze jednu entitu historie transakcí. Pokud existuje více entit nákupu, sjednoťte je před přijetím dat v Power Query.
> - Pokud jsou objednávka a podrobnosti objednávky různé entity, připojte se k nim před použitím v modelu. Model v entitě nefunguje pouze s ID objednávky nebo ID příjmu.


## <a name="create-a-product-recommendation-prediction"></a>Vytvoření predikce doporučení produktů

1. V části Customer Insights přejděte na **Analytické nástroje** > **Předpovědi**.

1. Vyberte dlaždici **Model doporučení produktů (Preview)** a vyberte **Použít tento model**.
   > [!div class="mx-imgBorder"]
   > ![Dlaždice modelu doporučení produktů s tlačítkem Použít tento model.](media/product-recommendation-usethismodel.PNG "Dlaždice modelu doporučení produktů s tlačítkem Použít tento model")

1. Zkontrolujte informace o požadavcích na model. Pokud máte požadovaná data, vyberte **Začít**.

### <a name="name-model"></a>Pojmenování modelu

1. Zadejte název modelu, abyste jej odlišili od ostatních modelů.

1. Zadejte název výstupní entity pouze pomocí písmen a číslic, bez mezer. Jedná se o název, který bude používat entita modelu. Pak vyberte **Další**.

### <a name="define-product-recommendation-configuration"></a>Definování konfigurace doporučení produktů

1. Nastavte **Počet produktů**, kolik chcete doporučit zákazníkovi. Tato hodnota závisí na tom, jak váš způsob doručení vyplňuje data. Pokud můžete doporučit tři produkty, nastavte tuto hodnotu odpovídajícím způsobem.
   
   >[!TIP]
   > Kdykoli můžete použít volbu **Uložit a zavřít**, kterou uložíte predikci jako koncept. Koncept predikce najdete na kartě **Moje predikce**.

1. Zvolte, zda chcete **Navrhovat produkty, které zákazníci nedávno zakoupili**.

1. Pokud jste se rozhodli *nedoporučit* nedávno zakoupené produkty, nastavte **Okno ohlédnutí**. Toto nastavení určuje časový rámec, kterým se model řídí před opětovným doporučením produktu uživateli. Například označte, že si zákazník kupuje notebook každé dva roky. Toto okno se zaměří na historii nákupů za poslední dva roky a pokud bude nalezena položka, bude položka filtrována z doporučení.

1. Vyberte **Další**.

### <a name="add-required-data"></a>Přidejte požadovaná data

1. Vyberte **Přidat data** a zvolte typ aktivity v postranním podokně, které obsahuje informace o požadované transakci nebo historii nákupů.

1. V položce **Vybrat aktivity** vyberte konkrétní aktivity z vybrané aktivity, na které se chcete při výpočtu zaměřit.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Boční podokno zobrazující výběr konkrétních aktivit pod sémantickým typem.":::

1. Pokud jste aktivitu dosud nemapovali na sémantický typ, proveďte to výběrem možnosti **Upravit**. Otevře se řízené prostředí s mapováním sémantických aktivit. Namapujte svá data na odpovídající pole ve zvoleném typu aktivity.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Typ aktivity nastavení stránky.":::

1. Po namapování aktivity na odpovídající sémantický typ pokračujte výběrem možosti **Další**. 
 
1. Namapujte sémantické atributy na pole, která jsou nutná ke spuštění modelu.

1. Zvolte **Uložit**.

1. Vyberte **Další**.


### <a name="configure-product-filters"></a>Konfigurace filtrů produktu

Pro typ predikce, který vytvoříte, jsou někdy výhodné nebo vhodné pouze určité produkty. Filtry produktů vám umožňují identifikovat podmnožinu produktů se specifickými vlastnostmi, které můžete doporučit svým zákazníkům. Model použije všechny dostupné produkty, aby se naučil vzory, ale ve svém výstupu použije pouze produkty odpovídající filtrům produktů.

1. V kroku **Přidat informace o produktu** přidejte svůj katalog produktů s informacemi o každém produktu. Mapujte požadované informace výběrem možnosti **Další**.

3. V kroku **Filtry produktů** vyberte z následujících možností.

   * **Žádné filtry**: Použijte všechny produkty v predikci doporučení produktu.

   * **Definovat konkrétní filtry produktu**: Použijte konkrétní produkty v predikci doporučení produktu.

1. Vyberte **Další**.

1. Pokud se rozhodnete definovat filtr produktu, musíte jej definovat nyní. V podokně **Atributy katalogu produktů** vyberte atributy z *entity katalogu produktů*, které chcete zahrnout do filtru.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Postranní podokno zobrazující atributy v entitě katalogu produktů, které chcete vybrat pro filtry produktů.":::

1. Vyberte, zda má produktový filtr použít konektory **and** pro logickou kombinaci vašeho výběru atributů z katalogu produktů.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Ukázková konfigurace produktových filtrů kombinovaná s logickými spojkami AND.":::

1. Vyberte **Další**.

### <a name="set-update-schedule-and-review-configuration"></a>Nastavení plánu aktualizací a kontrola konfigurace

1. Nastavte frekvenci opětovného cvičení modelu. Toto nastavení je důležité pro aktualizaci přesnosti predikcí, když jsou do Customer Insights importována nová data. Většina podniků může provést opětovné cvičení modelu jednou za měsíc a mít predikce s dobrou přesností.

1. Vyberte **Další**.

1. Zkontrolujte konfiguraci. Výběrem možnosti **Upravit** pod zobrazenou hodnotou se můžete vrátit do libovolné části konfigurace predikce. Nebo můžete vybrat krok konfigurace z ukazatele průběhu.

1. Pokud jsou všechny hodnoty správně nakonfigurovány, volbou **Uložit a spustit** zahájíte proces predikce. Na kartě **Moje predikce** se zobrazuje stav vašich predikcí. Dokončení procesu může trvat několik hodin v závislosti na množství dat použitých v predikci.

## <a name="review-a-prediction-status-and-results"></a>Kontrola stavu a výsledků predikce

1. Jděte na kartu **Moje predikce** v umístění **Analytické nástroje** > **Predikce**.
   > [!div class="mx-imgBorder"]
   > ![Zobrazení stránky Moje predikce.](media/product-recommendation-mypredictions.PNG "Zobrazení stránky Moje predikce")

1. Vyberte předpověď, kterou chcete zkontrolovat.
   - **Název predikce:** Název predikce zadaný při jejím vytvoření.
   - **Typ predikce:** Typ modelu použitého pro predikci.
   - **Výstupní entita:** Název entity pro uložení výstupu predikce. Můžete najít entitu s tímto názvem v umístění **Data** > **Entity**.    
      *Skóre* ve výstupní entitě je kvantitativní měřítko doporučení. Model doporučuje produkty s vyšším skóre než produkty s nižším skóre.
   - **Predikované pole:** Toto pole je vyplněno pouze pro některé typy predikcí a nepoužívá se v predikci doporučení produktu.
   - **Stav:** Aktuální stav běhu predikce.
        - **Ve frontě:** Predikce aktuálně čeká na spuštění dalších procesů.
        - **Aktualizace:** Predikce je v současné době ve fázi zpracování „skóre“, během které vznikají výsledky, které jsou předány do výstupní entity.
        - **Selhání:** Predikce selhala. Další podrobnosti zobrazíte výběrem položky **Protokoly**.
        - **Úspěch:** Predikce byla úspěšná. Volbou **Zobrazit** pod svislými třemi tečkami zkontrolujete predikci.
   - **Upraveno:** Datum, kdy byla konfigurace predikce změněna.
   - **Poslední aktualizace:** Datum, kdy predikce aktualizovala výsledky ve výstupní entitě.

1. Vyberte svislé tři tečky vedle predikce, pro kterou chcete zkontrolovat výsledky, a vyberte **Zobrazit**.
   > [!div class="mx-imgBorder"]
   > ![Zobrazení možností v nabídce svislých třech teček pro predikci včetně úprav, aktualizace, zobrazení, protokolů a odstranění.](media/product-recommendation-verticalellipses.PNG "Zobrazení možností v nabídce svislých třech teček pro predikci včetně úprav, aktualizace, zobrazení, protokolů a odstranění")

1. Na stránce s výsledky je pět primárních sekcí dat:
    1. **Výkon cvičení modelu:** Skóre může být A, B nebo C. Toto skóre označuje výkon predikce a může vám pomoci při rozhodování o použití výsledků uložených ve výstupní entitě.
        - Skóre je stanoveno na základě následujících pravidel:
            - **A** Kvalita modelu bude ohodnocena známkou **A**, pokud je metrika „Úspěch @ K“ alespoň o 10 % vyšší než základ. 
            - **B** Kvalita modelu bude ohodnocena známkou **B**, pokud je metrika „Úspěch @ K“ o 0 % až 10 % vyšší než základ.
            - **C** Kvalita modelu bude ohodnocena známkou **C**, pokud je metrika „Úspěch @ K“ nižší než základ.
               
               > [!div class="mx-imgBorder"]
               > ![Zobrazení výsledku výkonu modelu.](media/product-recommendation-modelperformance.PNG "Zobrazení výsledku výkonu modelu")
            - **Základ**: Model převezme nejvíce doporučované produkty podle počtu nákupů u všech zákazníků a na základě naučených pravidel rozpoznaných modelem vytvoří sadu doporučení pro zákazníky. Predikce jsou poté porovnány s nejlepšími produkty, které byly vypočítány podle počtu zákazníků, kteří si produkty koupili. Pokud má zákazník v doporučených produktech alespoň jeden produkt, který byl také mezi nejprodávanějšími produkty, považuje se za součást základu. Pokud by 10 z těchto zákazníků mělo zakoupený doporučený produkt ze 100 celkových zákazníků, byl by základ 10 %.
            - **Úspěch @ K.**: Pomocí ověřovací sady časového období transakcí se vytvoří doporučení pro všechny zákazníky a porovnají se s ověřovací sadou transakcí. Například v období 12 měsíců může být měsíc 12 vyčleněn jako ověřovací sada dat. Pokud model predikuje alespoň jednu věc, kterou byste si koupili v 12. měsíci na základě toho, co se dozvěděl z předchozích 11 měsíců, zákazník by zvýšil metriku „Úspěch @ K“.
    
    1. **Nejvíce doporučované produkty (se shodou):** Prvních pět produktů, které byly predikovány vašim zákazníkům.
       > [!div class="mx-imgBorder"]
       > ![Graf zobrazující prvních 5 nejdoporučovanějších produktů.](media/product-recommendation-topproducts.PNG "Graf zobrazující prvních 5 nejdoporučovanějších produktů")
    
    1. **Klíčové faktory doporučení:** Model používá k provádění doporučení produktů historii transakcí zákazníků. Učí se vzory založené na minulých nákupech a hledá podobnosti mezi zákazníky a produkty. Tyto podobnosti se pak využijí ke generování doporučení produktů.
    Následují faktory, které by mohly ovlivnit doporučení produktu generované modelem. 
        - **Minulé transakce**: Vzorce nákupu v minulosti využíval model ke generování doporučení produktu. Model může například doporučit _Povrchovou obloukovou myš_, pokud někdo nedávno koupil _Povrchovou knihu 3_ a _Povrchové pero_. Model se dozvěděl, že historicky si mnoho zákazníků koupilo _Povrchovou obloukovou myš_ po zakoupení _Povrchové knihy 3_ a _Povrchového pera_.
        - **Podobnost zákazníka**: Doporučený produkt byl historicky zakoupen jinými zákazníky, kteří vykazují podobné vzorce nákupu. Například Johnovi byla doporučena _Povrchová sluchátka 2_, protože Jennifer a Brad nedávno zakoupili _Povrchová sluchátka 2_. Model věří, že John je podobný Jennifer a Bradovi, protože historicky měli podobné nákupní vzorce.
        - **Podobnost produktu**: Doporučený produkt je podobný ostatním produktům, které si zákazník dříve zakoupil. Model považuje dva výrobky za podobné, pokud byly zakoupeny společně nebo podobnými zákazníky. Například někdo dostane doporučení pro _Úložiště USB_, protože dříve zakoupili _Adaptér USB-C na USB_ a model věří, že _Úložiště USB_ je podobné _Adaptéru USB-C na USB_ založenému na historických vzorcích nákupu.

        Každé doporučení produktu je ovlivněno jedním nebo více z těchto faktorů. Procento doporučení, kde každý ovlivňující faktor hrál roli, je zobrazeno v grafu. V následujícím příkladu bylo 100 % doporučení ovlivněno minulými transakcemi, 60 % podobností zákazníků a 22 % podobností produktů. Umístěním kurzoru myši nad pruhy v grafu zobrazíte přesné procento, kam přispěly ovlivňující faktory.

        > [!div class="mx-imgBorder"]
        > ![Klíčové faktory doporučení.](media/product-recommendation-keyrecommendationfactors.png "Klíčové faktory doporučení, které model získal při generování doporučení produktu")
       
     
   1. **Statistika údajů**: Poskytuje přehled počtu transakcí, zákazníků a produktů, které model zvažuje. Je založen na vstupních datech, která byla použita k osvojení vzorů a generování doporučení produktů.

      > [!div class="mx-imgBorder"]
      > ![Statistika dat.](media/product-recommendation-datastatistics.png "Statistiky dat kolem vstupních dat používaných modelem k učení vzorců")

      Tato část zobrazuje statistiky kolem datových bodů, které model používal k učení vzorů a generování doporučení produktů. Filtrování, jak je nakonfigurováno v konfiguraci modelu, se použije na výstup generovaný modelem. Model však používá všechna dostupná data k učení vzorců. Pokud tedy v konfiguraci modelu používáte filtrování produktů, v této části se zobrazí celkový počet produktů, které model analyzoval, aby se naučil vzorce, které se mohou lišit od počtu produktů, které odpovídají definovaným kritériím filtrování.

   1. **Doporučení produktů s vysokou spolehlivostí:** Ukázka doporučených produktů zákazníkům, o kterých se model domnívá, že si je zákazník pravděpodobně zakoupí.    
      Pokud je přidán katalog produktů, ID produktů budou nahrazena názvy produktů. Názvy produktů poskytují akčnější a intuitivnější informace o predikcích.
       > [!div class="mx-imgBorder"]
       > ![Seznam zobrazující návrhy s vysokou spolehlivostí pro vybranou sadu jednotlivých zákazníků.](media/product-recommendation-highconfidence.PNG "Seznam zobrazující návrhy s vysokou spolehlivostí pro vybranou sadu jednotlivých zákazníků")

## <a name="manage-predictions"></a>Správa predikcí

Predikce můžete optimalizovat, odstraňovat jejich problémy, aktualizovat nebo odstranit. Projděte si sestavu použitelnosti vstupních dat a zjistěte v ní, jak zajistit, aby predikce byla rychlejší a spolehlivější. Další informace naleznete v tématu [Správa predikcí](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
