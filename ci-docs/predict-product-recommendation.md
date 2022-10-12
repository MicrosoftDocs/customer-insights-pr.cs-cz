---
title: Predikce doporučení produktů
description: Predikujte produkty, které si zákazník pravděpodobně zakoupí nebo s nimž bude interagovat.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610274"
---
# <a name="predict-product-recommendations"></a>Predikce doporučení produktů

Model doporučení produktů vytváří sady prediktivních doporučení produktů. Doporučení jsou založena na předchozím nákupním chování a zákaznících s podobnými nákupními vzory. Tento model je určen pro individuální zákazníky (B2C).

Musíte mít obchodní znalosti různých typů produktů pro vaše podnikání a jak s nimi zákazníci interagují. Podporujeme doporučení produktů, které si vaši zákazníci dříve zakoupili, nebo doporučení pro nové produkty.

Doporučení produktů mohou podléhat místním zákonům a předpisům a očekáváním zákazníků, které model na základě svého sestavení nezohledňuje. Proto **musíte před doručením vašim zákazníkům zkontrolovat doporučení** k zajištění, že dodržujete všechny příslušné zákony nebo předpisy a očekávání zákazníků ohledně toho, co můžete doporučit.

Výstup tohoto modelu poskytuje doporučení založená na ID produktu. Váš doručovací mechanismus musí namapovat předpokládaná ID produktu na vhodný obsah pro vaše zákazníky, aby zohledňoval lokalizaci, obsah obrázku a další obsah nebo chování specifické pro firmy.

