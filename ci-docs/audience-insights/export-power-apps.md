---
title: Konektor pro Power Apps
description: Propojení aplikací Power Apps a Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 985e6c85795fba8ca3063cdffc7f9012e798856a
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623215"
---
# <a name="microsoft-power-apps-connector-preview"></a>Konektor Microsoft Power Apps (preview)

Přeneste sjednocené zákaznické profily do svých přizpůsobených aplikací pomocí Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Propojení aplikací Power Apps a Dynamics 365 Customer Insights

Customer Insights jsou jedním z mnoha [dostupných zdrojů dat v Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

V dokumentaci Power Apps najdete, jak [přidat datové připojení k aplikaci](/powerapps/maker/canvas-apps/add-data-connection). Doporučujeme také zkontrolovat, [jak Power Apps používá delegování ke zpracování velkých datových sad v aplikacích plátna](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Dostupné entity

Po přidání Customer Insights jako datového připojení si můžete v systému vybrat následující entity v Power Apps:

- **Zákazník**: chcete-li použít data z [jednotného profilu zákazníka](customer-profiles.md).
- **UnifiedActivity**: k zobrazení [časové osy aktivity](activities.md) v aplikaci.
- **ContactProfile**: k zobrazení kontaktů zákazníka. Tato entita je k dispozici pouze v prostředích přehledů cílových skupin pro obchodní účty.

## <a name="limitations"></a>Omezení

### <a name="retrievable-entities"></a>Vyhledatelné entity

Můžete načíst pouze entity **Customer**, **UnifiedActivity**, **Segments** a **ContactProfile** prostřednictvím konektoru Power Apps. Entita ContactProfile je k dispozici pouze v instanci přehledů cílových skupin pro obchodní účty. Jsou zobrazeny další entity, protože podkladový konektor je podporuje prostřednictvím spouštěčů v Power Automate.

### <a name="delegation"></a>Delegování

Delegování funguje pro entitu **Customer** a **UnifiedActivity** . 

- Delegace pro entitu **Zákazník**: Chcete-li použít delegování pro tuto entitu, je třeba indexovat pole v části [Index hledání a filtrování](search-filter-index.md).  
- Delegace pro **UnifiedActivity**: Delegace pro tuto entitu funguje pouze pro pole **ActivityId** a **CustomerId**.  
- Delegování pro **ContactProfile**: Delegování pro tuto entitu funguje pouze pro pole **ContactId** a **CustomerId**. Entita ContactProfile je k dispozici pouze v prostředích přehledů cílových skupin pro obchodní účty.

Další informace o delegování najdete v [delegovatelných funkcích a operacích Power Apps](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Příklad ovládání galerie

Profily zákazníků můžete přidat do souboru [ovládacího prvku galerie](/powerapps/maker/canvas-apps/add-gallery).

1. Přidejte ovládací prvek **Galerie** do aplikace, kterou vytváříte.

    > [!div class="mx-imgBorder"]
    > ![Přidat prvek galerie.](media/connector-powerapps9.png "Přidejte prvek galerie.")

2. Vyberte **Zákazník** jako zdroj dat pro položky.

    > [!div class="mx-imgBorder"]
    > ![Vyberte zdroj dat.](media/choose-datasource-powerapps.png "Vyberte zdroj dat.")

3. Panel dat můžete změnit vpravo a vybrat pole pro entitu Zákazník, které se má zobrazit v galerii.

4. Chcete-li zobrazit libovolné pole od vybraného zákazníka v galerii, vyplňte vlastnost **Text** popisku pomocí **{Name_of_the_gallery}.Selected.{property_name}**  
    - Příklad: _Gallery1.Selected.address1_city_

5. Chcete-li zobrazit jednotnou časovou osu pro zákazníka, přidejte element Galerie a přidejte vlastnost **Items** pomocí **Filtr('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Příklad: _Filtr('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
