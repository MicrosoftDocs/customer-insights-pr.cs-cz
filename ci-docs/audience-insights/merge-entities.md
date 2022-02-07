---
title: Sloučení entit ve sjednocení dat
description: Sloučením entit můžete vytvořit sjednocené profily zákazníků.
ms.date: 01/28/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
  - ci-merge
---

# <a name="merge-entities"></a>Správa entit

Fáze sloučení je poslední fází v procesu sjednocení dat. Jeho účelem je slazování protichůdných údajů. Příklady konfliktních dat mohou zahrnovat jméno zákazníka, které se nachází ve dvou vašich datových sadách, ale v každé z nich se zobrazuje trochu jinak ("Grant Marshall" versus "Grant Marshal") nebo telefonní číslo, které se liší ve formátu (617-803-091X versus 617803091X). Sloučení těchto konfliktních datových bodů se provádí na základě atribut - atribut.

:::image type="content" source="media/merge-fields-page.png" alt-text="Stránka sloučení v procesu sjednocení dat zobrazující tabulku se sloučenými poli, která definují sjednocený profil zákazníka.":::

Po dokončení [fáze párování](match-entities.md) můžete zahájit fázi sloučení výběrem dlaždice **Sloučit** na stránce **Sjednotit**.

## <a name="review-system-recommendations"></a>Zkkontrolovat systémová doporučení

V části **Data** > **Sjednotit** > **Sloučit** vybíráte a vylučujete atributy ke sloučení v rámci entity sjednoceného profilu zákazníka. Sjednocený profil zákazníka je výsledkem procesu sjednocení dat. Některé atributy jsou systémem automaticky sloučeny.

Chcete-li zobrazit atributy, které jsou zahrnuty v jednom z vašich automaticky sloučených atributů, vyberte tento sloučený atribut na kartě **Zákaznická pole** tabulky. Atributy, které tvoří tento sloučený atribut, se zobrazí ve dvou nových řádcích pod sloučeným atributem.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Oddělení, přejmenování, vyloučení a úprava sloučených polí

Můžete změnit způsob, jakým systém zpracovává sloučené atributy, aby vygeneroval sjednocený profil zákazníka. Vyberte **Zobrazit více** a zvolte, co chcete změnit.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Možnosti v rozevírací nabídce Zobrazit více pro správu sloučených atributů.":::

Další informace naleznete v následujících částech.

## <a name="separate-merged-fields"></a>Oddělení sloučených polí

Chcete-li oddělit sloučená pole, vyhledejte atribut v tabulce. Oddělená pole se zobrazují jako jednotlivé datové body ve sjednoceném profilu zákazníka. 

1. Vyberte sloučené pole.
  
1. Vyberte **Zobrazit více** a zvolte **Oddělená pole**.
 
1. Oddělení potvrďte.

1. Vyberte **Uložit** a **Spustit** ke zpracování změn.

## <a name="rename-merged-fields"></a>Přejmenování sloučených polí

Změňte zobrazované jméno sloučených atributů. Název výstupní entity nelze změnit.

1. Vyberte sloučené pole.
  
1. Vyberte **Zobrazit více** a zvolte **Přejmenovat**.

1. Potvrďte změněné zobrazované jméno. 

1. Vyberte **Uložit** a **Spustit** ke zpracování změn.

## <a name="exclude-merged-fields"></a>Vyloučit sloučená pole

Vylučte atribut ze sjednoceného profilu zákazníka. Pokud se pole používá v jiných procesech, například v segmentu, před vyloučením z profilu zákazníka jej z těchto procesů odstraňte. 

1. Vyberte sloučené pole.
  
1. Vyberte **Zobrazit více** a zvolte **Vyloučit**.

1. Potvrďte vyloučení.

1. Vyberte **Uložit** a **Spustit** ke zpracování změn. 

Na stránce **Sloučit** vyberte **Vyloučit pole** pro zobrazení seznamu všech vyloučených polí. V tomto podokně je možné přidat vyloučená pole zpět.

## <a name="edit-a-merged-field"></a>Úprava sloučeného pole

1.  Vyberte sloučené pole.

1.  Vyberte **Zobrazit více** a zvolte **Upravit**.

