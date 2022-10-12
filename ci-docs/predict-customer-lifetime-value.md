---
title: Predikce hodnoty životnosti zákazníka (CLV)
description: Predikce potenciálních výnosů pro aktivní zákazníky v budoucnosti.
ms.date: 09/30/2022
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
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610366"
---
# <a name="predict-customer-lifetime-value-clv"></a>Predikce hodnoty životnosti zákazníka (CLV)

Predikujte potenciální hodnotu (výnosy), kterou jednotliví aktivní zákazníci přivedou do vašeho podnikání v definovaném budoucím časovém období. Tato předpověď vám pomůže:

- Identifikovat zákazníky s vysokou hodnotou a zpracování tohoto přehledu.
- Vytvářet strategické zákaznické segmenty na základě jejich potenciální hodnoty k provádění personalizovaných kampaní s cíleným prodejem, marketingem a podporou.
- Směrovat vývoj produktů zaměřením na funkce, které zvyšují hodnotu pro zákazníka.
- Optimalizovat prodejní nebo marketingové strategie a přesnější přidělení rozpočtu pro dosah zákazníků.
- Rozpoznávat a odměňovat vysoce hodnotné zákazníky prostřednictvím věrnostních programů nebo programů odměn.

Určovat, co CLV znamená pro vaše podnikání. Podporujeme transakční predikce CLV. Predikovaná hodnota zákazníka je založena na historii obchodních transakcí. Zvažte vytvoření několika modelů s různými předvolbami vstupu a porovnejte výsledky modelů, abyste zjistili, který modelový scénář nejlépe vyhovuje vašim obchodním potřebám.

