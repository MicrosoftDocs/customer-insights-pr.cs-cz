---
title: Konektor Power Automate | Microsoft Docs
description: Vytváření toků v Microsoft Power Automate z Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dd90ef4576246b49d4a9c74005196ee9813a6744
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455899"
---
# <a name="power-automate-connector-preview"></a>Konektor Power Automate (preview)

Služba Power Automate podporuje automatické spouštění vybraných událostí při změně dat nebo přímou správu složitějších toků v [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Známá omezení

- Za 60 sekund můžete uskutečnit maximálně 100 hovorů. Pomocí parametru $skip můžete volat API koncový bod vícekrát. [Další informace o parametru $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Triggery Power Automate

Pomocí triggerů můžete vytvářet cloudové toky a automatizovat opakující se úlohy, jako jsou oznámení nebo pokročilé akce. 

- Spustí se, když selže aktualizace zdroje dat. 
- Spustí se, když uspěje aktualizace zdroje dat.
- Spustí se, když je v segmentu překročena prahová hodnota. Trigger je omezen na překročení nad prahovou hodnotu.
- Spustí se, když je v obchodní míře překročena prahová hodnota. Jsou podporovány pouze firemní míry bez dimenze. Trigger je omezen na překročení nad prahovou hodnotu.
- Spustí se, když je dokončena úplná aktualizace (zdroje dat, segmenty, míry, ...).
- Spustí se, když je dokončena aktualizace procesu sjednocení (mapování, spárování, sloučení).

[Konfigurace triggerů v Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Akce Power Automate

Konektor Power Automate poskytuje jiné akce než dostupné triggery. Další informace naleznete v dokumentaci [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Vytvoření toku Power Automate

1. V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.

1. Na dlaždici **Power Automate** vyberte **Nastavit**.

1. V Power Automate se otevře konektor Customer Insights (Preview). **Přihlaste se** k Power Automate.

1. Vyberte jeden z dostupných triggerů a do nového toku přidejte další kroky. Další informace viz [Vytvoření cloudového toku v Power Automate](/power-automate/get-started-logic-flow).

Příklady použití toků: 
- Odeslání zprávy do kanálu Microsoft Teams, pokud selže aktualizace zdroje dat. 
- Odeslání e-mailu vlastníkům dat po překročení prahové hodnoty v segmentu.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
