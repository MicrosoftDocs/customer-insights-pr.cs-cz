---
title: Navrhované segmenty na základě aktivity (náhled)
description: Nechte strojové učení, aby vám našlo nové a zajímavé segmenty založené na aktivitě zákazníků.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170581"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Navrhované segmenty na základě aktivity (náhled)

Objevte zajímavé segmenty svých zákazníků na základě údajů o aktivitě zákazníků, které jsou předány do Customer Insights. Příkladem údajů o aktivitě jsou transakce, doba trvání podpory hovoru, nákupy nebo vrácení. Chcete-li navrhnout segmenty, data aktivity se analyzují z hlediska aktuálnosti, frekvence a peněžní hodnoty (nebo trvání). Případně můžete generovat [navrhované segmenty ke zlepšení míry nebo lepšímu pochopení toho, co ovlivňuje atribut](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Karta Navrhované segmenty zobrazující návrhy segmentů pro segmenty založené na aktivitě a atributech.":::

## <a name="categorize-customers-by-activity"></a>Kategorizace zákazníků podle aktivity

S volbou [údaje o aktivitě](activities.md) dostupnou v Customer Insights můžeme generovat návrhy, které představují skupiny zákazníků:

- většina aktivních zákazníků 
- zákazníci, kteří uskutečnili nejvíce nákupů 
- zákazníci, kteří generovali největší tržby 
- zákazníci, kteří v poslední době nebyli aktivní 
- zákazníci, kteří často komunikují s vaší firmou  

Pokud podnikáte v maloobchodě, můžete zjistit, kteří zákazníci generují největší tržby, a odměnit je kupónem. Nebo můžete identifikovat příležitostné zákazníky a nabídnout jim, aby se připojili k programu odměn, aby vaši firmu navštěvovali častěji.
Pokud poskytujete veřejnou zdravotní péči a vaším cílem je minimalizovat náklady na jednotlivé pacienty, můžete se pokusit omezit opakované návštěvy tím, že poskytnete nejlepší možnou péči při co nejmenším počtu návštěv. V tomto případě je vaším cílem udržet nízkou frekvenci návštěv a minimalizovat opakující se náklady pro pacienty. Nebo můžete identifikovat segmenty pacientů, kteří mají časté schůzky a vysoké opakující se náklady, a analyzovat tyto případy s cílem zlepšit léčbu jednotlivce.

## <a name="required-data"></a>Požadovaná data

Návrhy se generují na základě vybraných vstupních údajů.

- Profily zákazníků: Všichni zákazníci nebo členové konkrétního segmentu.

- Časové období: minulý měsíc, minulý rok nebo jakýkoli vlastní časový rámec.

- Typ aktivity: nákupy, maloobchodní transakce, online transakce, případy zákaznické podpory, předplatné atd.  

- Entita v Customer Insights, která obsahuje data aktivity: entita UnifiedActivity nebo entita pro konkrétní aktivitu.

- Zahrnuté dimenze: Aktuálnost, frekvence nebo peněžní dimenze, v závislosti na vašich obchodních požadavcích.

## <a name="generate-suggested-segments"></a>Generování doporučovaných segmentů

1. Přejděte na **Segmenty** a vyberte kartu **Návrhy (Preview)**.

1. Vyberte **Najít nové návrhy** a vyberte **Zobrazit nebo očekávat chování zákazníků**. Vyberte **Spustit**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="První krok průvodce konfigurací pro navrhovaný segment na základě aktivity.":::

1. Zadejte požadovaná vstupní data a vyberte **Další**.

   - Vyberte zákazníky: Zahrňte všechny zákazníky nebo konkrétní segment.
   - Zvolte aktivitu: Vyberte typ aktivity a entity popisující aktivitu.
   - Předvolby: Nastavte časové období, které je třeba vzít v úvahu, faktory pro návrhy a mapujte atributy.

1. Zkontrolujte svůj vstup a vyberte **Spustit** ke spuštění modelu a generování návrhů.

V závislosti na počtu profilů zákazníků a vybraných aktivit může dokončení trvat několik minut.

Po vygenerování návrhů je můžete filtrovat podle dimenze nebo hodnoty, která vás nejvíce zajímá.

## <a name="manage-suggested-segments"></a>Správa doporučovaných segmentů

Jděte do sekce **Segmenty** a vyberte katu **Návrhy (Preview)**. V sekci **Návrhy segmentů založené na aktivitách** vyberte navrhovaný segment pro zobrazení dostupných akcí.

- Volbou **Zobrazit návrh** zobrazíte podrobnosti daného segmentu, jako je rozsah každé dimenze ve srovnání s cílovou skupinou. Rovněž zdůrazňuje počet potenciálních prvků v segmentu a odpovídající procento z celkového počtu zákazníků.
- Volbou **Vytvořit segment** uložíte návrh jako segment. Zobrazí se na kartě **Všechny segmenty** a může být [aktualizován nebo odstraněn](segments.md). Nelze upravit podrobnosti segmentu. Můžete však změnit vstupní kritéria pro návrhy a generovat různé návrhy.
- Volbou **Upravit návrhy** upravíte nakonfigurované atributy, které nahradí aktuální návrhy.
- Volbou **Aktualizovat návrhy** aktualizujete návrhy při zachování konfigurovaných atributů.

[!INCLUDE [footer-include](includes/footer-banner.md)]
