---
title: Predikce úbytku transakcí
description: Predikujte, zda je zákazník ohrožen, když přestane nakupovat produkty nebo služby.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 28c89693239393d93b7a816535b8c3fffe353935
ms.sourcegitcommit: e57d51ae3cc233f7b6185c074c66efd9800c02c1
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/14/2021
ms.locfileid: "6559397"
---
# <a name="transactional-churn-prediction-preview"></a>Predikce úbytku transakcí (Preview)

Predikce úbytku transakcí pomáhá předvídat, zda si zákazník v daném časovém intervalu již nebude kupovat vaše produkty nebo služby. Nové predikce odlivu zákazníků můžete vytvářet v části **Analytické nástroje** > **Predikce**. Volbou **Moje predikce** zobrazíte ostatní predikce, které jste vytvořili.

> [!TIP]
> Vyzkoušejte kurz pro predikci úbytku transakcí s využitím ukázkových dat: [Průvodce ukázkami predikce úbytku transakcí (Preview)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Požadavky

- Alespoň [oprávnění Přispěvatel](permissions.md) v Customer Insights.
- Obchodní znalosti k pochopení toho, co znamená pro vaši firmu odchod zákazníků. Podporujeme definice časově závislých ztrát, což znamená, že zákazník je považován za ztraceného po určitém období bez nákupu.
- Údaje o vašich transakcích/nákupech a jejich historie:
    - Identifikátory transakcí k rozlišení nákupů/transakcí.
    - Identifikátory zákazníků pro spárování transakcí s vašimi zákazníky.
    - Data událostí, kdy došlo k transakci.
    - Schéma sémantických dat pro nákupy/transakce vyžaduje následující informace:
        - **ID transakce:** Jedinečný identifikátor nákupu nebo transakce.
        - **Datum transakce:** Datum nákupu nebo transakce.
        - **Hodnota transakce:** Měna / číselná hodnota částky transakce/položky.
        - (Volitelně) **Jedinečné ID produktu:** ID zakoupeného produktu nebo služby, pokud jsou vaše data na úrovni řádkové položky.
        - (Volitelně) **Zda se jednalo o vrácení:** Pole true/false, které identifikuje, zda transakce byla návratová, nebo ne. Pokud **Hodnota transakce** je záporná, použijeme tyto informace také k odvození vratky.
- (Volitelně) Údaje o aktivitách zákazníka:
    - Identifikátory aktivit pro rozlišení aktivit stejného typu.
    - Identifikátory zákazníků pro mapování aktivit na vaše zákazníky.
    - Informace o aktivitě obsahující název a datum aktivity.
    - Schéma sémantických dat pro aktivity zákazníka zahrnuje:
        - **Primární klíč:** Jedinečný identifikátor aktivity. Například záznam o návštěvě nebo využití webu, který ukazuje, že zákazník vyzkoušel vzorek vašeho produktu.
        - **Časové razítko:** Datum a čas události identifikovaný primárním klíčem.
        - **Událot:** Název události, kterou chcete použít. Například pole s názvem „UserAction“ v obchodě s potravinami může být kupón použitý zákazníkem.
        - **Podrobnosti:** Podrobné informace o akci. Například pole s názvem „CouponValue“ v obchodě s potravinami může být hodnota měny kupónu.
- Navrhované vlastnosti dat:
    - Dostatečná historická data: Data transakce alespoň pro dvojnásobek vybraného časového okna. Pokud možno dva až tři roky historie transakcí. 
    - Vícenásobné nákupy na zákazníka: Ideálně alespoň dvě transakce na zákazníka.
    - Počet zákazníků: Nejméně 10 zákaznických profilů, nejlépe více než 1 000 jedinečných zákazníků. Model selže s méně než 10 zákazníky a nedostatečnými historickými daty.
    - Úplnost údajů: Méně než 20% chybějících hodnot v datovém poli poskytnuté entity.

> [!NOTE]
> U firmy s vysokou frekvencí nákupu zákazníků (každých několik týdnů) se doporučuje zvolit kratší okno predikce a definici úbytku. Pro nízkou frekvenci nákupů (každých několik měsíců nebo jednou ročně) zvolte delší okno predikce a definici úbytku.

## <a name="create-a-transactional-churn-prediction"></a>Vytvoření predikce úbytku transakcí

1. V části Customer Insights přejděte na **Analytické nástroje** > **Předpovědi**.

1. Vyberte dlaždici **Model úbytku zákazníků (Preview)** a vyberte **Použít tento model**.
   
1. V podokně **Model úbytku zákazníků** vyberte **Transakční** a vyberte **Začít**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Screenshot s vybranou možností transakce v podokně modelu úbytku zákazníků.":::

### <a name="name-model"></a>Pojmenujte model

1. Zadejte název modelu, abyste jej odlišili od ostatních modelů.

1. Zadejte název výstupní entity pouze pomocí písmen a číslic bez mezer. Jedná se o název, který bude používat entita modelu. 

1. Vyberte **Další**.

### <a name="define-customer-churn"></a>Definujte ztracené zákazníky

1. Nastavte interval ve dnech pro predikci úbytku zákazníků v poli **Identifikujte zákazníky, kteří mohou odejít za dalších:**. Například predikujte riziko odchodu vašich zákazníků v průběhu následujících 90 dnů pro slazení vaší marketingové úspěšnosti prodeje. Předvídání rizika odlivu zákazníků v delším nebo kratším časovém období může ztěžovat zohlednění faktorů v profilu rizika odlivu zákazníků, ale záleží na vašich konkrétních obchodních požadavcích. 
   >[!TIP]
   > Kdykoli můžete použít volbu **Uložit a zavřít**, kterou uložíte predikci jako koncept. Koncept predikce najdete na kartě **Moje predikce**.

1. Zadejte počet dní pro definici odchodu zákazníků v poli **Zákazník se považuje za ztraceného, pokud neprovedl žádné nákupy za:**. Pokud si například zákazník za posledních 30 dní nic nekoupil, může být pro vaši firmu považován za ztraceného. 

1. Pokračujte kliknutím na tlačítko **Další**.

### <a name="add-required-data"></a>Přidejte požadovaná data

1. Vyberte **Přidat data** pro **Historie nákupů** a vyberte entitu, která poskytuje informace o historii transakcí/nákupů, jak je popsáno v [předpokladech](#prerequisites).

1. Namapujte sémantická pole na atributy v rámci entity historie nákupu a vyberte **Další**. Pro popis polí se podívejte na [předpoklady](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Mapování sémantických polí entity nákupu.":::

1. Pokud pole níže nejsou vyplněna, nakonfigurujte vztah z entity historie nákupu na entitu zákazníka.
    1. Vyberte **Entita Historie nákupů**.
    1. Vyberte **Pole**, které identifikuje zákazníka v entitě historie nákupu. Musí se vztahovat k primárnímu ID zákazníka vaší entity zákazníka.
    1. Vyberte **entitu zákazníka**, která odpovídá vaší primární entitě zákazníka.
    1. Zadejte název, který popisuje daný vztah.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Stránka historie nákupů znázorňující vytvoření vztahu se zákazníkem.":::
   
1. Vyberte **Další**.

1. Volitelně vyberte **Přidat data** pro **Aktivity zákazníka**. Vyberte entitu, která poskytuje informace o aktivitě zákazníka, jak je popsáno v předpokladech.

1. Namapujte sémantická pole na atributy v rámci entity aktivity zákazníka a vyberte **Další**. Pro popis polí se podívejte na [předpoklady](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Mapování polí zákazníků pro transakční data.":::

1. Vyberte typ aktivity, který odpovídá typu aktivity zákazníka, kterou konfigurujete. Vyberte **Vytvořit nový** a vyberte dostupný typ aktivity nebo vytvořte nový typ.

1. Budete muset nakonfigurovat vztah mezi vaší entitou aktivity zákazníka a entitou zákazníka.
    1. Vyberte pole, které identifikuje zákazníka v tabulce aktivity zákazníka. Může přímo souviset s primárním ID zákazníka vaší entity zákazníka.
    1. Výběr entity zákazníka, která odpovídá vaší primární entitě zákazníka
    1. Zadejte název, který popisuje daný vztah.

1. Zvolte **Uložit**.

1. Pokud máte nějaké další aktivity zákazníků, které byste chtěli zahrnout, opakujte výše uvedené kroky.

1. Vyberte **Další**.

### <a name="set-schedule-and-review-configuration"></a>Nastavení plánu a kontrola konfigurace

1. Nastavte frekvenci opětovného cvičení modelu. Toto nastavení je důležité k aktualizaci přesnosti predikcí, když jsou ingestována nová data. Většina podniků může provést opětovné cvičení modelu jednou za měsíc a mít predikce s dobrou přesností.

1. Vyberte **Další**.

1. Zkontrolujte konfiguraci predikce. Výběrem **Upravit** pod zobrazenou hodnotou se můžete vrátit k předchozím krokům. Nebo můžete vybrat krok konfigurace z ukazatele průběhu.

1. Pokud jsou všechny hodnoty správně nakonfigurovány, volbou **Uložit a spustit** zahájíte proces predikce. Na kartě **Moje predikce** se zobrazuje stav vašich predikcí. Dokončení procesu může trvat několik hodin v závislosti na množství dat použitých v predikci.

## <a name="review-a-prediction-status-and-results"></a>Kontrola stavu a výsledků predikce

1. Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**.

1. Vyberte předpověď, kterou chcete zkontrolovat.
   - **Název predikce:** Název predikce poskytnutý při jeho vytvoření.
   - **Typ predikce:** Typ modelu použitého pro predikci
   - **Výstupní entita:** Název entity pro uložení výstupu predikce. Můžete najít entitu s tímto názvem v umístění **Data** > **Entity**.    
     Ve výstupní entitě *ChurnScore* je předpokládaná pravděpodobnost odchodu zákazníků a *IsChurn* je binární štítek založený na *ChurnScore* s prahovou hodnotou 0,5. Výchozí prahová hodnota nemusí ve vašem scénáři fungovat. [Vytvořte nový segment](segments.md#create-a-new-segment) s vaší preferovanou prahovou hodnotou.
     Ne všichni zákazníci jsou nutně aktivní zákazníci. Někteří z nich možná dlouho neměli žádnou aktivitu a jsou považováni za ty, u nichž došlo k úbytku, již na základě vaší definice úbytku. Předvídání rizika úbytku pro zákazníky, jejichž úbytek již nastal, nejsou užitečná, protože nejsou cílová skupina zájmu.
   - **Predikované pole:** Toto pole je vyplněno pouze pro některé typy predikcí a nepoužívá se v predikci odchodu zákazníků.
   - **Stav:** Stav spuštění predikce.
        - **Ve frontě:** Predikce čeká na spuštění dalších procesů.
        - **Aktualizace:** Predikce právě běží, aby vytvářela výsledky, které budou přenášeny do výstupní entity.
        - **Selhání:** Spuštění predikce selhalo. [Podívejte se do protokolů](manage-predictions.md#troubleshoot-a-failed-prediction) pro další podrobnosti.
        - **Úspěch:** Predikce byla úspěšná. Volbou **Zobrazit** pod svislými třemi tečkami zkontrolujete predikci.
   - **Upraveno:** Datum, kdy byla konfigurace predikce změněna.
   - **Poslední aktualizace:** Datum, kdy predikce aktualizovala výsledky ve výstupní entitě.

1. Vyberte svislé tři tečky vedle predikce, pro kterou chcete zkontrolovat výsledky, a vyberte **Zobrazit**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Ovládací prvek zobrazení s výsledky predikce.":::   

1. Na stránce výsledků jsou tři primární sekce s daty:
    1. **Výkon cvičení modelu:** Skóre může být A, B nebo C. Toto skóre označuje výkon predikce a může vám pomoci při rozhodování o použití výsledků uložených ve výstupní entitě. Skóre je stanoveno na základě následujících pravidel:
         
         - **A**, když model přesně predikoval alespoň 50 % celkových predikcí a když procento přesných predikcí ohledně zákazníků, kteří odešli, je větší než základní poměr alespoň o 10 %.
            
         - **B**, když model přesně predikoval alespoň 50 % celkových predikcí a když procento přesných predikcí ohledně zákazníků, kteří odešli, je větší než základní poměr alespoň do 10 %.
            
         - **C**, když model přesně predikoval méně než 50 % celkových predikcí nebo když procento přesných predikcí ohledně zákazníků, kteří odešli, je menší než základní poměr.
               
         - **Základní poměr** vezme vstupní časový interval predikce pro daný model (například jeden rok) a ten vytváří různé zlomky času dělením číslem 2, dokud nedosáhne jednoho měsíce nebo méně. Tyto zlomky používá k vytvoření obchodního pravidla pro zákazníky, kteří si v tomto časovém rámci nic nekoupili. Tito zákazníci jsou považováni za ztracené. Jako základní model je vybráno obchodní pravidlo založené na čase s nejvyšší schopností predikovat, kdo bude pravděpodobně ztracen.
            
    1. **Pravděpodobnost odchodu (počet zákazníků):** Skupiny zákazníků na základě jejich predikovaného rizika odchodu. Tato data vám mohou pomoci později, pokud chcete vytvořit segment zákazníků s vysokým rizikem odchodu. Takové segmenty pomáhají pochopit, kde by se pro členství v segmentech mělo nacházet vyřazení.
       
    1. **Nejvlivnější faktory:** Při vytváření predikce se bere v úvahu mnoho faktorů. Každý z faktorů má svou důležitost vypočítanou pro agregované predikce, které model vytváří. Tyto faktory můžete použít k ověření výsledků predikce. Nebo můžete tyto informace použít později při [vytváření segmentů](segments.md), které mohou pomoci ovlivnit riziko odchodů zákazníků.

## <a name="manage-predictions"></a>Správa predikcí

Predikce můžete optimalizovat, odstraňovat jejich problémy, aktualizovat nebo odstranit. Projděte si sestavu použitelnosti vstupních dat a zjistěte v ní, jak zajistit, aby predikce byla rychlejší a spolehlivější. Další informace naleznete v tématu [Správa predikcí](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
