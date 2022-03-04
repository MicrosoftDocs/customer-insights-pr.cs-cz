---
title: Spuštění ukázky iOS SDK
description: Ukázkový projekt s informacemi o iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232834"
---
# <a name="run-the-ios-sdk-sample"></a>Spuštění ukázky iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento ukázkový projekt iOS vám pomůže pochopit, jak funguje SDK v aplikaci. Nemusíte psát kód. Stačí přidat klíč pro příjem a hned uvidíte události ve vašem pracovním prostoru.

## <a name="prerequisites"></a>Požadavky

- [Verze Xcode 9+](https://developer.apple.com/xcode/downloads/)
- [Klíč příjmu](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Stažení ukázky iOS SDK

1. [Stáhnout ukázku přehledů zapojení iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip)
1. Rozbalte komprimovaný soubor `ei-ios-sample.zip`.
1. Otevřete projekt ukázkové aplikace v Xcode.
1. V souboru `EIConfig.plist` nahraďte řetězec `“YOUR-INGESTION-KEY”` v poli `ingestionKey` klíčem pro příjem pracovního prostoru z přehledu zapojení pod **Správa** > **Pracovní prostor** > **Průvodce instalací**.
1. Vyberte **Spustit** ke spuštění ukázkového projektu.
1. Zobrazte události ve svém pracovním prostoru.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
