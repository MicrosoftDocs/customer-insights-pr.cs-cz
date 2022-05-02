---
title: Predikce úbytku transakcí (obsahuje video)
description: Predikujte, zda je zákazník ohrožen, když přestane nakupovat produkty nebo služby.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: e55ca8c6926fa0bda05aaf52fd799ca25f7f585f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646477"
---
# <a name="transaction-churn-prediction"></a>Predikce úbytku transakcí

Predikce úbytku transakcí pomáhá předvídat, zda si zákazník v daném časovém intervalu již nebude kupovat vaše produkty nebo služby. Nové predikce odlivu zákazníků můžete vytvářet v části **Analytické nástroje** > **Predikce**. Volbou **Moje predikce** zobrazíte ostatní predikce, které jste vytvořili. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

U prostředí založených na firemních účtech můžeme predikovat úbytek transakcí pro účet a také kombinaci účtu a další úrovně informací, jako je kategorie produktu. Přidání dimenze může pomoci zjistit, jak je pravděpodobné, že účet „Contoso“ přestane kupovat kategorii produktů „kancelářské potřeby“. Kromě toho můžeme u obchodních účtů také použít umělou inteligenci ke generování seznamu potenciálních důvodů, proč pravděpodobně dojde k úbytku účtu pro kategorii informací sekundární úrovně.

