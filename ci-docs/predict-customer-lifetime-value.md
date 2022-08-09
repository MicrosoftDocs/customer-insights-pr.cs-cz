---
title: Predikce hodnoty životnosti zákazníka (CLV)
description: Predikce potenciálních výnosů pro aktivní zákazníky v budoucnosti.
ms.date: 07/21/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: b6f6665d906cc96688efe84035336f64d2a39303
ms.sourcegitcommit: 80d8436d8c940f1267e6f26b221b8d7ce02ed26b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186432"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Predikce hodnoty životnosti zákazníka (CLV)

Predikujte potenciální hodnotu (výnosy), kterou jednotliví aktivní zákazníci přivedou do vašeho podnikání v definovaném budoucím časovém období. Tato funkce vám pomůže dosáhnout různých cílů:

- Identifikace zákazníků s vysokou hodnotou a zpracování tohoto přehledu
- Vytváření strategických zákaznických segmentů na základě jejich potenciální hodnoty k provádění personalizovaných kampaní s cíleným prodejem, marketingem a podporou
- Směrování vývoje produktů zaměřením na funkce, které zvyšují hodnotu pro zákazníka
- Optimalizace prodejní nebo marketingové strategie a přesnější přidělení rozpočtu pro dosah zákazníků
- Rozpoznání a odměnění vysoce hodnotných zákazníků prostřednictvím věrnostních programů nebo programů odměn

## <a name="prerequisites"></a>Požadavky

Než začnete, zvažte, co CLV znamená pro vaše podnikání. V současné době podporujeme transakční predikce CLV. Predikovaná hodnota zákazníka je založena na historii obchodních transakcí. K vytvoření predikce potřebujete oprávnění alespoň [Přispěvatel](permissions.md).

Protože konfigurace a spuštění modelu CLV nezabere mnoho času, zvažte vytvoření několika modelů s různými předvolbami vstupu a porovnejte výsledky modelů, abyste zjistili, který modelový scénář nejlépe vyhovuje vašim obchodním potřebám.

### <a name="data-requirements"></a>Požadavky na data

Následující data jsou povinná, a ta, která jsou označena jako volitelná, se doporučují pro zvýšení výkonu modelu. Čím více dat model dokáže zpracovat, tím přesnější bude predikce. Proto doporučujeme, abyste ingestovali více údajů o aktivitě zákazníků, pokud jsou k dispozici.

- Identifikátor zákazníka: Jedinečný identifikátor pro přiřazení transakcí jednotlivému zákazníkovi

- Historie transakcí: Historický protokol transakcí s níže uvedeným sémantickým datovým schématem
    - **ID transakce**: Jedinečný identifikátor jednotlivých transakcí
    - **Datum transakce**: Datum, nejlépe časové razítko každé transakce
    - **Částka transakce**: Peněžní hodnota (například výnos nebo zisková marže) každé transakce
    - **Popisek přiřazený k vratkám** (volitelně): Booleovská hodnota označující, zda je transakce vratka 
    - **ID produktu** (volitelně): ID produktu, který je součástí transakce

- Další údaje (volitelně), například
    - Webové aktivity: historie návštěv webových stránek, historie e-mailů
    - Věrnostní aktivity: věrnostní bonusové body, akumulace a historie uplatnění
    - Protokol služeb zákazníkům, historie volání, reklamace nebo historie vratek
    - Informace o profilu zákazníka
- Údaje o aktivitách zákazníka (volitelně):
    - Identifikátory aktivit pro rozlišení aktivit stejného typu
    - Identifikátory zákazníků pro mapování aktivit na vaše zákazníky
    - Informace o aktivitě obsahující název a datum aktivity
    - Schéma sémantických dat pro aktivity zahrnuje:
        - **Primární klíč**: Jedinečný identifikátor aktivity.
        - **Časové razítko**: Datum a čas události identifikovaný primárním klíčem.
        - **Událost (název aktivity)**: Název události, kterou chcete použít
        - **Podrobnosti (částka nebo hodnota)**: Podrobnosti o aktivitě zákazníka

