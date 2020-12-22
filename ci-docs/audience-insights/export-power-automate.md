---
title: Konektor Power Automate | Microsoft Docs
description: Vytvářejte toky v Microsoft Power Automate z Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405351"
---
# <a name="power-automate-connector-preview"></a>Konektor Power Automate (preview)

Služba Power Automate podporuje automatické spouštění vybraných událostí při změně dat nebo přímou správu složitějších toků v [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Triggery Power Automate

K automatizaci opakujících se úkolů, jako jsou oznámení nebo pokročilejší akce, můžete použít různé triggery, které vám umožní vytvářet toky. 

- Spustí se, když selže aktualizace zdroje dat. 
- Spustí se, když uspěje aktualizace zdroje dat.
- Spustí se, když je v segmentu překročena prahová hodnota. Trigger je omezen na překročení nad prahovou hodnotu.
- Spustí se, když je v obchodní míře překročena prahová hodnota. Trigger je omezen na překročení nad prahovou hodnotu.
- Spustí se, když je dokončena úplná aktualizace (zdroje dat, segmenty, míry, ...).
- Spustí se, když je dokončena aktualizace procesu sjednocení (mapování, spárování, sloučení).

[Konfigurace triggerů v Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Akce Power Automate
Konektor Power Automate poskytuje jiné akce než dostupné triggery. Další informace naleznete v dokumentaci [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Vytvoření toku Power Automate v přehledech cílové skupiny

1. V přehledech cílové skupiny přejděte na **Správa** > **Systém**.

1. Na stránce **Systém** vyberte kartu **Stav**.

1. V sekci **Zdroje dat** vyberte **Toky** a vyberte **Vytvořte tok** z rozevíracího seznamu.
   > [!div class="mx-imgBorder"]
   > ![Konektor Power Automate zobrazující Vytvořit akci toku](media/power-automate-connector-create-flow.png "Konektor Power Automate zobrazující akci Vytvořit toku")

1. V Power Automate vyberte jeden z dostupných spouštěčů a vytvořte si preferovaný tok. Pokud vytváříte svůj první tok, musíte se nejprve autentizovat pomocí konektoru Power Automate.
