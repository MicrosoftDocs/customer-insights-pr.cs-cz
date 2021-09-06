---
title: Konektor pro Power Apps
description: Propojení aplikací Power Apps a Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031741"
---
# <a name="microsoft-power-apps-connector-preview"></a>Konektor Microsoft Power Apps (preview)

Přeneste sjednocené zákaznické profily do svých přizpůsobených aplikací pomocí Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Propojení aplikací Power Apps a Dynamics 365 Customer Insights

Customer Insights jsou jedním z mnoha [dostupných zdrojů dat v Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

V dokumentaci Power Apps najdete, jak [přidat datové připojení k aplikaci](/powerapps/maker/canvas-apps/add-data-connection). Doporučujeme také zkontrolovat, [jak Power Apps používá delegování ke zpracování velkých datových sad v aplikacích plátna](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostupné entity

Po přidání Customer Insights jako datového připojení si můžete v systému vybrat následující entity v Power Apps:

- Zákazník: chcete-li použít data z [jednotného profilu zákazníka](customer-profiles.md).
- UnifiedActivity: zobrazení [časové osy aktivity](activities.md) v aplikaci.

## <a name="limitations"></a>Omezení

### <a name="retrievable-entities"></a>Vyhledatelné entity

Načíst můžete pouze entity **Zákazník**, **UnifiedActivity** a **Segmenty** prostřednictvím konektoru Power Apps. Jsou zobrazeny další entity, protože podkladový konektor je podporuje prostřednictvím spouštěčů v Power Automate.  

### <a name="delegation"></a>Delegování

Delegování funguje pro entitu zákazníka a entitu UnifiedActivity. 

- Delegace pro entitu **Zákazník**: Chcete-li použít delegování pro tuto entitu, je třeba indexovat pole v části [Index hledání a filtrování](search-filter-index.md).  

- Delegace pro **UnifiedActivity**: Delegace pro tuto entitu funguje pouze pro pole **ActivityId** a **CustomerId**.  

- Další informace o delegování viz [Delegovatelné funkce a operace Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Příklad ovládání galerie

Například přidáte profily zákazníků do [ovládacího prvku galerie](/powerapps/maker/canvas-apps/add-gallery).

1. Přidat ovládací prvek **Galerie** do aplikace, kterou stavíte.

> [!div class="mx-imgBorder"]
> ![Přidat prvek galerie.](media/connector-powerapps9.png "Přidat prvek galerie")

1. Vyberte **Zákazník** jako zdroj dat pro položky.

    > [!div class="mx-imgBorder"]
    > ![Vyberte zdroj dat.](media/choose-datasource-powerapps.png "Vybrat zdroj dat")

1. Panel dat můžete změnit vpravo a vybrat pole pro entitu Zákazník, které se má zobrazit v galerii.

1. Chcete-li zobrazit libovolné pole od vybraného zákazníka v galerii, vyplňte vlastnost Text popisku: **{Name_of_the_gallery}.Vybrané.{property_name}**

    Příklad: Gallery1.Selected.address1_city

1. Chcete-li zobrazit jednotnou časovou osu pro zákazníka, přidejte element Galerie a přidejte vlastnost Položky: **Filtr('SjednocenáAktivita', CustomerId = {Customer_Id})**

    Příklad: Filtr('SjednocenáAktivita', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]