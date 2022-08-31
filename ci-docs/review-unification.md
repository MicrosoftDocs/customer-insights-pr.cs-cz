---
title: Zkontrolujte sjednocení dat
description: Zkontrolujte kroky sjednocení dat, vytvořte jednotné profily zákazníků a zkontrolujte výsledky
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303959"
---
# <a name="review-data-unification"></a>Zkontrolujte sjednocení dat

Zkontrolujte souhrn změn, vytvořte sjednocený profil a zkontrolujte výsledky.

## <a name="review-and-create-customer-profiles"></a>Kontrola a vytváření profilů zákazníků

Tento poslední krok v procesu sjednocení zobrazuje souhrn kroků v procesu a poskytuje možnost provést změny před vytvořením sjednoceného profilu.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Screenshot kontroly a vytváření profilů zákazníků.":::

1. Vyberte **Upravit** na kterémkoli z kroků sjednocení dat ke kontrole a provedení jakýchkoli změn.

1. Pokud jste se svým výběrem spokojeni, vyberte **Vytvořit profily zákazníků** (nebo **Vytvořit profily účtů** v případě B2B).. Stránka **Sjednotit** se zobrazí při vytváření jednotného profilu zákazníka.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Screenshot stránky Unify s dlaždicemi Ve frontě nebo Aktualizuje se.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Dokončení sjednocovacího algoritmu nějakou dobu trvá a konfiguraci nelze změnit, dokud nebude dokončena.

## <a name="view-the-results-of-data-unification"></a>Zobrazení výsledků sjednocení dat

Po sjednocení se na stránce **Data** > **Sjednotit** zobrazuje počet sjednocených zákaznických profilů (nebo účtů v případě B2B). Výsledky každého kroku v procesu sjednocení se zobrazí na každé dlaždici. Například **Zdrojová pole** zobrazuje počet mapovaných atributů (polí) a **Duplicitní záznamy** zobrazuje počet nalezených duplicitních záznamů.

:::image type="content" source="media/m3_unified.png" alt-text="Snímek obrazovky stránky Sjednocení dat po sjednocení dat.":::

> [!TIP]
> Dlaždice **Podmínky shody** se zobrazí pouze v případě, že bylo vybráno více entit.

Doporučujeme vám zkontrolovat výsledky, zejména kvalitu vašich [pravidel shody](data-unification-update.md#manage-match-rules) a v případě potřeby je upřesnit.

Když je potřeba, [proveďte změny v nastavení sjednocení](data-unification-update.md) a znovu spusťte jednotný profil.

### <a name="verify-output-entities-from-data-unification"></a>Ověření výstupních entit ze sjednocení dat

Jděte na **Data** > **Entity** k ověření výstupních entit.

Entita sjednoceného profilu zákazníka s názvem *Zákazník* se zobrazuje v sekci **Profily**. První úspěšný běh sjednocení vytvoří sjednocenou entitu *Zákazník*. Všechny následující běhy tuto entitu rozšiřují.

Deduplikační a slučovací entity jsou vytvořeny a zobrazeny v sekci **Systém**. Pro každou zdrojovou entitu je vytvořena entita deduplikace s názvem **Deduplication_DataSource_Entity**. Entita **ConflationMatchPairs** obsahuje informace o párováních mezi entitami.

Entita výstupu odstraněných duplicit obsahuje následující informace:
- ID/klíče
  - Pole Primární klíč a Alternativní ID. Pole Alternativní ID obsahuje všechna alternativní ID identifikovaná pro záznam.
  - Pole Deduplication_GroupId zobrazuje skupinu nebo cluster identifikované v rámci entity, které seskupují všechny podobné záznamy na základě zadaných polí odstraněných duplicit. Používá se pro účely systémového zpracování. Pokud nejsou zadána žádná pravidla pro ruční odstranění duplicit a platí systémově definovaná pravidla pro odstranění duplicit, možná toto pole v entitě výstupu odstraněných duplicit nenajdete.
  - Deduplication_WinnerId: Toto pole obsahuje vítězné ID z identifikovaných skupin nebo clusterů. Pokud je hodnota Deduplication_WinnerId stejná jako hodnota primárního klíče záznamu, znamená to, že záznam je vítězným záznamem.
- Pole použitá k definování pravidel odstranění duplicit.
- Pole Pravidlo a Skóre označují, která z pravidel pro odstranění duplicit byla použita a které skóre bylo vráceno algoritmem pro párování.

## <a name="next-step"></a>Další krok

- V případě B2B volitelně proveďte [sjednocení kontaktu](data-unification-contacts.md).

- V případě B2C nakonfigurujte [aktivity](activities.md), [rozšíření](enrichment-hub.md), [vztahy](relationships.md) nebo [míry](measures.md), abyste získali více informací o svých zákaznících.

[!INCLUDE[footer-include](includes/footer-banner.md)]
