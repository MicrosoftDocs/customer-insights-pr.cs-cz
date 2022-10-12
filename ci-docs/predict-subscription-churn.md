---
title: Predikce úbytku předplatitelů (obsahuje video)
description: Predikuje, zda hrozí odchod zákazníka, když přestane používat předplatné pro produkty nebo služby vaší společnosti.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610228"
---
# <a name="predict-subscription-churn"></a>Předpovídejte ukončení předplatného

Predikuje, zda hrozí odchod zákazníka, když přestane používat předplatné pro produkty nebo služby vaší společnosti. Data předplatného zahrnují aktivní a neaktivní předplatné pro každého zákazníka, takže na každé číslo zákazníka je více záznamů.

Musíte mít obchodní znalosti k pochopení toho, co znamená pro vaši firmu odchod zákazníků. Podporujeme definice časově závislých odchodů zákazníků, což znamená, že je zákazník považován za odchozího po uplynutí časového intervalu od konce jeho předplatného.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Vyzkoušejte predikci úbytku předplatných s využitím ukázkových dat: [Průvodce ukázkami predikce úbytku předplatných](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Předpoklady

- Alespoň [oprávnění Přispěvatel](permissions.md).
- Nejméně 10 zákaznických profilů, nejlépe více než 1000 jedinečných zákazníků.
- Identifikátor zákazníka, jedinečný identifikátor pro párování předplatných s vašimi zákazníky.
- Data předplatného alespoň pro dvojnásobek vybraného časového okna. Nejlépe dva až tři roky předplacených dat. Historie předplatného musí obsahovat:
  - **ID předplatného:** Jedinečný identifikátor předplatného.
  - **Datum ukončení předplatného:** Datum vypršení platnosti předplatného zákazníka.
  - **Datum zahájení předplatného:** Datum zahájení platnosti předplatného zákazníka.
  - **Datum transakce:** Datum změny předplatného. Například zákazník koupil nebo zrušil předplatné.
  - **Je to opakující se předplatné:** Logické pole pravda/nepravda, které určuje, zda bude odběr obnoven se stejným ID předplatného bez zásahu zákazníka.
  - **Frekvence opakování (v měsících):** U opakujících se předplatných je to měsíc, po kterém bude předplatné obnoveno. Například roční předplatné, které se automaticky obnovuje pro zákazníka z roku na rok, má hodnotu 12.
  - **Částka předplatného**: Částka měny, kterou zákazník platí za obnovení předplatného. Může pomoci identifikovat vzory pro různé úrovně předplatného.
- Alespoň dva záznamy o aktivitách pro 50 % zákazníků, pro které chcete vypočítat jejich možný odchod. Aktivity zákazníka musí zahrnovat:
  - **Primární klíč:** Jedinečný identifikátor aktivity. Například návštěva webové stránky nebo záznam o použití znázorňující, že zákazník sledoval epizodu televizního pořadu.
  - **Časové razítko**: Datum a čas události identifikovaný primárním klíčem.
  - **Událost:** Název události, kterou chcete použít. Například pole nazvané „AkceUživatele“ ve streamovací službě může mít hodnotu „Zobrazeno“.
  - **Podrobnosti:** Podrobné informace o akci. Například pole nazvané „NázevPořadu“ ve streamovací službě může mít hodnotu videa shlédnutého uživatelem.
- Méně než 20% chybějících hodnot v datovém poli poskytnuté entity.

## <a name="create-a-subscription-churn-prediction"></a>Vytvoření predikce odchodu předplatitelů

Kdykoliv můžete volbou **Uložit koncept** uložit predikci jako koncept. Koncept predikce se zobrazí na kartě **Moje predikce**.

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Vytvořit** vyberte **Použít model** na kartě **Model úbytku zákazníků**.

1. Vyberte **Předplatné** pro typ úbytku a pak **Začínáme**.

1. **Pojmenujte tento model** a zadejte **Název entity výstupu**, abyste je odlišili od jiných modelů nebo entit.

1. Vyberte **Další**.

### <a name="define-customer-churn"></a>Definujte ztracené zákazníky

1. Zadejte počet dní pro **Dny od ukončení předplatného**, po jejichž uplynutí vaše firma považuje zákazníka za odchozího. Toto období je obvykle přizpůsobeno obchodním činnostem, jako jsou nabídky nebo jiné marketingové činnosti, které se snaží zabránit ztrátě zákazníka.

1. Zadejte počet **dní, po které dívat do budoucnosti k predikci úbytku**. Například predikujte riziko odchodu vašich zákazníků v průběhu následujících 90 dnů pro slazení vaší marketingové úspěšnosti prodeje. Předvídání rizika odchodu zákazníků na delší nebo kratší období může ztížit řešení faktorů ve vašem profilu rizika odchodu zákazníků, v závislosti na vašich konkrétních obchodních požadavcích.

1. Vyberte **Další**.

### <a name="add-required-data"></a>Přidejte požadovaná data

1. Vyberte **Přidat data** u **Historie předplatného**.

1. Nastavte sémantický typ aktivity **Předplatné**, který obsahuje požadované informace o historii předplatného. Pokud aktivita nebyla nastavena, vyberte **zde** a vytvořte ji.

1. V části **Činnosti**, pokud byly atributy aktivity sémanticky namapovány při vytváření aktivity, vyberte konkrétní atributy nebo entitu, na kterou se má výpočet zaměřit. Pokud sémantické mapování neproběhlo, vyberte **Upravit** a namapujte data.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Přidejte požadovaná data pro model úbytku předplatného":::

1. Vyberte **Další** a zkontrolujte atributy požadované pro tento model.

1. Vyberte **Uložit**.

1. Vyberte **Přidat data** pro **Aktivity zákazníka**.

1. Vyberte typ sémantické aktivity, který poskytuje informace o aktivitě zákazníka. Pokud aktivita nebyla nastavena, vyberte **zde** a vytvořte ji.

1. V části **Činnosti**, pokud byly atributy aktivity sémanticky namapovány při vytváření aktivity, vyberte konkrétní atributy nebo entitu, na kterou se má výpočet zaměřit. Pokud sémantické mapování neproběhlo, vyberte **Upravit** a namapujte data.

1. Vyberte **Další** a zkontrolujte atributy požadované pro tento model.

1. Vyberte **Uložit**.

1. Přidejte další aktivity nebo vyberte **Další**.

### <a name="set-update-schedule"></a>Natavení plánu aktualizace

1. Vyberte frekvenci opětovného trénování modelu. Toto nastavení je důležité pro aktualizaci přesnosti předpovědí při zpracování nových dat v Customer Insights. Většina podniků může provést opětovné cvičení modelu jednou za měsíc a mít predikce s dobrou přesností.

1. Vyberte **Další**.

### <a name="review-and-run-the-model-configuration"></a>Zkontrolujte a spusťte konfiguraci modelu

Krok **Zkontrolovat a spustit** zobrazuje souhrn konfigurace a poskytuje možnost provést změny před vytvořením predikce.

1. Vyberte **Upravit** na kterémkoli z kroků ke kontrole a provedení jakýchkoli změn.

1. Pokud jste spokojení se svými výběry, volbou **Uložit a spustit** spusťte model. Vyberte **Hotovo**. Karta **Moje předpovědi** se zobrazí při vytváření predikce. Dokončení procesu může trvat několik hodin v závislosti na množství dat použitých v predikci.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Zobrazení výsledků predikce

1. Přejděte na **Analytické nástroje** > **Předpovědi**.

1. Na kartě **Moje predikce** vyberte predikci, kterou chcete zobrazit.

Na stránce výsledků jsou tři primární sekce s daty:

- **Výkon trénovacího modelu**: Známky A, B a C označují výkon predikce a mohou vám pomoci při rozhodování o použití výsledků uložených ve výstupní entitě.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Obrázek informačního rámečku se skóre modelu se známkou A.":::

  Známky se určují na základě následujících pravidel:
  - **A**, když model přesně predikoval alespoň 50 % celkových predikcí a když procento přesných predikcí ohledně zákazníků, kteří odešli, je větší než historický podíl výpovědí alespoň o 10 %.
  - **B**, když model přesně predikoval alespoň 50 % celkových predikcí a když procento přesných predikcí ohledně zákazníků, kteří odešli, je větší než historický podíl výpovědí do 10 %.
  - **C**, když model přesně predikoval méně než 50 % celkových predikcí nebo když procento přesných predikcí odešlých zákazníků je nižší, než historická průměrná míra odešlých zákazníků.
  
- **Pravděpodobnost odchodu (počet zákazníků)**: Skupiny zákazníků na základě jejich predikovaného rizika odchodu. Volitelně [můžete vytvářet segmenty zákazníků](prediction-based-segment.md) s vysokým rizikem odchodu. Takové segmenty pomáhají pochopit, kde by se pro členství v segmentech mělo nacházet vyřazení.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Graf znázorňující rozložení výsledných odchodů rozdělený do rozmezí od 0 do 100 %":::

- **Nejvlivnější faktory:** Při vytváření predikce se bere v úvahu mnoho faktorů. Každý z faktorů má svou důležitost vypočítanou pro agregované predikce, které model vytváří. Tyto faktory použijte k ověření výsledků predikce. Nebo tyto informace použijte později při [vytváření segmentů](.//prediction-based-segment.md), které mohou pomoci ovlivnit riziko odchodů zákazníků.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Seznam zobrazující vlivné faktory a jejich význam při predikci výsledných odchodů.":::

> [!NOTE]
> Ve výstupní entitě pro tento model, *ChurnScore*, je předpokládaná pravděpodobnost odchodu zákazníků a *IsChurn* je binární štítek založený na *ChurnScore* s prahovou hodnotou 0,5. Pokud tato výchozí prahová hodnota pro váš scénář nefunguje, [vytvořte nový segment](segments.md) s vaším preferovaným prahem. Chcete-li zobrazit skóre odchodů, přejděte na **Data** > **Entity** a zobrazte kartu data pro výstupní entitu, kterou jste definovali pro tento model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