> [!TIP]
> Vyzkoušejte predikci doporučení produktu pomocí ukázkových dat: [Příručka k ukázce predikce doporučení produktu](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Předpoklady

- Alespoň [oprávnění Přispěvatel](permissions.md)
- Nejméně 100 zákazníků, nejlépe více než 10 000 zákazníků.
- Identifikátor zákazníka, jedinečný identifikátor pro přiřazení transakcí jednotlivému zákazníkovi
- Nejméně jeden rok transakčních údajů, nejlépe dva až tři roky, aby zahrnovaly určitou sezónnost. V ideálním případě alespoň tři nebo více transakcí na jedno ID zákazníka. Historie transakcí musí obsahovat:
  - **ID transakce**: Jedinečný identifikátor nákupu nebo transakce.
  - **Datum transakce**: Datum nákupu nebo transakce.
  - **Hodnota transakce:** Číselná hodnota nákupu nebo transakce.
  - **Jedinečné ID produktu:** ID zakoupeného produktu nebo služby, pokud jsou vaše data na úrovni řádkové položky.
  - **Nákup, nebo vratka**: Logická hodnota true/false, kde hodnota *true* identifikuje, že transakce byla vratka. Pokud nejsou poskytnuty údaje o nákupu nebo vrácení v modelu a **Hodnota transakce** je záporná, považujeme transakci za vratku.
- Datová entita katalogu produktů pro použití filtru produktu.

> [!NOTE]
> - Model vyžaduje historii transakcí vašich zákazníků, kde transakce jsou jakákoli data, která popisují interakci uživatele s produktem. Například nákup produktu, absolvování kurzu nebo účast na události.
> - Lze konfigurovat pouze jednu entitu historie transakcí. Pokud existuje více entit nákupu, sjednoťte je před příjmem dat v Power Query.
> - Pokud jsou objednávka a podrobnosti objednávky různé entity, připojte se k nim před použitím v modelu. Model v entitě nefunguje pouze s ID objednávky nebo ID příjmu.

## <a name="create-a-product-recommendation-prediction"></a>Vytvoření predikce doporučení produktů

Kdykoliv můžete volbou **Uložit koncept** uložit predikci jako koncept. Koncept predikce se zobrazí na kartě **Moje predikce**.

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Vytvořit** vyberte **Použít model** na dlaždici **Doporučení produktů (Preview)**.

1. Vyberte **Začínáme**.

1. **Pojmenujte tento model** a zadejte **Název entity výstupu**, abyste je odlišili od jiných modelů nebo entit.

1. Vyberte **Další**.

### <a name="define-product-recommendation-preferences"></a>Definování předvoleb doporučení produktů

1. Nastavte **Počet produktů**, kolik chcete doporučit zákazníkovi. Tato hodnota závisí na tom, jak váš způsob doručení vyplňuje data.

1. Vyberte, zda chcete zahrnout produkty, které si zákazníci dříve zakoupili, v poli **Očekávány opakované nákupy**.

1. Nastavte **Období pohledu zpět** na časový rámec, kterým se model řídí před opětovným doporučením produktu uživateli. Například označte, že si zákazník kupuje notebook každé dva roky. Model hledá v historii nákupů za poslední dva roky, a pokud najde položku, bude položka filtrována z doporučení.

1. Vyberte **Další**.

### <a name="add-purchase-history"></a>Přidat historii nákupů

1. Vyberte **Přidat data** u **Historie transakcí zákazníka**.

1. Nastavte sémantický typ aktivity **SalesOrderLine**, který obsahuje informace o požadované transakci nebo historii nákupů. Pokud aktivita nebyla nastavena, vyberte **zde** a vytvořte ji.

1. V části **Činnosti**, pokud byly atributy aktivity sémanticky namapovány při vytváření aktivity, vyberte konkrétní atributy nebo entitu, na kterou se má výpočet zaměřit. Pokud sémantické mapování neproběhlo, vyberte **Upravit** a namapujte data.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Boční podokno zobrazující výběr konkrétních aktivit pod sémantickým typem.":::

1. Vyberte **Další** a zkontrolujte atributy požadované pro tento model.

1. Vyberte **Uložit**.

1. Vyberte **Další**.

### <a name="add-product-information-and-filters"></a>Přidání informací o produktu a filtrů

Pro typ predikce, který vytvoříte, jsou někdy výhodné nebo vhodné pouze určité produkty. Filtry produktů umožňují identifikovat podmnožinu produktů se specifickými vlastnostmi, které můžete doporučit svým zákazníkům. Model použije všechny dostupné produkty, aby se naučil vzory, ale ve svém výstupu použije pouze produkty odpovídající filtrům produktů.

1. Přidejte svou entitu katalogu produktů, která obsahuje informace pro každý produkt. Mapujte požadované informace a vyberte možnost **Uložit**.

1. Vyberte **Další**.

1. Vyberte **Filtry produktu**:

   - **Žádné filtry**: Použijte všechny produkty v predikci doporučení produktu.

   - **Definovat konkrétní filtry produktu**: Použijte konkrétní produkty v predikci doporučení produktu. V podokně **Atributy katalogu produktů** vyberte atributy z entit katalogu produktů, které chcete zahrnout do filtru.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Postranní podokno zobrazující atributy v entitě katalogu produktů, které chcete vybrat pro filtry produktů.":::

1. Vyberte, zda má produktový filtr použít konektory **and** nebo **or** pro logickou kombinaci vašeho výběru atributů z katalogu produktů.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Ukázková konfigurace produktových filtrů kombinovaná s logickými spojkami AND.":::

1. Vyberte **Další**.

### <a name="set-update-schedule"></a>Natavení plánu aktualizace

1. Vyberte frekvenci opětovného trénování modelu. Toto nastavení je důležité pro aktualizaci přesnosti predikcí, když jsou do Customer Insights vložena nová data. Většina podniků může provést opětovné cvičení modelu jednou za měsíc a mít predikce s dobrou přesností.

1. Vyberte **Další**.

### <a name="review-and-run-the-model-configuration"></a>Zkontrolujte a spusťte konfiguraci modelu

Krok **Zkontrolovat a spustit** zobrazuje souhrn konfigurace a poskytuje možnost provést změny před vytvořením predikce.

1. Vyberte **Upravit** na kterémkoli z kroků ke kontrole a provedení jakýchkoli změn.

1. Pokud jste spokojení se svými výběry, volbou **Uložit a spustit** spusťte model. Vyberte **Hotovo**. Karta **Moje předpovědi** se zobrazí při vytváření predikce. Dokončení procesu může trvat několik hodin v závislosti na množství dat použitých v predikci.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Zobrazení výsledků predikce

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Moje predikce** vyberte predikci, kterou chcete zobrazit.

Na stránce s výsledky je pět primárních sekcí dat.

- **Výkon modelu:** Známky A, B a C označují výkon predikce a mohou vám pomoci při rozhodování o použití výsledků uložených ve výstupní entitě.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Obrázek výsledku výkonu modelu se známkou A.":::

  Známky se určují na základě následujících pravidel:
  - **A**, když je metrika „Úspěch @ K“ alespoň o 10 % vyšší než výchozí hodnota.
  - **B**, když je metrika „Úspěch @ K“ o 0 až 10 % vyšší než výchozí hodnota.
  - **C**, když je metrika „Úspěch @ K“ menší výchozí hodnota.
  - **Základ**: Nejvíce doporučované produkty podle počtu nákupů u všech zákazníků a naučená pravidla rozpoznaná modelem = sada doporučení pro zákazníky. Predikce jsou poté porovnány s nejlepšími produkty, které byly vypočítány podle počtu zákazníků, kteří si produkty koupili. Pokud má zákazník v doporučených produktech alespoň jeden produkt, který byl také mezi nejprodávanějšími produkty, považuje se za součást základu. Pokud by například 10 z těchto zákazníků mělo zakoupený doporučený produkt ze 100 celkových zákazníků, byl by základ 10 %.
  - **Úspěch @ K.**: Doporučení jsou vytvořena pro všechny zákazníky a porovnají se s ověřovací sadou časového období transakcí. Například v období 12 měsíců může být měsíc 12 vyčleněn jako ověřovací sada dat. Pokud model predikuje alespoň jednu věc, kterou byste si koupili v 12. měsíci na základě toho, co se dozvěděl z předchozích 11 měsíců, zákazník by zvýšil metriku „Úspěch @ K“.

- **Nejvíce doporučované produkty (se shodou):** Prvních pět produktů, které byly predikovány vašim zákazníkům.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Graf zobrazující prvních 5 nejdoporučovanějších produktů.":::

- **Klíčové faktory doporučení:** Model používá k provádění doporučení produktů historii transakcí zákazníků. Učí se vzory založené na minulých nákupech a hledá podobnosti mezi zákazníky a produkty. Tyto podobnosti se pak využijí ke generování doporučení produktů.
  Následují faktory by mohly ovlivnit doporučení produktu generované modelem.
  - **Minulé transakce**: Doporučený produkt byl založen na minulých nákupních vzorcích. Model může například doporučit *Povrchovou obloukovou myš*, pokud někdo nedávno koupil *Povrchovou knihu 3* a *Povrchové pero*. Model se dozvěděl, že historicky si mnoho zákazníků koupilo *Povrchovou obloukovou myš* po zakoupení *Povrchové knihy 3* a *Povrchového pera*.
  - **Podobnost zákazníka**: Doporučený produkt byl historicky zakoupen jinými zákazníky, kteří vykazují podobné vzorce nákupu. Například Johnovi byla doporučena *Povrchová sluchátka 2*, protože Jennifer a Brad nedávno zakoupili *Povrchová sluchátka 2*. Model věří, že John je podobný Jennifer a Bradovi, protože historicky měli podobné nákupní vzorce.
  - **Podobnost produktu**: Doporučený produkt je podobný ostatním produktům, které si zákazník dříve zakoupil. Model považuje dva výrobky za podobné, pokud byly zakoupeny společně nebo podobnými zákazníky. Například někdo dostane doporučení pro *Úložiště USB*, protože dříve zakoupili *Adaptér USB-C na USB* a model věří, že *Úložiště USB* je podobné *Adaptéru USB-C na USB* založenému na historických vzorcích nákupu.

  Každé doporučení produktu je ovlivněno jedním nebo více z těchto faktorů. Procento doporučení, kde každý ovlivňující faktor hrál roli, je zobrazeno v grafu. V následujícím příkladu bylo 100 % doporučení ovlivněno minulými transakcemi, 60 % podobností zákazníků a 22 % podobností produktů. Umístěním kurzoru myši nad pruhy v grafu zobrazíte přesné procento, kam přispěly ovlivňující faktory.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Klíčové faktory doporučení, které model získal při generování doporučení produktu.":::

- **Statistika dat**: Přehled počtu transakcí, zákazníků a produktů, které model zvažuje. Je založen na vstupních datech, která byla použita k osvojení vzorů a generování doporučení produktů.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Statistiky dat kolem vstupních dat používaných modelem k učení vzorců.":::
  
  Model používá všechna dostupná data k učení vzorců. Pokud tedy v konfiguraci modelu používáte filtrování produktů, v této části se zobrazuje celkový počet produktů, které model analyzoval, aby se naučil vzorce, které se mohou lišit od počtu produktů, které odpovídají definovaným kritériím filtrování. Filtrování se aplikuje na výstup generovaný modelem.

- **Ukázková doporučení produktů:** Ukázka doporučených produktů, o kterých se model domnívá, že si je zákazník pravděpodobně zakoupí. Pokud je přidán katalog produktů, ID produktů jsou nahrazena názvy produktů.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Seznam zobrazující návrhy s vysokou spolehlivostí pro vybranou sadu jednotlivých zákazníků.":::

> [!NOTE]
> Ve výstupní entitě tohoto modelu *Skóre* ukazuje kvantitativní měřítko doporučení. Model doporučuje produkty s vyšším skóre než produkty s nižším skóre. Chcete-li zobrazit skóre, přejděte na **Data** > **Entity** a zobrazte kartu data pro výstupní entitu, kterou jste definovali pro tento model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
