---
title: Párování entit pro sjednocení dat
description: Spárováním entit můžete vytvořit sjednocené profily zákazníků.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405392"
---
# <a name="match-entities"></a>Párování entit

Po dokončení fáze mapování jste připraveni spárovat své entity. Fáze párování určuje, jak zkombinovat vaše datové sady do jednotného datového souboru zákaznického profilu. Fáze párování vyžaduje alespoň [dvě mapované entity](map-entities.md).

## <a name="specify-the-match-order"></a>Určení pořadí párování

Přejděte do **Sjednotit** > **Párování** a vyberte **Nastavit pořadí** pro zahájení fáze párování.

Každé párování sjednotí dvě nebo více entit do jedné entity, přičemž přetrvává každý jedinečný záznam zákazníka. V následujícím příkladu jsme vybrali tři entity: **ContactCSV: TestData** jako **Primární** entitu, **WebAccountCSV: TestData** jako **Entita 2** a **CallRecordSmall: TestData** jako **Entita 3**. Diagram nad výběry ukazuje, jak bude provedeno pořadí párování.

> [!div class="mx-imgBorder"]
> ![Upravte pořadí párování dat](media/configure-data-match-order-edit-page.png "Upravte pořadí párování dat")
  
**Hlavní** entita je párována s **Entitou 2**. Datový soubor, který je výsledkem prvního párování, je spárován s **Entitou 3**.
V tomto příkladu jsme vybrali pouze dvě párování, ale systém může podporovat více.

> [!IMPORTANT]
> Entita, kterou si vyberete jako svoji **Primární**, bude sloužit jako základ pro váš sjednocený hlavní datový soubor. K této entitě budou přidány další entity vybrané během fáze párování. Zároveň to neznamená, že sjednocená entita bude zahrnovat *Všechna* data obsažená v této entitě.
>
> Existují dva aspekty, které vám mohou pomoci vybrat hierarchii vašich entit:
>
> - Jakou entitu považujete za nejkompletnější a nejspolehlivější údaje o svých zákaznících?
> - Má entita, kterou jste právě identifikovali, atributy, které sdílí také jiné entity (například jméno, telefonní číslo nebo e-mailová adresa)? Pokud ne, vyberte druhou nejspolehlivější entitu.

Vyberte **Hotovo** pro uložení svého pořadí párování.

## <a name="define-rules-for-your-first-match-pair"></a>Definujte pravidla pro svůj první párovaný pár

Po zadání pořadí párování uvidíte definovaná párování na stránce **Párování**. Dlaždice v horní části obrazovky budou prázdné, dokud nespustíte pořadí párování.

> [!div class="mx-imgBorder"]
> ![Definujte pravidla](media/configure-data-match-need-rules.png "Definujte pravidla")

Varování **Potřebuje pravidla** naznačuje, že pro pár párování není definováno žádné pravidlo párování. Pravidla párováníí určují logiku, podle které bude přiřazen určitý pár entit.

1. Chcete-li definovat své první pravidlo, otevřete podokno **Definice pravidla** tím, že vyberte odpovídající řádek v tabulce shod (1) a poté vyberte **Vytvořit nové pravidlo** (2).

   > [!div class="mx-imgBorder"]
   > ![Vytvořit nové pravidlo](media/configure-data-match-new-rule2.png "Vytvořit nové pravidlo")

2. V podokně **Upravit pravidlo** nakonfigurujte podmínky tohoto pravidla. Každá podmínka je reprezentována dvěma řádky, které obsahují povinné výběry.

   > [!div class="mx-imgBorder"]
   > ![Nové podokno pravidla](media/configure-data-match-new-rule-condition.png "Nové podokno pravidla")

   Entita / Pole (první) - Atribut, který bude použit pro párování z první entity párů shody. Příkladem může být telefonní číslo nebo e-mailová adresa. Vyberte atribut, který bude pravděpodobně pro zákazníka jedinečný.

   > [!TIP]
   > Vyhněte se přiřazování na základě atributů typu aktivity. Jinými slovy, pokud atribut se zdá být aktivita, pak to můžou být špatná kritéria pro párování.  

   Entita / Pole (druhé) - Atribut, který bude použit pro párování ze druhé entity párů shody.

   Normalizovat - **Metoda normalizace**: Pro vybrané atributy jsou k dispozici různé možnosti normalizace. Například odebrání interpunkce nebo odebrání mezer

   Pro normalizaci názvu organizace (Náhled) můžete také vybrat **Typ (telefon, název, organizace)**

   > [!div class="mx-imgBorder"]
   > ![Normalizace-B2B](media/match-normalization-b2b.png "Normalizace-B2B")

   Úroveň přesnosti - Úroveň přesnosti, která bude použita pro tuto podmínku. Nastavení úrovně přesnosti pro podmínku párování může mít dva typy: **Základní** a **Vlastní**.  
   - Základní: Poskytuje čtyři možnosti, ze kterých si můžete vybrat: Nízká, Střední, Vysoká a Přesná. Vyberte **Přesná**, chcete-li porovnat pouze záznamy, které odpovídají 100 procentům. Vyberte jednu z dalších úrovní, které odpovídají záznamům, které nejsou 100% identické.
   - Vlastní: Pomocí posuvníku definujte vlastní procento, které záznamy potřebují ke shodě nebo zadání hodnoty do pole **Vlastní**. Systém bude odpovídat pouze záznamům, které tuto prahovou hodnotu překračují jako dvojice párování. Hodnoty na posuvníku jsou mezi 0 a 1. Takže 0,64 představuje 64 procent.

