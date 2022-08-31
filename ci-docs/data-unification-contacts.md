---
title: Vytvoření sjednoceného profilu kontaktu (Preview)
description: Projděte proces sjednocení dat a vytvořte jedinou hlavní datovou sadu kontaktů.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305015"
---
# <a name="create-a-unified-contact-profile-preview"></a>Vytvoření sjednoceného profilu kontaktu (Preview)

Po [sjednocení obchodních účtů](map-entities.md) můžete volitelně sjednotit kontakty pro tyto účty a propojit sjednocené kontakty se sjednocenými účty. Proces sjednocení kontaktů mapuje kontaktní data z více zdrojů dat, odstraňuje duplikáty, porovnává data napříč entitami, nastavuje sémantické mapování, vytváří vztahy mezi kontakty a účty a poté vytvoří jednotný profil kontaktu.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Prvních několik kroků je shodných s kroky pro sjednocení účtů.

## <a name="prerequisites"></a>Předpoklady

Záznamy účtů a kontaktů musí mít jedinečný klíč (nazývaný cizí klíč), který je propojuje. Například ID účtu, které existuje v záznamu účtu a záznamu kontaktu a propojuje účet a kontakt dohromady.

## <a name="preview-limitations"></a>Omezení verze Preview

- Kontakty bez propojení s účtem budou vynechány.
- Pokud je účet deduplikován, vítězný záznam je identifikován na základě předvoleb sloučení. Záznamy, které nevyhrály, nejsou vybrány, a proto jsou vynechány. Kontakty spojené se ztrátou záznamů budou vynechány.
- Účet může mít více kontaktů, ale kontakt je propojen jen s jedním účtem.
- Atributy kontaktu mapované v kroku sémantického mapování jsou jediné atributy, které lze zobrazit na kartě zákazníka. K dispozici je však 17 atributů.

## <a name="select-source-fields"></a>Výběr zdrojových polí

1. V části **Sjednocení kontaktů (Preview)** vyberte **Začít**.

1. [Vyberte entity a pole](map-entities.md) pro vaše zdroje kontaktních dat, včetně primárních klíčů a typů atributů.

1. Vyberte **Další**.

## <a name="remove-duplicate-records"></a>Odebrání duplicitních záznamů

1. Volitelně [definujte pravidla deduplikace](remove-duplicates.md) pro vámi vybrané entity.

1. Vyberte **Další**.

## <a name="match-conditions"></a>Podmínky shody

1. [Definujte pořadí a pravidla párování](match-entities.md) mezi entitami.

1. Vyberte **Další**.

## <a name="unify-contact-fields"></a>Sjednocení polí kontaktu

1. [Slučte a vylučte pole kontaktu](merge-entities.md).

1. Vyberte **Další**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definovat sémantická pole pro sjednocené kontakty

Tento krok v procesu sjednocení mapuje vaše sjednocená pole kontaktu na sémantické typy. V B2B se na zákaznických kartách zobrazují účty. Po výběru karty se zobrazí všechny kontakty spojené s účtem. Pole, která v tomto kroku mapujete, jsou pole, která se zobrazí na kartách.

1. Vyberte sémantický typ, který se mapuje na každé sjednocené pole. Vyberte **Žádný**, pokud sémantický typ není k dispozici.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Screenshot stránky sémantických polí k definování sémantických typů." lightbox="media/semantic_mapping.png":::

1. Po namapování všech sjednocených polí vyberte **Další**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Nastavení vztahu mezi kontakty a účty

Tento krok procesu sjednocení propojuje data kontaktu s odpovídajícími daty účtu.

1. Pro každou entitu zadejte následující informace.

   - **Cizí klíč od entity kontaktu**: Vyberte atribut, který propojuje vaši entitu kontaktu s účtem.
   - **S entitou účtu**: Vyberte entitu účtu přidruženou ke kontaktu.

   :::image type="content" source="media/contact_relationship.png" alt-text="Screenshot stránky Vztah k propojení entit kontaktu a účtu.":::

1. Vyberte **Další**.

## <a name="review-contact-unification"></a>Zkontrolovat sjednocení kontaktů

Zkontrolujte souhrn změn, vytvořte sjednocený profil a zkontrolujte výsledky.

### <a name="review-and-create-contact-profiles"></a>Kontrolovat a vytvářet profily kontaktů

