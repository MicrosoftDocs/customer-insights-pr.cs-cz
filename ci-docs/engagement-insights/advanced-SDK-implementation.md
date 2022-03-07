---
title: Pokročilé scénáře webového SDK
description: Pokročilé scénáře, které je třeba vzít v úvahu při vybavení vašeho webu pomocí SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036320"
---
# <a name="advanced-web-sdk-instrumentation"></a>Pokročilá webová instrumentace SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tento článek vás provede pokročilými scénáři, které je třeba zvážit při [instrumentaci vašeho webu](instrument-website.md) SDK funkcí přehledů zapojení Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Nastavení údajů uživatele pro vaši událost

Sada SDK umožňuje definovat informace o uživateli, které lze odeslat s každou událostí. Můžete zadat podrobnosti o uživateli ve vlastnosti s názvem `user` (očekávaná data pro tuto vlastnost je objekt `IUser`), podobně jako `src`, `name` a `cfg` v konfiguraci fragmentu kódu.

Objekt `IUser` obsahuje následující vlastnosti řetězce:

- **localId**: Místní ID uživatele.
- **authId**: Ověřené ID uživatele.
- **authType**: Typ ověřování používaný k získání ověřeného ID uživatele.
- **name**: Jméno uživatele.
- **email**: E-mailová adresa uživatele.
    
Následující příklad ukazuje fragment kódu odesílajícího informace o uživateli. Kde uvidíte Funkce označené *, nahraďte ji implementací volání těchto hodnot:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Můžete také zadat informace o uživateli voláním API `setUser(user: IUser)` na SDK. Telemetrie odeslána po volání `setUser API` bude obsahovat informace o uživateli.

## <a name="adding-custom-properties-for-each-event"></a>Přidání vlastních vlastností pro každou událost

Sada SDK umožňuje zadat vlastní vlastnosti, které lze odeslat s každou událostí. Můžete zadat vlastní vlastnosti jako objekt obsahující páry klíč-hodnota (hodnota může být typu `string | number | boolean`). Objekt lze přidat do vlastnosti s názvem `props`, podobně jako `src`, `name` a `cfg` v konfiguraci fragmentu kódu. 

Následující příklad ukazuje fragment kódu odesílajícího vlastní vlastnosti:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Můžete také zadat vlastní vlastnosti jednotlivě voláním API `setProperty(name: string, value: string | number | boolean)` na SDK.

## <a name="sending-custom-events"></a>Odesílání vlastních událostí

Pomocí sady SDK můžete odesílat vlastní události. Musíte zadat název události a vlastnosti, které se mají s událostí odeslat.

Následující příklad ukazuje fragment kódu sledujícího vlastní událost. „NAME“ je hodnota v klíči `name` v konfiguraci fragmentu. Je to také název proměnné v objektu okna, kde je načten SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]