3. Pravidlo uložte kliknutím na tlačítko **Hotovo**.

### <a name="add-multiple-conditions"></a>Přidání více podmínek

Chcete-li párovat entity pouze v případě, že je splněno více podmínek, přidejte další podmínky, které jsou propojeny prostřednictvím operátora AND.

1. V podokně **Upravit pravidlo** vyberte **Přidat podmínku**. Podmínky můžete také odstranit výběrem tlačítka odebrat vedle existující podmínky.

2. Pravidlo uložte kliknutím na tlačítko **Hotovo**.

## <a name="add-multiple-rules"></a>Přidání více pravidel

Každá podmínka platí pro jednu dvojici atributů, zatímco pravidla představují sady podmínek. Chcete-li, aby byly entity spárovány s různými sadami atributů, můžete přidat další pravidla.

1. V přehledech cílové skupiny přejděte na **Data** > **Sjednotit** > **Párování**.

2. Vyberte entitu, kterou chcete aktualizovat, a vyberte **Přidat pravidla**.

3. Postupujte podle postupu, jak je uvedeno v [Definovat pravidla pro první pár shody](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Na pořadí pravidel záleží. Algoritmus párování se pokusí párovat na základě prvního pravidla a pokračuje do druhého pravidla pouze v případě, že nebyly identifikovány žádné shody podle prvního pravidla.

## <a name="define-deduplication-on-a-match-entity"></a>Definování zrušení duplicit v entitě párování

Spolu se zadáním pravidel párování mezi entitami, jak je uvedeno v částech výše, můžete také určit pravidla zrušení duplicit. *Zrušení duplicit* je proces. Identifikuje duplicitní záznamy, sloučí je do jednoho záznamu a propojí všechny zdrojové záznamy s tímto sloučeným záznamem pomocí alternativního ID se sloučeným záznamem.

Po identifikaci záznamu se zrušenou duplicitou bude tento záznam použit v procesu párování mezi entitami. Zrušení duplicity je implementováno na úrovni entity a lze ji použít na každou entitu použitou v procesu párování.

### <a name="add-deduplication-rules"></a>Přidání pravidel zrušení duplicit

1. V přehledech cílové skupiny přejděte na **Data** > **Sjednotit** > **Párování**.

1. V sekci **Sloučené duplicity** vyberte **Nastavit entity**.

1. V sekci **Sloučení předvoleb** vyberte entity, na které chcete použít zrušení duplicit.

1. Určete, jak sloučit duplicitní záznamy, a vyberte jednu ze tří možností sloučení:
   - *Nejvíce vyplněný*: Identifikuje záznam s nejvíce vyplněnými atributy jako vítězný záznam. Toto je výchozí možnost sloučení.
   - *Nejnovější*: Identifikuje vítězný záznam na základě největší aktuálnosti. Vyžaduje datum nebo číselné pole pro definování aktuálnosti.
   - *Nejdřívější*: Identifikuje vítězný záznam na základě nejmenší aktuálnosti. Vyžaduje datum nebo číselné pole pro definování aktuálnosti.
 
   > [!div class="mx-imgBorder"]
   > ![Pravidla zrušení duplicit – krok 1](media/match-selfconflation.png "Pravidla zrušení duplicit – krok 1")
 
1. Jakmile jsou entity vybrány a je nastavena jejich předvolba sloučení, vyberte **Vytvořit nové pravidlo** pro definování pravidel na úrovni entity.
   - Možnost **Vyberte pole** vypíše všechna dostupná pole z této entity, u které chcete zrušit duplicity zdrojových dat.
   - Zadejte nastavení normalizace a přesnosti podobným způsobem jako při párování entit.
   - Další podmínky můžete definovat volbou **Přidat podmínku**.
 
   > [!div class="mx-imgBorder"]
   > ![Pravidla zrušení duplicit – krok 2](media/match-selfconflation-rules.png "Pravidla zrušení duplicit – krok 2")

  Pro entitu můžete vytvořit několik pravidel zrušení duplicit. 

1. Spuštění procesu párování nyní seskupuje záznamy na základě podmínek definovaných v pravidlech zrušení duplicity. Po seskupení záznamů se zásada sloučení použije k identifikaci vítězného záznamu.

1. Tento vítězný záznam je poté předán k párování mezi entitami.

1. Jakákoli vlastní pravidla párování definovaná pro „vždy párovat“ nebo „nikdy nepárovat“ jsou nadřazená zrušení duplicit. Pokud pravidlo zrušení duplicit identifikuje shodné záznamy a vlastní pravidlo párování je nastaveno tak, aby tyto záznamy nikdy napárovalo, nebudou tyto dva záznamy porovnány.

1. Po spuštění procesu párování uvidíte statistiky zrušení duplicit.
   
> [!NOTE]
> Zadání pravidel zrušení duplikace není povinné. Pokud nejsou nakonfigurována žádná taková pravidla, použijí se systémově definovaná pravidla. Sbalí všechny záznamy, které sdílejí stejnou kombinaci hodnot (přesná shoda) z primárního klíče a polí v pravidlech párování, do jednoho záznamu před předáním dat entity do procesu párování mezi entitami pro lepší výkon a správné fungování systému.

## <a name="run-your-match-order"></a>Spuštění pořadí párování

Po definování pravidel párování, včetně pravidel párování mezi entitami a pravidel zrušení duplicit, můžete spustit pořadí párování. Na stránce **Párování** vyberte **Spustit**, chcete-li zahájit proces. Algoritmu párování může trvat nějakou dobu, než bude dokončen. Vlastnosti na stránce **Párování** nelze změnit, dokud proces párování neskončí. Na stránce **Entity** najdete entitu jednotného profilu zákazníka, která byla vytvořena. Vaše sjednocená entita zákazníka se nazývá **ConflationMatchPairs : CustomerInsights**.

Chcete-li provést další změny a znovu spustit krok, můžete zrušit probíhající párování. Vyberte text **Aktualizace** a vyberte **Zrušit úlohu** ve spodní části postranního podokna, které se objeví.

Po dokončení procesu párování se text **Aktualizace** text se změní na **Úspěšný** a můžete znovu použít všechny funkce stránky.

Výsledkem prvního procesu párování je vytvoření sjednocené hlavní entity. Výsledkem všech následných spuštění párování je rozšíření této entity.

> [!TIP]
> Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy. Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies). Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy. Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.