- Navrhované vlastnosti dat:
    - Dostatečná historická data: Nejméně jeden rok transakčních dat. Nejlépe dva až tři roky transakčních dat k předpovědi CLV na jeden rok.
    - Vícenásobné nákupy na zákazníka: V ideálním případě alespoň dvě až tři transakce na ID zákazníka, nejlépe v několika termínech.
    - Počet zákazníků: Nejméně 100 jedinečných zákazníků, nejlépe více než 10 000 zákazníků. Model selže s méně než 100 zákazníky a nedostatečnými historickými daty
    - Úplnost dat: Méně než 20 % chybějící hodnoty v požadovaných polích ve vstupních datech

> [!NOTE]
> - Model vyžaduje historii transakcí vašich zákazníků. Aktuálně lze konfigurovat pouze jednu entitu historie transakcí. Pokud existuje více entit nákupu/transakce, ještě před příjmem dat je můžete sjednotit v Power Query.
> - Pro další údaje o aktivitě zákazníka (volitelně) však můžete přidat tolik entit aktivity zákazníků, kolik chcete pro zohlednění v modelu.

## <a name="create-a-customer-lifetime-value-prediction"></a>Vytvoření predikce hodnoty životnosti zákazníka

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Vyberte dlaždici **Hodnota životnosti zákazníka** a vyberte **Použít model**. 

1. V podokně **Hodnota životnosti zákazníka** vyberte **Začít**.

1. **Pojmenujte tento model** a zadejte **Název entity výstupu**, abyste je odlišili od jiných modelů nebo entit.

1. Vyberte **Další**.

### <a name="define-model-preferences"></a>Definování předvoleb modelu

1. Nastavit **Časové období predikce**, kterým definujte, jak daleko do budoucnosti chcete predikovat CLV.    
   Ve výchozím nastavení je jednotka nastavena jako měsíce. Můžete to změnit na roky, abyste se dívali dále do budoucnosti.

   > [!TIP]
   > Chcete-li přesně předpovědět CLV pro vámi nastavené časové období, potřebujete srovnatelné období historických dat. Chcete-li například předpovídat CLV na příštích 12 měsíců, doporučujeme mít alespoň 18–24 měsíců historických dat.

1. Upřesněte, co **Aktivní zákazníci** znamenají pro vaše podnikání. Nastavte časový rámec, ve kterém zákazník musel mít alespoň jednu transakci, aby mohl být považován za aktivního. Model bude predikovat CLV pouze pro aktivní zákazníky. 
   - **Nechat model vypočítat nákupní interval (doporučeno)**: Model analyzuje vaše data a určuje časové období na základě historických nákupů.
   - **Nastavte interval ručně**: Pokud máte konkrétní obchodní definici aktivního zákazníka, vyberte tuto možnost a podle toho nastavte časové období.

