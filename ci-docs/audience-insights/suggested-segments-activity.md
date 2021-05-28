---
title: Navrhované segmenty na základě aktivity.
description: Nechte strojové učení, aby vám našlo nové a zajímavé segmenty založené na aktivitě zákazníků.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034059"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Navrhované segmenty na základě dat aktivity (náhled)

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
Pokud podnikáte ve zdravotnictví a poskytujete veřejnou zdravotní péči, je vaším cílem minimalizovat výdaje jednotlivých pacientů. Způsobem, jak toho dosáhnout, může být snížení opakujících se návštěv poskytováním nejlepší možné péče při co nejmenším počtu návštěv. V tomto případě je vaším cílem udržet nízkou frekvenci návštěv a minimalizovat opakující se náklady pro pacienty. Nebo můžete identifikovat segmenty pacientů, kteří mají časté schůzky a vysoké opakující se náklady, a analyzovat tyto případy s cílem zlepšit léčbu jednotlivce. 

## <a name="required-data"></a>Požadovaná data

Návrhy se generují na základě vybraných vstupních údajů. 

- Profily zákazníků: Všichni zákazníci nebo členové konkrétního segmentu. 

- Časové období: minulý měsíc, minulý rok nebo jakýkoli vlastní časový rámec.

- Typ aktivity: nákupy, maloobchodní transakce, online transakce, případy zákaznické podpory, předplatné atd.  

- Entita v Customer Insights, která obsahuje data aktivity: entita UnifiedActivity nebo entita pro konkrétní aktivitu. 

- Zahrnuté dimenze: Aktuálnost, frekvence nebo peněžní dimenze, v závislosti na vašich obchodních požadavcích.

## <a name="generate-suggested-segments"></a>Generování doporučovaných segmentů

1. Jděte na **Segmenty**.

1. Vyberte kartu **Návrhy (preview)**.

1. Vyberte **Najít nové návrhy** a vyberte **Zobrazit nebo očekávat chování zákazníků**. Vyberte **Start** ke spuštění řízeného prostředí.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="První krok průvodce konfigurací pro navrhovaný segment na základě aktivity.":::

1. Zadejte požadovaná vstupní data a pokračujte výběrem **Další**.

   - Vyberte zákazníky: Zahrňte všechny zákazníky nebo konkrétní segment.
   - Zvolte aktivitu: Vyberte typ aktivity a entity popisující aktivitu.
   - Předvolby: Nastavte časové období, které je třeba vzít v úvahu, faktory pro návrhy a mapujte atributy.

1. Zkontrolujte svůj vstup a vyberte **Spustit** ke spuštění modelu a generování návrhů.

1. V závislosti na počtu profilů zákazníků a vybraných aktivit může dokončení trvat několik minut. 

Po vygenerování návrhů je můžete filtrovat podle dimenze nebo hodnoty, která vás nejvíce zajímá. 

## <a name="view-details-of-a-suggested-segment"></a>Zobrazení podrobností navrhovaného segmentu

Jakmile jsou návrhy vygenerovány, najdete je v seznamu **Segmenty** > **Návrhy (náhled)** v sekci **Návrhy založené na aktivitě**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Rozšířený boční panel zobrazující podrobná data navrhovaného segmentu.":::

Vyberte **Zobrazit návrh** v navrhovaném segmentu pro zobrazení podrobností o tomto segmentu. Postranní panel poskytuje podrobnosti, jako je rozsah každé dimenze ve srovnání s cílovou skupinou. Rovněž zdůrazňuje počet potenciálních prvků v segmentu a odpovídající procento z celkového počtu zákazníků. Pokud si chcete ponechat návrh jako segment, vyberte **Vytvořit segment**.    

## <a name="save-a-suggestion-as-a-segment"></a>Uložení návrhu jako segmentu

1. Jděte na **Segmenty** > **Návrhy (Preview)**.

1. Vyberte segment, který chcete uložit. 

1. V postranním panelu vyberte **Vytvořit segment**. 

1. Po uložení segmentu se zobrazí v seznamu segmentů na kartě **Všechny segmenty**. Nyní to může být [obnoveno nebo odstraněno jako jakýkoli jiný segment](segments.md). Nelze upravit podrobnosti segmentu. Můžete však změnit vstupní kritéria pro návrhy a generovat různé návrhy.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Aktualizace nebo úprava sadu návrhů

1. Jděte na **Segmenty** > **Návrhy (náhled)** a vyhledejte segment v části **Návrhy na základě aktivity**.

1. Volbou **Aktualizovat návrhy** aktualizujete návrhy při zachování konfigurovaných atributů. Nebo vyberte **Upravit návrhy** pro úpravu nakonfigurovaných atributů. Systém proces znovu spustí, vygeneruje návrhy segmentů na základě nejnovějších dat a nahradí aktuální návrhy.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