Tento poslední krok v procesu sjednocení zobrazuje souhrn kroků v procesu a poskytuje možnost provést změny před vytvořením sjednoceného profilu kontaktu.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Screenshot Kontrola a vytváření profilů kontaktů.":::

1. Vyberte **Upravit** v kterémkoli z kroků sjednocení kontaktu ke kontrole a provedení libovolných změn.

1. Pokud jste se svým výběrem spokojeni, vyberte **Vytvořit profily kontaktů**. Stránka **Sjednocení** se zobrazí při vytváření sjednoceného profilu kontaktu.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Screenshot stránky Sjednocení kontaktů s dlaždicemi Ve frontě nebo Aktualizuje se.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Dokončení sjednocovacího algoritmu nějakou dobu trvá a konfiguraci nelze změnit, dokud nebude dokončena.

### <a name="view-the-results-of-contact-unification"></a>Zobrazení výsledků sjednocení kontaktů

Po dokončení sjednocení se na stránce **Data** > **Sjednocení** zobrazí počet sjednocených profilů kontaktů. Výsledky každého kroku v procesu sjednocení se zobrazí na každé dlaždici. Například **Zdrojová pole** zobrazuje počet mapovaných atributů (polí) a **Duplicitní záznamy** zobrazuje počet nalezených duplicitních záznamů.

:::image type="content" source="media/unified_contacts.png" alt-text="Screenshot stránky Sjednocení dat po sjednocení kontaktů.":::

> [!TIP]
> Dlaždice **Podmínky shody** se zobrazí pouze v případě, že bylo vybráno více entit.

Doporučujeme vám zkontrolovat výsledky, zejména kvalitu vašich [pravidel shody](data-unification-update.md#manage-match-rules) a v případě potřeby je upřesnit.

Když je potřeba, [proveďte změny v nastavení sjednocení kontaktů](data-unification-update.md) a znovu spusťte jednotný profil.

### <a name="verify-output-entities-from-data-unification"></a>Ověření výstupních entit ze sjednocení dat

Jděte na **Data** > **Entity** k ověření výstupních entit.

Entita sjednoceného profilu kontaktu, tzv. *ContactProfile*, se zobrazí v sekci **Sémantické entity**. První úspěšný běh sjednocení vytvoří sjednocenou entitu *ContactProfile*. Všechny následující běhy tuto entitu rozšiřují.

Entita *ContactsCustomer* (Preview) je vytvořena a zobrazena v sekci **Profily**. Tato entita obsahuje kontaktní údaje bez odkazů na účty. Tato entita slouží jako vstup do kroků sémantického mapování a vztahů při sjednocení kontaktů.

Deduplikační a slučovací entity jsou vytvořeny a zobrazeny v sekci **Systém**. Pro každou zdrojovou entitu je vytvořena entita deduplikace s názvem **Deduplication_DataSource_Entity**. Entita **ContactsConflationMatchPairs** obsahuje informace o párováních mezi entitami.

Entita výstupu odstraněných duplicit obsahuje následující informace:
- ID/klíče
  - Pole Primární klíč a Alternativní ID. Pole Alternativní ID obsahuje všechna alternativní ID identifikovaná pro záznam.
  - Pole Deduplication_GroupId zobrazuje skupinu nebo cluster identifikované v rámci entity, které seskupují všechny podobné záznamy na základě zadaných polí odstraněných duplicit. Používá se pro účely systémového zpracování. Pokud nejsou zadána žádná pravidla pro ruční odstranění duplicit a platí systémově definovaná pravidla pro odstranění duplicit, možná toto pole v entitě výstupu odstraněných duplicit nenajdete.
  - Deduplication_WinnerId: Toto pole obsahuje vítězné ID z identifikovaných skupin nebo clusterů. Pokud je hodnota Deduplication_WinnerId stejná jako hodnota primárního klíče záznamu, znamená to, že záznam je vítězným záznamem.
- Pole použitá k definování pravidel odstranění duplicit.
- Pole Pravidlo a Skóre označují, která z pravidel pro odstranění duplicit byla použita a které skóre bylo vráceno algoritmem pro párování.

## <a name="next-step"></a>Další krok

Konfigurujte [Aktivity](activities.md), [obohacení](enrichment-hub.md) nebo [Vztahy](relationships.md) pro další přehledy o kontaktech.
