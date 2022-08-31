---
title: Vyberte zdrojová pole pro sjednocení dat
description: Prvním krokem v procesu sjednocení je výběr entit, atributů, primárních klíčů a sémantických typů pro mapování dat do jednotného profilu zákazníka.
recommendations: false
ms.date: 08/12/2022
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
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304557"
---
# <a name="select-source-fields-for-data-unification"></a>Vyberte zdrojová pole pro sjednocení dat

Prvním krokem sjednocení je výběr entit a polí ve vašich datových sadách, které chcete sjednotit. Vyberte entity, které obsahují podrobnosti týkající se zákazníka, jako je jméno, adresa, telefonní číslo a e-mail. Lze vybrat jednu nebo více entit.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Vybrat entity a pole

1. Přejděte na **Data** > **Sjednotit**.

   Pro jednotlivé zákazníky (B2C) zobrazuje cílová stránka **Sjednocení** možnost **Začínáme** v prvním kroku **Zdrojová pole**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Screenshot cílové stránky sjednocení při prvním spuštění pro jednotlivé zákazníky.":::

   Pro obchodní účty (B2B) zobrazuje cílová stránka **Sjednocení** možnost **Sjednotit účty** s volbou **Začínáme** v prvním kroku **Zdrojová pole**. Kroky **Sjednocení kontaktů (Preview)** jsou volitelné a čekají na dokončení sjednocení účtu.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Screenshot cílové stránky sjednocení při prvním spuštění pro obchodní účty.":::

1. Vyberte **Začínáme**.

1. Na stránce **Zdrojová pole** vyberte **Vybrat entity a pole**. Zobrazí se podokno **Vybrat entity a pole**.

1. Vyberte alespoň jednu entitu.

1. Pro každou vybranou entitu určete pole, která chcete použít ke spárování záznamů zákazníků a polí, která mají být zahrnuta do jednotného profilu. Tato pole se nazývají *Atributy*. Můžete vybrat požadované atributy jednotlivě z entity nebo zahrnout všechny atributy z entity zaškrtnutím políčka na úrovni entity. Můžete vyhledávat klíčová slova ve všech atributech a entitách a vybrat požadované atributy, které chcete mapovat.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Snímek obrazovky vybraných entit a atributů.":::

   V tomto příkladu přidáváme entity **eCommerceContacts** a **loyCustomer**. Výběrem těchto entit můžete získat přehled, kteří z online obchodních zákazníků jsou členy věrnostního programu.

1. Volbou **Použít** potvrďte svůj výběr. Zobrazení vybraných entit a atributů

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Výběr primárního klíče a sémantického typu pro atributy

   :::image type="content" source="media/m3_select_primary.png" alt-text="Screenshot vybraných entit s nevybraným primárním klíčem." lightbox="media/m3_select_primary.png":::

Pro každou entitu proveďte následující kroky.

1. Zvolte **Primární klíč**. Primární klíč je atribut jedinečný pro entitu. Aby byl atribut platným primárním klíčem, nesmí obsahovat duplicitní hodnoty, chybějící hodnoty nebo hodnoty null. Jako primární klíče jsou podporovány atributy typu String, Integer a GUID.

1. Chcete-li používat modely AI pro inteligentní predikce sémantiky, které šetří čas a zlepšují přesnost, ujistěte se, že je zapnuto **Inteligentní mapování**. Inteligentní mapování poskytuje sémantická doporučení založená na AI v poli **Typ**.

1. Pro každý atribut vyberte sémantiku **Typ**, který nejlépe popisuje daný atribut, jako je jméno, město nebo e-mailová adresa.

   > [!NOTE]
   > V případě B2C by se jedno pole mělo namapovat na sémantický typ *Person.FullName* k vyplnění jména zákazníka na zákaznické kartě. V případě B2B by měl být název účtu namapován na *Organization.Name*. Jinak se zákaznické karty objeví beze jména.

   1. Chcete-li přepsat typ atributu identifikovaný systémem, vyberte jinou možnost. Pokud typ neexistuje, vytvořte vlastní sémantický typ výběrem pole **Typ** pro atribut a zadání názvu vlastního sémantického typu.

   1. Chcete-li přidat atribut, který obsahuje adresu URL, k veřejně dostupným profilovým obrázkům nebo logům, vyberte entitu a pole obsahující adresu URL. V poli **Typ** zadejte následující:
      - Pro osobu: Person.ProfileImage
      - Pro organizaci: Organization.LogoImage

1. Zkontrolujte atributy, kde je sémantický typ automaticky identifikován. Tyto atributy jsou uvedeny pod části **Zkontrolujte namapovaná pole**. V kroku **Sjednocení zákaznických polí** lze kombinovat pouze atributy stejného typu. Sémantické typy se používají k automatickému navrhování přehledů. Ujistěte se, že typy, které jste vybrali, jsou konzistentní ve všech vybraných entitách.

1. U atributů, které nejsou automaticky namapovány na sémantický typ, vyberte pole sémantického typu, zadejte název vlastního typu atributu nebo je ponechte nenamapované. Tyto atributy jsou uvedeny pod položkou **Definovat data v nenamapovaných polích**.

1. Po dokončení kroků pro každou entitu vyberte **Uložit zdrojová pole**.

1. Vyberte **Další**.

> [!div class="nextstepaction"]
> [Další krok: Odstraňte duplikáty](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
