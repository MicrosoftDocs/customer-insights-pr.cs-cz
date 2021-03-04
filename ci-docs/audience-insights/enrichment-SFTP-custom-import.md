---
title: Rozšíření pomocí vlastního importu SFTP
description: Obecné informace o rozšíření pomocí vlastního importu SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269598"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Rozšíření profilů zákazníků o vlastní data (Preview)

Vlastní import prostřednictvím protokolu SFTP (Secure File Transfer Protocol) umožňuje importovat data, která nemusí projít procesem sjednocení dat. Je to flexibilní, bezpečný a snadný způsob, jak přenést svá data. Vlastní import SFTP lze použít v kombinaci s [exportem SFTP](export-sftp.md), který vám umožní exportovat data profilu zákazníka, která jsou potřebná pro rozšíření. Data lze poté zpracovat, rozšířit a vlastní import SFTP lze použít k přenesení rozšířených dat zpět do přehledů cílové skupiny v Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Požadavky

Chcete-li nakonfigurovat vlastní import SFTP, musíte splnit následující předpoklady:

- Máte přihlašovací údaje uživatele (uživatelské jméno a heslo) pro umístění SFTP, odkud budou importována data.
- Máte adresu URL a číslo portu (obvykle 22) pro hostitele STFP.
- Máte název souboru a umístění souboru, který se má importovat na hostitele SFTP.
- Existuje soubor *model.json*, který určuje schéma pro data, která mají být importována. Tento soubor musí být ve stejném adresáři jako soubor, který chcete importovat.
- Máte oprávnění pro [správu](permissions.md#administrator).

## <a name="configuration"></a>Konfigurace

1. Přejděte na **Data** > **Obohacení** a vyberte kartu **Objevit**.

1. V **dlaždici vlastního importu SFTP** vyberte **Rozšířit moje data**.

   > [!div class="mx-imgBorder"]
   > ![Dlaždice vlastního importu SFTP](media/SFTP_Custom_Import_tile.png "Dlaždice vlastního importu SFTP")

1. Vyberte **Začít** a zadejte přihlašovací údaje a adresu serveru SFTP. Například sftp://mysftpserver.com:22.

1. Zadejte název souboru, který obsahuje data, a cestu k souboru na serveru SFTP, pokud není v kořenové složce.

1. Potvrďte všechny vstupy volbou **Připojit k vlastnímu importu**.

   > [!div class="mx-imgBorder"]
   > ![Informační rámeček s konfigurací vlastního importu SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Informační rámeček s konfigurací vlastního importu SFTP")

## <a name="defining-field-mappings"></a>Definování mapování polí 

Adresář obsahující soubor, který se má importovat na server SFTP, musí také obsahovat soubor *model.json*. Tento soubor definuje schéma, které se má použít pro import dat. Schéma musí používat [Common Data Model](https://docs.microsoft.com/common-data-model/) pro zadání mapování polí. Jednoduchý příklad souboru model.json vypadá takto:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>Výsledky rozšíření

Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů. Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab). Doba zpracování bude záviset na velikosti dat, která mají být importována, a na připojení k serveru SFTP.

Po dokončení procesu rozšíření můžete zkontrolovat nově importovaná data v sekci **Moje rozšíření**. Dále najdete čas poslední aktualizace a počet obohacených profilů.

Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.

## <a name="next-steps"></a>Další kroky

Stavte na svých obohacených zákaznických údajích. Vytvořte [segmenty](segments.md), [míry](measures.md) a [exportujte data](export-destinations.md) pro zajištění prostředí na míru zákazníkům.




[!INCLUDE[footer-include](../includes/footer-banner.md)]