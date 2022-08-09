---
title: Export dat do Salesforce Marketing Cloud (Preview)
description: Naučte se, jak nakonfigurovat propojení a exportovat ho do Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197030"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Export dat do Salesforce Marketing Cloud (Preview)

Využijte svá zákaznická data ve službě Salesforce Marketing Cloud jejich exportem prostřednictvím umístění SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Předpoklady

- [Hostitel SFTP pro Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) a odpovídající pověření správce.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Nastavení připojení k Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Salesforce Marketing Cloud**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **Uživatelské jméno**, **Heslo**, **Název hostitele** a **Složku pro export** pro váš účet SFTP.

1. Vyberte **Ověřit** pro otestování připojení.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části SFTP. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Vyberte, zda chcete exportovat data **komprimovaná jako gzip** nebo **rozbalená** a vyberte **oddělovač polí** pro exportované soubory.

1. Vyberte entity, například segmenty, které chcete exportovat.

   > [!NOTE]
   > Každá vybraná entita bude při exportu rozdělena maximálně na pět výstupních souborů.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Import dat z umístění SFTP do Salesforce Marketing Cloud

1. Vytvořte [datová rozšíření v Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) pro import datového souboru Customer Insights z umístění SFTP.

2. [Importujte data z umístění SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) do datového rozšíření Salesforce Marketing Cloud.

3. Nastavte automatizaci pro import dat do datových rozšíření. Zjistěte více o [automatizaci přetažení souborů a plánované automatizaci](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definujte [automatizaci přetahování souborů](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) nebo [plánovanou automatizaci](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Zde je příklad [automatizace se SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