> [!TIP]
> Vyzkoušejte výukový program pro přechod transakcí predikce pomocí ukázkových dat: [Ukázkový průvodce pro predikcí úbytku transakcí](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Předpoklady

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

- Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.
- Obchodní znalosti k pochopení toho, co znamená pro vaši firmu odchod zákazníků. Podporujeme definice časově závislých ztrát, což znamená, že zákazník je považován za ztraceného po určitém období bez nákupu.
- Údaje o vašich transakcích/nákupech a jejich historie:
    - Identifikátory transakcí k rozlišení nákupů/transakcí.
    - Identifikátory zákazníků pro spárování transakcí s vašimi zákazníky.
    - Data událostí, kdy došlo k transakci.
    - Schéma sémantických dat pro nákupy/transakce vyžaduje následující informace:
        - **ID transakce**: Jedinečný identifikátor nákupu nebo transakce.
        - **Datum transakce**: Datum nákupu nebo transakce.
        - **Hodnota transakce**: Měna / číselná hodnota částky transakce/položky.
        - (Volitelně) **Jedinečné ID produktu**: ID zakoupeného produktu nebo služby, pokud jsou vaše data na úrovni řádkové položky.
        - (Volitelně) **Zda se jednalo o vrácení**: Pole true/false, které identifikuje, zda transakce byla návratová, nebo ne. Pokud **Hodnota transakce** je záporná, použijeme tyto informace také k odvození vratky.
- (Volitelně) Údaje o aktivitách zákazníka:
    - Identifikátory aktivit pro rozlišení aktivit stejného typu.
    - Identifikátory zákazníků pro mapování aktivit na vaše zákazníky.
    - Informace o aktivitě obsahující název a datum aktivity.
    - Schéma sémantických dat pro aktivity zákazníka zahrnuje:
        - **Primární klíč:** Jedinečný identifikátor aktivity. Například záznam o návštěvě nebo využití webu, který ukazuje, že zákazník vyzkoušel vzorek vašeho produktu.
        - **Časové razítko:** Datum a čas události identifikovaný primárním klíčem.
        - **Událot:** Název události, kterou chcete použít. Například pole s názvem „UserAction“ v obchodě s potravinami může být kupón použitý zákazníkem.
        - **Podrobnosti:** Podrobné informace o akci. Například pole s názvem „CouponValue“ v obchodě s potravinami může být hodnota měny kupónu.

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

- Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.
- Obchodní znalosti k pochopení toho, co znamená pro vaši firmu odchod zákazníků. Podporujeme definice časově závislých ztrát, což znamená, že zákazník je považován za ztraceného po určitém období bez nákupu.
- Údaje o vašich transakcích/nákupech a jejich historie:
    - Identifikátory transakcí k rozlišení nákupů/transakcí.
    - Identifikátory zákazníků pro spárování transakcí s vašimi zákazníky.
    - Data událostí, kdy došlo k transakci.
    - Schéma sémantických dat pro nákupy/transakce vyžaduje následující informace:
        - **ID transakce**: Jedinečný identifikátor nákupu nebo transakce.
        - **Datum transakce**: Datum nákupu nebo transakce.
        - **Hodnota transakce**: Měna / číselná hodnota částky transakce/položky.
        - (Volitelně) **Jedinečné ID produktu**: ID zakoupeného produktu nebo služby, pokud jsou vaše data na úrovni řádkové položky.
        - (Volitelně) **Zda se jednalo o vrácení**: Pole true/false, které identifikuje, zda transakce byla návratová, nebo ne. Pokud **Hodnota transakce** je záporná, použijeme tyto informace také k odvození vratky.
- (Volitelně) Údaje o aktivitách zákazníka:
    - Identifikátory aktivit pro rozlišení aktivit stejného typu.
    - Identifikátory zákazníků pro mapování aktivit na vaše zákazníky.
    - Informace o aktivitě obsahující název a datum aktivity.
    - Schéma sémantických dat pro aktivity zákazníka zahrnuje:
        - **Primární klíč:** Jedinečný identifikátor aktivity. Například záznam o návštěvě nebo využití webu, který ukazuje, že zákazník vyzkoušel vzorek vašeho produktu.
        - **Časové razítko:** Datum a čas události identifikovaný primárním klíčem.
        - **Událot:** Název události, kterou chcete použít. Například pole s názvem „UserAction“ v obchodě s potravinami může být kupón použitý zákazníkem.
        - **Podrobnosti:** Podrobné informace o akci. Například pole s názvem „CouponValue“ v obchodě s potravinami může být hodnota měny kupónu.
- (Volitelné) Údaje o vašich zákaznících:
    - Tato data by měla být přizpůsobena statičtějším atributům, aby model fungoval co nejlépe.
    - Sémantické datové schéma pro údaje o zákaznících zahrnuje:
        - **CustomerID:** Jedinečný identifikátor pro zákazníka.
        - **Datum vytvoření:** Datum, kdy byl zákazník původně přidán.
        - **Stát nebo provincie:** Poloha státu nebo provincie zákazníka.
        - **Země:** Země zákazníka.
        - **Odvětví:** Typ odvětví zákazníka. Například pole s názvem „Odvětví“ v pražírně kávy může indikovat, zda byl zákazník maloobchod.
        - **Klasifikace:** Kategorizace zákazníka pro vaši firmu. Například pole s názvem „ValueSegment“ v pražírně kávy může být úrovní zákazníka na základě velikosti zákazníka.

---

- Navrhované vlastnosti dat:
    - Dostatečná historická data: Data transakce alespoň pro dvojnásobek vybraného časového okna. Pokud možno dva až tři roky historie transakcí. 
    - Vícenásobné nákupy na zákazníka: Ideálně alespoň dvě transakce na zákazníka.
    - Počet zákazníků: Nejméně 10 zákaznických profilů, nejlépe více než 1 000 jedinečných zákazníků. Model selže s méně než 10 zákazníky a nedostatečnými historickými daty.
    - Úplnost údajů: Méně než 20% chybějících hodnot v datovém poli poskytnuté entity.

> [!NOTE]
> U firmy s vysokou frekvencí nákupu zákazníků (každých několik týdnů) se doporučuje zvolit kratší okno predikce a definici úbytku. Pro nízkou frekvenci nákupů (každých několik měsíců nebo jednou ročně) zvolte delší okno predikce a definici úbytku.

## <a name="create-a-transaction-churn-prediction"></a>Vytvoření predikce úbytku transakcí

1. V části Customer Insights přejděte na **Analytické nástroje** > **Předpovědi**.

1. Vyberte dlaždici **Model úbytku zákazníků** a vyberte **Použít tento model**.

1. V podokně **Model úbytku zákazníků** zvolte **Transakce** a vyberte **Začínáme**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Snímek obrazovky s vybranou možností transakce v podokně Model úbytku zákazníků.":::
 
### <a name="name-model"></a>Pojmenování modelu

1. Zadejte název modelu, abyste jej odlišili od ostatních modelů.

1. Zadejte název výstupní entity pouze pomocí písmen a číslic bez mezer. Jedná se o název, který bude používat entita modelu. 

1. Vyberte **Další**.

### <a name="define-customer-churn"></a>Definujte ztracené zákazníky

1. Nastavte **Okno predikce**. Například predikujte riziko odchodu vašich zákazníků v průběhu následujících 90 dnů pro slazení vaší marketingové úspěšnosti prodeje. Předvídání rizika odlivu zákazníků v delším nebo kratším časovém období může ztěžovat zohlednění faktorů v profilu rizika odlivu zákazníků, ale záleží na vašich konkrétních obchodních požadavcích.
   >[!TIP]
   > Kdykoliv můžete volbou **Uložit koncept** uložit predikci jako koncept. Koncept predikce najdete na kartě **Moje predikce**.

1. Zadejte počet dní definující úbytek v poli **Definice úbytku**. Pokud si například zákazník za posledních 30 dní nic nekoupil, může být pro vaši firmu považován za ztraceného. 

1. Pokračujte kliknutím na tlačítko **Další**.

### <a name="add-required-data"></a>Přidejte požadovaná data

1. Vyberte **Přidat data** a zvolte typ aktivity v postranním podokně, které obsahuje informace o požadované transakci nebo historii nákupů.

1. V sekci **Vyberte aktivity** vyberte konkrétní aktivity z vybraného typu aktivit, na které se má výpočet zaměřit.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Boční podokno zobrazující výběr konkrétních aktivit pod sémantickým typem.":::

   Pokud jste aktivitu dosud nemapovali na sémantický typ, proveďte to výběrem možnosti **Upravit**. Otevře se řízené prostředí s mapováním sémantických aktivit. Namapujte svá data na odpovídající pole ve zvoleném typu aktivity.

1. Namapujte sémantické atributy na pole, která jsou nutná ke spuštění modelu. Pokud pole níže nejsou vyplněna, nakonfigurujte vztah z entity historie nákupu na entitu *Zákazník*. Vyberte **Uložit**.

1. V kroku **Přidejte požadovaná data** volbou **Další** pokračujte, pokud nechcete přidat další aktivity.


# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Přidat další údaje (volitelné)

Nakonfigurujte vztah z vaší entity aktivity zákazníka s entitou *Zákazník*.

1. Vyberte pole, které identifikuje zákazníka v tabulce aktivity zákazníka. Může přímo souviset s primárním ID zákazníka vaší entity *Zákazník*.

1. Vyberte entitu, která je vaší primární entitou *Zákazník*.

1. Zadejte název, který popisuje daný vztah.

#### <a name="customer-activities"></a>Aktivity zákazníka

1. Volitelně vyberte **Přidat data** pro **Aktivity zákazníka**.

1. Vyberte typ sémantické aktivity, který obsahuje data, která chcete použít, a poté vyberte jednu nebo více aktivit v sekci **Aktivity**.

1. Vyberte typ aktivity, který odpovídá typu aktivity zákazníka, kterou konfigurujete. Vyberte **Vytvořit nový** a vyberte dostupný typ aktivity nebo vytvořte nový typ.

1. Vyberte **Další** a pak **Uložit**.

1. Pokud máte nějaké další aktivity zákazníků, které byste chtěli zahrnout, opakujte výše uvedené kroky.

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Vybrat úroveň predikce

Většina predikcí je vytvářena na úrovni zákazníků. V některých situacích to nemusí být dostatečně podrobné, aby to vyhovovalo potřebám vaší firmy. Tuto funkci můžete použít k předpovídání úbytku například pro pobočku zákazníka, nikoli pro zákazníka jako celek.

1. Chcete-li vytvořit predikce na podrobnější úrovni než zákazník, vyberte **Vybrat entitu pro sekundární úroveň**. Pokud tato možnost není k dispozici, zkontrolujte, zda jste vyplnili předchozí část.

1. Rozbalte entity, ze kterých chcete vybrat sekundární úroveň, nebo použijte pole filtrování k vyfiltrování vybraných možností.

1. Vyberte atribut, který chcete použít jako sekundární úroveň, a poté vyberte **Přidat**.

1. Vyberte **Další**.

> [!NOTE]
> Entity dostupné v této sekci jsou zobrazeny, protože mají vztah k entitě, kterou jste vybrali v předchozí sekci. Pokud nevidíte entitu, kterou chcete přidat, ujistěte se, že má platný vztah v sekci **Vztahy**. Pro tuto konfiguraci jsou platné pouze vztahy 1:1 a 1:N.

### <a name="add-additional-data-optional"></a>Přidat další údaje (volitelné)

Nakonfigurujte vztah z vaší entity aktivity zákazníka s entitou *Zákazník*.

1. Vyberte pole, které identifikuje zákazníka v tabulce aktivity zákazníka. Může přímo souviset s primárním ID zákazníka vaší entity *Zákazník*.

1. Vyberte entitu, která je vaší primární entitou *Zákazník*.

1. Zadejte název, který popisuje daný vztah.

#### <a name="customer-activities"></a>Aktivity zákazníka

1. Volitelně vyberte **Přidat data** pro **Aktivity zákazníka**.

1. Vyberte typ sémantické aktivity, který obsahuje data, která chcete použít, a poté vyberte jednu nebo více aktivit v sekci **Aktivity**.

1. Vyberte typ aktivity, který odpovídá typu aktivity zákazníka, kterou konfigurujete. Vyberte **Vytvořit nový** a vyberte dostupný typ aktivity nebo vytvořte nový typ.

1. Vyberte **Další** a pak **Uložit**.

1. Pokud máte nějaké další aktivity zákazníků, které byste chtěli zahrnout, opakujte výše uvedené kroky.

#### <a name="customers-data"></a>Zákaznická data 

1. Volitelně vyberte **Přidat data** pro **Údaje o zákaznících**.

1. Mapujte sémantické atributy do polí ve vašich vlastních zákaznických datech, jak jsou identifikována. Data v použitých polích by se neměla často měnit, aby byl zajištěn nejlepší výkon modelu. Například výběr pole pro „Klasifikaci“, která by se měnila každý měsíc, by měla mít pouze poslední hodnotu použitou v predikce, přestože by se historicky stejná hodnota nemusela vztahovat na zákazníka při vytváření vzorců predikce.

1. Vyberte **Další**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Poskytněte volitelný seznam srovnávacích účtů

Přidejte seznam svých firemních zákazníků a účtů, které chcete použít jako měřítka. Získáte [podrobnosti o těchto srovnávacích účtech](#review-a-prediction-status-and-results) včetně jejich skóre úbytku a nejvlivnějších funkcí, které ovlivnily jejich predikci úbytku.

1. Vyberte **+ Přidat zákazníky**.

1. Vyberte zákazníky, kteří fungují jako měřítko.

1. Pokračujte kliknutím na tlačítko **Další**.

---

### <a name="set-schedule-and-review-configuration"></a>Nastavení plánu a kontrola konfigurace

1. Nastavte frekvenci opětovného cvičení modelu. Toto nastavení je důležité k aktualizaci přesnosti predikcí, když jsou ingestována nová data. Většina podniků může provést opětovné cvičení modelu jednou za měsíc a mít predikce s dobrou přesností.

1. Vyberte **Další**.

1. Zkontrolujte konfiguraci predikce. Výběrem **Upravit** pod zobrazenou hodnotou se můžete vrátit k předchozím krokům. Nebo můžete vybrat krok konfigurace z ukazatele průběhu.

1. Pokud jsou všechny hodnoty správně nakonfigurovány, volbou **Uložit a spustit** zahájíte proces predikce. Na kartě **Moje predikce** se zobrazuje stav vašich predikcí. Dokončení procesu může trvat několik hodin v závislosti na množství dat použitých v predikci.

## <a name="review-a-prediction-status-and-results"></a>Kontrola stavu a výsledků predikce

1. Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**.

1. Vyberte předpověď, kterou chcete zkontrolovat.
   - **Název predikce**: Název predikce poskytnutý při jeho vytvoření.
   - **Typ predikce**: Typ modelu použitého pro predikci
   - **Výstupní entita**: Název entity pro uložení výstupu predikce. Můžete najít entitu s tímto názvem v umístění **Data** > **Entity**.
     Ve výstupní entitě *ChurnScore* je předpokládaná pravděpodobnost odchodu zákazníků a *IsChurn* je binární štítek založený na *ChurnScore* s prahovou hodnotou 0,5. Výchozí prahová hodnota nemusí ve vašem scénáři fungovat. [Vytvořte nový segment](segments.md#create-a-new-segment) s vaší preferovanou prahovou hodnotou.
     Ne všichni zákazníci jsou nutně aktivní zákazníci. Někteří z nich možná dlouho neměli žádnou aktivitu a jsou považováni za ty, u nichž došlo k úbytku, již na základě vaší definice úbytku. Předpovídání rizika úbytku zákazníků, kteří již ubyli, není užitečné, protože nejsou cílová skupina, který nás zajímá.
   - **Predikované pole**: Toto pole je vyplněno pouze pro některé typy predikcí a nepoužívá se v predikci odchodu zákazníků.
   - **Stav**: Stav spuštění predikce.
        - **Ve frontě**: Predikce čeká na spuštění dalších procesů.
        - **Aktualizace**: Predikce právě běží, aby vytvářela výsledky, které budou přenášeny do výstupní entity.
        - **Selhání**: Spuštění predikce selhalo. [Podívejte se do protokolů](manage-predictions.md#troubleshoot-a-failed-prediction) pro další podrobnosti.
        - **Úspěch**: Predikce byla úspěšná. Volbou **Zobrazit** pod svislými třemi tečkami zkontrolujete predikci.
   - **Upraveno**: Datum, kdy byla konfigurace predikce změněna.
   - **Poslední aktualizace**: Datum, kdy predikce aktualizovala výsledky ve výstupní entitě.

1. Vyberte svislé tři tečky vedle predikce, pro kterou chcete zkontrolovat výsledky, a vyberte **Zobrazit**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Ovládací prvek zobrazení s výsledky predikce.":::

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

1. Na stránce výsledků jsou tři primární sekce s daty:
   - **Výkon cvičení modelu**: Skóre může být A, B nebo C. Toto skóre označuje výkon predikce a může vám pomoci při rozhodování o použití výsledků uložených ve výstupní entitě. Skóre je stanoveno na základě následujících pravidel: 
        - **A**, když model přesně predikoval alespoň 50 % celkových predikcí a když procento přesných predikcí ohledně zákazníků, kteří odešli, je větší než základní poměr alespoň o 10 %.
            
        - **B**, když model přesně predikoval alespoň 50 % celkových predikcí a když procento přesných predikcí ohledně zákazníků, kteří odešli, je větší než základní poměr alespoň do 10 %.
            
        - **C**, když model přesně predikoval méně než 50 % celkových predikcí nebo když procento přesných predikcí ohledně zákazníků, kteří odešli, je menší než základní poměr.
               
        - **Základní poměr** vezme vstupní časový interval predikce pro daný model (například jeden rok) a ten vytváří různé zlomky času dělením číslem 2, dokud nedosáhne jednoho měsíce nebo méně. Tyto zlomky používá k vytvoření obchodního pravidla pro zákazníky, kteří si v tomto časovém rámci nic nekoupili. Tito zákazníci jsou považováni za ztracené. Jako základní model je vybráno obchodní pravidlo založené na čase s nejvyšší schopností predikovat, kdo bude pravděpodobně ztracen.
            
    - **Pravděpodobnost odchodu (počet zákazníků)**: Skupiny zákazníků na základě jejich predikovaného rizika odchodu. Tato data vám mohou pomoci později, pokud chcete vytvořit segment zákazníků s vysokým rizikem odchodu. Takové segmenty pomáhají pochopit, kde by se pro členství v segmentech mělo nacházet vyřazení.
       
    - **Nejvlivnější faktory**: Při vytváření predikce se bere v úvahu mnoho faktorů. Každý z faktorů má svou důležitost vypočítanou pro agregované predikce, které model vytváří. Tyto faktory můžete použít k ověření vašich výsledků predikce, nebo tyto informace můžete použít později k [vytváření segmentů](segments.md), což by mohlo pomoci ovlivnit riziko úbytku zákazníků.


# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

1. Na stránce výsledků jsou tři primární sekce s daty:
   - **Výkon cvičení modelu**: Skóre může být A, B nebo C. Toto skóre označuje výkon predikce a může vám pomoci při rozhodování o použití výsledků uložených ve výstupní entitě. Skóre je stanoveno na základě následujících pravidel: 
        - **A**, když model přesně predikoval alespoň 50 % celkových predikcí a když procento přesných predikcí ohledně zákazníků, kteří odešli, je větší než základní poměr alespoň o 10 %.
            
        - **B**, když model přesně predikoval alespoň 50 % celkových predikcí a když procento přesných predikcí ohledně zákazníků, kteří odešli, je větší než základní poměr alespoň do 10 %.
            
        - **C**, když model přesně predikoval méně než 50 % celkových predikcí nebo když procento přesných predikcí ohledně zákazníků, kteří odešli, je menší než základní poměr.
               
        - **Základní poměr** vezme vstupní časový interval predikce pro daný model (například jeden rok) a ten vytváří různé zlomky času dělením číslem 2, dokud nedosáhne jednoho měsíce nebo méně. Tyto zlomky používá k vytvoření obchodního pravidla pro zákazníky, kteří si v tomto časovém rámci nic nekoupili. Tito zákazníci jsou považováni za ztracené. Jako základní model je vybráno obchodní pravidlo založené na čase s nejvyšší schopností predikovat, kdo bude pravděpodobně ztracen.
            
    - **Pravděpodobnost odchodu (počet zákazníků)**: Skupiny zákazníků na základě jejich predikovaného rizika odchodu. Tato data vám mohou pomoci později, pokud chcete vytvořit segment zákazníků s vysokým rizikem odchodu. Takové segmenty pomáhají pochopit, kde by se pro členství v segmentech mělo nacházet vyřazení.
       
    - **Nejvlivnější faktory**: Při vytváření predikce se bere v úvahu mnoho faktorů. Každý z faktorů má svou důležitost vypočítanou pro agregované predikce, které model vytváří. Tyto faktory můžete použít k ověření vašich výsledků predikce, nebo tyto informace můžete použít později k [vytváření segmentů](segments.md), což by mohlo pomoci ovlivnit riziko úbytku zákazníků.


1. U obchodních účtů najdete informační stránku **Analýza vlivných funkcí**. Obsahuje čtyři části dat:

    - Položka vybraná v pravém podokně určuje obsah na této stránce. Vyberte položku z okna **přední zákazníci** nebo **Zákazníci srovnávacích testů**. Oba seznamy jsou seřazeny podle klesající hodnoty skóre úbytku, ať už je skóre jen pro zákazníka nebo kombinované skóre pro zákazníky a sekundární úroveň, jako je kategorie produktu.
        
        - **Hlavní zákazníci**: Seznam 10 zákazníků, kteří jsou vystaveni nejvyššímu riziku střetu a nejnižšímu riziku odlivu na základě jejich skóre. 
        - **Zákazníci srovnávacích testů**: Seznam až 10 zákazníků, kteří byli vybráni při konfiguraci modelu.
 
    - **Skóre úbytku:** V pravém podokně zobrazuje skóre pro vybrané položky.
    
    - **Distribuce rizika proměny:** Ukazuje rozdělení rizika přechodu mezi zákazníky a percentil, ve kterém se vybraný zákazník nachází. 
    
    - **Nejlepší funkce zvyšující a snižující riziko úbytku:** Pro vybranou položku v pravém podokně je uvedeno pět nejlepších funkcí, které zvýšily a snížily riziko úbytku. U každé vlivné funkce najdete hodnotu funkce pro danou položku a její vliv na skóre úbytku. Je také zobrazena průměrná hodnota každé funkce napříč zákaznickými segmenty s nízkým, středním a vysokým úbytkem. Pomáhá lépe kontextualizovat hodnoty nejdůležitějších funkcí vlivu pro vybranou položku a porovnat je se segmenty zákazníků s nízkým, středním a vysokým úbytkem.

       - Nízký: účty nebo kombinace účtu a sekundární úrovně se skóre úbytku mezi 0 a 0,33
       - Střední: účty nebo kombinace účtu a sekundární úrovně se skóre úbytku mezi 0,33 a 0,66
       - Vysoká: účty nebo kombinace účtu a sekundární úrovně se skóre úbytku vyšším než 0,66
    
       Když predikujete úbytek na úrovni účtu, všechny účty se berou v úvahu při odvozování průměrných hodnot funkcí pro segmenty úbytku. U předpovědí úbytku na sekundární úrovni pro každý účet závisí derivace segmentů úbytku na sekundární úrovni položky vybrané v bočním panelu. Pokud má například položka sekundární úroveň kategorie produktů = kancelářské potřeby, pak se při odvozování průměrných hodnot funkcí pro segmenty úbytku berou v úvahu pouze položky, které mají jako kategorii produktů kancelářské potřeby. Tato logika se používá k zajištění spravedlivého srovnání hodnot vlastností položky s průměrnými hodnotami v segmentech s nízkým, středním a vysokým úbytkem.

       V některých případech je průměrná hodnota segmentů s nízkým, středním nebo vysokým úbytkem prázdná nebo není k dispozici, protože neexistují žádné položky, které by patřily k odpovídajícím segmentům úbytku na základě výše uvedené definice.
       
       > [!NOTE]
       > Interpretace hodnot ve sloupcích průměrná nízká, střední a vysoká se liší u kategoriálních prvků, jako je země nebo odvětví. Protože pojem „průměrná“ hodnota prvku se nevztahuje na kategoriální prvky, hodnoty v těchto sloupcích představují podíl zákazníků v segmentech nízkého, středního nebo vysokého odchodu zákazníků, které mají stejnou hodnotu kategoriálního prvku ve srovnání s položkou vybranou na postranním panelu.

---

## <a name="manage-predictions"></a>Správa predikcí

Predikce můžete optimalizovat, odstraňovat jejich problémy, aktualizovat nebo odstranit. Projděte si sestavu použitelnosti vstupních dat a zjistěte v ní, jak zajistit, aby predikce byla rychlejší a spolehlivější. Další informace viz [Správa predikcí](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
