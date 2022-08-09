---
title: Vyberte zdrojová pole pro sjednocení dat
description: Prvním krokem v procesu sjednocení je výběr entit, atributů, primárních klíčů a sémantických typů pro mapování dat do jednotného profilu zákazníka.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a75218c996b277e00924f2b7b38ea686a1f4dc38
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139774"
---
# <a name="select-source-fields-for-data-unification"></a>Vyberte zdrojová pole pro sjednocení dat

Prvním krokem sjednocení je výběr entit a polí ve vašich datových sadách, které chcete sjednotit. Vyberte entity, které obsahují podrobnosti týkající se zákazníka, jako je jméno, adresa, telefonní číslo a e-mail. Lze vybrat jednu nebo více entit.

## <a name="select-entities-and-fields"></a>Vybrat entity a pole

1. Přejděte na **Data** > **Sjednotit**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Snímek obrazovky sjednocení vstupní stránky pro první spuštění se zvýrazněnou možností Začít.":::

1. Vyberte **Začínáme**.

1. Na stránce **Zdrojová pole** vyberte **Vybrat entity a pole**. Zobrazí se podokno **Vybrat entity a pole**.

1. Vyberte alespoň jednu entitu.

1. Pro každou vybranou entitu určete pole, která chcete použít ke spárování záznamů zákazníků a polí, která mají být zahrnuta do jednotného profilu. Tato pole se nazývají *Atributy*. Můžete vybrat požadované atributy jednotlivě z entity nebo zahrnout všechny atributy z entity zaškrtnutím políčka na úrovni entity. Můžete vyhledávat klíčová slova ve všech atributech a entitách a vybrat požadované atributy, které chcete mapovat.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Snímek obrazovky vybraných entit a atributů.":::

   V tomto příkladu přidáváme entity **Kontakty** a **CustomerLoyalty**. Výběrem těchto entit můžete získat přehled, kteří z online obchodních zákazníků jsou členy věrnostního programu.

1. Volbou **Použít** potvrďte svůj výběr. Zobrazení vybraných entit a atributů

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Výběr primárního klíče a sémantického typu pro atributy

   :::image type="content" source="media/m3_select_primary.png" alt-text="Screenshot vybraných entit s nevybraným primárním klíčem." lightbox="media/m3_select_primary.png":::

Pro každou entitu proveďte následující kroky.

1. Zvolte **Primární klíč**. Primární klíč je atribut jedinečný pro entitu. Aby byl atribut platným primárním klíčem, nesmí obsahovat duplicitní hodnoty, chybějící hodnoty nebo hodnoty null. Jako primární klíče jsou podporovány atributy typu String, Integer a GUID.

1. Chcete-li používat modely AI pro inteligentní predikce sémantiky, ušetřit čas a zlepšit přesnost, ujistěte se, že je **Inteligentní mapování** zapnuto. Inteligentní mapování využívá doporučení sémantiky založené na AI v poli **Typ**. Navrhovaný výběr můžete přepsat výběrem libovolného sémantického typu ze seznamu dostupných možností.

1. Pro každý atribut vyberte sémantiku **Typ**, který nejlépe popisuje daný atribut, jako je jméno, město nebo e-mailová adresa.

   > [!NOTE]
   > Jedno pole by se mělo namapovat na sémantický typ *Person.FullName* k vyplnění jména zákazníka na zákaznické kartě. Jinak se zákaznické karty objeví beze jména.

   1. Chcete-li změnit typ atributu identifikovaný systémem, vyberte jiný typ. Pokud typ neexistuje, vytvořte vlastní sémantický typ výběrem pole **Typ** pro atribut a zadání názvu vlastního sémantického typu.

   1. Chcete-li přidat atribut, který obsahuje adresu URL, k veřejně dostupným profilovým obrázkům nebo logům, vyberte entitu a pole obsahující adresu URL. V poli **Typ** zadejte následující:
      - Pro osobu: Person.ProfileImage
      - Pro organizaci: Organization.LogoImage

   1. Pro atribut názvu účtu zadejte do pole **Typ** Organization.Name".

1. Zkontrolujte atributy, kde je sémantický typ automaticky identifikován. Tyto atributy jsou uvedeny pod části **Zkontrolujte namapovaná pole**. V kroku **Sjednocená zákaznická pole** lze kombinovat pouze atributy stejného typu. Sémantické typy se používají k automatickému navrhování přehledů. Ujistěte se, že typy, které jste vybrali, jsou konzistentní ve všech vybraných entitách.

1. U atributů, které nejsou automaticky namapovány na sémantický typ, vyberte pole sémantického typu, zadejte název vlastního typu atributu nebo je ponechte nenamapované. Tyto atributy jsou uvedeny pod položkou **Definovat data v nenamapovaných polích**.

1. Po dokončení kroků pro každou entitu vyberte **Uložit zdrojová pole**.

1. Vyberte **Další**.

> [!div class="nextstepaction"]
> [Další krok: Odstraňte duplikáty](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