## <a name="review-and-validate-your-matches"></a>Kontrola a ověření shody

Posouzení kvality párů shody a jejich úprava:

- Na stránce **Párování** najdete dvě dlaždice, které zobrazují počáteční přehledy o vašich datech.

  - **Jedineční zákazníci**: zobrazuje počet jedinečných profilů, které systém identifikoval.
  - **Spárované záznamy**: zobrazuje počet shod ve všech párech shody.

- V tabulce **Pořadí párování** můžete vyhodnotit výsledky každého páru shody porovnáním počtu záznamů, které pocházejí z této entity dvojice shody, s procentem úspěšně spárovaných záznamů.

- V části **Pravidla** entity v tabulce **Pořadí párování** najdete procento úspěšně spárovaných záznamů na úrovni pravidla. Výběrem symbolu tabulky vedle pravidla můžete zobrazit všechny tyto záznamy na úrovni pravidla. Doporučujeme zkontrolovat podmnožinu záznamů a ověřit, zda byly správně spárovány.

- Experimentujte s různými přesnými prahy kolem vašich podmínek a identifikujte optimální hodnotu.

  1. Vyberte tři tečky (...) pro pravidlo dvojice shody, se kterým chcete experimentovat, a vyberte **Upravit**.

  2. Vyberte podmínku, se kterou chcete experimentovat. Každé kritérium je reprezentováno jedním řádkem v podokně **Pravidlo párování**.

  3. To, co uvidíte na stránce **Náhled kritérií**, závisí na úrovni přesnosti, kterou jste pro podmínku vybrali. Vyhledejte počet odpovídajících a nespárovaných záznamů pro vybranou podmínku.

     Získejte bohaté pochopení účinků různých prahových hodnot. Můžete porovnat počet záznamů, které budou spárovány pod každou z prahových úrovní, a zobrazit záznamy pod každou možností. Vyberte každou dlaždici a zkontrolujte data v části tabulky.

## <a name="optimize-your-matches"></a>Optimalizujte své shody

