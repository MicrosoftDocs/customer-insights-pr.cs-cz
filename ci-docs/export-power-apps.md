---
title: Konektor Power Apps (preview)
description: Propojení aplikací Power Apps a Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196892"
---
# <a name="power-apps-connector-preview"></a>Konektor Power Apps (preview)

Přeneste sjednocené zákaznické profily do svých přizpůsobených aplikací pomocí Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Propojení aplikací Power Apps a Dynamics 365 Customer Insights

Customer Insights jsou jedním z mnoha [dostupných zdrojů dat v Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

V dokumentaci Power Apps najdete, jak [přidat datové připojení k aplikaci](/powerapps/maker/canvas-apps/add-data-connection). Doporučujeme také zkontrolovat, [jak Power Apps používá delegování ke zpracování velkých datových sad v aplikacích plátna](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostupné entity

Po přidání Customer Insights jako datového připojení si můžete v systému vybrat následující entity v Power Apps:

- **Zákazník**: chcete-li použít data z [jednotného profilu zákazníka](customer-profiles.md).
- **UnifiedActivity**: k zobrazení [časové osy aktivity](activities.md) v aplikaci.
- **ContactProfile**: k zobrazení kontaktů zákazníka. Tato entita je k dispozici pouze v prostředích Customer Insights pro obchodní účty.

## <a name="limitations"></a>Omezení

### <a name="retrievable-entities"></a>Vyhledatelné entity

Můžete načíst pouze entity **Customer**, **UnifiedActivity**, **Segments** a **ContactProfile** prostřednictvím konektoru Power Apps. Entita ContactProfile je k dispozici pouze v prostředích Customer Insights pro obchodní účty. Jsou zobrazeny další entity, protože podkladový konektor je podporuje prostřednictvím spouštěčů v Power Automate.

Za 60 sekund můžete uskutečnit maximálně 100 hovorů. Pomocí parametru $skip můžete volat API koncový bod vícekrát. [Další informace o parametru $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegování

Delegování funguje pro entitu **Customer** a **UnifiedActivity** .

- Delegace pro entitu **Zákazník**: Chcete-li použít delegování pro tuto entitu, je třeba indexovat pole v části [Index hledání a filtrování](search-filter-index.md).  
- Delegace pro **UnifiedActivity**: Delegace pro tuto entitu funguje pouze pro pole **ActivityId** a **CustomerId**.  
- Delegování pro **ContactProfile**: Delegování pro tuto entitu funguje pouze pro pole **ContactId** a **CustomerId**. Entita ContactProfile je k dispozici pouze v prostředích Customer Insights pro obchodní účty.

Další informace o delegování najdete v [delegovatelných funkcích a operacích Power Apps](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Příklad ovládání galerie

Volitelně můžete přidat zákaznické profily do [ovládacího prvku galerie](/powerapps/maker/canvas-apps/add-gallery).

1. Přidejte ovládací prvek **Galerie** do aplikace, kterou vytváříte.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Přidat prvek galerie.":::

1. Vyberte **Zákazník** jako zdroj dat pro položky.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Vyberte zdroj dat.":::

1. Panel dat změníte vpravo a vybrat pole pro entitu Zákazník, které se má zobrazit v galerii.

1. Chcete-li zobrazit libovolné pole od vybraného zákazníka v galerii, vyplňte vlastnost **Text** popisku pomocí **{Name_of_the_gallery}.Selected.{property_name}**  
    - Příklad: _Gallery1.Selected.address1_city_

1. Chcete-li zobrazit jednotnou časovou osu pro zákazníka, přidejte element Galerie a přidejte vlastnost **Items** pomocí **Filtr('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Příklad: _Filtr('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
