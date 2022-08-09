---
title: Rozšíření profilů zákazníků s vlastním importem SFTP (Preview)
description: Obecné informace o rozšíření pomocí vlastního importu SFTP.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 81ef6c62240e26cb5c9475e6306e08edc7e5eb31
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195788"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Rozšíření profilů zákazníků s vlastním importem SFTP (Preview)

Vlastní import prostřednictvím protokolu SFTP (Secure File Transfer Protocol) umožňuje importovat data, která nemusí projít procesem sjednocení dat. Je to flexibilní, bezpečný a snadný způsob, jak přenést svá data. Vlastní import SFTP lze použít v kombinaci s [exportem SFTP](export-sftp.md), který vám umožní exportovat data profilu zákazníka, která jsou potřebná pro rozšíření. Data lze poté zpracovat a obohatit a pomocí vlastního importu SFTP lze obohacená data vrátit zpět do Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Předpoklady

- Je znám název souboru a umístění (cesta) souboru, který má být importován na hostitele SFTP.

- Soubor *model.json*, který specifikuje schéma Common Data Model pro data, která mají být importována. Tento soubor musí být ve stejném adresáři jako soubor, který chcete importovat.

- SFTP [připojení](connections.md) je [nakonfigurováno](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Příklad schématu souboru

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurace připojení pro vlastní import SFTP

Musíte být [správce](permissions.md#admin) v Customer Insights a mít přihlašovací údaje uživatele, adresu URL a číslo portu pro umístění SFTP, ze kterého chcete importovat data.

1. Při konfiguraci rozšíření vyberte **Přidat připojení** nebo přejděte na **Správce** > **Připojení** a v dlaždici **Vlastní import** vyberte Nastavit.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Stránka konfigurace připojení vlastního importu":::

1. Zadejte název připojení.

1. Zadejte platné uživatelské jméno, heslo a adresu URL hostitele pro server SFTP, na kterém se nacházejí importovaná data.

1. Zkontrolujte a poskytněte svůj souhlas s [ochranou osobních údajů a dodržováním předpisů](#data-privacy-and-compliance) výběrem **souhlasím**.

1. Zvolte **Ověřit** pro ověření konfigurace a poté vyberte **Uložit**.

### <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte aplikaci Dynamics 365 Customer Insights přenos dat pomocí vlastního importu, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft taková data přenese na váš pokyn, ale vy jste odpovědní za zajištění toho, že data splňují veškeré vaše případné povinnosti týkající se ochrany soukromí nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.

## <a name="configure-the-import"></a>Konfigurace importu

1. Přejděte na **Data** > **Rozšíření** a vyberte kartu **Objevit**.

1. Vyberte příkaz **Rozšířit moje data** na dlaždici **Vlastní import SFTP**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Dlaždice vlastního importu SFTP":::

1. Zkontrolujte přehled a poté vyberte **Další**.

1. Vyberte připojení. Pokud není k dispozici propojení , kontaktujte správce.

1. Vyberte **Sada údajů o zákazníkovi** a zvolte profil nebo segment, které chcete rozšířit. Entita *Zákazník* rozšíří všechny profily vašich zákazníků zatímco segment rozšíří pouze profily zákazníků obsažené v tomto segmentu.

1. Vyberte **Další**.

1. Zadejte **Cesta** a **Název souboru** datového souboru, který chcete importovat.

1. Vyberte **Další**.

1. Zadejte **Název** rozšíření a **název výstupní entity**.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

1. Vyberte **Spustit** k zahájení procesu obohacování nebo blízko k návratu na stránku **Rozšíření**.

## <a name="view-enrichment-results"></a>Zobrazení výsledků rozšiřování

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Další kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
