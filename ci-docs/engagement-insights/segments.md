---
title: Zobrazení a vytvoření segmentů
description: Jak vytvářet, upravovat a odstraňovat segmenty a kde je použít.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036140"
---
# <a name="view-and-create-segments"></a>Zobrazení a vytvoření segmentů

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmenty umožňují identifikovat podmnožiny návštěvníků na základě charakteristik nebo interakcí s webem. Segmenty umožňují použít filtry a analyzovat tyto podmnožiny. Analýza může pomoci prozkoumat trendy ve vašem podnikání a reagovat na ně. 

:::image type="content" source="media/segments-page.png" alt-text="Snímek aplikace přehledů zapojení zobrazující seznam existujících segmentů v pracovním prostoru.":::

## <a name="view-segments"></a>Zobrazení segmentů

1. V levém navigačním podokně přejděte na **Data**. 

1. Po výběru karty **Segmenty** se zobrazí seznam všech segmentů v pracovním prostoru. 

## <a name="create-a-segment"></a>Vytvořit segment

Segmenty se skládají z pravidel a podmínek, které jsou propojeny logickými operátory. Podmínky aplikují filtry na vybranou dimenzi. Každý segment může používat až pět dimenzí.

Následující příklad ukazuje segment se dvěma podmínkami v jednom pravidle. Filtruje všechny události webu, kde se vyskytuje prohlížeč Chrome a operační systémy jsou iOS nebo Android.

:::image type="content" source="media/segment-sample.png" alt-text="Příklad segmentů se dvěma podmínkami v pravidle pro filtrování událostí webu.":::

Tato část popisuje, jak vytvořit *prázdný segment*.

1. Přejděte na nabídku **Data** > **Segmenty**.

1. Vyberte **Nový segment**.

1. V **Knihovně zdrojů** vyberte atribut, podle kterého chcete filtrovat. V současné době můžete vytvářet pouze segmenty na základě dimenzí.

1. Zvolte operátor a hodnotu vybraného atributu. Použít můžete následující operace:
   - **je**: vyžaduje přesnou shodu pro zahrnutí hodnot. Používá operátor **rovná se** pro jednu hodnotu nebo **jakýkoliv z** pro zahrnutí více hodnot.
   - **není**: vyžaduje přesnou shodu pro vyloučení hodnot. Používá operátor **rovná se** pro jednu hodnotu nebo **jakýkoliv z** pro zahrnutí více hodnot.
   - **začíná na**: řetězec, kterým začínají odpovídající hodnoty.
   - **končí na**: řetězec, kterým končí odpovídající hodnoty.
   - **obsahuje**: řetězec obsažený v odpovídajících hodnotách.

1. Chcete-li do skupiny přidat další podmínky, můžete použít dva logické operátory. Při použití operátorů sady jsou zohledněny projektované atributy.
   - Operátor **AND**: Obě podmínky musí být splněny v rámci procesu segmentace. Tato možnost je nejužitečnější při definování podmínek mezi různými entitami.
   - Operátor **OR**: Buď je třeba splnit jednu z podmínek v rámci procesu segmentace. Tato možnost je nejužitečnější při definování více podmínek pro stejnou entitu.

1. Vyberte **Uložit** a pojmenujte segment. 

Segment bude uveden na stránce Segmenty a můžete jej použít na všechny sestavy a trychtýře v pracovním prostoru.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Použití segmentu v sestavě nebo trychtýři

Segmenty můžete použít na přehled nebo trychtýř a filtrovat je podle podmínek v segmentu. V sestavě využití v reálném čase však nelze segmenty použít.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Sestava zobrazení stránky s rozbaleným rozevíracím seznamem pro výběr, které segmenty se mají použít.":::

Chcete-li použít segment, otevřete sestavu nebo trychtýř. Vyberte **Přidat podmínku** a poté **Filtrovat podle segmentu**. V seznamu vyberte segment, který chcete použít. Segment bude použit na sestavu. Pokud graf nepodporuje segment, zobrazí chybu.
 
Na sestavu nebo trychtýř můžete použít *až tři segmenty*.

## <a name="edit-a-segment"></a>Úprava segmentu

1. Přejděte na nabídku **Data** > **Segmenty**.
1. Výběrem segmentu v seznamu ho otevřete. 
1. Podle potřeby měňte nebo přidávejte hodnoty.
1. Výběrem možnosti **Uložit** se vaše změny uplatní.

## <a name="change-the-name-of-a-segment"></a>Změna názvu segmentu

1. Přejděte na nabídku **Data** > **Segmenty**.
1. V seznamu segmentů vyberte **Další [...]**. 
1. Z rozevíracího seznamu vyberte **Upravit jméno**.
1. Zadejte nový název a vyberte **Přejmenovat**.

## <a name="delete-a-segment"></a>Odstranění segmentu

1. Přejděte na nabídku **Data** > **Segmenty**.
1. V seznamu segmentů vyberte **Další [...]**. 
1. Z rozevíracího seznamu vyberte **Odstranit**.
1. Výběrem možnosti **Odstranit** potvrdíte akci.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
