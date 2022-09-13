---
title: Aktualizace nastavení sjednocení zákazníků, účtů nebo kontaktů
description: Aktualizujte duplicitní pravidla, pravidla shody nebo sjednocená pole v nastavení sjednocení zákazníků nebo účtů.
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392463"
---
# <a name="update-unification-settings"></a>Aktualizace nastavení sjednocení

Chcete-li zkontrolovat nebo změnit nastavení sjednocení po vytvoření sjednoceného profilu, proveďte následující kroky.

1. Přejděte na **Data** > **Sjednotit**.

   Pro individuální zákazníky (B2C) se na stránce **Sjednocení** zobrazuje počet sjednocených zákaznických profilů a dlaždice pro každý z kroků sjednocení.

   :::image type="content" source="media/m3_unified.png" alt-text="Snímek obrazovky stránky Sjednocení dat po sjednocení dat." lightbox="media/m3_unified.png":::

   Pro obchodní účty (B2B) se na stránce **Sjednocení** zobrazuje počet sjednocených profilů účtů a dlaždice pro každý z kroků sjednocení účtů. Pokud byly kontakty sjednoceny, zobrazí se počet sjednocených profilů kontaktů a dlaždice pro každý z kroků sjednocení kontaktů. Vyberte vhodnou dlaždici v části **Sjednocení účtů** nebo **Sjednocení kontaktů (Preview)** podle toho, co chcete aktualizovat.

   :::image type="content" source="media/b2b_unified.png" alt-text="Screenshot stránky Sjednocení dat po sjednocení dat účtů a kontaktů." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Dlaždice **Podmínky shody** se zobrazí pouze v případě, že bylo vybráno více entit.

