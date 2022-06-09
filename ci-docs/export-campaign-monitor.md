---
title: Export údajů ze služby Customer Insights do služby Campaign Monitor
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Campaign Monitor.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b351e491ee830b6360d4efe33d32a726c2e553ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645748"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Export segmentů do služby Campaign Monitor (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby Campaign Monitor a použijte je pro marketingové aktivity.

## <a name="prerequisites"></a>Požadavky

-   Máte [účet Campaign Monitor](https://www.campaignmonitor.com/) a odpovídající přihlašovací údaje správce.
-   [Nakonfigurovali jste segmenty](segments.md) v Customer Insights.
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Do Campaign Monitor můžete exportovat až 1 milion zákaznických profilů na export.
- Export do Campaign Monitor je omezen na segmenty.
- Export až 1 milionu zákaznických profilů do Campaign Monitor může trvat až 20 minut. 
- Počet zákaznických profilů, které můžete exportovat do Campaign Monitor, závisí na vaší smlouvě s Campaign Monitor a je jí omezen.

## <a name="set-up-connection-to-campaign-monitor"></a>Nastavení propojení s Campaign Monitor

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Campaign Monitor** pro konfiguraci propojení .

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. K inicializaci propojení se službou Campaign Monitor vyberte **Propojit**.

1. Vyberte **Ověření pomocí Campaign Monitor** a poskytněte své přihlašovací údaje pro Campaign Monitor.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **propojení pro export** vyberte propojení v části Campaign Monitor. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zadejte [**ID seznamu Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Vygenerujte klíč API](https://www.campaignmonitor.com/api/getting-started/) z **Nastavení účtu** nejprve v nástroji Campaign Monitor pro zobrazení ID seznamu API.  

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. Je nutné exportovat segmenty do Campaign Monitor.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights k přenosu dat do Campaign Monitor, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že Campaign Monitor bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.