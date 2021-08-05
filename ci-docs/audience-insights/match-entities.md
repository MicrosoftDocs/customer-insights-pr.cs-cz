---
title: Párování entit pro sjednocení dat
description: Spárováním entit můžete vytvořit sjednocené profily zákazníků.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: de53927f7ed1f58176a7ba83f89be7c39064947c
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650310"
---
# <a name="match-entities"></a>Párování entit

Fáze párování určuje, jak zkombinovat vaše datové sady do jednotného datového souboru zákaznického profilu. Po dokončení [kroku mapování](map-entities.md) v procesu sjednocení dat jste připraveni spárovat své entity. Fáze párování vyžaduje alespoň dvě mapované entity.

Stránka párování se skládá ze tří částí: 
- Klíčové metriky, které shrnují počet spárovaných záznamů
- Pořadí párování a pravidla párování mezi entitami
- Pravidla pro zrušení duplikace párovaných entit

## <a name="specify-the-match-order"></a>Určení pořadí párování

Přejděte na **Data** > **Sjednocení** > **Párování** a pro zahájení fáze párování vyberte **Nastavit pořadí**.

Každé párování sjednocuje dvě nebo více entit do jedné konsolidované entity. Zároveň uchovává jedinečné záznamy o zákaznících. Například jsme vybrali dvě entity: **eCommerce:eCommerceContacts** jako primární entitu a **LoyaltyScheme:loyCustomers** jako druhou entitu. Pořadí entit určuje, v jakém pořadí se systém pokusí spárovat záznamy.

:::image type="content" source="media/match-page.png" alt-text="Screenshot stránky Párování v oblasti Sjednocení pro proces sjednocení dat.":::
  
Primární entita *eCommerce:eCommerceContacts* je spárována s další entitou *LoyaltyScheme:loyCustomers*. Datová sada, která je výsledkem prvního kroku párování, je spárována s následující entitou, pokud máte více než dvě entity.

> [!IMPORTANT]
> Entita, kterou si vyberete jako svoji primární, bude sloužit jako základ pro vaši datovou sadu sjednocených profilů. K této entitě budou přidány další entity vybrané během fáze párování. To neznamená, že sjednocená entita bude zahrnovat *všechna* data obsažená v této entitě.
>
> Existují dva aspekty, které vám mohou pomoci vybrat hierarchii vašich entit:
>
> - Vyberte entitu s nejúplnějšími a nejspolehlivějšími daty profilu o vašich zákaznících jako primární entitu.
> - Vyberte entitu, která má několik společných atributů s jinými entitami (například jméno, telefonní číslo nebo e-mailová adresa) jako primární entitu.

Po zadání pořadí párování uvidíte definované párované dvojice v sekci **Podrobnosti o spárovaných záznamech** v umístění **Data** > **Sjednocení** > **Párování**. Klíčové metriky budou prázdné, dokud nebude dokončen proces párování.

## <a name="define-rules-for-match-pairs"></a>Definování pravidel pro párování

Pravidla párováníí určují logiku, podle které bude přiřazen určitý pár entit.

Varování **Jsou zapotřebí pravidla** vedle názvu entity naznačuje, že pro párovanou dvojici není definováno žádné pravidlo párování. 

:::image type="content" source="media/match-rule-add.png" alt-text="Screenshot sekce Podrobnosti o spárovaných záznamech s ovládacím prvkem pro přidání zvýrazněných pravidel.":::

1. Vyberte **Přidat pravidla** pod entitou v sekci **Podrobnosti o spárovaných záznamech** pro definování pravidel párování.

