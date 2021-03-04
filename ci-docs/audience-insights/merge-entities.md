---
title: Sloučení entit ve sjednocení dat
description: Sloučením entit můžete vytvořit sjednocené profily zákazníků.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268494"
---
# <a name="merge-entities"></a>Správa entit

Fáze sloučení je poslední fází v procesu sjednocení dat. Jeho účelem je slazování protichůdných údajů. Příklady konfliktních dat mohou zahrnovat jméno zákazníka, které se nachází ve dvou vašich datových sadách, ale v každé z nich se zobrazuje trochu jinak ("Grant Marshall" versus "Grant Marshal") nebo telefonní číslo, které se liší ve formátu (617-803-091X versus 617803091X). Sloučení těchto konfliktních datových bodů se provádí na základě atribut - atribut.

Po dokončení [fáze párování](match-entities.md) můžete zahájit fázi sloučení výběrem dlaždice **Sloučit** na stránce **Sjednotit**.

## <a name="review-system-recommendations"></a>Zkkontrolovat systémová doporučení

Na stránce **Sloučení** můžete zvolit a vyloučit atributy, které mají být sloučeny v rámci entity jednotného profilu zákazníka (výsledek procesu konfigurace). Některé atributy jsou systémem automaticky sloučeny.

### <a name="view-merged-attributes"></a>Prohlédnout sloučené atributy

Chcete-li zobrazit atributy, které jsou zahrnuty v jednom z automaticky sloučených atributů, vyberte tento sloučený atribut. Dva atributy, které tvoří tento sloučený atribut, se zobrazí ve dvou nových řádcích pod sloučeným atributem.

> [!div class="mx-imgBorder"]
> ![Vybrat sloučený atribut](media/configure-data-merge-profile-attributes.png "Vybrat sloučený atribut")

### <a name="separate-merged-attributes"></a>Oddělit sloučené atributy

Chcete-li oddělit nebo zrušit sloučení některých automaticky sloučených atributů, vyhledejte atribut v tabulce **Atributy profilu**.

1. Vyberte tlačítko se třemi tečkami (...).
  
2. V rozevíracím seznamu vyberte **Oddělit pole**.

### <a name="remove-merged-attributes"></a>Odebrat sloučené atributy

Chcete-li vyloučit atribut z entity profilu konečného zákazníka, najděte ho v tabulce **Atributy profilu**.

1. Vyberte tlačítko se třemi tečkami (...).
  
2. V rozevíracím seznamu vyberte **Neslučovat**.

   Atribut je přesunut do části **Odebrat ze záznamu zákazníka**.

## <a name="manually-add-a-merged-attribute"></a>Ruční přidání sloučeného atributu

Chcete-li přidat sloučený atribut, přejděte na stránku **Sloučení**.

1. Vyberte **Přidat sloučený atribut**.

2. Zadejte **Název**, který chcete později identifikovat na stránce **Sloučení**.

3. Volitelně zadejte **Zobrazované jméno**, které se zobrazí ve sjednocené entitě Profil zákazníka.

4. Nakonfigurujte **Vybrat duplicitní atributy**, abyste vybrali atributy, které chcete sloučit ze spárovaných entit. Můžete také vyhledat atributy.

5. Nastavte **Hodnotu podle důležitosti**, abyste upřednostnili jeden atribut nad ostatními. Pokud například entita *WebAccountCSV* obsahuje nejpřesnější údaje o atributu *Celá jména*, můžete tuto entitu upřednostnit před *ContactCSV* výběrem možnosti *WebAccountCSV*. V důsledku se *webAccountCSV* přesune na první prioritu, zatímco *ContactCSV* se přesune na druhou prioritu při tahání hodnoty pro atribut *Celé jméno*.

## <a name="run-your-merge"></a>Spuštění sloučení

Ať už ručně sloučíte atributy nebo necháte systém je sloučit, můžete vždy spustit sloučení. Vyberte **Spustit** na stránce **Sloučení**, chcete-li zahájit proces.

> [!div class="mx-imgBorder"]
> ![Ukládání a spuštění sloučení dat](media/configure-data-merge-save-run.png "Ukládání a spuštění sloučení dat")

Chcete-li provést další změny a znovu spustit krok, můžete zrušit probíhající slučování. Vyberte text **Aktualizace** a vyberte **Zrušit úlohu** v postranním podokně, které se objeví.

Po **Aktualizaci** se text změní na **Úspěšný**, sloučení se dokončilo a vyřešilo rozpory ve vašich údajích podle zásad, které jste definovali. Sloučené a nesloučené atributy jsou zahrnuty v entitě sjednoceného profilu. Vyloučené atributy nejsou zahrnuty v entitě sjednoceného profilu.

Pokud to nebylo poprvé, kdy jste úspěšně provedli sloučení, všechny následné procesy, včetně obohacení, segmentace a opatření, se automaticky znovu spustí. Po opětovném spuštění všech navazujících procesů budou profily zákazníků odrážet všechny provedené změny.

> [!TIP]
> Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy. Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies). Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy. Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.

## <a name="next-step"></a>Další krok

Konfigurujte [Aktivity](activities.md), [obohacení](enrichment-microsoft-graph.md) nebo [Vztahy](relationships.md) pro další přehledy o zákaznících.

Pokud jste již nakonfigurovali aktivity, obohacení nebo Vztahy, nebo pokud jste definovali segmenty, budou automaticky zpracovány, aby se využily nejnovější údaje o zákaznících.




[!INCLUDE[footer-include](../includes/footer-banner.md)]