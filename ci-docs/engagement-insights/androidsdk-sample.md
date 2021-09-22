---
title: Ukázka Android SDK
description: Ukázkový projekt s informacemi o Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035818"
---
# <a name="run-the-android-sdk-sample"></a>Spuštění ukázky Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento ukázkový projekt Android vám pomůže pochopit, jak funguje SDK v aplikaci. Nemusíte psát kód. Stačí přidat klíč pro příjem a hned uvidíte události ve vašem pracovním prostoru.

## <a name="prerequisites"></a>Požadavky

- [Android Studio](https://developer.android.com/studio)
- [Klíč příjmu](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Stažení ukázky Android SDK

1. [Stáhnout ukázku přehledů zapojení Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Rozbalte komprimovaný soubor `ei-android-sample.zip`.
1. Otevřete rozbalenou složku v Android Studio.
1. V souboru `AndroidManifest.xml` nahraďte řetězec `"Your-Ingestion-Key"` klíčem pro příjem pracovního prostoru z přehledu zapojení pod **Správa** > **Pracovní prostor** > **Průvodce instalací**. 

   > [!NOTE]
   > Nemusíte nahrazovat část `${applicationId}`. Měla by být automaticky vyplněna.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Vyberte **Spustit** ke spuštění ukázkového projektu.
1. Zobrazte události ve svém pracovním prostoru.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