1. V podokně **Vytvoření pravidla** nakonfigurujte podmínky pravidla.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Screenshot otevřeného pravidla párování s přidanými podmínkami.":::

   - **Entita/pole (první řádek)**: Vyberte související entitu a atribut pro zadání vlastnosti záznamu, která je pro zákazníka potenciálně jedinečná. Například telefonní číslo nebo e-mailová adresa. Vyvarujte se párování podle atributů typu aktivity. Například ID nákupu pravděpodobně nenajde shodu v jiných typech záznamů.

   - **Entita/pole (druhý řádek)**: Vyberte atribut, který souvisí s atributem entity zadaném v prvním řádku.

   - **Normalizovat**: Vyberte z následujících možností normalizace pro vybrané atributy. 
     - Mezera: Odebere všechny mezery. Z *Ahoj světe* se stane *Ahojsvěte*.
     - Symboly: Odstraní všechny symboly a speciální znaky. Z *Head&Shoulder* se stane *HeadShoulder*.
     - Text na malá písmena: Převede všechny znaky na malá písmena. Z *VŠECHNA PÍSMENA VELKÁ a Název Případu* se stane *všechna písmena velká a název případu*.
     - Unicode na ASCII: Převede zápis Unicode na znaky ASCII. Z */u00B2* se stane *2*.
     - Číslice: Převede jiné číselné systémy, například římské číslice, na arabské číslice. Z *VIII* se stane *8*.
     - Sémantické typy: Standardizuje jména, tituly, telefonní čísla, adresy atd. 

   - **Přesnost**: Nastaví úroveň přesnosti pro tuto podmínku. 
     - **Základní**: Vyberte jednu z možností *Nízká*, *Střední*, *Vysoká* a *Přesná*. Vyberte **Přesná**, chcete-li porovnat pouze záznamy, které odpovídají 100 procentům. Vyberte jednu z dalších úrovní, které odpovídají záznamům, které nejsou 100% identické.
     - **Vlastní**: Nastaví procento, kterému musí záznamy odpovídat. Systém bude párovat pouze záznamy splňující tuto prahovou hodnotu.

1. Zadejte **Jméno** tohoto pravidla.

