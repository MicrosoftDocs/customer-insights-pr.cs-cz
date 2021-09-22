---
title: Spuštění ukázky webové sady SDK
description: Naučte se, jak přizpůsobit a spustit ukázku webové sady SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036595"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Spusťte ukázku webové SDK pro funkci přehledů zapojení Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Knihovna webových SDK s možnostmi přehledů zapojení je knihovna JavaScriptu s ukázkovým kódem, který můžete použít na svém webu.

## <a name="prerequisites"></a>Požadavky

- Nainstalujte [Visual Studio Code](https://code.visualstudio.com/).
- [Nainstalujte si rozšíření Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) do Visual Studio Code a seznamte se s tím, jak spustit Live Server.
- Musíte mít [přijímací klíč](instrument-website.md).

## <a name="run-sample"></a>Spuštění ukázky

1. [Stáhněte ukázku webové sady SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Rozbalte komprimovaný soubor `ei_websdk_sample.zip`.

1. Otevřete vybalenou složku ve Visual Studio Code.

1. V souboru `ei_websdk_sample.html` nahraďte řetězec „INGESTION_KEY“ klíčem pro příjem z portálu funkce přehledů zapojení a řetězec „NAME“ globálním názvem, ve kterém chcete vytvořit instanci sady SDK. Ujistěte se, že nahradíte všechny výskyty.

1. Otevřete soubor `ei_websdk_sample.html` pomocí Live Server ve Visual Studio Code výběrem **Přejít online** ze stavového řádku.

1. Při otevření stránky by měla být automaticky odeslána událost zobrazení. Kliknutím na kterékoli z tlačítek na stránce odešlete události akce. Tlačítko **Sledovat události** také odešle vlastní události. Výběrem tlačítka **Přejít na Bing** odešlete událost akce před přechodem na web Bing.

1. Podívejte se na probíhající události při přechodu do pracovního prostoru. Tento pracovní prostor je spojen s klíčem příjmu zadaným v kroku 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]