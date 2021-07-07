---
title: Rozšíření pomocí vlastního importu SFTP
description: Obecné informace o rozšíření pomocí vlastního importu SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304642"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Rozšíření profilů zákazníků o vlastní data (Preview)

Vlastní import prostřednictvím protokolu SFTP (Secure File Transfer Protocol) umožňuje importovat data, která nemusí projít procesem sjednocení dat. Je to flexibilní, bezpečný a snadný způsob, jak přenést svá data. Vlastní import SFTP lze použít v kombinaci s [exportem SFTP](export-sftp.md), který vám umožní exportovat data profilu zákazníka, která jsou potřebná pro rozšíření. Data lze poté zpracovat a obohatit a vlastní import SFTP lze použít k přenesení obohacených dat zpět do schopnosti cílové skupiny Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Požadavky

Chcete-li nakonfigurovat vlastní import SFTP, musíte splnit následující předpoklady:

- Máte název souboru a umístění (cestu) souboru, který se má importovat do hostitele SFTP.
- Tady je soubor *model.json*, který určuje [schéma Common Data Model](/common-data-model/) pro data k importu. Tento soubor musí být ve stejném adresáři jako soubor, který chcete importovat.
- Správce již nakonfiguroval připojení SFTP *nebo* máte oprávnění [správce](permissions.md#administrator). Budete potřebovat přihlašovací údaje uživatele, adresu URL a číslo portu pro umístění SFTP, ze kterého chcete importovat data.


## <a name="configure-the-import"></a>Konfigurace importu

1. Přejděte na **Data** > **Obohacení** a vyberte kartu **Objevit**.

1. V **dlaždici Vlastní import SFTP** vyberte **Rozšířit moje údaje** a pak vyberte **Začínáme**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Dlaždice vlastního importu SFTP":::

1. V rozevíracím seznamu vyberte [připojení](connections.md). Pokud není k dispozici propojení , kontaktujte správce. Pokud jste správce, můžete vytvořit připojení výběrem **Přidat připojení** a výběrem **Vlastní import SFTP** z rozevíracího seznamu.

1. Vybrané připojení potvrďte výběrem **Propojit s Custom Import**.

1.  Vyberte **Další** a zadejte **Cesta** a **Název souboru** datového souboru, který chcete importovat.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Screenshot při zadávání datového umístění.":::

1. Vyberte **Další** a zadejte název rozšíření a název výstupní entity. 

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurace připojení pro vlastní import SFTP 

Abyste mohli konfigurovat propojení, musíte být správce. Při konfiguraci rozšíření vyberte **Přidat připojení** *nebo* přejděte na **Správce** > **Připojení** a v dlaždici Vlastní import vyberte **Nastavit**.

1. Do pole **Zobrazované jméno** zadejte jméno.

1. Zadejte platné uživatelské jméno, heslo a adresu URL hostitele pro server SFTP, na kterém se nacházejí importovaná data.

1. Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.

1. Vyberte **Ověřit** k ověření konfigurace.

1. Po dokončení ověření lze připojení uložit výběrem **Uložit**.

   > [!div class="mx-imgBorder"]
   > ![Stránka konfigurace připojení Experian](media/enrichment-SFTP-connection.png "Stránka konfigurace připojení Experian")


## <a name="defining-field-mappings"></a>Definování mapování polí 

Adresář obsahující soubor, který se má importovat na server SFTP, musí také obsahovat soubor *model.json*. Tento soubor definuje schéma, které se má použít pro import dat. Schéma musí používat [Common Data Model](/common-data-model/) ke specifikaci mapování pole. Jednoduchý příklad souboru model.json vypadá takto:

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

Stavte na svých obohacených zákaznických údajích. Vytvořte [segmenty](segments.md) a [měření](measures.md) a [exportujte data](export-destinations.md), abyste svým zákazníkům poskytli přizpůsobené prostředí.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
