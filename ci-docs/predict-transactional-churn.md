---
title: Predikce úbytku transakcí (obsahuje video)
description: Predikujte, zda je zákazník ohrožen, když přestane nakupovat produkty nebo služby.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610504"
---
# <a name="predict-transaction-churn"></a>Predikce úbytku transakcí

Predikce úbytku transakcí pomáhá předvídat, zda si zákazník v daném časovém intervalu již nebude kupovat vaše produkty nebo služby.

Musíte mít obchodní znalosti k pochopení toho, co znamená pro vaši firmu odchod zákazníků. Podporujeme definice časově závislých ztrát, což znamená, že zákazník je považován za ztraceného po určitém období bez nákupu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

U prostředí založených na firemních účtech můžeme predikovat úbytek transakcí pro účet a také kombinaci účtu a další úrovně informací, jako je kategorie produktu. Například přidání dimenze může pomoci určit, jak je pravděpodobné, že účet „Contoso“ přestane kupovat kategorii produktů „kancelářské potřeby“. Kromě toho můžeme u obchodních účtů také použít umělou inteligenci ke generování seznamu potenciálních důvodů, proč pravděpodobně dojde k úbytku účtu pro kategorii informací sekundární úrovně.

> [!TIP]
> Vyzkoušejte predikci úbytku transakcí pomocí ukázkových dat: [Ukázkový průvodce pro predikcí úbytku transakcí](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Předpoklady

- Alespoň [oprávnění Přispěvatel](permissions.md).
- Nejméně 10 zákaznických profilů, nejlépe více než 1000 jedinečných zákazníků.
- Identifikátor zákazníka, jedinečný identifikátor pro párování transakcí s vašimi zákazníky.
- Údaje o transakcích za alespoň dvojnásobek zvoleného časového okna, jako jsou dva až tři roky historie transakcí. V ideálním případě alespoň dvě transakce na zákazníka. Historie transakcí musí obsahovat:
  - **ID transakce**: Jedinečný identifikátor nákupu nebo transakce.
  - **Datum transakce**: Datum nákupu nebo transakce.
  - **Hodnota transakce**: Měna nebo číselná hodnota částky transakce.
  - **Jedinečné ID produktu:** ID zakoupeného produktu nebo služby, pokud jsou vaše data na úrovni řádkové položky.
  - **Zda se jednalo o vrácení**: Pole true/false, které identifikuje, zda transakce byla návratová, nebo ne. Pokud **Hodnota transakce** je záporná, předpokládáme vratku.
- Data aktivity zákazníka:
  - Identifikátor zákazníka, jedinečný identifikátor pro mapování aktivit s vašimi zákazníky.
  - **Primární klíč:** Jedinečný identifikátor aktivity. Například záznam o návštěvě nebo využití webu, který ukazuje, že zákazník vyzkoušel vzorek vašeho produktu.
  - **Časové razítko**: Datum a čas události identifikovaný primárním klíčem.
  - **Událost:** Název události, kterou chcete použít. Například pole s názvem „UserAction“ v obchodě s potravinami může být kupón použitý zákazníkem.
  - **Podrobnosti:** Podrobné informace o akci. Například pole s názvem „CouponValue“ v obchodě s potravinami může být hodnota měny kupónu.
- Méně než 20 % chybějících hodnot v datovém poli poskytnuté entity

U obchodních účtů (B2B) přidejte zákaznická data přiřazená ke statičtějším atributům, abyste zajistili nejlepší výkon modelu:
- **CustomerID:** Jedinečný identifikátor pro zákazníka.
- **Datum vytvoření:** Datum, kdy byl zákazník původně přidán.
- **Stát nebo provincie:** Poloha státu nebo provincie zákazníka.
- **Země:** Země zákazníka.
- **Odvětví:** Typ odvětví zákazníka. Například pole s názvem „Odvětví“ v pražírně kávy může indikovat, zda byl zákazník maloobchod.
- **Klasifikace:** Kategorizace zákazníka pro vaši firmu. Například pole s názvem „ValueSegment“ v pražírně kávy může být úrovní zákazníka na základě velikosti zákazníka.

> [!NOTE]
> U firmy s vysokou frekvencí nákupu zákazníků (každých několik týdnů) se doporučuje zvolit kratší okno predikce a definici úbytku. Pro nízkou frekvenci nákupů (každých několik měsíců nebo jednou ročně) zvolte delší okno predikce a definici úbytku.

## <a name="create-a-transaction-churn-prediction"></a>Vytvoření predikce úbytku transakcí

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Vytvořit** vyberte **Použít model** na kartě **Model úbytku zákazníků**.

1. Vyberte **Transakce** pro typ úbytku a pak **Začínáme**.

1. **Pojmenujte tento model** a zadejte **Název entity výstupu**, abyste je odlišili od jiných modelů nebo entit.

1. Vyberte **Další**.

### <a name="define-customer-churn"></a>Definujte ztracené zákazníky

Kdykoliv můžete volbou **Uložit koncept** uložit predikci jako koncept. Koncept predikce se zobrazí na kartě **Moje predikce**.

1. Nastavte **Okno predikce**. Například predikujte riziko odchodu vašich zákazníků v průběhu následujících 90 dnů pro slazení vaší marketingové úspěšnosti prodeje. Předvídání rizika odlivu zákazníků v delším nebo kratším časovém období může ztěžovat zohlednění faktorů v profilu rizika odlivu zákazníků, ale záleží na vašich konkrétních obchodních požadavcích.

1. Zadejte počet dní definující úbytek v poli **Definice úbytku**. Pokud si například zákazník za posledních 30 dní nic nekoupil, může být pro vaši firmu považován za ztraceného.

1. Vyberte **Další**.

### <a name="add-purchase-history"></a>Přidat historii nákupů

1. Vyberte **Přidat data** u **Historie transakcí zákazníka**.

1. Vyberte typ sémantické aktivity, **SalesOrder** nebo **SalesOrderLine**, která obsahuje údaje o historii transakcí. Pokud aktivita nebyla nastavena, vyberte **zde** a vytvořte ji.

1. V části **Činnosti**, pokud byly atributy aktivity sémanticky namapovány při vytváření aktivity, vyberte konkrétní atributy nebo entitu, na kterou se má výpočet zaměřit. Pokud sémantické mapování neproběhlo, vyberte **Upravit** a namapujte data.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Boční podokno zobrazující výběr konkrétních aktivit pod sémantickým typem.":::

1. Vyberte **Další** a zkontrolujte atributy požadované pro tento model.

1. Vyberte **Uložit**.

1. Přidejte další aktivity nebo vyberte **Další**.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Přidat další údaje (volitelné)

1. Vyberte **Přidat data** pro **Aktivity zákazníka**.

1. Vyberte typ sémantické aktivity, který obsahuje data, která chcete použít. Pokud aktivita nebyla nastavena, vyberte **zde** a vytvořte ji.

1. V části **Činnosti**, pokud byly atributy aktivity sémanticky namapovány při vytváření aktivity, vyberte konkrétní atributy nebo entitu, na kterou se má výpočet zaměřit. Pokud sémantické mapování neproběhlo, vyberte **Upravit** a namapujte data.

1. Vyberte **Další** a zkontrolujte atributy požadované pro tento model.

1. Vyberte **Uložit**.

1. Vyberte **Další**.

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Vybrat úroveň predikce

Většina predikcí je vytvářena na úrovni zákazníků. V některých situacích to nemusí být dostatečně podrobné, aby to vyhovovalo potřebám vaší firmy. Tuto funkci použijte k předpovídání úbytku například pro pobočku zákazníka, nikoli pro zákazníka jako celek.

1. Vyberte **Vybrat entitu pro sekundární úroveň**. Pokud tato možnost není k dispozici, zkontrolujte, zda jste vyplnili předchozí část.

1. Rozbalte entity, ze kterých chcete vybrat sekundární úroveň, nebo použijte pole filtrování k vyfiltrování vybraných možností.

1. Vyberte atribut, který chcete použít jako sekundární úroveň, a poté vyberte **Přidat**.

1. Vyberte **Další**.

> [!NOTE]
> Entity dostupné v této sekci jsou zobrazeny, protože mají vztah k entitě, kterou jste vybrali v předchozí sekci. Pokud nevidíte entitu, kterou chcete přidat, ujistěte se, že má platný vztah v sekci **Vztahy**. Pro tuto konfiguraci jsou platné pouze vztahy 1:1 a 1:N.

### <a name="add-additional-data-optional"></a>Přidat další údaje (volitelné)

1. Vyberte **Přidat data** pro **Aktivity zákazníka**.

1. Vyberte typ sémantické aktivity, který obsahuje data, která chcete použít. Pokud aktivita nebyla nastavena, vyberte **zde** a vytvořte ji.

1. V části **Činnosti**, pokud byly atributy aktivity sémanticky namapovány při vytváření aktivity, vyberte konkrétní atributy nebo entitu, na kterou se má výpočet zaměřit. Pokud sémantické mapování neproběhlo, vyberte **Upravit** a namapujte data.

1. Vyberte **Další** a zkontrolujte atributy požadované pro tento model.

1. Vyberte **Uložit**.

1. Vyberte **Další**.

1. Volitelně vyberte **Přidat data** pro **Údaje o zákaznících**.

1. Mapujte sémantické atributy do polí ve vašich vlastních zákaznických datech, jak jsou identifikována. Data v použitých polích by se neměla často měnit, aby byl zajištěn nejlepší výkon modelu. Například výběr pole pro „Klasifikaci“, která by se měnila každý měsíc, by měla mít pouze poslední hodnotu použitou v predikce, přestože by se historicky stejná hodnota nemusela vztahovat na zákazníka při vytváření vzorců predikce.

1. Vyberte **Další**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Poskytněte volitelný seznam srovnávacích účtů

Přidejte seznam svých firemních zákazníků a účtů, které chcete použít jako měřítka. [Údaje o těchto srovnávacích účtech](#view-prediction-results) obsahují jejich skóre úbytku a nejvlivnější funkce, které ovlivnily predikci úbytku.

1. Vyberte **+ Přidat zákazníky**.

1. Vyberte zákazníky, kteří fungují jako měřítko.

1. Vyberte **Další**.

---

### <a name="set-update-schedule"></a>Natavení plánu aktualizace

1. V kroku **Aktualizace dat** vyberte frekvenci pro přetrénování vašeho modelu. Toto nastavení je důležité pro aktualizaci přesnosti predikcí, když jsou do Customer Insights vložena nová data. Většina podniků může provést opětovné cvičení modelu jednou za měsíc a mít predikce s dobrou přesností.

1. Vyberte **Další**.

### <a name="review-and-run-the-model-configuration"></a>Zkontrolujte a spusťte konfiguraci modelu

Krok **Zkontrolovat a spustit** zobrazuje souhrn konfigurace a poskytuje možnost provést změny před vytvořením predikce.

1. Vyberte **Upravit** na kterémkoli z kroků ke kontrole a provedení jakýchkoli změn.

1. Pokud jste spokojení se svými výběry, volbou **Uložit a spustit** spusťte model. Vyberte **Hotovo**. Karta **Moje předpovědi** se zobrazí při vytváření predikce. Dokončení procesu může trvat několik hodin v závislosti na množství dat použitých v predikci.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Zobrazení výsledků predikce

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Moje predikce** vyberte predikci, kterou chcete zobrazit.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

Na stránce výsledků jsou tři primární sekce s daty:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

Na stránce výsledků jsou tři primární sekce s daty:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Stránka s informacemi **Analýza vlivných vlastností** obsahuje čtyři části dat:

- V pravém podokně vyberte položku z okna **Hlavní zákazníci** nebo **Zákazníci srovnávacích testů**. Oba seznamy jsou seřazeny podle klesající hodnoty skóre úbytku, ať už je skóre jen pro zákazníka nebo kombinované skóre pro zákazníky a sekundární úroveň, jako je kategorie produktu. Vybraná položka určuje obsah na této stránce.

  - **Hlavní zákazníci**: Seznam 10 zákazníků, kteří jsou vystaveni nejvyššímu riziku střetu a nejnižšímu riziku odlivu na základě jejich skóre.
  - **Zákazníci srovnávacích testů**: Seznam až 10 zákazníků, kteří byli vybráni při konfiguraci modelu.

- **Skóre úbytku:** V pravém podokně zobrazuje skóre pro vybrané položky.

- **Distribuce rizika úbytku:** Ukazuje rozdělení rizika úbytku mezi zákazníky a percentil, ve kterém se vybraný zákazník nachází.

- **Nejlepší funkce zvyšující a snižující riziko úbytku:** Pro vybranou položku v pravém podokně je uvedeno pět nejlepších funkcí, které zvýšily a snížily riziko úbytku. U každé vlivné funkce najdete hodnotu funkce pro danou položku a její vliv na skóre úbytku. Je také zobrazena průměrná hodnota každé funkce napříč zákaznickými segmenty s nízkým, středním a vysokým úbytkem. Pomáhá lépe kontextualizovat hodnoty nejdůležitějších funkcí vlivu pro vybranou položku a porovnat je se segmenty zákazníků s nízkým, středním a vysokým úbytkem.

  - Nízký: účty nebo kombinace účtu a sekundární úrovně se skóre úbytku mezi 0 a 0,33.
  - Střední: účty nebo kombinace účtu a sekundární úrovně se skóre úbytku mezi 0,33 a 0,66.
  - Vysoká: účty nebo kombinace účtu a sekundární úrovně se skóre úbytku vyšším než 0,66.

  Když predikujete úbytek na úrovni účtu, všechny účty se berou v úvahu při odvozování průměrných hodnot funkcí pro segmenty úbytku. U předpovědí úbytku na sekundární úrovni pro každý účet závisí derivace segmentů úbytku na sekundární úrovni položky vybrané v bočním panelu. Pokud má například položka sekundární úroveň kategorie produktů (kancelářské potřeby), pak se při odvozování průměrných hodnot funkcí pro segmenty úbytku berou v úvahu pouze položky, které mají jako kategorii produktů kancelářské potřeby. Tato logika se používá k zajištění spravedlivého srovnání hodnot vlastností položky s průměrnými hodnotami v segmentech s nízkým, středním a vysokým úbytkem.

  V některých případech je průměrná hodnota segmentů s nízkým, středním nebo vysokým úbytkem prázdná nebo není k dispozici, protože neexistují žádné položky, které by patřily k odpovídajícím segmentům úbytku na základě výše uvedené definice.

  Interpretace hodnot ve sloupcích průměrná nízká, střední a vysoká se liší u kategoriálních prvků, jako je země nebo odvětví. Protože pojem „průměrná“ hodnota prvku se nevztahuje na kategoriální prvky, hodnoty v těchto sloupcích představují podíl zákazníků v segmentech nízkého, středního nebo vysokého odchodu zákazníků, které mají stejnou hodnotu kategoriálního prvku ve srovnání s položkou vybranou na postranním panelu.

---

 > [!NOTE]
 > Ve výstupní entitě pro tento model, *ChurnScore*, ukazuje předpokládanou pravděpodobnost odchodu zákazníků a *IsChurn* je binární štítek založený na *ChurnScore* s prahovou hodnotou 0,5. Pokud tato výchozí prahová hodnota pro váš scénář nefunguje, [vytvořte nový segment](segments.md#create-a-segment) s vaším preferovaným prahem. Ne všichni zákazníci jsou nutně aktivní zákazníci. Někteří z nich možná dlouho neměli žádnou aktivitu a jsou považováni za ty, u nichž došlo k úbytku, již na základě vaší definice úbytku. Předpovídání rizika úbytku zákazníků, kteří již ubyli, není užitečné, protože nejsou cílová skupina, který nás zajímá.
>
> Chcete-li zobrazit skóre odchodů, přejděte na **Data** > **Entity** a zobrazte kartu data pro výstupní entitu, kterou jste definovali pro tento model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
