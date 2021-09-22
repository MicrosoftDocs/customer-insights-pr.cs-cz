---
title: Začínáme s Android SDK
description: Naučte se, jak přizpůsobit a spustit sadu Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036910"
---
# <a name="get-started-with-the-android-sdk"></a>Začínáme s Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento kurz vás provede procesem instrumentace aplikace Android pomocí sady SDK postřehů zapojení Dynamics 365 Customer Insights. Události se na vašem portálu začnou zobrazovat za pět nebo méně minut.

## <a name="configuration-options"></a>Možnosti konfigurace
Následující možnosti konfigurace lze předat do SDK:

- **ingestionKey**: Klíč příjmu použitý k odeslání událostí do vašeho pracovního prostoru.

## <a name="prerequisites"></a>Požadavky

- Android Studio

- Minimální úroveň API Android API: 16 (Jelly Bean)

- Klíč pro příjem (získáte podle pokynů níže)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Krok 1. Integrace SDK do vaší aplikace
Začněte proces výběrem pracovního prostoru pro práci, výběrem mobilní platformy Android a stažením sady SDK Android.

- Pomocí přepínače pracovního prostoru v levém navigačním podokně vyberte svůj pracovní prostor.

- Pokud nemáte existující pracovní prostor, vyberte **Nový pracovní prostor** a podle pokynů vytvořte [nový pracovní prostor](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Krok 2. Konfigurace SDK

1. Po vytvoření pracovního prostoru přejděte na **Správce** > **Pracovní prostor** a poté vyberte **Průvodce instalací**. 

1. Stáhněte si [sadu SDK Android přehledů zapojení](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) a vložte soubor `eiandroidsdk-debug.aar` do složky `libs`.

1. Otevřít soubor `build.gradle` na úrovni projektu a přidat následující fragmenty:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Nastavte konfiguraci SDK statistiky zapojení prostřednictvím souboru `AndroidManifest.xml` umístěného ve složce `manifests`. 
1. Zkopírujte fragment XML z **Instalační příručky**. `Your-Ingestion-Key` by měl být automaticky vyplněn.

   > [!NOTE]
   > Nemusíte nahrazovat část `${applicationId}`. Měla by být automaticky vyplněna.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Povolte nebo zakažte automatický záznam zobrazení událostí `View` nastavením výše uvedeného pole `autoCapture` na hodnotu `true` nebo `false`.

1. (Volitelné) Mezi další konfigurace patří nastavení adresy URL kolektoru koncový bod. Lze je přidat pod metadata klíče příjmu v `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Krok 3. Inicializovat SDK z MainActivity 

Po inicializaci SDK můžete pracovat s událostmi a jejich vlastnostmi v prostředí MainActivity.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Nastavit vlastnost pro všechny události (volitelně)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Pro vlastnosti kontextové události jsou podporovány následující typy:
- String
- Datum
- Hodnota s dvojitou přesností
- Dlouhé celé číslo
- Logický
- UUID

### <a name="track-an-event"></a>Sledovat událost

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Nastavení podrobností o uživateli události (volitelné)

Sada SDK umožňuje definovat informace o uživateli, které lze odeslat s každou událostí. Informace o uživateli můžete určit voláním API `setUser(user: User)` na úrovni `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Třída dat `User` obsahuje následující vlastnosti řetězce:

- **localId**: Místní ID uživatele.
- **authId**: Ověřené ID uživatele.
- **authType**: Typ ověřování použitý k získání ověřeného ID uživatele.
- **name**: Jméno uživatele.
- **email**: E-mailová adresa uživatele.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
