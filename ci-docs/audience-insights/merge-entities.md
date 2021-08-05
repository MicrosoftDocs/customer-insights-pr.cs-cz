---
title: Sloučení entit ve sjednocení dat
description: Sloučením entit můžete vytvořit sjednocené profily zákazníků.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 24b523786158ff36c314601846ee25ea64cfabbe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650126"
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

## <a name="manually-combine-fields"></a>Ruční zkombinování polí

Ručně zadejte sloučený atribut. 

1. Na stránce **Sloučit** vyberte **Zkombinovat pole**.

1. Zadejte **Název** a **Název výstupního pole**.

1. Vyberte pole k přidání. Vyberte **Přidat pole** ke zkombinování více polí.

1. Potvrďte vyloučení.

1. Vyberte **Uložit** a **Spustit** ke zpracování změn. 

## <a name="change-the-order-of-fields"></a>Změna pořadí polí

Některé entity obsahují více podrobností než jiné. Pokud entita obsahuje nejnovější data o poli, můžete ji při slučování hodnot upřednostnit před jinými entitami.

1. Vyberte sloučené pole.
  
1. Vyberte **Zobrazit více** a zvolte **Upravit**.

1. V podokně **Zkombinovat pole** vyberte **Přesunout nahoru / dolů** k nastavení pořadí nebo je přetáhněte na požadované místo.

1. Změnu potvrďte.

1. Vyberte **Uložit** a **Spustit** ke zpracování změn.

## <a name="run-your-merge"></a>Spuštění sloučení

Ať už ručně sloučíte atributy nebo necháte systém je sloučit, můžete vždy spustit sloučení. Vyberte **Spustit** na stránce **Sloučení**, chcete-li zahájit proces.

> [!div class="mx-imgBorder"]
> ![Ukládání a spuštění sloučení dat.](media/configure-data-merge-save-run.png "Ukládání a spuštění sloučení dat")

Zvolte **Spustit pouze sloučení**, pokud chcete vidět pouze výstup odražený v entitě sjednoceného zákazníka. Následné procesy budou aktualizovány jako [definované v plánu aktualizací](system.md#schedule-tab).

Zvolte **Spustit procesy sloučení a následné procesy** k aktualizaci systému změnami. Všechny procesy, včetně obohacení, segmentů a opatření, se znovu spustí automaticky. Po dokončení všech následných procesů budou profily zákazníků odrážet všechny provedené změny.

Chcete-li provést další změny a znovu spustit krok, můžete zrušit probíhající sloučení. Vyberte text **Aktualizace** a vyberte **Zrušit úlohu** v postranním podokně, které se objeví.

> [!TIP]
> Po spuštění procesu sloučení vyberte stav procesu a otevřete podokno **Podrobnosti o úkolu**. Poskytuje přehled o době zpracování, datu posledního zpracování a všech chybách a výstrahách spojených s úkolem. Vyberte **Zobrazit podrobnosti**, abyste zjistili, které entity se zúčastnily procesu porovnávání, zda bylo řešení konfliktů úspěšné, jaká pravidla u nich byla použita a zda byly aktualizace úspěšně publikovány.  
> Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy. Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Podrobná cesta k získání podrobností o zpracování z odkazu na stav úkolu.":::

## <a name="next-step"></a>Další krok

Konfigurujte [Aktivity](activities.md), [obohacení](enrichment-hub.md) nebo [Vztahy](relationships.md) pro další přehledy o zákaznících.

Pokud jste již nakonfigurovali aktivity, obohacení nebo segmenty, budou automaticky zpracovány, aby používaly nejnovější údaje o zákaznících.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
