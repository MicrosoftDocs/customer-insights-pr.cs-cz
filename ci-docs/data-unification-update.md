---
title: Aktualizace nastavení sjednocení
description: Aktualizujte duplicitní pravidla, pravidla shody nebo sjednocená pole v nastavení sjednocení.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 590a2996cf8b2b1c6def59b78583169ec1910b59
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844032"
---
# <a name="update-the-unification-settings"></a>Aktualizace nastavení sjednocení

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Chcete-li zkontrolovat nebo změnit nastavení sjednocení po vytvoření sjednoceného profilu, proveďte následující kroky.

1. Přejděte na **Data** > **Sjednotit**.

   :::image type="content" source="media/m3_unified.png" alt-text="Snímek obrazovky stránky Sjednocení dat po sjednocení dat.":::

   > [!TIP]
   > Dlaždice **Podmínky shody** se zobrazí pouze v případě, že bylo vybráno více entit.

1. Zvolte, co chcete aktualizovat:
   - [Zdrojová pole](#edit-source-fields) pro přidání entit nebo atributů nebo změnu typů atributů.
   - [Duplicitní záznamy](#manage-deduplication-rules) ke správě pravidel deduplikace nebo předvoleb sloučení.
   - [Odpovídající podmínky](#manage-match-rules) k aktualizaci pravidel shody ve dvou nebo více entitách.
   - [Sjednocená zákaznická pole](#manage-unified-fields) pro zkombinování nebo vyloučení polí. Související profily můžete také seskupit do clusterů.

1. Po provedení změn vyberte další možnost:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Snímek obrazovky stránky Sjednocení dat se zvýrazněnými možnostmi sjednocení.":::

   - [Spusťte podmínky shody](#run-matching-conditions) pro rychlé vyhodnocení kvality vašich odpovídajících podmínek bez aktualizace sjednoceného profilu (pravidla deduplicace a shody). Možnost **Spustit pouze podmínky shody** se nezobrazuje pro jednu entitu.
   - [Sjednoťte profily zákazníků](#run-updates-to-the-unified-customer-profile), abyste mohli spustit podmínky shody a aktualizovat entitu sjednoceného profilu zákazníka bez ovlivnění závislostí (jako jsou obohacení, segmenty nebo opatření). Závislé procesy nejsou spuštěny, ale budou aktualizovány jako [definované v plánu aktualizací](system.md#schedule-tab).
   - [Sjednoťte profily zákazníků a závislosti](#run-updates-to-the-unified-customer-profile), abyste mohli spustit podmínky shody a aktualizovat entitu sjednoceného profilu zákazníka a všechny závislosti (jako jsou obohacení, segmenty nebo opatření). Všechny procesy jsou automaticky znovu spuštěny.

## <a name="edit-source-fields"></a>Upravit zdrojová pole

Atribut nebo entitu nelze odstranit, pokud již byly sjednoceny.

1. Vyberte **Upravit** v dlaždici **Zdrojová pole**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Snímek obrazovky stránky Zdrojová pole zobrazující počet primárních klíčů, mapovaných a nenamapovaných polí":::

   Zobrazí se počet namapovaných a nenamapovaných polí.

1. Vyberte **Vybrat entity a pole** pro přidání dalších atributů nebo entit. Vyhledejte nebo posunutím vyhledejte a vyberte své atributy a entity, které vás zajímají. Vyberte **Použít**.

1. Volitelně můžete změnit primární klíč entity, typy atributů a zapnout nebo vypnout **Inteligentní mapování**. Více informací získáte v části [Výběr primárního klíče a sémantického typu pro atributy](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Vyberte **Další** a proveďte změny v pravidlech deduplikace nebo vyberte **Uložit a zavřít** a vraťte se do pole [Aktualizovat nastavení sjednocení](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Správa pravidel odstranění duplicit

1. Vyberte **Upravit** v dlaždici **Duplikovat záznamy**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Screenshot stránky Duplicitní záznamy zobrazující počet duplicitních záznamů" lightbox="media/m3_duplicates_edit.png":::

   Počet nalezených duplicitních záznamů se zobrazuje v části **Duplikáty**. Sloupec **Deduplikované záznamy** ukazuje, které entity měly duplicitní záznamy a procento duplicitních záznamů.

1. Pokud jste přidali obohacenou entitu, vyberte **Použít obohacené entity**. Další informace najdete v tématu [Rozšíření zdrojů dat](data-sources-enrichment.md).

1. Chcete-li spravovat pravidla deduplikace, vyberte kteroukoli z následujících možností:
   - **Vytvoření nového pravidla**: Vyberte **Přidat pravidlo** pod příslušnou entitou. Další informace viz [Definování pravidel deduplikace](remove-duplicates.md#define-deduplication-rules).
   - **Změna podmínek pravidla**: Vyberte pravidlo a poté **Upravit**. Změňte pole, přidejte nebo odeberte podmínky nebo přidejte nebo odeberte výjimky.
   - **Náhled**: Vyberte pravidlo a poté **Náhled** k zobrazení výsledků posledního běhu pro toto pravidlo.
   - **Deaktivace pravidla**: Vyberte pravidlo a poté **Deaktivovat** pro zachování pravidla deduplikace a jeho současného vyloučení z procesu porovnání.
   - **Duplikace pravidla**: Vyberte pravidlo a poté **Duplikovat** pro vytvoření podobného pravidla s úpravami.
   - **Odstranění pravidla**: Vyberte pravidlo a poté **Odstranit**.

1. Chcete-li změnit předvolby sloučení, vyberte entitu. Předvolby můžete změnit pouze v případě, že je vytvořeno pravidlo.
   1. Vyberte **Upravit předvolby sloučení** a změňte volu **Záznam k uchování**.
   1. Chcete-li změnit předvolby sloučení u jednotlivých atributů entity, vyberte **Pokročilý** a proveďte potřebné změny.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Snímek obrazovky rozšířených předvoleb zobrazující poslední e-mail a úplnou adresu":::

   1. Vyberte **Hotovo**.

1. Vyberte **Další** a proveďte změny v odpovídajících podmínkách nebo vyberte **Uložit a zavřít** a vraťte se do pole [Aktualizovat nastavení sjednocení](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Správa pravidel párování

Většinu parametrů párování můžete překonfigurovat a doladit. Nemůžete přidávat nebo odstraňovat entity. Pravidla shody se nevztahují na jednu entitu.

1. Vyberte **Upravit** v dlaždici **Podmínky shody**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Snímek obrazovky stránky Pravidla a podmínky shody se statistikami." lightbox="media/m3_match_edit.png":::

   Stránka zobrazuje pořadí shody a definovaná pravidla a následující statistiky:
   - **Jedinečné zdrojové záznamy** zobrazuje počet jednotlivých zdrojových záznamů, které byly zpracovány při posledním spuštění párování.
   - **Spárované a nespárované záznamy** zdůrazňuje, kolik jedinečných záznamů zbývá po zpracování pravidel párování.
   - **Pouze spárované záznamy** zobrazuje počet párování všech spárovaných dvojic.

1. Chcete-li zobrazit výsledky všech pravidel a jejich skóre, vyberte **Zobrazit poslední spuštění**. Zobrazí se výsledky, včetně alternativních ID kontaktu. Výsledky si můžete stáhnout.

1. Chcete-li zobrazit výsledky a skóre konkrétního pravidla, vyberte pravidlo a poté **Náhled**. Zobrazí se výsledky. Výsledky si můžete stáhnout.

1. Chcete-li zobrazit výsledky konkrétní podmínky v pravidle, vyberte pravidlo a poté **Upravit**. V podokně Úpravy vyberte **Náhled** pod podmínkou. Výsledky si můžete stáhnout.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafické znázornění nespárovaných a spárovaných záznamů včetně seznamu dat.":::

1. Pokud jste přidali obohacenou entitu, vyberte **Použít obohacené entity**. Další informace najdete v tématu [Rozšíření zdrojů dat](data-sources-enrichment.md).

1. Chcete-li spravovat pravidla, vyberte kteroukoli z následujících možností:
   - **Vytvoření nového pravidla**: Vyberte **Přidat pravidlo** pod příslušnou entitou. Více informací viz [Definování pravidel pro dvojice shody](match-entities.md#define-rules-for-match-pairs).
   - **Změňte pořadí pravidel**, pokud jste definovali více pravidel: Přetáhněte pravidla do požadovaného pořadí. Další informace získáte v části [Specifikace CORS](match-entities.md#specify-the-match-order).
   - **Změna podmínek pravidla**: Vyberte pravidlo a poté **Upravit**. Změňte pole, přidejte nebo odeberte podmínky nebo přidejte nebo odeberte výjimky.
   - **Deaktivace pravidla**: Vyberte pravidlo a poté **Deaktivovat** pro zachování pravidla shody a jeho současného vyloučení z procesu porovnání.
   - **Duplikace pravidla**: Vyberte pravidlo a poté **Duplikovat** pro vytvoření podobného pravidla s úpravami.
   - **Odstranění pravidla**: Vyberte pravidlo a poté **Odstranit**.

1. Vyberte **Další** a proveďte změny ve sjednocených polích nebo vyberte **Uložit a zavřít** a vraťte se do pole [Aktualizovat nastavení sjednocení](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Správa sjednocených polí

1. Vyberte **Upravit** v dlaždici **Sjednocená pole zákazníka**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Snímek obrazovky sjednocených zákaznických polí":::

1. Zkontrolujte kombinovaná a vyloučená pole a podle potřeby proveďte změny. Přidejte nebo upravte klíč CustomerID nebo seskupte profily do clusterů. Další informace viz [Sjednocená zákaznická pole](merge-entities.md).

1. Vyberte **Další** ke kontrole nastavení sjednocení a [aktualizaci sjednoceného profilu a závislostí](#run-updates-to-the-unified-customer-profile) nebo vyberte **Uložit a zavřít** a vraťte se do okna [Aktualizovat nastavení sjednocení](#update-the-unification-settings) k provedení dalších změn.

## <a name="run-matching-conditions"></a>Spuštění podmínek shody

Spuštění podmínek shody spustí pouze pravidla deduplikace a shody a aktualizuje entity *Deduplication_* a *ConflationMatchPair*.

1. Na stránce **Data** > **Sjednotit** vyberte **Spustit pouze podmínky shody**.

   Dlaždice **Duplicitní záznamy** a **Podmínky shody** ukazují stav **Ve frontě** nebo **Aktualizace**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Po dokončení procesu přiřazování vyberte **Upravit** na dlaždici **Podmínky shody**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Oříznutý screenshot klíčových metrik na stránce Párování s čísly a podrobnostmi.":::

1. Chcete-li provést změny, získáte informace v části [Správa pravidel deduplikace](#manage-deduplication-rules) nebo [Správa pravidel shody](#manage-match-rules).

1. Spusťte proces shody znovu nebo [spusťte aktualizace profilu zákazníka](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Spusťte aktualizace sjednoceného profilu zákazníka

1. Na stránce **Data** > **Sjednotit** vyberte:

   - **Sjednotit profily zákazníků**: Spustí podmínky shody a aktualizuje entitu sjednoceného profilu zákazníka bez ovlivnění závislostí (jako jsou obohacení, segmenty nebo opatření). Závislé procesy nejsou spuštěny, ale budou aktualizovány jako [definované v plánu aktualizací](system.md#schedule-tab).

   - **Sjednotit profily zákazníků a závislosti**: Spustí spustit podmínky shody a aktualizuje entitu sjednoceného profilu zákazníka a všechny závislosti. Všechny procesy jsou automaticky znovu spuštěny. Po dokončení všech navazujících procesů se v profilu zákazníka promítnou aktualizované údaje.

   Dlaždice **Duplicitní záznamy**, **Podmínky shody** a dlaždice **Sjednocená zákaznická pole** ukazují stav **Ve frontě** nebo **Aktualizuje se**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Výsledky úspěšného běhu se zobrazí na stránce **Sjednotit** zobrazující počet sjednocených zákaznických profilů.
