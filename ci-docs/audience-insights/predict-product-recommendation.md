---
title: Predikce doporučení produktů
description: Predikujte produkty, které si zákazník pravděpodobně zakoupí nebo s nimž bude interagovat.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598055"
---
# <a name="product-recommendation-prediction-preview"></a>Predikce doporučení produktů (Preview)

Model doporučení produktů vytváří sady prediktivních doporučení produktů. Doporučení jsou založena na předchozím nákupním chování a zákaznících s podobnými nákupními vzory. Nové predikce doporučení produktů můžete vytvořit na stránce **Analytické nástroje** > **Predikce**. Volbou **Moje predikce** zobrazíte ostatní predikce, které jste vytvořili.

Doporučení produktů mohou podléhat místním zákonům a předpisům i očekáváním zákazníků, přičemž model není sestaven tak, aby to konkrétně zohledňoval.  Jako uživatel této prediktivní funkce **musíte doporučení zkontrolovat, než je doručíte zákazníkům,** abyste zajistili, že dodržujete veškeré příslušné zákony nebo předpisy, jakož i očekávání zákazníků ohledně toho, co můžete doporučit. 

Kromě toho vám výstup tohoto modelu poskytne doporučení založená na ID produktu. Váš mechanismus doručení musí převzít predikovaná ID produktu a namapovat je na vhodný obsah pro vaše zákazníky, aby zohledňoval lokalizaci, obsah obrázku a další obsah nebo chování specifické pro danou obchodní oblast.

## <a name="sample-guide"></a>Průvodce ukázkami