1.  Určete, jak kombinovat nebo sloučit pole jednou ze tří možností:
    - **Důležitost**: Identifikuje hodnotu vítěze na základě pořadí důležitosti specifikovaného pro zúčastněná pole. Toto je výchozí možnost sloučení. Vyberte **Přesunout nahoru/dolů** a nastavte pořadí důležitosti.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Možnost důležitosti v dialogovém okně sloučení polí."::: 
    - **Nejnovější**: Identifikuje vítěznou hodnotu na základě aktuálnosti. K definování aktuálnosti vyžaduje datum nebo číselné pole pro každou zúčastněnou entitu v rozsahu sloučených polí.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Možnost aktuálnosti v dialogovém okně sloučení polí.":::
    - **Nejstarší**: Identifikuje vítěznou hodnotu na základě nejstarší aktuálnosti. K definování aktuálnosti vyžaduje datum nebo číselné pole pro každou zúčastněnou entitu v rozsahu sloučených polí.

1.  Chcete -li se účastnit procesu sloučení, můžete přidat další pole.

1.  Sloučené pole můžete přejmenovat.

1. Výběrem možnosti **Hotovo** se vaše změny použijí.

1. Vyberte **Uložit** a **Spustit** ke zpracování změn. 

## <a name="combine-fields-manually"></a>Ruční kombinace polí

Ručně zadejte sloučený atribut.

1. Na stránce **Sloučit** vyberte **Kombinovat**.

1. Vyberte možnost **Pole**.

1. Upřesněte vítěznou zásadu sloučení v rozevíracím seznamu **Kombinovat pole podle**.

1. Vyberte pole k přidání. Vyberte **Přidat pole** ke zkombinování více polí.

1. Zadejte **Název** a **Název výstupního pole**.

1. Výběrem možnosti **Hotovo** se změny použijí.

1. Vyberte **Uložit** a **Spustit** ke zpracování změn. 

## <a name="combine-a-group-of-fields"></a>Kombinace skupiny polí

Zacházejte se skupinou polí jako s jednou jednotkou. Například když naše záznamy obsahují pole Adresa1, Adresa2, Město, Stát a PSČ. Pravděpodobně nechceme sloučit adresu2 do jiného záznamu kvůli tomu, že by to udělalo naše data úplnější

1. Na stránce **Sloučit** vyberte **Kombinovat**.

1. Vyberte možnost **Skupina polí**.

1. Upřesněte vítěznou zásadu sloučení v rozevíracím seznamu **Seřadit skupiny podle**.

1. Vyberte možnost **Přidat** a zvolte, zda chcete k polím přidat další pole nebo další skupiny.

1. Zadejte **Název** a **Název výstupu** pro každé kombinované pole.

1. Zadejte **Název** pro skupinu polí. 

1. Výběrem možnosti **Hotovo** se změny použijí.

1. Vyberte **Uložit** a **Spustit** ke zpracování změn.

## <a name="change-the-order-of-fields"></a>Změna pořadí polí

Některé entity obsahují více podrobností než jiné. Pokud entita obsahuje nejnovější data o poli, můžete ji při slučování hodnot upřednostnit před jinými entitami.

1. Vyberte sloučené pole.
  
1. Vyberte **Zobrazit více** a zvolte **Upravit**.

1. V podokně **Zkombinovat pole** vyberte **Přesunout nahoru / dolů** k nastavení pořadí nebo je přetáhněte na požadované místo.

1. Změnu potvrďte.

1. Vyberte **Uložit** a **Spustit** ke zpracování změn.

## <a name="configure-customer-id-generation"></a>Konfigurace generování ID zákazníka 

Po konfiguraci slučování polí můžete definovat, jak generovat hodnoty CustomerId, jedinečné identifikátory profilu zákazníka. Krok sloučení v procesu sjednocení dat generuje jedinečný identifikátor profilu zákazníka. Identifikátor je CustomerId v entitě *Zákazník*, která je výsledkem procesu sjednocení dat. 

Entita CustomerIdin v entitě Zákazník je založena na hašování první hodnoty vítězných nenulových primárních klíčů. Tyto klíče pocházejí z entit použitých ve fázi shody a sloučení a jsou ovlivněny pořadím shody.Vygenerované CustomerID se tedy může změnit, když se změní hodnota primárního klíče v primární entitě pořadí shody. Hodnota primárního klíče tedy nemusí vždy představovat stejného zákazníka.

