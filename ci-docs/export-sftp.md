---
title: Export dat do hostitelů SFTP (Preview) (obsahuje video)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do umístění SFTP.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67789a87cf0ff1b0d9933f2c0adde37762c83476
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080920"
---
# <a name="export-data-to-sftp-preview"></a>Export dat do SFTP (Preview)

Využijte svá zákaznická data v aplikacích třetích stran a exportujte je do umístění Secure File Transfer Protocol (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Předpoklady pro připojení

- Dostupnost hostitele SFTP a odpovídajících pověření.

## <a name="known-limitations"></a>Známá omezení

- Cíle SFTP za branami firewall v současnosti nejsou podporovány. 
- Běh exportu závisí na výkonu vašeho systému. Jako minimální konfiguraci vašeho serveru doporučujeme dvě jádra CPU a 1 GB paměti.
- Export entit s až 100 miliony zákaznických profilů může trvat 90 minut při použití doporučené minimální konfigurace dvou jader CPU a 1 GB paměti.

## <a name="set-up-connection-to-sftp"></a>Nastavení propojení k SFTP

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **SFTP** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **Uživatelské jméno**, **Heslo**, **Název hostitele** a **Složku pro export** pro váš účet SFTP.

1. Vyberte **Ověřit** pro otestování připojení.

1. Vyberte, zda chcete exportovat data **komprimovaná jako gzip** nebo **rozbalená** a vyberte **oddělovač polí** pro exportované soubory.

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **propojení pro export** vyberte propojení v části SFTP. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Vyberte entity, například segmenty, které chcete exportovat.

   > [!NOTE]
   > Každá vybraná entita bude při exportu rozdělena až na pět výstupních souborů.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).
Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).

> [!TIP]
> Export entit, které obsahují velké množství dat, může vést k více souborům CSV ve stejné složce pro každý export. K rozdělení exportů dochází z důvodu výkonu, aby se minimalizovala doba potřebná k dokončení exportu.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat prostřednictvím protokolu SFTP, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že cíl exportu splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
