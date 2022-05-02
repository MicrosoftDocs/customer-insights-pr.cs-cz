---
title: Export dat Customer Insights do Iterable
description: Zjistěte, jak nakonfigurovat připojení a export do Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 714a1323521be7d2f29ccaacd7799b2174e2937d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646437"
---
# <a name="export-segment-lists-to-iterable-preview"></a>Export seznamů segmentů do Iterable (Preview)

Zjistěte, jak exportovat segmenty profilů Unified Customer Profile do Iterable a použít je pro marketingové aktivity.

## <a name="prerequisites"></a>Předpoklady

-   Máte [účet Iterable](https://iterable.com/) a odpovídající přihlašovací údaje správce.
-   [Nakonfigurovali jste segmenty](segments.md) v Customer Insights.
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Export do Iterable je omezen na segmenty.
- Export až 1 milionu zákaznických profilů do Iterable může trvat až 30 minut. 
- Počet zákaznických profilů, které můžete exportovat do Iterable, závisí na vaší smlouvě s Iterable a je jí omezen.

## <a name="set-up-connection-to-iterable"></a>Nastavení připojení k Iterable

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a volbou **Iterable** začněte konfigurovat připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadáním [klíče rozhraní API pro Iterable](https://support.iterable.com/hc/en-us/articles/360043464871) pokračujte v přihlášení. 

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Volbou **Připojit** inicializujete připojení k Iterable.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **Připojení pro export** vyberte připojení v sekci Iterable. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

3. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. Segmenty je potřeba exportovat do Iterable. Seznam vytvořený v Iterable bude mít přesně stejný název jako váš segment v Dynamics 365 Customer Insights.

1. Vyberte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte aplikaci Dynamics 365 Customer Insights přenos dat do služby Iterable, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft taková data přenese na váš pokyn, ale vy jste odpovědní za zajištění toho, že Iterable splňuje veškeré vaše případné povinnosti týkající se ochrany soukromí nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.
