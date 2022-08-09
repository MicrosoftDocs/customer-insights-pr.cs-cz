---
title: Konektor Power Automate (preview) | Microsoft Docs
description: Vytváření toků v Microsoft Power Automate z Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196110"
---
# <a name="power-automate-connector-preview"></a>Konektor Power Automate (preview)

Služba Power Automate podporuje automatické spouštění vybraných událostí při změně dat nebo přímou správu složitějších toků v [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Známá omezení

- Maximálně 100 hovorů za 60 sekund. Pomocí [parametru $skip](/connectors/customerinsights/#get-items-from-an-entity) můžete volat koncový bod rozhraní API vícekrát.

## <a name="power-automate-triggers"></a>Triggery Power Automate

Pomocí triggerů můžete vytvářet cloudové toky a automatizovat opakující se úlohy, jako jsou oznámení nebo pokročilé akce. Používejte triggery, když:

- Aktualizace zdroje dat selže.
- Aktualizace zdroje dat uspěje.
- V segmentu je překročena prahová hodnota. Trigger je omezen na překročení nad prahovou hodnotu.
- V obchodní míře je překročena prahová hodnota. Jsou podporovány pouze firemní míry bez dimenze. Trigger je omezen na překročení nad prahovou hodnotu.
- Kompletní plánovaná aktualizace je dokončena. Tento trigger nefunguje pro ručně spuštěné aktualizace.
- Je dokončena aktualizace procesu sjednocení.

[Konfigurace triggerů v Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Akce Power Automate

Konektor Power Automate poskytuje jiné akce než dostupné triggery. Další informace naleznete v dokumentaci [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Vytvoření toku Power Automate

1. Přejděte na **Správce** > **Propojení**.

1. Na dlaždici **Power Automate** vyberte **Nastavit**.

1. V Power Automate se otevře konektor Customer Insights (Preview). **Přihlaste se** k Power Automate.

1. Vyberte jeden z dostupných triggerů a do nového toku přidejte další kroky. Další informace viz [Vytvoření cloudového toku v Power Automate](/power-automate/get-started-logic-flow).

Příklady použití toků: 
- Odeslání zprávy do kanálu Microsoft Teams, pokud selže aktualizace zdroje dat. 
- Odeslání e-mailu vlastníkům dat po překročení prahové hodnoty v segmentu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
