---
title: Vytvořit a spravovat segmenty
description: Vytvořte segmenty zákazníků a seskupte je podle různých atributů.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270348"
---
# <a name="create-and-manage-segments"></a>Vytvořit a spravovat segmenty

Segmenty umožňují seskupit zákazníky na základě demografických, transakčních nebo behaviorálních atributů. Segmenty můžete použít k cílení propagačních kampaní, prodejních aktivit a akcí podpory zákazníků k dosažení vašich obchodních cílů.

Můžete definovat složité filtry kolem entity Profil zákazníka a souvisejících entit. Každý segment po zpracování vytvoří sadu záznamů o zákaznících, které můžete exportovat a se kterými můžete provádět akce. Použijí se některé [servisní limity](service-limits.md).

Pokud není uvedeno jinak, všechny segmenty jsou **Dynamické segmenty**, které se obnovují podle opakujícího se plánu.

Následující příklad ukazuje funkci segmentace. Definovali jsme segment pro zákazníky, kteří si za posledních 90 dní objednali zboží alespoň za $500 *a* kteří se účastnili volání služby zákazníkům, které bylo eskalováno.

> [!div class="mx-imgBorder"]
> ![Více skupin](media/segmentation-group1-2.png "Více skupin")

## <a name="create-a-new-segment"></a>Vytvořit nový segment

Segmenty jsou spravovány na stránce **Segmenty**.

1. V přehledech cílové skupiny přejděte na stránku **Segmenty**.

2. Vybrat **Nový** > **Prázdný segmeny**.

3. V podokně **Nový segment** zvolte typ segmentu a zadejte **Název**.

   Volitelně zadejte zobrazované jméno a popis, který pomáhá identifikovat segment.

4. Vyberte **Další**, chcete-li se dostat na stránku **Tvůrce segmentu**, kde definujete skupinu. Skupina je sada zákazníků.

5. Zvolte entitu, která obsahuje atribut, který chcete zahrnout do segmentace.

6. Vyberte atribut, podle kterého chcete segmentovat. Tento atribut může mít jeden ze čtyř typů hodnot: číselný, řetězec, datum nebo logický.

7. Zvolte operátor a hodnotu vybraného atributu.

   > [!div class="mx-imgBorder"]
   > ![Vlastní filtr skupin](media/customer-group-numbers.png "Filtr skupin zákazníků")

   |Počet |definice  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operátor         |
   |4    |Hodnota         |

8. Pokud je entita propojena se sjednocenou entitou zákazníka prostřednictvím [Vztahů](relationships.md), musíte definovat cestu vztahu k vytvoření platného segmentu. Přidávejte entity z cesty vztahu, dokud nevyberete entitu **Zákazník: CustomerInsights** z rozevíracího seznamu. Pak zvolte **Všechny záznamy** pro každou podmínku.

   > [!div class="mx-imgBorder"]
   > ![Cesta vztahů při vytváření segmentů](media/segments-multiple-relationships.png "Cesta vztahů při vytváření segmentů")

9. Výběrem možnosti **Uložit** uložte segment. Pokud budou všechny požadavky ověřeny, bude váš segment uložen a zpracován. V opačném případě bude uložen jako koncept.

10. Volbou **Zpět na segmenty** přejdete zpět na stránku **Segmenty**.

## <a name="manage-existing-segments"></a>Správa existujících segmentů

Na stránce **Segmenty** můžete zobrazit všechny uložené segmenty a spravovat je.

Každý segment je reprezentován řádkem, která obsahuje další informace o segmentu.

Segmenty ve sloupci můžete třídit výběrem záhlaví sloupce.

Použijte pole **Vyhledávání** v pravém horním rohu a filtrujte segmenty.

> [!div class="mx-imgBorder"]
> ![Možnosti správy existujícího segmentu](media/segments-selected-segment.png "Možnosti správy existujícího segmentu")

Když vyberete segment, jsou k dispozici následující akce:

