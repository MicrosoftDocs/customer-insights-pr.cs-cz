---
title: Zkontrolujte sjednocení dat
description: Zkontrolujte kroky sjednocení dat, vytvořte jednotné profily zákazníků a zkontrolujte výsledky
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741626"
---
# <a name="review-data-unification"></a>Zkontrolujte sjednocení dat

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Tento poslední krok v procesu sjednocení zobrazuje souhrn kroků v procesu a poskytuje možnost provést změny před vytvořením sjednoceného profilu.

:::image type="content" source="media/m3_review.png" alt-text="Screenshot Kontrola a vytváření profilů zákazníků":::

## <a name="review-the-data-unification-steps"></a>Projděte si kroky sjednocení dat

1. Vyberte **Upravit** na kterémkoli z kroků sjednocení dat ke kontrole a provedení jakýchkoli změn.

1. Pokud jste se svým výběrem spokojeni, vyberte **Vytvořit profily zákazníků**. Stránka **Sjednotit** se zobrazí při vytváření jednotného profilu zákazníka. Dokončení sjednocovacího algoritmu nějakou dobu trvá a konfiguraci nelze změnit, dokud nebude dokončena.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Po dokončení procesu sjednocení je entita sjednoceného profilu zákazníka nazvaná *Zákazník* uvedena na stránce **Entity** v sekci **Profily**. První úspěšný běh sjednocení vytvoří sjednocenou entitu *Zákazník*. Všechny následující běhy tuto entitu rozšiřují.

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
