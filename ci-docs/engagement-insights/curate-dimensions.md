---
title: Použití demografických dimenzí k rozdělení údajů o chování (kurátorované dimenze)
description: Pomocí kurátorovaných dimenzí sjednoceného profilu povolíte vlastnosti profilu zákazníka přehledů cílových skupin.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a3d7f9276330a6daacbe9428d84a371b81bbefe
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466340"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Použití demografických dimenzí k rozdělení údajů o chování

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Pomocí demografických dimenzí jednotného profilu mají uživatelé přehledů zapojení přístup k vlastnostem profilu přehledů cílových skupin. Tyto vlastnosti pak můžete použít v interaktivních analýzách údajů o chování, včetně dat zachycených přehledy zapojení na vašem webu nebo mobilní aplikaci.

>[!NOTE]
> Přehledy zapojení zahrnují předem připravené vestavěné dimenze pro vlastnosti události. Další informace: [Zobrazení a vytváření dimenzí](dimensions.md)

## <a name="prerequisite"></a>Požadavek

- Prostředí přehledů zapojení, ve kterém máte data profilu zákazníků propojená s prostředím přehledů cílových skupin, kde jsou profily zákazníků vytvářeny. Více informací: [Vytvoření propojení mezi přehledy cílových skupin a přehledy zapojení](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Poté, co vytvoříte propojení mezi přehledy cílových skupin a přehledy zapojení můžete chtít pouze data specifická pro vlastnosti zákaznického profilu, což může být užitečné jako dimenze v přehledech zapojení. Pro další informace přejděte na část [Povolte atributy a segmenty sjednocených profilů přehledů cílových skupin](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Vytvoření nové vlastní sestavy

1. V levém podokně vyberte **Vlastní** > **Nová sestava** a poté vyberte požadovanou metriku. (Pro tento příklad jsme vybrali sestavu **Zobrazení stránky podle hodin**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Vyberte metriku.":::

2. V editoru vizualizace vyberte **Dimenze** a poté vyberte **Demografický** v rozevírací nabídce **Typ dimenze**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Vyberte demografický.":::

3. Vyberte dimenzi **Signal.Customer.*xxx***. (Tento příklad ukazuje Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Vybrat dimenzi.":::
  
## <a name="limitations"></a>Omezení

Momentálně můžete použít pouze demografické dimenze k rozdělení údajů o chování.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