- **Zobrazit** podrobnosti o segmentu, včetně trendu počtu členů, náhledu členů segmentu.
- **Upravit** segment změnit jeho vlastnosti.
- **Obnovit** segment a zahrnout nejnovější data.
- **Aktivace** nebo **deaktivace** segmentu. Segmenty mají dva možné stavy – aktivní nebo neaktivní. Tyto stavy jsou užitečné při úpravách segmentu. Pro neaktivní segmenty existuje jejich definice, ale zatím neobsahuje žádné zákazníky. Když aktivujete segment, jeho stav se změní z „neaktivní“ na „aktivní“ a začne hledat zákazníky, kteří odpovídají definici segmentu. Pokud je konfigurována [plánovaná aktualizace](system.md#schedule-tab), neaktivní segmenty mají **Stav** uveden jako **Přeskočeno**, což označuje, že u nich neproběhl ani pokus o aktualizaci. Když je neaktivní segment aktivován, aktualizuje se a bude součástí plánovaných aktualizací.
  Případně můžete použít funkci **Plánovat později** v rozevíracím seznamu **Aktivovat/deaktivovat** pro určení budoucího data a času aktivace a deaktivace konkrétního segmentu.
- **Přejmenovat** segment.
- **Stáhnout** seznam členů jako soubor .CSV.
- Možnost **Přidat do** odešle seznam ID zákazníků v segmentu ke zpracování v jiné aplikaci.
- **Odstranit** segment.

## <a name="refresh-segments"></a>Aktualizovat segmenty

Můžete aktualizovat všechny segmenty najednou výběrem **Aktualizovat vše** na stránce **Segmenty** nebo můžete aktualizovat jeden nebo více segmentů, když je vyberete a z možností vyberete volbu **Aktualizovat**. Případně můžete nakonfigurovat opakovanou aktualizaci **Správce** > **Systém** > **Plán**.

> [!TIP]
> Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy. Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies). Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy. Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.

## <a name="download-and-export-segments"></a>Stahujte a exportujte segmenty

Můžete si stáhnout své segmenty do souboru CSV nebo je exportovat do Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Stáhněte segmenty do souboru CSV

1. V přehledech cílové skupiny přejděte na stránku **Segmenty**.

2. Vyberte tři tečky v dlaždici konkrétního segmentu.

3. Vyberte **Stáhnout jako CSV** z rozevíracího seznamu akcí.

### <a name="export-segments-to-dynamics-365-sales"></a>Exportovat segmenty do aplikace Dynamics 365 Sales

Před exportem segmentů do Dynamics 365 Sales musí administrátor [vytvořit cíl exportu](export-destinations.md) pro Dynamics 365 Sales.

1. V přehledech cílové skupiny přejděte na stránku **Segmenty**.

2. Vyberte tři tečky v dlaždici konkrétního segmentu.

3. Vyberte **Přidat do** z rozevíracího seznamu akcí a vyberte cílové místo exportu, do kterého chcete data odeslat.

## <a name="draft-mode-for-segments"></a>Režim konceptu pro segmenty

Pokud nejsou splněny všechny požadavky na zpracování segmentu, můžete segment uložit jako koncept a získat k němu přístup ze stránky **Segmenty**.

Bude uložen jako neaktivní segment a nelze jej aktivovat, dokud nebude platný.

## <a name="add-more-conditions-to-a-group"></a>Přidání dalších podmínek do skupiny

Chcete-li do skupiny přidat další podmínky, můžete použít dva logické operátory:

- Operátor **AND**: Obě podmínky musí být splněny v rámci procesu segmentace. Tato možnost je nejužitečnější při definování podmínek mezi různými entitami.

- Operátor **OR**: Buď je třeba splnit jednu z podmínek v rámci procesu segmentace. Tato možnost je nejužitečnější při definování více podmínek pro stejnou entitu.

   > [!div class="mx-imgBorder"]
   > ![Operátor OR, u kterého je třeba splnit obě podmínky](media/segmentation-either-condition.png "Operátor OR, u kterého je třeba splnit obě podmínky")

V současné době je možné vnořit operátor **OR** do operátoru **AND**, ale ne naopak.

## <a name="combine-multiple-groups"></a>Zkombinování více skupin

Každá skupina produkuje specifický soubor zákazníků. Tyto skupiny můžete zkombinovat a zahrnout zákazníky potřebné pro váš obchodní případ.

1. V přehledech cílové skupiny přejděte na stránku **Segmenty** a vyberte segment.

2. Vyberte **Přidat skupinu**.

   > [!div class="mx-imgBorder"]
   > ![Skupina zákazníků přidat skupinu](media/customer-group-add-group.png "Skupina zákazníků přidat skupinu")

