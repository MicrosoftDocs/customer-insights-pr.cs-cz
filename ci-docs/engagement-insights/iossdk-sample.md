---
title: Spuštění ukázky iOS SDK
description: Ukázkový projekt s informacemi o iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036820"
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
