---
title: Vytvoření jednoduchých segmentů s rychlými segmenty
description: Vytvořte jednoduché segmenty zákazníků a seskupte je podle různých atributů.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171128"
---
# <a name="create-simple-segments-with-quick-segments"></a>Vytvoření jednoduchých segmentů s rychlými segmenty

Rychlé segmenty umožňují rychle vytvářet jednoduché segmenty jediným operátorem a získat tak rychlejší přehledy. Rychlé segmenty jsou podporovány pouze v prostředích pro **jednotlivé zákazníky**.

## <a name="create-a-new-segment-with-quick-segments"></a>Vytvoření nového segmentu s rychlými segmenty

1. Jděte na **Segmenty**.

1. Vyberte **Nový** > **Vytvořit z**.
   - Vyberte možnost **Profiley**, chcete-li vytvořit segment založený na entitě *sjednocený zákazník*.
   - Vyberte možnost **Míry**, pokud chcete vytvořit segment kolem měr, které jste dříve vytvořili.
   - Vyberte možnost **Analytické nástroje**, chcete-li sestavit segment kolem jedné z výstupních entit, které jste vygenerovali pomocí funkcí **Predikce** nebo **Vlastní modely**.

1. V dialogovém okně **Nový rychlý segment** vyberte atribut z rozbalovací nabídky **Pole**. Na základě vašeho výběru systém poskytuje různé hodnoty.
   - Pro kategorická pole se zobrazí 10 nejlepších zákazníků. Vyberte **Hodnotu** a zvolte **Hodnotit**.
   - U číselného atributu systém zobrazí, jaká hodnota atributu spadá pod percentil každého zákazníka. Zvolte **Operátor** a **Hodnotu** a pak vyberte **Zkontrolovat**.

1. Systém poskytne **Odhadovanou velikost segmentu**. Zvolte, zda chcete vygenerovat segment, který jste definovali, nebo jděte zpět a zvolte jiné pole.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Název a odhad pro rychlý segment.":::

1. Pro segment zadejte **Název** a **Název výstupní entity**. Volitelně přidejte [značky](work-with-tags-columns.md#manage-tags).

1. Výběrem možnosti **Uložit** vytvořte segment. Zobrazí se stránka **Segmenty**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Další kroky

[Exportujte segment](export-destinations.md) a prozkoumejte [integraci karty zákazníka](customer-card-add-in.md) pro použití segmentů v jiných aplikacích.

[!INCLUDE [footer-include](includes/footer-banner.md)]