3. Vyberte jeden z následujících operátorů sady: **Sjednocení**, **Průnik** nebo **Kromě**.

   > [!div class="mx-imgBorder"]
   > ![Skupina zákazníků přidat sjednocení](media/customer-group-union.png "Skupina zákazníků přidat sjednocení")

   Vyberte operátor sady, abyste mohli definovat novou skupinu. Uložením různých skupin určíte, jaká data se uchovají:

   - **Sjednocení** sjednotí dvě skupiny.

   - **Průnik** překrývá dvě skupiny. Pouze data, která *jsou společná* pro obě skupiny, zůstanou zachována ve sjednocené skupině.

   - **Výjimka** kombinuje dvě skupiny. Pouze data ve skupině A, která *nejsou společná* s daty ve skupině B, zůstanou zachována.

## <a name="view-processing-history-and-segment-members"></a>Zobrazit historii zpracování a členy segmentu

Konsolidovaná data o segmentu můžete zobrazit kontrolou jeho podrobností.

Na stránce **Segmenty** vyberte segment, který chcete zkontrolovat.

Horní část stránky obsahuje graf trendů, který vizualizuje změny v počtu členů. Najeďte na datové body, abyste viděli počet členů k určitému datu.

Můžete aktualizovat časový rámec vizualizace.

> [!div class="mx-imgBorder"]
> ![Časový rozsah segmentu](media/segment-time-range.png "Časový rozsah segmentu")

Spodní část obsahuje seznam členů segmentu.

> [!NOTE]
> Pole, která se zobrazí v tomto seznamu, jsou založena na atributech entit segmentu.
>
>Seznam je náhledem odpovídajících členů segmentu a zobrazuje prvních 100 záznamů segmentu, takže jej můžete rychle vyhodnotit a v případě potřeby zkontrolovat jeho definice. Chcete-li zobrazit všechny odpovídající záznamy, je třeba [segment exportovat](export-destinations.md).

## <a name="quick-segments"></a>Rychlé segmenty

Kromě nástroje pro vytváření segmentů existuje další cesta k vytváření segmentů. Rychlé segmenty vám umožňují rychle a snadno vytvářet jednoduché segmenty s jediným operátorem.

1. Na stránce **Segmenty** vyberte **Nový** > **Rychle vytvořte z**.

   - Vyberte možnost **Profily**, chcete-li vytvořit segment založený na sjednocené entitě Zákazník.
   - Vyberte možnost **Opatření**, chcete-li vytvořit segment kolem každého typu atributu zákazníka, které jste dříve vytvořili na stránce **Opatření**.
   - Vyberte možnost **Analytické nástroje**, chcete-li sestavit segment kolem jedné z výstupních entit, které jste vygenerovali pomocí funkcí **Predikce** nebo **Vlastní modely**.

2. V dialogovém okně **Nový rychlý segment** vyberte atribut z rozbalovací nabídky **Pole**.

3. Systém vám poskytne další přehledy, které vám pomohou vytvořit lepší segmenty vašich zákazníků.
   - Pro kategorická pole zobrazíme 10 nejlepších zákazníků. Vyberte **Hodnotu** a zvolte **Hodnotit**.

   - U číselného atributu systém zobrazí, jaká hodnota atributu spadá pod percentil každého zákazníka. Zvolte **Operátor** a **Hodnotu** a pak vyberte **Zkontrolovat**.

4. Systém vám poskytne **Odhadovanou velikost segmentu**. Můžete zvolit, zda chcete vygenerovat segment, který jste definovali, nebo jej nejprve znovu navštívit, abyste získali jinou velikost segmentu.

    > [!div class="mx-imgBorder"]
    > ![Název a odhad pro rychlý segment](media/quick-segment-name.png "Název a odhad pro rychlý segment")

5. Zadejte **Název** svého sgmentu. Volitelně zadejte **Zobrazovaný název**.

6. Výběrem možnosti **Uložit** vytvořte segment.

7. Po dokončení zpracování segmentu jej můžete zobrazit jako jakýkoli jiný segment, který jste vytvořili.

Pro následující scénáře doporučujeme používat tvůrce segmentů spíše než doporučené funkce segmentů:

- Vytváření segmentů s filtry v kategorických polích, kde se operátor liší od operátoru **Je**
- Vytváření segmentů s filtry na číselných polích, kde je operátor jiný, než **Mezi**, **Větší než** a **Méně než**
- Vytváření segmentů s filtry v polích typu data

## <a name="next-steps"></a>Další kroky

[Exportujtesegment](export-destinations.md) a prozkoumejte [Kartu zákazníka](customer-card-add-in.md) a [Konektory](export-power-bi.md), abyste získali přehled o úrovni zákazníka.


[!INCLUDE[footer-include](../includes/footer-banner.md)]