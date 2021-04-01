---
title: Export dat Customer Insights do hostitelů SFTP
description: Naučte se, jak nakonfigurovat připojení k hostiteli SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598377"
---
# <a name="connector-for-sftp-preview"></a>Konektor pro SFTP (preview)

Konektor SFTP umožňuje bezpečně exportovat vaše zákaznická data, která pak můžete používat v aplikacích třetích stran, do hostitele SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Požadavky

- Dostupnost hostitele SFTP a odpovídajících pověření.

## <a name="connect-to-sftp"></a>Připojit k SFTP

1. Přejděte na **Správce** > **Cíle exportu**.

1. V **SFTP** vyberte **Založit**

1. Zadejte rozpoznatelný název cíle do pole **Zobrazovaný název**.

1. Zadejte **Uživatelské jméno**, **Heslo**, **Název hostitele** a **Složku pro export** pro váš účet SFTP.

1. Vyberte **Ověřit** pro otestování připojení.

1. Po úspěšném ověření zvolte, zda chcete exportovat svá data **sbalená** nebo **rozbalená** a vyberte **oddělovač polí** pro exportované soubory.

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Vyberte **Další** pro spuštění konfigurace exportu.

## <a name="configure-the-export"></a>Konfigurace exportu

1. Vyberte entity, například segmenty, které chcete exportovat.

   > [!NOTE]
   > Každá vybraná entita bude mít při exportu až pět výstupních souborů. 

1. Zvolte **Uložit**.

## <a name="export-the-data"></a>Export dat

Můžete [exportovat data na vyžádání](export-destinations.md). Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).

## <a name="known-limitations"></a>Známá omezení

- Běh exportu závisí na výkonu vašeho systému. Jako minimální konfiguraci vašeho serveru doporučujeme dvě jádra CPU a 1 GB paměti. 
- Export entit s až 100 miliony zákaznických profilů může trvat 90 minut při použití doporučené minimální konfigurace dvou jader CPU a 1 GB paměti. 

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat prostřednictvím protokolu SFTP, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že cíl exportu splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](../includes/footer-banner.md)]