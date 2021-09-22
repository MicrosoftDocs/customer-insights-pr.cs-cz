---
title: Použití segmentů přehledů cílových skupin k filtrování sestav přehledů zapojení
description: Použijte segmenty přehledů cílových skupin v interaktivních analýzách údajů o chování zaznamenaných přehledy zapojení na webu zákazníka.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461050"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Použití segmentů přehledů cílových skupin k filtrování sestav přehledů zapojení

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

S přehledy zapojení můžete použít segmenty přehledů cílových skupin v interaktivních analýzách údajů o chování zaznamenaných přehledy zapojení na vašem webu.

## <a name="prerequisite"></a>Požadavek

- Prostředí přehledů zapojení, ve kterém máte data segmentů přehledů cílových skupin propojená s prostředím přehledů cílových skupin, kde jsou segmenty a profily zákazníků vytvářeny. Více informací: [Vytvoření propojení mezi přehledy cílových skupin a přehledy zapojení](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Vytvoření segmentů přehledů cílových skupin 

> [!IMPORTANT]
> Aby se segmenty přehledů cílových skupin zobrazovaly v přehledech zapojení, musíte nejprve[spustit slučovací a navazující procesy](../audience-insights/merge-entities.md). Následné procesy jsou důležité, protože generují jedinečnou tabulku, která připravuje segmenty přehledů cílových skupin ke sdílení s přehledy zapojení. (Pokud je naplánována aktualizace systému, bude automaticky zahrnovat navazující procesy.)

Segmenty přehledů cílových skupin můžete použít v přednastavených sestavách přehledů zapojení nebo ve vlastních sestavách, které jste vytvořili. Další informace najdete v části [Integrované sestavy profilu](profile-reports.md) a [Vytváření a úprava vlastních sestav](custom-reports.md).

**Použití segmentů přehledů cílových skupin v sestavách přehledů zapojení**

1. Zestránky **Pracovní prostor** vyberte **Data** a poté vyberte kartu **Segmenty**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Výběr karty Segmenty":::

   >[!NOTE]
   > Výběrem segmentu přehledů cílových skupin přejdete na přehledy cílových skupin, kde můžete zjistit, jak byl tento segment vytvořen z hlediska pravidel a logiky. Další informace o segmentech přehledů cílových skupin najdete v části [Zobrazení a vytvoření segmentů](../audience-insights/segments.md).

2. Vyberte integrovanou sestavu nebo [vytvořte vlastní sestavu](custom-reports.md) a poté vyberte **Přidat podmínku**. (Pro tento příklad jsme vybrali sestavu **Zobrazení stránky**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Přidat podmínku.":::

3. Vyberte **Filtrovat podle segmentu**, rozbalte seznam **Typ segmentu** a poté vyberte **Demografický**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Vyberte typ demografického segmentu.":::

4. Rozbalte seznam **Název segmentu** a poté vyberte segment přehledů cílových skupin.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Zvolte segment.":::

5. Můžete použít jeden nebo více segmentů, včetně behaviorálních (přehledy zapojení) a demografických (přehledy cílových skupin) segmentů. 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Sestava zobrazení stránek je omezena na zákazníky z USA a segmenty domovské stránky.":::

Na předchozím obrázku byly zvoleny segmenty **USA zákazníci** a **Domovská stránka** byly vybrány, což omezuje sestavu **Zobrazení stránky** na zobrazení pouze těcho dvou segmentů. 


>[!NOTE]
> Segmenty přehledů cílových skupin můžete použít k filtrování přednastavených sestav, vlastních sestav a trychtýřů v přehledech zapojení. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]