Konfigurace stabilního ID zákazníka vám umožní vyhnout se tomuto chování.

**Konfigurovat jedinečné ID zákazníka**

1. Přejděte na **Sjednotit** > **Sloučit**.

1. Vyberte kartu **Klíče**. 

1. Najeďte myší na řádek **CustomerId** a vyberte možnost **Konfigurovat**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Ovládací prvek pro přizpůsobení generování ID.":::

1. Vyberte až pět polí, která budou obsahovat jedinečné ID zákazníka a jsou stabilnější. Záznamy, které neodpovídají vaší konfiguraci, používají místo toho ID nakonfigurované systémem.  

1. Vyberte **Hotovo** a spusťte proces sloučení, abyste použili změny.

## <a name="group-profiles-into-households-or-clusters"></a>Seskupení profilů do domácností nebo clusterů

V rámci procesu konfigurace generování profilu zákazníka můžete definovat pravidla pro seskupování souvisejících profilů do clusteru. V současné době jsou k dispozici dva typy clusterů - clustery domácnosti a vlastní clustery. Systém automaticky vybere domácnost s předdefinovanými pravidly, pokud entita *Zákazník* obsahuje sémantická pole *Osoba. Příjmení* a *Umístění. Adresa*. Můžete také vytvořit cluster s vlastními pravidly a podmínkami, podobně jako [pravidla porovnání](match-entities.md#define-rules-for-match-pairs).

**Definování domácnosti nebo clusteru**

1. Přejděte na **Sjednotit** > **Sloučit**.

1. Na kartě **Sloučit** vyberte **Upřesnit** > **Vytvořit cluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Ovládací prvek pro vytvoření nového clusteru.":::

1. Vyberte si mezi clusterem **Domácnost** nebo **Vlastní**. Pokud sémantická pole *Osoba. Příjmení* a *Místo. Adresa* existují v entitě *Zákazník*, je automaticky vybrána domácnost.

1. Zadejte název klastru a vyberte **Hotovo**.

1. Vyberte kartu **Clustery** a vyhledejte cluster, který jste vytvořili.

1. Zadejte pravidla a podmínky pro definování clusteru.

1. Vyberte **Spustit** ke spuštění procesu sloučení a vytvoření clusteru.

Po spuštění procesu sloučení jsou identifikátory clusteru přidány jako nová pole do entity *Zákazník*.

## <a name="run-your-merge"></a>Spuštění sloučení

Ať už ručně sloučíte atributy nebo necháte systém je sloučit, můžete vždy spustit sloučení. Vyberte **Spustit** na stránce **Sloučení**, chcete-li zahájit proces.

> [!div class="mx-imgBorder"]
> ![Ukládání a spuštění sloučení dat.](media/configure-data-merge-save-run.png "Ukládání a spuštění sloučení dat")

Zvolte **Spustit pouze sloučení**, pokud chcete vidět pouze výstup odražený v entitě sjednoceného zákazníka. Následné procesy budou aktualizovány jako [definované v plánu aktualizací](system.md#schedule-tab).

Zvolte **Spustit procesy sloučení a následné procesy** k aktualizaci systému změnami. Všechny procesy, včetně obohacení, segmentů a opatření, se znovu spustí automaticky. Po dokončení všech následných procesů budou profily zákazníků odrážet všechny provedené změny.

Chcete-li provést další změny a znovu spustit krok, můžete zrušit probíhající sloučení. Vyberte text **Aktualizace** a vyberte **Zrušit úlohu** v postranním podokně, které se objeví.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Podrobná cesta k získání podrobností o zpracování z odkazu na stav úkolu.":::

## <a name="next-step"></a>Další krok

Konfigurujte [Aktivity](activities.md), [obohacení](enrichment-hub.md) nebo [Vztahy](relationships.md) pro další přehledy o zákaznících.

Pokud jste již nakonfigurovali aktivity, obohacení nebo segmenty, budou automaticky zpracovány, aby používaly nejnovější údaje o zákaznících.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