1. [Přidejte další podmínky](#add-conditions-to-a-rule) nebo volbou **Hotovo** dokončete vytváření pravidla.

1. Volitelně [přidejte další pravidla](#add-rules-to-a-match-pair).

1. Výběrem možnosti **Uložit** se vaše změny uplatní.

### <a name="add-conditions-to-a-rule"></a>Přidání podmínek do pravidla

Chcete-li párovat entity, pouze pokud atributy splňují více podmínek, přidejte do pravidla párování další podmínky. Podmínky jsou spojeny s logickým operátorem AND a jsou tedy prováděny pouze tehdy, jsou-li všechny splněny.

1. Jděte na **Data** > **Sjednocení** > **Párování** a vyberte **Upravit** u pravidla, do kterého chcete přidat podmínky.

1. V podokně **Upravit pravidlo** vyberte **Přidat podmínku**.

1. Pravidlo uložte kliknutím na tlačítko **Hotovo**.

### <a name="add-rules-to-a-match-pair"></a>Přidání pravidel pro spárování dvojice

Pravidla párování jsou sady podmínek. Pro párování entit podle podmínek založených na několika atributech přidejte další pravidla.

1.  Jděte na **Data** > **Sjednocení** > **Párování** a vyberte **Přidat pravidlo** u entity, do které chcete přidat pravidla.

2. Postupujte podle pokynů v části [Definování pravidel pro párování](#define-rules-for-match-pairs).

> [!NOTE]
> Na pořadí pravidel záleží. Algoritmus párování se pokouší párovat na základě vašeho prvního pravidla a pokračuje k druhému pravidlu, pouze pokud nebyly identifikovány žádné shody s prvním pravidlem.

### <a name="change-the-entity-order-in-match-rules"></a>Změna pořadí entit v pravidlech shody

Můžete změnit pořadí entit pro pravidla shody a změnit tak pořadí, ve kterém jsou zpracovávány. Pravidla, která jsou v rozporu kvůli změněnému pořadí, budou odstraněna. Odebraná pravidla musíte znovu vytvořit s aktualizovanou konfigurací.

1. Jděte na **Data** > **Sjednotit** > **Shoda** a vyberte **Upravit**.

1. V podokně **Upravit pravidlo** vyberte ovládací prvek **Přesunout nahoru/dolů** nebo přetáhněte entity pro změnu jejich pořadí.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Možnosti změnit pořadí, ve kterém jsou entity objednávky zpracovány ve fázi shody.":::

1. Pravidlo uložte kliknutím na tlačítko **Hotovo**.

## <a name="define-deduplication-on-a-match-entity"></a>Definování zrušení duplicit v entitě párování

Navíc pro [pravidla párování mezi entitami](#define-rules-for-match-pairs) můžete také zadat pravidla zrušení duplicit. *Zrušení duplicit* je další proces párování záznamů. Tato funkce identifikuje duplicitní záznamy a sloučí je do jednoho záznamu. Zdrojové záznamy se propojí se sloučeným záznamem s alternativními ID.

Záznamy se zrušenými duplicitami budou použity v procesu párování mezi entitami. Zrušení duplicit se děje u jednotlivých entit a lze jej nakonfigurovat pro každou entitu použitou v párovaných dvojicích.

Zadání pravidel zrušení duplikace není povinné. Pokud nejsou nakonfigurována žádná taková pravidla, použijí se systémově definovaná pravidla. Ta zkombinují všechny záznamy do jednoho záznamu před předáním dat entit do párování mezi entitami pro lepší výkon.

### <a name="add-deduplication-rules"></a>Přidání pravidel zrušení duplicit

1. Přejděte na **Data** > **Sjednocení** > **Párování**.

1. V sekci **Sloučené duplicity** vyberte **Nastavit entity**. V případě, že pravidla pro zrušení duplicit jsou již vytvořena, vyberte **Upravit**.

1. V podokně **Sloučení předvoleb** vyberte entity, pro které chcete spustit zrušení duplicit.

1. Zadejte, jak zkombinovat duplicitní záznamy, a vyberte jednu ze tří možností sloučení:
   - **Nejvíce vyplněný**: Identifikuje záznam s nejvíce vyplněnými poli atributů jako vítězný záznam. Toto je výchozí možnost sloučení.
   - **Nejnovější**: Identifikuje vítězný záznam na základě největší aktuálnosti. Vyžaduje datum nebo číselné pole pro definování aktuálnosti.
   - **Nejdřívější**: Identifikuje vítězný záznam na základě nejmenší aktuálnosti. Vyžaduje datum nebo číselné pole pro definování aktuálnosti.
 
   > [!div class="mx-imgBorder"]
   > ![Pravidla zrušení duplicit – krok 1.](media/match-selfconflation.png "Pravidla zrušení duplicit – krok 1")
 
1. Jakmile jsou entity vybrány a je nastavena jejich předvolba sloučení, vyberte **Přidat pravidlo** pro definování pravidel na úrovni entity.
   - **Vyberte pole** udává všechna dostupná pole z dané entity. Vyberte pole, u kterého chcete zkontrolovat duplicity. Vyberte pole, která jsou potenciálně jedinečná pro každého jednotlivého zákazníka. Například e-mailová adresa nebo kombinace jména, města a telefonního čísla.
   - Zadejte nastavení normalizace a přesnosti.
   - Definujte podmínky volbou **Přidat podmínku**.
 
   > [!div class="mx-imgBorder"]
   > ![Pravidla zrušení duplicit – krok 2.](media/match-selfconflation-rules.png "Pravidla zrušení duplicit – krok 2")

  Pro entitu můžete vytvořit několik pravidel zrušení duplicit. 

1. Spuštění procesu párování nyní seskupuje záznamy na základě podmínek definovaných v pravidlech zrušení duplicity. Po seskupení záznamů se zásada sloučení použije k identifikaci vítězného záznamu.

1. Tento vítězný záznam je poté předán k párování mezi entitami spolu s nevítěznými záznamy (například alternativní ID), aby se zlepšila kvalita párování.

1. Jakákoli definovaná vlastní pravidla párování přepíšou pravidla zrušení duplicit. Pokud pravidlo zrušení duplicit identifikuje shodné záznamy a vlastní pravidlo párování je nastaveno tak, aby tyto záznamy nikdy napárovalo, nebudou tyto dva záznamy porovnány.

1. Po [spuštění procesu párování](#run-the-match-process) uvidíte statistiky zrušení duplicit v dlaždicích klíčových metrik.

### <a name="deduplication-output-as-an-entity"></a>Výstup odebraných duplicit jako entita

Proces zrušení duplicit vytvoří novou entitu pro každou entitu z párovaných dvojic kvůli identifikaci záznamů se zrušenými duplicitami. Tyto entity lze nalézt spolu s **ConflationMatchPairs:CustomerInsights** v sekci **Systém** na stránce **Entity** s názvem **Deduplication_DataSource_Entity**.

Entita výstupu odstraněných duplicit obsahuje následující informace:
- ID/klíče
  - Pole primárního klíče a pole s alternativními ID. Pole alternativních ID se skládá ze všech alternativních ID identifikovaných pro záznam.
  - Pole Deduplication_GroupId zobrazuje skupinu nebo cluster identifikované v rámci entity, které seskupují všechny podobné záznamy na základě zadaných polí odstraněných duplicit. Používá se pro účely systémového zpracování. Pokud nejsou zadána žádná pravidla pro ruční odstranění duplicit a platí systémově definovaná pravidla pro odstranění duplicit, možná toto pole v entitě výstupu odstraněných duplicit nenajdete.
  - Deduplication_WinnerId: Toto pole obsahuje vítězné ID z identifikovaných skupin nebo clusterů. Pokud je hodnota Deduplication_WinnerId stejná jako hodnota primárního klíče záznamu, znamená to, že záznam je vítězným záznamem.
- Pole použitá k definování pravidel odstranění duplicit.
- Pole Pravidlo a Skóre označují, která z pravidel pro odstranění duplicit byla použita a které skóre bylo vráceno algoritmem pro párování.
   
## <a name="run-the-match-process"></a>Spuštění procesu párování

S konfigurovanými pravidly párování, včetně pravidel párování mezi entitami a pravidel zrušení duplicit, můžete spustit proces párování. 

Jděte na **Data** > **Sjednocení** > **Párování** a volbou **Spustit** spusťte proces. Dokončení algoritmu párování trvá nějakou dobu a do té doby nemůžete změnit její konfiguraci. Chcete-li provést změny, můžete zrušit spuštění. Vyberte stav úlohy a vyberte **Zrušit úlohu** v podokně **Podrobnosti o průběhu**.

Výsledek úspěšného spuštění, sjednocenou entitu profilu zákazníka, najdete na stránce **Entity**. Sjednocená entita profilu zákazníka se jmenuje **Zákazníci** v sekci **Profily**. První úspěšné spuštění párování vytvoří sjednocenou entitu *Zákazník*. Všechna následná spuštění shody tuto entitu rozšíří.

> [!TIP]
> Po spuštění procesu shody vyberte stav procesu a otevřete podokno **Podrobnosti o úkolu**. Poskytuje přehled o době zpracování, datu posledního zpracování a všech chybách a výstrahách spojených s úkolem. Vyberte **Zobrazit podrobnosti**, abyste zjistili, které entity se zúčastnily procesu porovnávání, jaká pravidla u nich byla použita a zda byly aktualizace úspěšně publikovány.  
> Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy. Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Podrobná cesta k získání podrobností o zpracování z odkazu na stav úkolu.":::

## <a name="review-and-validate-your-matches"></a>Kontrola a ověření shody

Jděte na **Data** > **Sjednocení** > **Párování**, kde můžete zhodnotit kvalitu párování dvojic a v případě potřeby ji vylepšit.

Dlaždice v horní části stránky zobrazují klíčové metriky, které shrnují počet párovaných záznamů a duplicit.

:::image type="content" source="media/match-KPIs.png" alt-text="Oříznutý screenshot klíčových metrik na stránce Párování s čísly a podrobnostmi.":::

- **Jedinečné zdrojové záznamy** zobrazuje počet jednotlivých zdrojových záznamů, které byly zpracovány při posledním spuštění párování.
- **Spárované a nespárované záznamy** zdůrazňuje, kolik jedinečných záznamů zbývá po zpracování pravidel párování.
- **Pouze spárované záznamy** zobrazuje počet párování všech spárovaných dvojic.

Výsledky každého párování a jeho pravidla můžete posoudit v tabulce **Podrobnosti o spárovaných záznamech**. Porovnejte počet záznamů, které pocházejí z párované dvojice, s procentem úspěšně spárovaných záznamů.

Zkontrolujte pravidla párované dvojice a podívejte se na procento úspěšně spárovaných záznamů na úrovni pravidel. Vyberte tři tečky (...) a poté volbou **Náhled párování** zobrazte všechny tyto záznamy na úrovni pravidel. Doporučujeme vám podívat se na některé záznamy a ověřit, zda byly správně spárovány.

Pro podmínky vyzkoušejte různé prahové hodnoty přesnosti, abyste našli optimální hodnotu.

  1. Vyberte tři tečky (...) pro pravidlo, se kterým chcete experimentovat, a vyberte **Upravit**.

  2. Změňte hodnoty přesnosti v podmínkách, které chcete revidovat.

  3. Volbou **Náhled** zobrazíte počet spárovaných a nespárovaných záznamů pro vybranou podmínku.

## <a name="manage-match-rules"></a>Správa pravidel párování

Většinu parametrů párování můžete překonfigurovat a doladit.

:::image type="content" source="media/match-rules-management.png" alt-text="Screenshot rozevírací nabídky s možnostmi pravidla shody.":::

- **Změňte pořadí pravidel**, pokud jste definovali více pravidel. Pořadí pravidel párování můžete změnit výběrem možností **Přesunout nahoru** a **Přesunout dolů** nebo přetažením.

- **Z,ěňte podmínky pravidla** výběrem **Upravit** a volbou různých polí.

- **Deaktivujte pravidlo** pro zachování pravidla shody a vyloučení z procesu párování.

- **Duplikujte svá pravidla**, pokud jste definovali pravidlo párování a chtěli byste vytvořit podobné pravidlo s úpravami volbou **Duplikovat**.

- **Odstraňte pravidlo** výběrem symbolu **Odstranit**.

## <a name="specify-custom-match-conditions"></a>Zadání vlastních podmínek párování

Můžete určit podmínky, za kterých by se určité záznamy měly vždy shodovat nebo by se neměly nikdy shodovat. Tato pravidla lze nahrát, čímž dojde k přepsání standardního procesu párování. Pokud jsou například v našich záznamech John Doe I a John Doe II, systém by je mohl spárovat jako jednu osobu. Vlastní pravidla párování umožňují určit, že jejich profily odkazují na různé lidi. 

1. Jděte na **Data** > **Sjednocení** > **párování** a vyberte **Vlastní párování** v sekci **Podrobnosti o spárovaných záznamech**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Screenshot sekce Pravidla párování se zvýrazněným ovládacím prvkem Vlastní párování.":::

1. Pokud nemáte nastavena žádná vlastní pravidla párování, zobrazí se nové podokno **Vlastní párování** s více podrobnostmi.

1. Vyberte **Vyplnit šablonu**, chcete-li získat soubor šablony, který může určit, které záznamy entit by se měly vždy párovat nebo nikdy párovat. Budete muset samostatně zadat záznamy "vždy párovat" a záznamy "nikdy nepárovat" ve dvou různých souborech.

1. Šablona obsahuje pole pro určení entity a hodnoty primárního klíče entity, které mají být použity ve vlastní shodě. Například pokud chcete, aby se primární klíč *12345* z entity *Prodej* vždy shodoval s primárním klíčem *34567* z entity *Kontakt*, vyplňte šablonu:
    - Entita 1: Prodej
    - Klíč entity 1: 12345
    - Entita 2: Kontakt
    - Klíč entity 2: 34567

   Stejný soubor šablony může určit vlastní záznamy shody z více entit.
   
   Pokud chcete zadat vlastní párování pro odstranění duplicit v entitě, zadejte stejnou entitu jako Entita 1 a Entita 2 a nastavte různé hodnoty primárního klíče.

1. Po přidání všech přepsání, které chcete použít, uložte soubor šablony.

1. Přejděte na **Data** > **Zdroje dat** a ingestujte soubory šablon jako nové entity. Po požití je můžete použít k určení konfigurace Shoda.

1. Po nahrání souborů a entit opět vyberte možnost **Vlastní párování**. Zobrazí se možnosti určující entity, které chcete zahrnout. V rozevírací nabídce vyberte požadované entity.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Screenshot dialogového okna pro výběr přepsání v případě scénáře vlastní shody.":::

1. Vyberte entity, které chcete použít pro **Vždy párovat** a **Nikdy nepárovat**, a vyberte **Hotovo**.

1. Volbou **Uložit** na stránce **Párování** použijte vlastní konfiguraci párování.

1. Volbou **Spustit** na stránce **Párování** spusťte proces párování. Ostatní zadaná pravidla párování jsou přepsána vlastní konfigurací párování.

> [!TIP]
> Jděte na **Data** > **Entity** a zkontrolujte entitu **ConflationMatchPair**, zda došlo k přepsání.

## <a name="next-step"></a>Další krok

Po dokončení procesu shody pro alespoň jednu dvojici shody můžete vyřešit možné rozpory v datech procházením tématu [**Sloučení**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
