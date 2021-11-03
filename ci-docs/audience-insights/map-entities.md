---
title: Mapování entit a atributů pro unifikaci dat
description: Vyberte entity, atributy, primární klíče a sémantické typy pro mapování dat do jednotného zákaznického profilu.
ms.date: 10/18/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
ms.openlocfilehash: 8b84ed1a860e383e4eb3f7499be6d397ba3f1db1
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673255"
---
# <a name="map-entities-and-attributes"></a>Mapování entit a atributů

**Mapování** je první fáze procesu sjednocení dat v přehledech cílové skupiny. Mapování se skládá ze tří fází:

- *Výběr entity*: Identifikujte kombinovatelné entity, které vedou k datové sadě, s úplnějšími informacemi o vašich zákaznících.
- *Výběr atributů*: U každé entity určete sloupce, které chcete zkombinovat a spárovat ve fázích *přiřazení* a *sloučení*. Tyto sloupce se nazývají *Atributy*.
- *Výběr primárního klíče a sémantického typu*: Pro každou entitu identifikujte atribut, který chcete definovat jako primární klíč pro danou entitu, a pro každý atribut identifikujte sémantický typ, který tento atribut nejlépe popisuje.

Další informace o obecném toku sjednocení dat naleznete na stránce [Sjednotit](data-unification.md).

## <a name="select-the-first-entities"></a>Vyberte první entity

1. V přehledech cílové skupiny přejděte na **Data** > **Sjednocení** > **Mapování**.

2. Začněte fázi mapování výběrem možnosti **Vybrat entity**.

3. Vyberte entity a atributy, které chcete použít ve fázích *párování* a *sloučení*. Můžete vybrat požadované atributy jednotlivě z entity nebo zahrnout všechny atributy z entity zaškrtnutím políčka **Zahrnout všechna pole** na úrovni entity. Doporučujeme vybrat alespoň dvě entity, aby bylo možné proces sjednocení dat používat výhodně.

   > [!div class="mx-imgBorder"]
   > ![Přiklad Přidat entity.](media/data-manager-configure-map-add-entities-example.png "Přiklad Přidat entity")

   V tomto příkladu přidáváme entity **eCommerceContacts** a **loyCustomers**. Výběrem těchto entit můžete získat přehled, kteří z online obchodních zákazníků jsou členy věrnostního programu.
   
   Můžete vyhledávat klíčová slova ve všech atributech a entitách a vybrat požadované atributy, které chcete mapovat.
   
     > [!div class="mx-imgBorder"]
   > ![Příklad vyhledávacích polí.](media/data-manager-configure-map-search-fields-example.png "Příklad vyhledávacích polí")

4. Volbou **Použít** potvrďte svůj výběr.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Výběr primárního klíče a sémantického typu pro atributy

Po výběru entit se zobrazí stránka **Mapa** s vybranými entitami pro vaši kontrolu. Definujte primární klíč pro entitu a identifikujte sémantický typ pro atribut v entitě.

- **Primární klíč**: Vyberte jeden atribut jako primární klíč pro každou ze svých entit. Aby byl atribut platným primárním klíčem, nesmí obsahovat duplicitní hodnoty, chybějící hodnoty nebo hodnoty null. Atributy datových typů řetězce, celého čísla a GUID jsou podporovány jako primární klíče a budou zobrazeny v poli, ze kterého si můžete vybrat.

- **Sémantický typ atributu**: Kategorie vašich atributů, jako je e-mailová adresa nebo jméno. Chcete-li použít modely AI pro inteligentní predikci sémantiky, ušetřit čas a zlepšit přesnost, nastavte **Inteligentní mapování** na **ZAPNUTO**. Inteligentní mapování využívá doporučení sémantiky založené na AI v poli **Typ**. Pokud ji nastavíte na **VYPNUTO**, uvidíte naše pravidelná doporučení pro mapování. Z dostupného seznamu možností můžete vybrat libovolný sémantický typ a přepsat navrhovaný výběr.

> [!div class="mx-imgBorder"]
> ![Typ atributu a sémantická predikce.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Typ atributu a sémantická predikce")

Je také možné přidat vlastní sémantický typ entity. Vyberte pole typu pro atribut a zadejte název vlastního sémantického typu. Tímto způsobem můžete také změnit typy atributů, které byly systémem identifikovány.

Všechny atributy, pro které je sémantický typ automaticky identifikován, jsou seskupeny v sekci **Kontrola mapovaných polí**. Zkontrolujte tyto atributy a jejich sémantické typy, protože se použijí ke sloučení vašich entit v kroku sloučení během sjednocení dat.

Atributy, které nejsou automaticky mapovány na sémantický typ, jsou seskupeny v sekci **Definování dat v nemapovaných polích**. Vyberte pole sémantického typu pro nemapované atributy nebo zadejte vlastní název typu atributu.

> [!div class="mx-imgBorder"]
> ![Primární klíč a typ atributu.](media/data-manager-configure-map-add-attributes.png "Primární klíč a typ atributu")

> [!NOTE]
> Jedno pole by se mělo namapovat na sémantický typ Person.FullName k naplnění jména zákazníka na kartě zákazníka. Jinak se zákaznické karty objeví beze jména. 

## <a name="add-and-remove-attributes-and-entities"></a>Přidání a odebrání atributů a entit

1. V **Sjednocení** > **Mapování** vyberte **Upravit pole**.

2. V podokně **Upravit pole** přidejte nebo odeberte atributy a entity. Vyhledejte nebo posunutím vyhledejte a vyberte své atributy a entity, které vás zajímají. Nelze odebrat atribut nebo entitu, pokud již byly spárovány.

   > [!div class="mx-imgBorder"]
   > ![Přidat či odebrat atributy.](media/configure-data-map-edit.png "Přidat či odebrat atributy")

3. Vyberte **Použít**.

## <a name="add-images-to-profiles"></a>Přidání obrázků do profilů

Pokud entita obsahuje adresy URL pro veřejně dostupné profily nebo loga profilů, můžete je přidat do sjednoceného profilu zákazníka.

Vyberte entitu a najděte pole, které obsahuje adresu URL obrázku profilu. V poli **Typ** ručně zadejte následující hodnotu: 
- Pro osobu: Person.ProfileImage
- Pro organizaci: Organization.LogoImage

Pokračujte v krocích sjednocení a zajistěte, aby atribut, který obsahuje adresu URL obrázku, byl také přidán v kroku [Sloučení](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Nastavení atributů pro organizace

U organizací (Preview) by měl být typ atributu mapován na „Organization.Name“
> [!div class="mx-imgBorder"]
> ![Primární klíč a typ atributu B2B.](media/configure-data-map-edit-b2b.png "Primární klíč a typ atributu B2B")

## <a name="next-step"></a>Další krok

V rámci procesu sjednocení údajů přejděte na stránku **Přiřazení**. Návštivte [**Přiřazení**](match-entities.md) a získejte další informace o této fázi.

> [!TIP]
> Podívejte se na následující video: [Začínáme: Vytvoření jednotného profilu zákazníka](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]