> [!TIP]
> Vyzkoušejte CLV predikce s využitím ukázkových dat: [Průvodce vzorkem predikce Celoživotní hodnota zákazníka (CLV)](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Předpoklady

- Alespoň oprávnění [Přispěvatel](permissions.md)
- Nejméně 100 jedinečných zákazníků, nejlépe více než 10 000 zákazníků
- Identifikátor zákazníka, jedinečný identifikátor pro přiřazení transakcí jednotlivému zákazníkovi
- Alespoň rok historie transakcí, ideálně dva až tři roky. V ideálním případě alespoň dvě až tři transakce na ID zákazníka, nejlépe v několika termínech. Historie transakcí musí obsahovat:
  - **ID transakce**: Jedinečný identifikátor jednotlivých transakcí
  - **Datum transakce**: Datum nebo časové razítko každé transakce
  - **Částka transakce**: Peněžní hodnota (například výnos nebo zisková marže) každé transakce
  - **Popisek přiřazený k vratkám**: Logická hodnota true/false označující, zda je transakce vratka
  - **ID produktu**: ID produktu, který je součástí transakce
- Údaje o zákaznických aktivitách:
  - **Primární klíč**: Jedinečný identifikátor aktivity
  - **Časové razítko**: Datum a čas události identifikovaný primárním klíčem
  - **Událost (název aktivity)**: Název události, kterou chcete použít
  - **Podrobnosti (částka nebo hodnota)**: Podrobnosti o aktivitě zákazníka
- Další údaje, jako je:
  - Webové aktivity: historie návštěv webu nebo historie e-mailů
  - Věrnostní aktivity: věrnostní bonusové body, akumulace a historie uplatnění
  - Protokol služeb zákazníkům: historie volání, reklamace nebo historie vratek
  - Informace o profilu zákazníka
- Méně než 20 % chybějících hodnot v povinných polích

> [!NOTE]
> Lze konfigurovat pouze jednu entitu historie transakcí. Pokud existuje více entit nákupu nebo transakce, před příjmem dat je zkombinujte do Power Query.

## <a name="create-a-customer-lifetime-value-prediction"></a>Vytvoření predikce hodnoty životnosti zákazníka

Kdykoliv můžete volbou **Uložit koncept** uložit predikci jako koncept. Koncept predikce se zobrazí na kartě **Moje predikce**.

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Vytvořit** vyberte **Použít model** na dlaždici **Celoživotní hodnota zákazníka**.

1. Vyberte **Začínáme**.

1. **Pojmenujte tento model** a zadejte **Název entity výstupu**, abyste je odlišili od jiných modelů nebo entit.

1. Vyberte **Další**.

### <a name="define-model-preferences"></a>Definování předvoleb modelu

1. Nastavit **Časové období predikce**, kterým definujte, jak daleko do budoucnosti chcete predikovat CLV. Ve výchozím nastavení je jednotka nastavena jako měsíce.

   > [!TIP]
   > Chcete-li přesně předpovědět CLV pro nastavené časové období, je potřeba srovnatelné období historických dat. Chcete-li například předpovídat CLV na příštích 12 měsíců, mějte alespoň 18–24 měsíců historických dat.

1. Nastavte časový rámec, ve kterém zákazník musel mít alespoň jednu transakci, aby mohl být považován za aktivního. Model predikujte CLV pouze pro **aktivní zákazníky**.
   - **Nechat model vypočítat nákupní interval (doporučeno)**: Model analyzuje vaše data a určuje časové období na základě historických nákupů.
   - **Nastavit interval ručně**: Časové období pro vaši definici aktivního zákazníka.

1. Definujte percentil **zákazníka s vysokou hodnotou**.
    - **Výpočet modelu (doporučeno)**: Model používá pravidlo 80/20. Procento zákazníků, kteří v historickém období přispěli k 80% kumulativním výnosům vaší firmy, se považuje za zákazníky s vysokou hodnotou. Méně než 30–40 % zákazníků obvykle přispívá k 80% kumulativním výnosům. Toto číslo se však může lišit v závislosti na vašem podnikání a oboru.
    - **Procento nejaktivnějších zákazníků**: Specifický percentil pro zákazníka s vysokou hodnotou. Zadejte například **25** k definování zákazníků s vysokou hodnotou jako 25 % nejlepších budoucích platících zákazníků.

    Pokud vaše firma definuje zákazníky s vysokou hodnotou jiným způsobem, [dejte nám vědět, protože bychom rádi věděli, jak](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Vyberte **Další**.

### <a name="add-required-data"></a>Přidejte požadovaná data

1. Vyberte **Přidat data** u **Historie transakcí zákazníka**.

1. Vyberte typ sémantické aktivity, **SalesOrder** nebo **SalesOrderLine**, která obsahuje historii transakcí. Pokud aktivita nebyla nastavena, vyberte **zde** a vytvořte ji.

1. V části **Činnosti**, pokud byly atributy aktivity sémanticky namapovány při vytváření aktivity, vyberte konkrétní atributy nebo entitu, na kterou se má výpočet zaměřit. Pokud sémantické mapování neproběhlo, vyberte **Upravit** a namapujte data.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Přidejte požadovaná data pro model CLV":::

1. Vyberte **Další** a zkontrolujte atributy požadované pro tento model.

1. Vyberte **Uložit**.

1. Přidejte další aktivity nebo vyberte **Další**.

### <a name="add-optional-activity-data"></a>Přidání volitelných dat aktivity

Data odrážející klíčové interakce se zákazníky (jako je web, služby zákazníkům a protokoly událostí) přidávají kontext do záznamů transakcí. Více vzorů nalezených v datech aktivit zákazníků může zlepšit přesnost predikcí.

1. Vyberte **Přidat data** v části **Posílit přehledy modelů pomocí dalších údajů o aktivitách**.

1. Vyberte typ aktivity, který odpovídá typu aktivity zákazníka, kterého přidáváte. Pokud aktivita nebyla nastavena, vyberte **zde** a vytvořte ji.

1. V části **Činnosti**, pokud byly atributy aktivity namapovány při vytváření aktivity, vyberte konkrétní atributy nebo entitu, na kterou se má výpočet zaměřit. Pokud mapování neproběhlo, vyberte **Upravit** a namapujte data.

1. Vyberte **Další** a zkontrolujte atributy požadované pro tento model.

1. Vyberte **Uložit**.

1. Vyberte **Další**.

1. [Přidejte nepovinná data zákazníka](#add-optional-customer-data) nebo vyberte **Další** a přejděte na [Nastavit plán aktualizace](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Přidání volitelných zákaznických dat

Vyberte si z 18 běžně používaných atributů profilu zákazníka, které chcete zahrnout jako vstup do modelu. Tyto atributy mohou vést k přizpůsobenějším, relevantnějším a použitelnějším výsledkům modelů pro vaše případy obchodního použití.

Například: Contoso Coffee chce předpovědět celoživotní hodnotu zákazníka, aby se zaměřila na zákazníky s vysokou důležitostí pomocí personalizované nabídky související s uvedením jejich nového espresso kávovaru. Contoso používá model CLV a přidává všech 18 atributů profilu zákazníka, aby zjistila, které faktory ovlivňují jejich zákazníky s nejvyšší důležitostí. Zjišťují, že poloha zákazníka je pro tyto zákazníky nejvlivnějším faktorem.
Na základě této informace uspořádají lokální akci uvádějící stroj na espresso na trh a spojí se s místními prodejci za účelem personalizované nabídky a speciálního zážitku z akce. Bez této informace by společnost Contoso možná posílala pouze obecné marketingové e-maily a promeškala příležitost přizpůsobit se tomuto místnímu segmentu svých vysoce důležitých zákazníků.

1. Vyberte **Přidat data** v části **Posílit přehledy modelů ještě více pomocí dalších zákaznických dat**.

1. U možnosti **Entita** vyberte **Zákazník: CustomerInsights**, abyste vybrali jednotný profil zákazníka, který se mapuje na data atributů zákazníka. Pro **ID zákazníka** zvolte **System.Customer.CustomerId**.

1. Namapujte více polí, pokud jsou data dostupná ve vašich sjednocených zákaznických profilech.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Příklad mapovaných polí pro data profilu zákazníka.":::

1. Vyberte **Uložit**.

1. Vyberte **Další**.

### <a name="set-update-schedule"></a>Natavení plánu aktualizace

1. Vyberte frekvenci opětovného trénování modelu na základě nejnovějších dat. Toto nastavení je důležité pro aktualizaci přesnosti predikcí, když jsou do Customer Insights vložena nová data. Většina podniků může provést opětovné cvičení modelu jednou za měsíc a mít predikce s dobrou přesností.

1. Vyberte **Další**.

### <a name="review-and-run-the-model-configuration"></a>Zkontrolujte a spusťte konfiguraci modelu

Krok **Zkontrolovat a spustit** zobrazuje souhrn konfigurace a poskytuje možnost provést změny před vytvořením predikce.

1. Vyberte **Upravit** na kterémkoli z kroků ke kontrole a provedení jakýchkoli změn.

1. Pokud jste spokojení se svými výběry, volbou **Uložit a spustit** spusťte model. Vyberte **Hotovo**. Karta **Moje předpovědi** se zobrazí při vytváření predikce. Dokončení procesu může trvat několik hodin v závislosti na množství dat použitých v predikci.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Zobrazení výsledků predikce

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Moje predikce** vyberte predikci, kterou chcete zobrazit.

Na stránce výsledků jsou tři primární sekce s daty.

- **Výkon trénovacího modelu**: Známky A, B a C označují výkon predikce a mohou vám pomoci při rozhodování o použití výsledků uložených ve výstupní entitě.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Obrázek informačního rámečku se skóre modelu se známkou A.":::

  Customer Insights vyhodnotí, jak si model AI při predikování zákazníků s vysokou hodnotou vedl v porovnání se základním modelem.

  Známky se určují na základě následujících pravidel:
  - **A**, když model přesně predikoval nejméně o 5 % více hodnotných zákazníků ve srovnání se základním modelem.
  - **B**, když model přesně predikoval o 0 až 5 % více hodnotných zákazníků ve srovnání se základním modelem.
  - **C**, když model přesně predikoval méně hodnotných zákazníků ve srovnání se základním modelem.
  
  Vyberte [**Další informace o tomto skóre**](#learn-about-the-score) a otevřete podokno **Hodnocení modelu**, které obsahuje další podrobnosti o výkonu modelu AI a základním modelu. Pomůže vám lépe porozumět základním metrikám výkonu modelu a jak byla odvozena výsledná známka výkonu modelu. Základní model používá přístup, který není založen na AI, k výpočtu hodnoty životnosti zákazníka primárně dle historických nákupů provedených zákazníky.

- **Hodnota zákazníků podle percentilu**: Zákazníci s nízkou a vysokou hodnotou se zobrazí v grafu. Umístěním kurzoru nad pruhy v histogramu můžete zobrazit počet zákazníků v každé skupině a průměrnou hodnotu CLV této skupiny. Volitelně můžete [vytvářet segmenty zákazníků](prediction-based-segment.md) na základě jejich predikcí CLV.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Hodnota zákazníků podle percentilu pro model CLV":::

- **Nejvlivnější faktory**: Při vytváření CLV na základě vstupních dat poskytnutých modelu AI se zvažují různé faktory predikce. Každý z faktorů má svou důležitost vypočítanou pro agregované predikce, které model vytváří. Tyto faktory použijte k ověření výsledků predikce. Tyto faktory také poskytují lepší přehled o nejvlivnějších faktorech, které přispěly k predikci CLV u všech vašich zákazníků.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Nejvlivnější faktory pro model CLV":::

### <a name="learn-about-the-score"></a>Další informace o tomto skóre

Standardní vzorec použitý k výpočtu CLV základním modelem:

 _**CLV pro každého zákazníka** = Průměrný měsíční nákup provedený zákazníkem v aktivním okně zákazníka * Počet měsíců v období predikce CLV * Celková míra uchování všech zákazníků_

Model AI se porovná se základním modelem na základě dvou metrik výkonu modelu.
  
- **Míra úspěšnosti predikování zákazníků s vysokou hodnotou**

  Podívejte se na rozdíl v predikování zákazníků s vysokou hodnotou s použitím modelu AI v porovnání se základním modelem. Například 84% úspěšnost znamená, že ze všech vysoce hodnotných zákazníků v tréninkových datech dokázal model AI přesně zachytit 84 %. Poté porovnáme tuto úspěšnost s úspěšností základního modelu, abychom vykázali relativní změnu. Tato hodnota se používá k přiřazení známky k modelu.

- **Metriky chyb**

  Podívejte se na celkový výkon modelu z hlediska chyby při predikování budoucích hodnot. K posouzení této chyby používáme celkovou metriku RMSE (Root Mean Squared Error). RMSE je standardní způsob měření chyby modelu v predikci kvantitativních dat. RMSE modelu AI se porovnává s RMSE základního modelu a vykáže se relativní rozdíl.

Model AI upřednostňuje přesné hodnocení zákazníků podle hodnoty, kterou přinášejí vašemu podniku. K odvození konečné známky modelu se tedy používá pouze úspěšnost predikování zákazníků s vysokou hodnotou. Metrika RMSE je citlivá na odlehlé hodnoty. V situacích, kdy máte malé procento zákazníků s mimořádně vysokými hodnotami nákupu, nemusí celková metrika RMSE poskytnout úplný obraz o výkonu modelu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