1. Zvolte, co chcete aktualizovat:
   - [Zdrojová pole](#edit-source-fields) pro přidání atributů nebo entit nebo změnu typů atributů. Chcete-li odstranit atribut, viz [Odebrání sjednoceného pole](#remove-a-unified-field). Chcete-li odstranit entitu, viz [Odebrání sjednocené entity](#remove-a-unified-entity).
   - [Duplicitní záznamy](#manage-deduplication-rules) ke správě pravidel deduplikace nebo předvoleb sloučení.
   - [Odpovídající podmínky](#manage-match-rules) k aktualizaci pravidel shody ve dvou nebo více entitách.
   - [Sjednocená zákaznická pole](#manage-unified-fields) pro zkombinování nebo vyloučení polí. Související profily můžete také seskupit do clusterů.
   - [Sémantická pole](#manage-semantic-fields-for-unified-contacts) ke správě sémantických typů pro sjednocená pole kontaktů.
   - [Vztahy](#manage-contact-and-account-relationships) ke správě vztahu kontaktu k účtu.

1. Po provedení změn vyberte další možnost:

   - [Spusťte podmínky shody](#run-matching-conditions) pro rychlé vyhodnocení kvality vašich odpovídajících podmínek bez aktualizace sjednoceného profilu (pravidla deduplicace a shody). Možnost **Spustit pouze podmínky shody** se nezobrazuje pro jednu entitu.
   - [Sjednoťte profily](#run-updates-to-the-unified-profile), abyste mohli spustit podmínky shody a aktualizovat entitu sjednoceného profilu bez ovlivnění závislostí (jako jsou rozšíření, segmenty nebo míry). Závislé procesy nejsou spuštěny, ale budou aktualizovány jako [definované v plánu aktualizací](schedule-refresh.md).
   - [Sjednoťte profily a závislosti](#run-updates-to-the-unified-profile), abyste mohli spustit podmínky shody, aktualizovat entitu sjednoceného profilu a aktualizovat všechny závislosti (jako jsou rozšíření, segmenty nebo míry). Všechny procesy jsou automaticky znovu spuštěny. V B2B je sjednocení spuštěno u entit účtu i kontaktu a jsou aktualizovány sjednocené profily.

## <a name="edit-source-fields"></a>Upravit zdrojová pole

1. Vyberte **Upravit** v dlaždici **Zdrojová pole**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Snímek obrazovky stránky Zdrojová pole zobrazující počet primárních klíčů, mapovaných a nenamapovaných polí":::

   Zobrazí se počet namapovaných a nenamapovaných polí.

1. Chcete-li přidat další atributy nebo entity, vyberte **Vybrat entity a pole**.

1. Volitelně můžete změnit primární klíč entity, typy atributů a zapnout nebo vypnout **Inteligentní mapování**. Další informace viz [Výběr zdrojových polí](map-entities.md).

1. Vyberte **Další** a proveďte změny v pravidlech deduplikace nebo vyberte **Uložit a zavřít** a vraťte se do pole [Aktualizovat nastavení sjednocení](#update-unification-settings).

### <a name="remove-a-unified-field"></a>Odebrání sjednoceného pole

Chcete-li odebrat pole, které bylo sjednoceno, musí být pole odstraněno ze všech závislostí, jako jsou segmenty, míry, rozšiřování nebo vztahy.

1. Po odstranění všech závislostí pro pole přejděte na **Data** > **Sjednotit**.

1. Vyberte **Upravit** v dlaždici **Sjednocená pole zákazníka**.

1. Vyberte všechny výskyty pole a poté vyberte **Vyloučit**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Snímek obrazovky stránky Sjednocená pole zobrazující vybraná pole a tlačítko Vyloučit":::

1. Zvolte **Hotovo** k potvrzení a pak vyberte **Uložit a zavřít**.

   > [!TIP]
   > Pokud se zobrazí zpráva „Nelze uložit sjednocení. Zadaný zdroj nelze upravit ani odstranit z důvodu navazujících závislostí,“ pak se pole stále používá v navazující závislosti.

1. Pokud je pole použito v pravidle pro duplicitní záznamy nebo odpovídajících podmínkách, proveďte následující kroky. Jinak přejděte k dalšímu kroku.
   1. Vyberte **Upravit** v dlaždici **Duplikovat záznamy**.
   1. Odeberte pole ze všech pravidel, ve kterých se používá, pokud existují, a poté vyberte **Další**.
   1. Na stránce **Odpovídající podmínky** odeberte pole ze všech pravidel, ve kterých se používá, pokud existují, a poté vyberte **Uložit a zavřít**.
   1. Vyberte **Sjednotit** > **Sjednotit zákaznické profily a závislosti**. Než přejdete k dalšímu kroku, počkejte na dokončení sjednocení.

1. Vyberte **Upravit** v dlaždici **Zdrojová pole**.

1. Vyberte **Vybrat entity a pole** a zrušte zaškrtnutí políčka vedle každého výskytu pole.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Snímek obrazovky dialogového okna Vybrat entity a pole zobrazující zrušená zaškrtávací políčka":::

1. Vyberte **Použít**.

1. Zvolte **Uložit a zavřít**.

1. Vyberte **Sjednotit** > **Sjednotit profily a závislostí zákazníků** pro aktualizaci sjednoceného profilu.

### <a name="remove-a-unified-entity"></a>Odebrání sjednocené entity

Chcete-li odebrat entity, která byla sjednocena, musí být entita odstraněna ze všech závislostí, jako jsou segmenty, míry, rozšiřování nebo vztahy.

1. Po odstranění všech závislostí pro entitu přejděte na **Data** > **Sjednotit**.

1. Vyberte **Upravit** v dlaždici **Sjednocená pole zákazníka**.

1. Vyberte všechna pole pro entitu a poté vyberte **Vyloučit**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Snímek obrazovky stránky Sjednocená pole se všemi poli pro vybranou entitu a tlačítko Vyloučit":::

1. Zvolte **Hotovo** k potvrzení a pak vyberte **Uložit a zavřít**.

   > [!TIP]
   > Pokud se zobrazí zpráva „Nelze uložit sjednocení. Zadaný zdroj nelze upravit ani odstranit z důvodu navazujících závislostí,“ pak se entita stále používá v navazující závislosti.

1. Vyberte **Upravit** v dlaždici **Duplikovat záznamy**.

1. Odeberte všechna pravidla z entity, pokud existují, a poté vyberte **Další**.

1. Na stránce **Odpovídající podmínky** vyberte entitu a poté vyberte **Odstranit**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Snímek obrazovky s podmínkami shody s vybranou entitou a tlačítkem Odstranit":::

1. Zvolte **Uložit a zavřít**.

1. Vyberte **Upravit** v dlaždici **Zdrojová pole**.

1. Vyberte **Vybrat entity a pole** a zrušte zaškrtnutí políčka vedle entity.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Snímek obrazovky dialogového okna Vybrat entity s nezaškrtnutým políčkem entity":::

1. Vyberte **Použít**.

1. Zvolte **Uložit a zavřít**.

1. Vyberte **Sjednotit** > **Sjednotit profily a závislostí zákazníků** pro aktualizaci sjednoceného profilu.

## <a name="manage-deduplication-rules"></a>Správa pravidel odstranění duplicit

1. Vyberte **Upravit** v dlaždici **Duplikovat záznamy**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Screenshot stránky Duplicitní záznamy zobrazující počet duplicitních záznamů" lightbox="media/m3_duplicates_edit.png":::

   Počet nalezených duplicitních záznamů se zobrazuje v části **Duplikáty**. Sloupec **Deduplikované záznamy** ukazuje, které entity měly duplicitní záznamy a procento duplicitních záznamů.

1. Chcete-li použít rozšířenou entitu, vyberte **Použít rozšířené entity**. Další informace najdete v tématu [Rozšíření zdrojů dat](data-sources-enrichment.md).

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

   1. Vyberte **Hotovo**.

1. Vyberte **Další** a proveďte změny v odpovídajících podmínkách nebo vyberte **Uložit a zavřít** a vraťte se do pole [Aktualizovat nastavení sjednocení](#update-unification-settings).

## <a name="manage-match-rules"></a>Správa pravidel párování

Většinu parametrů párování můžete překonfigurovat a doladit. Nemůžete přidávat nebo odstraňovat entity. Pravidla shody se nevztahují na jednu entitu.

1. Vyberte **Upravit** v dlaždici **Podmínky shody**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Snímek obrazovky stránky Pravidla a podmínky shody se statistikami." lightbox="media/m3_match_edit.png":::

   Stránka zobrazuje pořadí shody a definovaná pravidla a následující statistiky:
   - **Jedinečné zdrojové záznamy** zobrazuje počet jednotlivých zdrojových záznamů, které byly zpracovány při posledním spuštění párování.
   - Část **Spárované a nespárované záznamy** zdůrazňuje, kolik jedinečných záznamů zbývá po zpracování pravidel párování.
   - **Pouze spárované záznamy** zobrazuje počet párování všech spárovaných dvojic.

1. Chcete-li zobrazit výsledky všech pravidel a jejich skóre, vyberte **Zobrazit poslední spuštění**. Zobrazí se výsledky, včetně alternativních ID kontaktů. Výsledky si můžete stáhnout.

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

1. Vyberte **Další** a proveďte změny ve sjednocených polích nebo vyberte **Uložit a zavřít** a vraťte se do pole [Aktualizovat nastavení sjednocení](#update-unification-settings).

## <a name="manage-unified-fields"></a>Správa sjednocených polí

1. Vyberte **Upravit** v dlaždici **Sjednocená pole zákazníka**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Snímek obrazovky sjednocených zákaznických polí":::

1. Zkontrolujte kombinovaná a vyloučená pole a podle potřeby proveďte změny. Přidejte nebo upravte klíč CustomerID nebo seskupte profily do clusterů. Další informace viz [Sjednocená zákaznická pole](merge-entities.md).

1. Pro zákazníky nebo účty vyberte **Další**, čímž zkontrolujete a [aktualizujete sjednocemý profil a závislosti](#run-updates-to-the-unified-profile). Případně vyberte **Uložit a zavřít** a vraťte se do pole [Aktualizovat nastavení sjednocení](#update-unification-settings), chcete-li provést další změny.

   Pro kontakty vyberte **Další**, čímž přejdete ke správě sémantických polí. Případně vyberte **Uložit a zavřít** a vraťte se do pole [Aktualizovat nastavení sjednocení](#update-unification-settings), chcete-li provést další změny.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Správa sémantických polí pro sjednocené kontakty

1. Vyberte **Upravit** v dlaždici **Sémantická pole**.

1. Chcete-li změnit sémantický typ sjednoceného pole, vyberte nový typ. Další informace viz [Definování sémantických polí pro sjednocené kontakty](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Vyberte **Další**, čímž přejdete ke správě vztahů mezi účty a kontakty, nebo vyberte **Uložit a zavřít** a vraťte se do pole [Aktualizovat nastavení sjednocení](#update-unification-settings), chcete-li provést další změny.

## <a name="manage-contact-and-account-relationships"></a>Správa vztahů mezi kontakty a účty

1. Vyberte **Upravit** v dlaždici **Vztahy**.

1. Chcete-li změnit vztah mezi kontaktem a účtem, změňte některou z následujících informací:

   - **Cizí klíč od entity kontaktu**: Vyberte atribut, který propojuje vaši entitu kontaktu s účtem.
   - **S entitou účtu**: Vyberte entitu účtu přidruženou ke kontaktu.

1. Vyberte **Další** ke kontrole nastavení sjednocení a [aktualizaci sjednoceného profilu a závislostí](#run-updates-to-the-unified-profile) nebo vyberte **Uložit a zavřít** a vraťte se do okna [Aktualizovat nastavení sjednocení](#update-unification-settings) k provedení dalších změn.

## <a name="run-matching-conditions"></a>Spuštění podmínek shody

Spuštění podmínek shody spustí pouze pravidla deduplikace a shody a aktualizuje entity *Deduplication_* a *ConflationMatchPair*.

1. Na stránce **Data** > **Sjednotit** vyberte **Spustit pouze podmínky shody**.

   Dlaždice **Duplicitní záznamy** a **Podmínky shody** ukazují stav **Ve frontě** nebo **Aktualizace**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Po dokončení procesu přiřazování vyberte **Upravit** na dlaždici **Podmínky shody**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Oříznutý screenshot klíčových metrik na stránce Párování s čísly a podrobnostmi.":::

1. Chcete-li provést změny, získáte informace v části [Správa pravidel deduplikace](#manage-deduplication-rules) nebo [Správa pravidel shody](#manage-match-rules).

1. Spusťte proces shody znovu nebo [spusťte aktualizace profilu](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Spuštění aktualizací sjednoceného profilu

- Chcete-li spustit podmínky párování a aktualizovat entitu sjednoceného profilu *bez* ovlivnění závislostí (jako jsou karty zákazníků, rozšíření, segmenty nebo míry), vyberte **Sjednotit profily zákazníků**. Pro účty vyberte **Sjednotit účty** > **Sjednotit profily**. Pro kontakty vyberte **Sjednotit kontakty (Preview)** > **Sjednotit profily**. Závislé procesy nejsou spuštěny, ale budou aktualizovány jako [definované v plánu aktualizací](schedule-refresh.md).
- Chcete-li spustit podmínky párování, aktualzovat sjednocený profil a spustit všechny závislosti, vyberte **Sjednotit profily zákazníků a závislosti**. Všechny procesy jsou automaticky znovu spuštěny. Pro účty a kontakty vyberte **Sjednotit účty** > **Sjednotit profily a závislosti**. Podmínky párování jsou spuštěny pro účty a kontakty, přičemž se aktualizují oba sjednocené profily a spustí všechny ostatní závislosti.

Všechny dlaždice kromě **Zdrojová pole** ukazují stav **Ve frontě** nebo **Aktualizuje se**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Výsledky úspěšného spuštění se zobrazí na stránce **Sjednocení** zobrazující počet sjednocených profilů.
