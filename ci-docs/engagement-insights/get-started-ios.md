---
title: Začínáme s iOS SDK
description: Naučte se, jak přizpůsobit a spustit sadu iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036865"
---
# <a name="get-started-with-the-ios-sdk"></a>Začínáme s iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento kurz vás provede procesem instrumentace aplikace iOS pomocí SDK přehledů zapojení Dynamics 365 Customer Insights. Události se na vašem portálu začnou zobrazovat za pět nebo méně minut.

## <a name="configuration-options"></a>Možnosti konfigurace

Následující možnosti konfigurace lze předat SDK prostřednictvím dodaného souboru `EIConfig.plist`:

- **ingestionKey**: Klíč příjmu použitý k odeslání událostí do vašeho projektu.
- **autocollectAction**: Logická hodnota pro povolení nebo zakázání automatické instrumentace události akce.
- **autocollectView**: Logická hodnota pro povolení nebo zakázání automatické instrumentace události zobrazení.
- **endpointUrl**: Adresa URL koncového bodu, na kterou budou události směrovány.

## <a name="prerequisites"></a>Požadavky

- Verze Xcode 9+
- iOS verze 8.2+
- Klíč pro příjem (získáte podle pokynů níže)

## <a name="integrate-the-sdk-into-your-application"></a>Integrace SDK do vaší aplikace

Začněte proces výběrem pracovního prostoru pro práci, výběrem mobilní platformy iOS a stažením sady SDK.

- Pomocí přepínače pracovního prostoru v levém navigačním podokně vyberte svůj pracovní prostor.

- Pokud nemáte existující pracovní prostor, vyberte **Nový pracovní prostor** a podle pokynů vytvořte [nový pracovní prostor](create-workspace.md).

## <a name="configure-the-sdk"></a>Konfigurace SDK

Jakmile si SDK stáhnete, můžete s ní v Xcode pracovat a povolit a definovat události.

1. Po vytvoření pracovního prostoru přejděte na **Správce** > **Pracovní prostor** a poté vyberte **Průvodce instalací**.

1. Stáhněte si [sadu iOS SDK přehledů zapojení](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) a umístěte soubor `EIObjC.xcframework` do složky `Frameworks`.

1. Pokud složka `Frameworks` neexistuje, vytvořte ji ve složce projektu.

## <a name="enable-auto-instrumentation"></a>Povolit automatickou instrumentaci
 
Automatickou instrumentaci můžete snadno povolit bez kódování. Po spuštění projektu bude automaticky sledovat události `view` a `action` pomocí nakonfigurovaného klíče příjmu. 

1. Aktualizujte a zahrňte poskytnutý soubor `EIConfig.plist` ve složce adresáře projektu pro následující pole:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = ANO
    - autocollectAction = ANO

2. Pak přidejte soubor `EIConfig.plist` do projektu v Xcode. 



Pokud chcete zakázat automatickou instrumentaci, aktualizujte následující pole v dodaném souboru `EIConfig.plist` ve složce adresáře projektu. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementace vlastních událostí

1. Otevřete projekt v Xcode a přejděte na nastavení **Obecné**. 
1. Přidejte `EIObjC.xcframework` do projektu v části „Rámce, knihovny a zabudovaný obsah“.

1. Importujte soubor záhlaví architektury v AppDelegate.m pomocí následujícího fragmentu:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inicializace sady SDK přehledu zapojení z aplikace: didFinishLaunchingWithOptions.
1. Zkopírujte fragment XML z **Instalační příručky**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Sledovat událost:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Nastavení podrobností o uživateli události

Sada SDK umožňuje definovat informace o uživateli, které lze odeslat s každou událostí. Informace o uživateli můžete určit voláním API `setUser:(nonnull EIUser *)user` v sadě SDK.

Určení podrobností uživatele na úrovni `Analytics` znamená, že tyto informace budou mít všechny telemetrie. Pokud však určíte na úrovni události voláním API `setUser:(nonnull EIUser *)user` v objektu EIEvent, informace bude obsahovat pouze konkrétní událost.

Třída dat `EIUser` obsahuje následující vlastnosti NSString:

- **localId**: Místní ID uživatele.
- **authId**: Ověřené ID uživatele.
- **authType**: Typ ověřování používaný k získání ověřeného ID uživatele.
- **name**: Jméno uživatele.
- **email**: E-mailová adresa uživatele.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
