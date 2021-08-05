---
title: Export dat ze služby Customer Insights do Salesforce Marketing Cloud
description: Naučte se, jak nakonfigurovat propojení a exportovat ho do Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8ce243918c2388e931a98df3bbe576ddf692f707
ms.sourcegitcommit: 4823684a1399fd66ffecfce21735f2bc90a1733c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2021
ms.locfileid: "6660259"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Export segmentů a dalších dat do Salesforce Marketing Cloud (náhled)

Využijte svá zákaznická data ve službě Salesforce Marketing Cloud jejich exportem prostřednictvím umístění SFTP (Secure File Transfer Protocol).

## <a name="prerequisites-for-connection"></a>Předpoklady pro připojení

- Dostupnost hostitele SFTP a odpovídajících pověření správce. [Jak nastavit umístění SFTP pro Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Nastavení připojení k Salesforce Marketing Cloud

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Salesforce Marketing Cloud** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **Uživatelské jméno**, **Heslo**, **Název hostitele** a **Složku pro export** pro váš účet SFTP.

1. Vyberte **Ověřit** pro otestování připojení.

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **propojení pro export** vyberte propojení v části SFTP. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Vyberte, zda chcete exportovat data **komprimovaná jako gzip** nebo **rozbalená** a vyberte **oddělovač polí** pro exportované soubory.

1. Vyberte entity, například segmenty, které chcete exportovat.

   > [!NOTE]
   > Každá vybraná entita bude při exportu rozdělena až na pět výstupních souborů. 

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Import dat z umístění SFTP do Salesforce Marketing Cloud

1. Vytvořte [datová rozšíření v Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) pro import datového souboru Customer Insights z umístění SFTP.

2. [Importujte data z umístění SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) do datového rozšíření Salesforce Marketing Cloud. 

3. Nastavte automatizaci pro import dat do datových rozšíření. Zjistěte více o [automatizaci přetažení souborů a plánované automatizaci](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definujte [automatizaci přetahování souborů](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) nebo [plánovanou automatizaci](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Zde je příklad [automatizace se SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat prostřednictvím protokolu SFTP, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že cíl exportu splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
