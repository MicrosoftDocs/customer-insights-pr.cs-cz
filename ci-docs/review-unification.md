---
title: Zkontrolujte sjednocení dat
description: Zkontrolujte kroky sjednocení dat, vytvořte jednotné profily zákazníků a zkontrolujte výsledky
ms.date: 06/02/2022
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
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139567"
---
# <a name="review-data-unification"></a>Zkontrolujte sjednocení dat

Tento poslední krok v procesu sjednocení zobrazuje souhrn kroků v procesu a poskytuje možnost provést změny před vytvořením sjednoceného profilu.

:::image type="content" source="media/m3_review.png" alt-text="Screenshot Kontrola a vytváření profilů zákazníků":::

## <a name="review-the-data-unification-steps"></a>Projděte si kroky sjednocení dat

1. Vyberte **Upravit** na kterémkoli z kroků sjednocení dat ke kontrole a provedení jakýchkoli změn.

1. Pokud jste se svým výběrem spokojeni, vyberte **Vytvořit profily zákazníků**. Stránka **Sjednotit** se zobrazí při vytváření jednotného profilu zákazníka. Všechny dlaždice kromě **Zdrojová pole** ukazují stav **Ve frontě** nebo **Aktualizuje se**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Screenshot stránky Unify s dlaždicemi Ve frontě nebo Aktualizuje se.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Dokončení sjednocovacího algoritmu nějakou dobu trvá a konfiguraci nelze změnit, dokud nebude dokončena. Po dokončení procesu sjednocení je entita sjednoceného profilu zákazníka nazvaná *Zákazník* uvedena na stránce **Entity** v sekci **Profily**. První úspěšný běh sjednocení vytvoří sjednocenou entitu *Zákazník*. Všechny následující běhy tuto entitu rozšiřují.

## <a name="review-the-results-of-data-unification"></a>Projděte si výsledky sjednocení dat

Po sjednocení se na stránce **Data** > **Sjednotit** zobrazuje počet sjednocených zákaznických profilů. Výsledky každého kroku v procesu sjednocení se zobrazí na každé dlaždici. Například **Zdrojová pole** zobrazuje počet mapovaných atributů (polí) a **Duplicitní záznamy** zobrazuje počet nalezených duplicitních záznamů.

:::image type="content" source="media/m3_unified.png" alt-text="Snímek obrazovky stránky Sjednocení dat po sjednocení dat.":::

> [!TIP]
> Dlaždice **Podmínky shody** se zobrazí pouze v případě, že bylo vybráno více entit.

Doporučujeme vám zkontrolovat výsledky, zejména kvalitu vašich [pravidel shody](data-unification-update.md#manage-match-rules) a v případě potřeby je upřesnit.

Když je potřeba, [proveďte změny v nastavení sjednocení](data-unification-update.md) a znovu spusťte jednotný profil.

## <a name="next-step"></a>Další krok

Nakonfigurujte [aktivity](activities.md), [obohacení](enrichment-hub.md), [vztahy](relationships.md), nebo [opatření](measures.md), abyste získali více informací o svých zákaznících.

[!INCLUDE[footer-include](includes/footer-banner.md)]
