---
title: O vlastních sestavách
description: Zjistěte, jak vytvářet vlastní sestavy.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: e8cdfc07b67b78febc1d50b3b1fd44ab94448e64
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232140"
---
# <a name="create-and-edit-custom-reports"></a>Vytváření a úprava vlastních sestav

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Kromě předdefinovaných sestav (OOB) můžete vytvořit vlastní sestavu s vizualizacemi grafů a tabulek, které vám pomohou porozumět chování uživatelů. Tento článek vysvětluje, jak vytvořit sestavu s daty, která potřebujete, pomocí vizualizací tabulek a grafů. Informace o sestavách OOB viz [Zobrazení sestav](view-reports.md).

## <a name="create-a-custom-report"></a>Vytvoření vlastní sestavy

1. Přejděte na **Analyzovat** > **Vlastní** pro přístup k vlastnímu seznamu zpráv.

1. Vyberte **Nová zpráva** k zahájení vytváření vlastní sestavy.

   :::image type="content" source="media/new-custom-report.png" alt-text="Nové vlastní sestavy.":::

1. Určete typ sestavy, kterou chcete vytvořit:

    - Vyberte **Přidat vizuální** na panelu příkazů k vytvoření výchozí vizualizace tabulky.
    - Nebo vyberte vizualizaci sloupce, lišty, čáry, plochu, koláče, kruhu nebo tabulky z podokna **Editor sestav**.

1. V části **Data** podokna **Editor vizualizace** yberte jednu z dostupných možností (například zobrazení stránky) z rozevíracího seznamu **Metriky**. Můžete také přidat **Dimenze** (například země) k zobrazení ve vizualizaci. Další informace viz [Zobrazení a vytvoření metrik](metrics.md) a [Zobrazení a vytvoření dimenzí](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Výběr metriky pro sestavu":::

1. Vybert část **Design** podokna **Editor vizualizace** pro přidání **textu nadpisu** a přepněte **Titul** na zapnutí a vypnutí.  Typ vizualizace můžete také změnit výběrem jiného grafu, jako je **výsečový graf**.

1. Chcete -li změnit velikost a polohu vizualizace:
   - Vyberte vizualizaci a poté přetažením jednoho z rohů nebo ohraničení upravte její velikost.
   - Vyberte vizualizaci a přesuňte ji na novou pozici. Pozici můžete změnit také pomocí kláves se šipkami.
1. Chcete-li přidat jinou vizualizaci vyberte **Přidat vizualizací** na panelu příkazů.
1. Po přidání požadovaných vizualizací pro sestavu vyberte **Uložit** na panelu příkazů.

1. Zadejte název vlastní sestavy a vyberte **Uložit** k jejímu vytvoření.
 
## <a name="filter-a-custom-report"></a>Filtrování vlastní sestavy

Chcete -li se zaměřit na hodnotu nebo časové období, můžete vybrat časový rámec nebo časové období ve vlastní sestavě.

Chcete-li vybrat časový rámec, v pravém horním rohu zobrazení sestavy vyberte hodnotu z rozevíracího seznamu sestavy. Můžete si také vybrat *pevný rozsah dat*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtrovat podle času nebo období":::

U většiny sestav vyberte **+ Přidat podmínku** pro výběr dimenze nebo segmentu k filtrování sestavy. Další informace najdete v tématu [Zobrazení a vytvoření segmentů](segments.md).

## <a name="edit-a-custom-report"></a>Úprava výchozí sestavy

1. Přejděte na **Analyzovat** > **Vlastní** pro přístup k vlastnímu seznamu zpráv.

1. V seznamu vlastních sestav vyberte **Více [...]** 

1. Vyberte **Upravit název** pro změnu názvu sestavy.

1. Vyberte název sestavy a použijte možnosti **+ Přidat vizualizaci** a **Upravit** pro přidání, odebrání, přemístění nebo změně velikosti vizualizací.

1. Chcete -li změnit vlastnosti vizualizace, vyberte vizuál, vyberte **...** a pak **Upravit vizuál**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Úpravy vlastností grafu pro vlastní sestavy.":::

1. Po úpravě sestavy použijte změny výběrem možnosti **Uložit**. 

## <a name="delete-a-custom-report"></a>Odstranění vlastní sestavy

1. Přejděte na **Analyzovat** > **Vlastní** pro přístup k vlastnímu seznamu zpráv.

1. V seznamu vlastních sestav vyberte **...**

1. Vyberte **Odstranit** k odstranění sestavy.

1. Chcete-li sestavu trvale odstranit, potvrďte odstranění.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