Pokud máte zájem o vyzkoušení této funkce, ale nemáte data k splnění níže uvedených požadavků, můžete [vytvořit ukázkovou implementaci](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Požadavky

- Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.
- Obchodní znalosti, abyste rozuměli různým typům produktů pro vaše podnikání a jak s nimi zákazníci interagují. Podporujeme doporučení produktů, které si vaši zákazníci dříve zakoupili, nebo doporučení pro nové produkty.
- Údaje o transakcích a nákupech a jejich historie:
    - Identifikátory transakcí k rozlišení nákupů nebo transakcí.
    - Identifikátory zákazníků pro mapování transakcí na vaše zákazníky.
    - Data událostí, kdy došlo k transakcím.
    - (Volitelně) Informace o ID produktu pro danou transakci.
    - (Volitelně) Zda je transakce vratka nebo ne.
    - Schéma sémantických dat vyžaduje následující informace:
        - **ID transakce:** Jedinečný identifikátor nákupu nebo transakce.
        - **Datum transakce:** Datum nákupu nebo transakce.
        - **Hodnota transakce:** Číselná hodnota nákupu nebo transakce.
        - **Jedinečné ID produktu:** ID zakoupeného produktu nebo služby, pokud jsou vaše data na úrovni řádkové položky.
        - (Volitelně) **Nákup nebo vratka:** Pole true/false, které identifikuje, zda transakce byla vratka, nebo ne. Pokud **Hodnota transakce** je záporná, použijeme tyto informace také k odvození vratky.


## <a name="create-a-product-recommendation-prediction"></a>Vytvoření predikce doporučení produktů

1. V části Customer Insights přejděte na **Analytické nástroje** > **Předpovědi**.

1. Vyberte dlaždici **Model doporučení produktů (Preview)** a vyberte **Použít tento model**.
   > [!div class="mx-imgBorder"]
   > ![Dlaždice modelu doporučení produktů s tlačítkem Použít tento model](media/product-recommendation-usethismodel.PNG "Dlaždice modelu doporučení produktů s tlačítkem Použít tento model")

1. Zkontrolujte informace o požadavcích na model. Pokud máte požadovaná data, vyberte **Začít**.

### <a name="name-model"></a>Pojmenování modelu

1. Zadejte název modelu, abyste jej odlišili od ostatních modelů.

1. Zadejte název výstupní entity pouze pomocí písmen a číslic, bez mezer. Jedná se o název, který bude používat entita modelu. Pak vyberte **Další**.

### <a name="define-product-recommendation-configuration"></a>Definování konfigurace doporučení produktů

1. Nastavte **Počet produktů**, kolik chcete doporučit zákazníkovi. Tato hodnota závisí na tom, jak váš způsob doručení vyplňuje data. Pokud můžete doporučit tři produkty, nastavte tuto hodnotu odpovídajícím způsobem.
   
   >[!TIP]
   > Kdykoli můžete použít volbu **Uložit a zavřít**, kterou uložíte predikci jako koncept. Koncept predikce najdete na kartě **Moje predikce**.

1. Zvolte, zda chcete **Navrhovat produkty, které zákazníci nedávno zakoupili**.

1. Pokud jste se rozhodli *nedoporučit* nedávno zakoupené produkty, nastavte **Okno ohlédnutí**. Toto nastavení určuje časový rámec, kterým se model řídí před opětovným doporučením produktu uživateli. Například uveďte, že si zákazník kupuje notebook každé 2 roky. Toto časové okno projde historii nákupů za poslední 2 roky a pokud nalezne položku, bude položka vyfiltrována z doporučení.

1. Vyberte **Další**.

### <a name="add-required-data"></a>Přidejte požadovaná data

1. Vyberte **Přidat data** pro **Historie transakcí zákazníka** a vyberte entitu, která poskytuje informace o historii transakcí/nákupů, jak je popsáno v [předpokladech](#prerequisites).

1. Namapujte sémantická pole na atributy v rámci entity historie nákupu a vyberte **Další**. Pro popis polí se podívejte na [předpoklady](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definování vztahů entit](media/product-recommendation-purchasehistorymapping.PNG "Stránka historie nákupu zobrazující sémantické atributy, které jsou mapovány na pole ve vybrané entitě historie nákupů")

1. Pokud pole nejsou vyplněna, nakonfigurujte vztah z entity historie nákupu na entitu *Zákazník*.
    1. Vyberte **Entita Historie nákupů**.
    1. Vyberte **Pole**, které identifikuje zákazníka v entitě historie nákupu. Musí se vztahovat k primárnímu ID zákazníka vaší entity *Zákazník*.
    1. Vyberte **entitu zákazníka**, která odpovídá vaší primární entitě zákazníka.
    1. Zadejte název, který popisuje daný vztah.
       > [!div class="mx-imgBorder"]
       > ![Stránka historie nákupů znázorňující vytvoření vztahu se zákazníkem](media/model-purchase-join.png "Stránka historie nákupů znázorňující vytvoření vztahu se zákazníkem")

1. Zvolte **Uložit**.

1. Vyberte **Další**.

### <a name="set-schedule-and-review-configuration"></a>Nastavení plánu a kontrola konfigurace

1. Nastavte frekvenci opětovného cvičení modelu. Toto nastavení je důležité pro aktualizaci přesnosti predikcí, když jsou do Customer Insights importována nová data. Většina podniků může provést opětovné cvičení modelu jednou za měsíc a mít predikce s dobrou přesností.

1. Vyberte **Další**.

1. Zkontrolujte konfiguraci. Výběrem možnosti **Upravit** pod zobrazenou hodnotou se můžete vrátit do libovolné části konfigurace predikce. Nebo můžete vybrat krok konfigurace z ukazatele průběhu.

1. Pokud jsou všechny hodnoty správně nakonfigurovány, volbou **Uložit a spustit** zahájíte proces predikce. Na kartě **Moje predikce** se zobrazuje stav vašich predikcí. Dokončení procesu může trvat několik hodin v závislosti na množství dat použitých v predikci.

## <a name="review-a-prediction-status-and-results"></a>Kontrola stavu a výsledků predikce

1. Jděte na kartu **Moje predikce** v umístění **Analytické nástroje** > **Predikce**.
   > [!div class="mx-imgBorder"]
   > ![Zobrazení stránky Moje predikce](media/product-recommendation-mypredictions.PNG "Zobrazení stránky Moje predikce")

1. Vyberte předpověď, kterou chcete zkontrolovat.
   - **Název predikce:** Název predikce zadaný při jejím vytvoření.
   - **Typ predikce:** Typ modelu použitého pro predikci.
   - **Výstupní entita:** Název entity pro uložení výstupu predikce. Můžete najít entitu s tímto názvem v umístění **Data** > **Entity**.
   - **Predikované pole:** Toto pole je vyplněno pouze pro některé typy predikcí a nepoužívá se v predikci odchodu zákazníků.
   - **Stav:** Aktuální stav běhu predikce.
        - **Ve frontě:** Predikce aktuálně čeká na spuštění dalších procesů.
        - **Aktualizace:** Predikce je v současné době ve fázi zpracování „skóre“, během které vznikají výsledky, které jsou předány do výstupní entity.
        - **Selhání:** Predikce selhala. Další podrobnosti zobrazíte výběrem položky **Protokoly**.
        - **Úspěch:** Predikce byla úspěšná. Volbou **Zobrazit** pod svislými třemi tečkami zkontrolujete predikci.
   - **Upraveno:** Datum, kdy byla konfigurace predikce změněna.
   - **Poslední aktualizace:** Datum, kdy predikce aktualizovala výsledky ve výstupní entitě.

1. Vyberte svislé tři tečky vedle predikce, pro kterou chcete zkontrolovat výsledky, a vyberte **Zobrazit**.
   > [!div class="mx-imgBorder"]
   > ![Zobrazení možností v nabídce svislých třech teček pro predikci včetně úprav, aktualizace, zobrazení, protokolů a odstranění](media/product-recommendation-verticalellipses.PNG "Zobrazení možností v nabídce svislých třech teček pro predikci včetně úprav, aktualizace, zobrazení, protokolů a odstranění")

1. Na stránce výsledků jsou tři primární sekce s daty:
    1. **Výkon cvičení modelu:** Skóre může být A, B nebo C. Toto skóre označuje výkon predikce a může vám pomoci při rozhodování o použití výsledků uložených ve výstupní entitě.
        - Skóre je stanoveno na základě následujících pravidel:
            - **A** Kvalita modelu bude ohodnocena známkou **A**, pokud je metrika „Úspěch @ K“ alespoň o 10 % vyšší než základ. 
            - **B** Kvalita modelu bude ohodnocena známkou **B**, pokud je metrika „Úspěch @ K“ o 0 až 10 % vyšší než základ.
            - **C** Kvalita modelu bude ohodnocena známkou **C**, pokud je metrika „Úspěch @ K“ menší než základ.
               
               > [!div class="mx-imgBorder"]
               > ![Zobrazení výsledku výkonu modelu](media/product-recommendation-modelperformance.PNG "Zobrazení výsledku výkonu modelu")
            - **Základ**: Model převezme nejvíce doporučované produkty podle počtu nákupů u všech zákazníků a na základě naučených pravidel rozpoznaných modelem vytvoří sadu doporučení pro zákazníky. Predikce jsou poté porovnány s nejlepšími produkty, které byly vypočítány podle počtu zákazníků, kteří si produkty koupili. Pokud má zákazník v doporučených produktech alespoň jeden produkt, který byl také mezi nejprodávanějšími produkty, považuje se za součást základu. Pokud by 10 z těchto zákazníků mělo zakoupený doporučený produkt ze 100 celkových zákazníků, byl by základ 10 %.
            - **Úspěch @ K.**: Pomocí ověřovací sady časového období transakcí se vytvoří doporučení pro všechny zákazníky a porovnají se s ověřovací sadou transakcí. Například v období 12 měsíců může být měsíc 12 vyčleněn jako ověřovací sada dat. Pokud model predikuje alespoň jednu věc, kterou byste si koupili v 12. měsíci na základě toho, co se dozvěděl z předchozích 11 měsíců, zákazník by zvýšil metriku „Úspěch @ K“.
    
    1. **Nejdoporučovanější produkty (s počítadlem):** Prvních 5 produktů, které byly predikovány vašim zákazníkům.
       > [!div class="mx-imgBorder"]
       > ![Graf zobrazující prvních 5 nejdoporučovanějších produktů](media/product-recommendation-topproducts.PNG "Graf zobrazující prvních 5 nejdoporučovanějších produktů")
    
    1. **Doporučení produktů s vysokou spolehlivostí:** Ukázka doporučených produktů zákazníkům, o kterých se model domnívá, že si je zákazník pravděpodobně zakoupí.
       > [!div class="mx-imgBorder"]
       > ![Seznam zobrazující návrhy s vysokou spolehlivostí pro vybranou sadu jednotlivých zákazníků](media/product-recommendation-highconfidence.PNG "Seznam zobrazující návrhy s vysokou spolehlivostí pro vybranou sadu jednotlivých zákazníků")

## <a name="fix-a-failed-prediction"></a>Oprava neúspěšné predikce

1. Jděte na kartu **Moje predikce** v umístění **Analytické nástroje** > **Predikce**.

1. Vyberte predikci, pro kterou chcete zobrazit protokoly chyb, a vyberte **Protokoly**.

1. Zkontrolujte všechny chyby. Existuje několik typů chyb, které mohou nastat a které popisují, jaký stav chybu způsobil. Například chyba, že není k dispozici dostatek dat, aby bylo možné provést přesnou predikci, se obvykle vyřeší načtením dalších dat do Customer Insights.

## <a name="refresh-a-prediction"></a>Aktualizace předpovědi

Predikce se automaticky aktualizují podle stejného [plánu aktualizace dat](system.md#schedule-tab), jaký je konfigurován v nastavení.

1. Jděte na kartu **Moje predikce** v umístění **Analytické nástroje** > **Predikce**.

1. Vyberte svislé tři tečky vedle predikce, kterou chcete aktualizovat.

1. Vyberte **Aktualizovat**.

## <a name="delete-a-prediction"></a>Odstranění predikce

Odstraněním predikce odstraníte také jeho výstupní entitu.

1. Jděte na kartu **Moje predikce** v umístění **Analytické nástroje** > **Predikce**.

1. Vyberte svislé tři tečky vedle predikce, kterou chcete odstranit.

1. Vyberte **Odstranit**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]