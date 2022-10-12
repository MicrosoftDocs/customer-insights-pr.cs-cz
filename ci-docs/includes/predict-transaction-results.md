---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611096"
---
- **Výkon trénovacího modelu**: Známky A, B a C označují výkon predikce a mohou vám pomoci při rozhodování o použití výsledků uložených ve výstupní entitě.

  Známky se určují na základě následujících pravidel:
  - **A**, když model přesně predikoval alespoň 50 % celkových predikcí a když procento přesných predikcí ohledně zákazníků, kteří odešli, je větší než základní poměr alespoň o 10 %.
  - **B**, když model přesně predikoval alespoň 50 % celkových predikcí a když procento přesných predikcí ohledně zákazníků, kteří odešli, je větší než základní poměr alespoň do 10 %.
  - **C**, když model přesně predikoval méně než 50 % celkových predikcí nebo když procento přesných predikcí ohledně zákazníků, kteří odešli, je menší než základní poměr.
  - **Základní poměr** vezme vstupní časový interval predikce pro daný model (například jeden rok) a vytváří různé zlomky času dělením číslem 2, dokud nedosáhne jednoho měsíce nebo méně. Tyto zlomky používá k vytvoření obchodního pravidla pro zákazníky, kteří si v tomto časovém rámci nic nekoupili. Tito zákazníci jsou považováni za ztracené. Jako základní model je vybráno obchodní pravidlo založené na čase s nejvyšší schopností predikovat, kdo bude pravděpodobně ztracen.

- **Pravděpodobnost odchodu (počet zákazníků)**: Skupiny zákazníků na základě jejich predikovaného rizika odchodu. Volitelně [můžete vytvářet segmenty zákazníků](../prediction-based-segment.md) s vysokým rizikem odchodu. Takové segmenty pomáhají pochopit, kde by se pro členství v segmentech mělo nacházet vyřazení.

- **Nejvlivnější faktory**: Při vytváření predikce se bere v úvahu mnoho faktorů. Každý z faktorů má svou důležitost vypočítanou pro agregované predikce, které model vytváří. Tyto faktory použijte k ověření výsledků predikce. Nebo tyto informace použijte později při [vytváření segmentů](../prediction-based-segment.md), které mohou pomoci ovlivnit riziko odchodů zákazníků.