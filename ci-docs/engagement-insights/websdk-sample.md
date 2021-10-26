---
title: Spuštění ukázky webové sady SDK
description: Naučte se, jak přizpůsobit a spustit ukázku webové sady SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606192"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Spusťte ukázku webové SDK pro funkci přehledů zapojení Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Knihovna webových SDK s možnostmi přehledů zapojení je knihovna JavaScriptu s ukázkovým kódem, který můžete použít na svém webu.

## <a name="prerequisites"></a>Požadavky

- Nainstalujte [Visual Studio Code](https://code.visualstudio.com/).
- [Nainstalujte si rozšíření Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) do Visual Studio Code a seznamte se s tím, jak spustit Live Server.
- Musíte mít [pracovní prostor přehledů zapojení](create-workspace.md).

## <a name="run-sample"></a>Spuštění ukázky

1. [Stáhněte ukázku webové sady SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Rozbalte komprimovaný soubor `ei_websdk_sample.zip`.

1. Otevřete vybalenou složku ve Visual Studio Code.

1. Přejděte na portál pracovního přehledu zapojení pro svůj pracovní prostor. Vyberte **Správce** > **Pracovní prostor** a pak **Průvodce instalací**. Postupujte podle první možnosti a vyberte **Zkopírovat kód** ke zkopírování fragmentu kódu JavaScript.

1. V souboru `ei_websdk_sample.html` vložte právě zkopírovaný fragment kódu pod tento řádek:

   - <-VLOŽTE FRAGMENT KÓDU JAVASKRIPTU Z PORTÁLU PřEHLEDů ZAPOJENí ZDE POD TENTO ŘÁDEK->

1. Otevřete soubor `ei_websdk_sample.html` pomocí Live Server ve Visual Studio Code výběrem **Přejít online** ze stavového řádku.

1. Při otevření stránky by měla být automaticky odeslána událost zobrazení. Kliknutím na kterékoli z tlačítek na stránce odešlete události akce. Tlačítko **Sledovat události** také odešle vlastní události. Výběrem tlačítka **Přejít na Bing** odešlete událost akce před přechodem na web Bing.

1. Podívejte se na probíhající události při přechodu do pracovního prostoru. Tento pracovní prostor je spojen s klíčem příjmu zadaným v kroku 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