1. Definujte percentil pro hodnotu **Zákazník s vysokou důležitostí**, abyste umožnili modelu poskytovat výsledky, které odpovídají vaší obchodní definici.
    - **Výpočet modelu (doporučeno)**: Model analyzuje vaše data a na základě historie transakcí vašich zákazníků určuje, co by pro vaši firmu mohl být vysoce hodnotný zákazník. Model používá heuristické pravidlo (inspirované pravidlem 80/20 neboli paretovým principem) k nalezení podílu zákazníků s vysokou hodnotou. Procento zákazníků, kteří v historickém období přispěli k 80% kumulativním výnosům vaší firmy, se považuje za zákazníky s vysokou hodnotou. Méně než 30–40 % zákazníků obvykle přispívá k 80% kumulativním výnosům. Toto číslo se však může lišit v závislosti na vašem podnikání a oboru.    
    - **Procento nejlepších aktivních zákazníků**: Definujte pro svou firmu vysoce hodnotné zákazníky jako percentil nejvíce platících zákazníků. Tuto možnost můžete použít například k definování zákazníků s vysokou hodnotou jako 20 % nejlepších budoucích platících zákazníků.

    Pokud vaše firma definuje zákazníky s vysokou hodnotou jiným způsobem, [dejte nám vědět, protože bychom rádi věděli, jak](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Vyberte **Další** a přejděte k dalšímu kroku.

### <a name="add-required-data"></a>Přidejte požadovaná data

1. V kroku **Požadovaná data** vyberte **Přidat data** pro **Historie transakcí zákazníka** a vyberte entitu, která poskytuje informace o historii transakcí, jak je popsáno v [předpokladech](#prerequisites).

1. Namapujte sémantická pole na atributy v rámci entity historie nákupu a vyberte **Další**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Obrázek konfiguračního kroku pro mapování atributů dat pro požadovaná data.":::
 
1. Pokud pole níže nejsou vyplněna, nakonfigurujte vztah z entity historie nákupu na entitu *Zákazník* a vyberte **Uložit**.
    1. Vyberte entitu historie transakcí.
    1. Vyberte pole, které identifikuje zákazníka v entitě historie nákupu. Musí se vztahovat k primárnímu ID zákazníka vaší entity zákazníka.
    1. Vyberte entitu, která odpovídá vaší primární entitě zákazníka.
    1. Zadejte název, který popisuje daný vztah.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Obrázek konfiguračního kroku k definování vztahu s entitou zákazníka.":::

1. Vyberte **Další**.

### <a name="add-optional-activity-data"></a>Přidání volitelných dat aktivity

Data odrážející klíčové interakce se zákazníky (jako je web, služby zákazníkům a protokoly událostí) přidávají kontext do záznamů transakcí. Více vzorů nalezených v datech aktivit zákazníků může zlepšit přesnost predikcí.

1. V kroku **Další údaje (volitelně)** vyberte **Přidat údaje** v sekci **Posilte přehledy modelů pomocí dalších údajů o aktivitách**. Vyberte entitu aktivit zákazníka, která poskytuje informace o aktivitě zákazníka, jak je popsáno v [předpokladech](#prerequisites).

1. Namapujte sémantická pole na atributy v rámci entity aktivity zákazníka a vyberte **Další**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Obrázek konfiguračního kroku pro mapování polí pro dodatečná data.":::

1. Vyberte typ aktivity, který odpovídá typu aktivity zákazníka, kterého přidáváte. Vyberte si z existujících typů aktivit nebo přidejte nový typ aktivity.

1. Nakonfigurujte vztah z vaší entity aktivity zákazníka s entitou *Zákazník*.

    1. Vyberte pole, které identifikuje zákazníka v tabulce aktivity zákazníka. Může přímo souviset s primárním ID zákazníka vaší entity *Zákazník*.
    1. Vyberte entitu *Zákazník*, která odpovídá vaší primární entitě *Zákazník*.
    1. Zadejte název, který popisuje daný vztah.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Obrázek kroku v toku konfigurace pro přidání dodatečných dat a konfiguraci aktivity s vyplněnými příklady.":::

1. Zvolte **Uložit**.
    Přidejte další data, pokud chcete zahrnout další aktivity zákazníků.

1. Přidejte volitelná zákaznická data nebo vyberte **Další**.

### <a name="add-optional-customer-data"></a>Přidání volitelných zákaznických dat

Vyberte si z 18 běžně používaných atributů profilu zákazníka, které chcete zahrnout jako vstup do modelu. Tyto atributy mohou vést k přizpůsobenějším, relevantnějším a použitelnějším výsledkům modelů pro vaše případy obchodního použití.

Například: Contoso Coffee chce předpovědět celoživotní hodnotu zákazníka, aby se zaměřila na zákazníky s vysokou důležitostí pomocí personalizované nabídky související s uvedením jejich nového espresso kávovaru. Contoso používá model CLV a přidává všech 18 atributů profilu zákazníka, aby zjistila, které faktory ovlivňují jejich zákazníky s nejvyšší důležitostí. Zjišťují, že poloha zákazníka je pro tyto zákazníky nejvlivnějším faktorem.
Na základě této informace uspořádají lokální akci uvádějící stroj na espresso na trh a spojí se s místními prodejci za účelem personalizované nabídky a speciálního zážitku z akce. Bez této informace by společnost Contoso možná posílala pouze obecné marketingové e-maily a promeškala příležitost přizpůsobit se tomuto místnímu segmentu svých vysoce důležitých zákazníků.

1. V kroku **Další údaje (volitelně)** vyberte **Přidat údaje** v sekci **Posilte přehledy modelů ještě více pomocí dalších zákaznických dat**.

1. Pro položku **Entita** volbou **Zákazník: CustomerInsights** vyberte tabulku sjednoceného profilu zákazníka, která je mapována na data atributů zákazníka. Pro **ID zákazníka** zvolte **System.Customer.CustomerId**.

1. Namapujte více polí, pokud jsou data dostupná ve vašich sjednocených zákaznických profilech.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Příklad mapovaných polí pro data profilu zákazníka.":::

1. Vyberte **Uložit** po namapování atributů, které má model použít k predikci celoživotní důležitosti zákazníka.

1. Vyberte **Další**.

### <a name="set-update-schedule"></a>Natavení plánu aktualizace

1. V kroku **Plán aktualizace dat** vyberte frekvenci opětovného trénování modelu na základě nejnovějších dat. Toto nastavení je důležité pro aktualizaci přesnosti předpovědí při zpracování nových dat v Customer Insights. Většina podniků může provést opětovné cvičení modelu jednou za měsíc a mít predikce s dobrou přesností.

1. Vyberte **Další**.

### <a name="review-and-run-the-model-configuration"></a>Zkontrolujte a spusťte konfiguraci modelu

1. V kroku **Kontrola podrobností modelu** ověřte konfiguraci predikce. Výběrem možnosti **Upravit** pod zobrazenou hodnotou se můžete vrátit do libovolné části konfigurace predikce. Krok konfigurace můžete vybrat také z ukazatele průběhu.

1. Pokud jsou všechny hodnoty správně nakonfigurovány, volbou **Uložit a spustit** spusťte model. Na kartě **Moje predikce** vidíte stav procesu predikce. Dokončení procesu může trvat několik hodin v závislosti na množství dat použitých v predikci.

## <a name="review-prediction-status-and-results"></a>Kontrola stavu a výsledků predikce

### <a name="review-prediction-status"></a>Kontrola stavu predikce

1.  Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**.
2.  Vyberte předpověď, kterou chcete zkontrolovat.

- **Název predikce**: Název predikce poskytnutý při jeho vytvoření.
- **Typ predikce**: Typ modelu použitého pro predikci
- **Výstupní entita**: Název entity pro uložení výstupu predikce. Přejděte na **Data** > **Entity**, chcete-li vyhledat entitu s tímto názvem.
- **Predikované pole**: Toto pole je vyplněno pouze pro některé typy predikcí a nepoužívá se v predikci hodnoty životnosti zákazníka.
- **Stav**: Stav spuštění predikce.
    - **Ve frontě**: Predikce čeká na dokončení dalších procesů.
    - **Aktualizace**: Predikce právě běží, aby vytvářela výsledky, které budou přenášeny do výstupní entity.
    - **Selhání**: Spuštění predikce selhalo. [Podívejte se do protokolů](manage-predictions.md#troubleshoot-a-failed-prediction) pro další podrobnosti.
    - **Úspěch**: Predikce byla úspěšná. Vyberte **Zobrazení** pod svislými elipsami, abyste zkontrolovali výsledky predikce.
- **Upraveno**: Datum, kdy byla konfigurace predikce změněna.
- **Poslední aktualizace**: Datum, kdy predikce aktualizovala výsledky ve výstupní entitě.

### <a name="review-prediction-results"></a>Kontrola výsledků predikce

1. Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**.

1. Vyberte predikci, u které chcete zkontrolovat výsledky.

Na stránce výsledků jsou tři primární sekce s daty.

- **Výkon tréninkového modelu**: A, B nebo C jsou možné známky. Tato známka označuje výkon predikce a může vám pomoci při rozhodování o použití výsledků uložených ve výstupní entitě. Vyberte **Další informace o tomto skóre**, abyste lépe porozuměli základním metrikám výkonu modelu a jak byla odvozena výsledná známka výkonu modelu.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Obrázek informačního rámečku se skóre modelu se známkou A.":::

  Pomocí definice vysoce hodnotných zákazníků poskytnuté při konfiguraci predikce systém vyhodnotí, jak model AI fungoval při predikování vysoce hodnotných zákazníků ve srovnání se základním modelem.    

  Známky se určují na základě následujících pravidel:
  - **A**, když model přesně predikoval nejméně o 5 % více hodnotných zákazníků ve srovnání se základním modelem.
  - **B**, když model přesně predikoval o 0 až 5 % více hodnotných zákazníků ve srovnání se základním modelem.
  - **C**, když model přesně predikoval méně hodnotných zákazníků ve srovnání se základním modelem.

  Podokno **Hodnocení modelu** obsahuje další podrobnosti o výkonu modelu AI a základním modelu. Základní model používá přístup, který není založen na AI, k výpočtu hodnoty životnosti zákazníka primárně dle historických nákupů provedených zákazníky.     
  Standardní vzorec použitý k výpočtu CLV základním modelem:    

  _**CLV pro každého zákazníka** = Průměrný měsíční nákup provedený zákazníkem v aktivním okně zákazníka * Počet měsíců v období predikce CLV * Celková míra uchování všech zákazníků*_

  Model AI se porovná se základním modelem na základě dvou metrik výkonu modelu.
  
  - **Míra úspěšnosti predikování zákazníků s vysokou hodnotou**

    Podívejte se na rozdíl v predikování zákazníků s vysokou hodnotou s použitím modelu AI v porovnání se základním modelem. Například 84% úspěšnost znamená, že ze všech vysoce hodnotných zákazníků v tréninkových datech dokázal model AI přesně zachytit 84 %. Poté porovnáme tuto úspěšnost s úspěšností základního modelu, abychom vykázali relativní změnu. Tato hodnota se používá k přiřazení známky k modelu.

  - **Metriky chyb**
    
    Další metrika umožňuje zkontrolovat celkový výkon modelu z hlediska chyby při predikování budoucích hodnot. K posouzení této chyby používáme celkovou metriku RMSE (Root Mean Squared Error). RMSE je standardní způsob měření chyby modelu v predikci kvantitativních dat. RMSE modelu AI se porovnává s RMSE základního modelu a vykáže se relativní rozdíl.

  Model AI upřednostňuje přesné hodnocení zákazníků podle hodnoty, kterou přinášejí vašemu podniku. K odvození konečné známky modelu se tedy používá pouze úspěšnost predikování zákazníků s vysokou hodnotou. Metrika RMSE je citlivá na odlehlé hodnoty. V situacích, kdy máte malé procento zákazníků s mimořádně vysokými hodnotami nákupu, nemusí celková metrika RMSE poskytnout úplný obraz o výkonu modelu.   

- **Hodnota zákazníků podle percentilu**: Podle vaší definice zákazníků s vysokou hodnotou jsou zákazníci seskupeni do skupin s nízkou a vysokou hodnotou na základě jejich predikcí CLV a zobrazeni v grafu. Umístěním kurzoru nad pruhy v histogramu můžete zobrazit počet zákazníků v každé skupině a průměrnou hodnotu CLV této skupiny. Tato data vám mohou pomoci, pokud chcete [vytvářet segmenty zákazníků](segments.md) na základě jejich predikcí CLV.

- **Nejvlivnější faktory**: Při vytváření CLV na základě vstupních dat poskytnutých modelu AI se zvažují různé faktory predikce. Každý z faktorů má svou důležitost vypočítanou pro agregované predikce, které model vytváří. Tyto faktory můžete použít k ověření výsledků predikce. Tyto faktory také poskytují lepší přehled o nejvlivnějších faktorech, které přispěly k predikci CLV u všech vašich zákazníků.

## <a name="manage-predictions"></a>Správa predikcí

Predikce můžete optimalizovat, odstraňovat jejich problémy, aktualizovat nebo odstranit. Projděte si sestavu použitelnosti vstupních dat a zjistěte v ní, jak zajistit, aby predikce byla rychlejší a spolehlivější. Další informace naleznete v tématu [Správa predikcí](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
