---
title: Sdílené úkoly pro scénáře predikcí
description: Naučte se spravovat a vylepšovat předpovědi a odstraňovat problémy s nimi.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: eaccf23a81ca4de19763b761cc5a27c14515fe522ee36dc78f294208b681966e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036457"
---
# <a name="manage-predictions"></a>Správa predikcí

Tento článek probírá některé úkoly, které sdílí většina scénářů predikcí.

## <a name="troubleshoot-a-failed-prediction"></a>Řešení potíží se selháním predikce

1. Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**.

1. Vyberte svislé tři tečky vedle predikce, u které chcete zobrazit protokoly chyb.

1. Vyberte **Protokoly**.

1. Zkontrolujte všechny chyby. Existuje několik typů chyb, které mohou nastat a které popisují, jaký stav chybu způsobil. Například chyba, že není k dispozici dostatek dat, aby bylo možné provést přesnou predikci, se obvykle vyřeší načtením dalších dat do Customer Insights.

## <a name="input-data-usability-report"></a>Sestava použitelnosti vstupních dat

Sestava použitelnosti vstupních dat poskytuje konsolidovaný pohled na chyby a varování, které mohou generovat vaše předdefinované predikce. Poskytuje také doporučení, jak zlepšit výkon modelu.

Sestava je k dispozici poté, co model dokončí tréninkový proces. Je vytvořena pro každý model samostatně, bez ohledu na to, zda byl úspěšně dokončen nebo ne.

### <a name="view-the-input-data-usability-report"></a>Zobrazení sestavy použitelnosti vstupních dat

Poté, co předpřipravený model dokončí svůj tréninkový krok, zobrazte sestavu:
- Vyberte tři tečky vedle názvu modelu a zvolte možnost **Sestava použitelnosti vstupních dat**.
- Vyberte stav modelu a vyberte položku **Zobrazit sestavu použitelnosti vstupních dat** v bočním podokně.
- Vyberte jeden z modelů v seznamu a na panelu příkazů vyberte **Sestava použitelnosti vstupních dat**.
- Otevřete stránku výsledků modelu a na panelu příkazů vyberte **Sestava použitelnosti vstupních dat**.

### <a name="information-in-the-input-data-usability-report"></a>Informace v sestavě použitelnosti vstupních dat

Následující sloupce v sestavě obsahují užitečné informace ke zlepšení dat pro model.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Příklad sestavy použitelnosti vstupních dat zobrazující tabulku s chybami, varováními a doporučeními.":::

- Název: Popisný název chyby, varování nebo doporučení.
- Krok: Fáze, školení nebo skóre modelu, které se informace týká.
- Stav: Závažnost informací (chyba, varování, doporučení).
- Název sloupce: Sloupec v entitě, který je třeba upravit, aby se zlepšil výkon modelu.
- Název entity: Název entity, kterou je třeba upravit, aby se zlepšil výkon modelu.
- Podrobnosti: Podrobnosti o chybě, varování nebo doporučení.

## <a name="refresh-a-prediction"></a>Aktualizace předpovědi

Předpovědi se automaticky aktualizují podle stejného [plánu aktualizace dat](system.md#schedule-tab), jaký je konfigurován v nastavení. Můžete je také aktualizovat ručně.

1. Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**.

1. Vyberte svislé tři tečky vedle predikce, kterou chcete aktualizovat.

1. Vyberte **Aktualizovat**.

## <a name="delete-a-prediction"></a>Odstranění predikce

Odstraněním predikce odstraníte také jeho výstupní entitu.

1. Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**.

1. Vyberte svislé tři tečky vedle predikce, kterou chcete odstranit.

1. Vyberte **Odstranit**.