Zvyšte kvalitu změnou konfigurace některých parametrů shody:

- **Změňte pořadí párování** výběrem možnosti **Upravit** a změňte pole pořadí párování.

  > [!div class="mx-imgBorder"]
  > ![Upravte pořadí párování dat](media/configure-data-match-order-edit.png "Upravte pořadí párování dat")

- **Změňte pořadí pravidel**, pokud jste definovali více pravidel. Pravidla shody můžete přeřadit tak, že vyberte **Přesunout nahoru** a **Přesunout dolů** v mřížce pravidel shody.

  > [!div class="mx-imgBorder"]
  > ![Změnit pořadí pravidel](media/configure-data-change-rule-order.png "Změnit pořadí pravidel")

- **Duplikujte pravidla**, pokud jste definovali pravidlo shody a chtěli byste vytvořit podobné pravidlo s úpravami. To udělejte výběrem možnosti **Duplikovat**.

  > [!div class="mx-imgBorder"]
  > ![Duplikovat roli](media/configure-data-duplicate-rule.png "Duplikovat roli")

- **Upravtepravidla** výběrem symbolu **Úpravy**. Můžete provést následující změny:

  - Změna atributů pro podmínku: Vyberte nové atributy v rámci určitého řádku podmínky.
  - Změna prahové hodnoty pro podmínku: Upravte posuvník přesnosti.
  - Změna metody normalizace pro podmínku: Aktualizujte metodu normalizace.

## <a name="specify-your-custom-match-records"></a>Určení vlastních záznamů shody

Můžete určit podmínky, za kterých by se určité záznamy měly vždy shodovat nebo by se neměly nikdy shodovat. Tato pravidla lze nahrát hromadně do procesu shody.

1. Vyberte možnost **Vlastní párování** na obrazovce **Pořadí párování**.

   > [!div class="mx-imgBorder"]
   > ![Vytvoření vlastního párování](media/custom-match-create.png "Vytvoření vlastního párování")

2. Pokud nemáte žádné nahrané entity, zobrazí se dialogové okno **Vlastní párování**, které vyžaduje vyplnění některých podrobností. Pokud jste tyto podrobnosti zadali dříve, přeskočte ke kroku 8.

   > [!div class="mx-imgBorder"]
   > ![Dialogové okno Nové vlastní párování](media/custom-match-new-dialog-box.png "Dialogové okno Nové vlastní párování")

3. Vyberte **Vyplnit šablonu**, chcete-li získat soubor šablony, který může určit, které záznamy entit by se měly vždy párovat nebo nikdy párovat. Budete muset samostatně zadat záznamy "vždy párovat" a záznamy "nikdy nepárovat" ve dvou různých souborech.

4. Šablona obsahuje pole pro určení entity a hodnoty primárního klíče entity, které mají být použity ve vlastní shodě. Pokud například chcete, aby primární klíč 12345 z prodejní entity vždy odpovídal primárnímu klíči 34567 entity Kontakt, budete muset zadat následující:
    - Entita 1: Prodej
    - Klíč entity 1: 12345
    - Entita 2: Kontakt
    - Klíč entity 2: 34567

   Stejný soubor šablony může určit vlastní záznamy shody z více entit.

5. Po přidání všech přepsání, které chcete použít, uložte soubor šablony.

6. Přejděte na **Data** > **Zdroje dat** a ingestujte soubory šablon jako nové entity. Po požití je můžete použít k určení konfigurace Shoda.

7. Po nahrání souborů a entit opět vyberte možnost **Vlastní párování**. Zobrazí se možnosti určující entity, které chcete zahrnout. V rozevírací nabídce vyberte požadované entity.

   > [!div class="mx-imgBorder"]
   > ![Přepsání vlastních párování](media/custom-match-overrides.png "Přepsání vlastních párování")

8. Vyberte entity, které chcete použít pro **Vždy párovat** a **Nikdy nepárovat**, a vyberte **Hotovo**.

9. Vyberte **Uložit** na stránce **Párování** pro vlastní konfiguraci párování, kterou jste právě nastavili.

10. Vyberte **Spustit** na stránce **Párování**, chcete-li spustit proces párování, a vlastní konfigurace shody bude přijata v platnost. Všechna pravidla shody systému jsou přepsána konfigurační sadou.

11. Po dokončení párování můžete ověřit entitu **ConflationMatchPair** a potvrdit tak, že přepsání jsou použity ve sloučených shodách.

## <a name="next-step"></a>Další krok

Po dokončení procesu shody pro alespoň jednu dvojici shody můžete vyřešit možné rozpory v datech procházením tématu [**Sloučení**](merge-entities.md).
