---
title: Export segmentů do Braze (Preview)
description: Zjistěte, jak nakonfigurovat připojení a export do Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080908"
---
# <a name="export-segments-to-braze-preview"></a>Export segmentů do Braze (Preview)

Zjistěte, jak exportovat segmenty profilů Unified Customer Profile do Braze a použít je pro marketingové aktivity.

## <a name="prerequisites"></a>Předpoklady

- [Účet Braze](https://www.braze.com/) a odpovídající přihlašovací údaje správce.
- Existující [segmenty v Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Profily Unified Customer Profile v exportovaných segmentech obsahují pole představující e-mailovou adresu a ID zákazníka Braze.

## <a name="known-limitations"></a>Známá omezení

- Export do Braze je omezen na segmenty.
- Export až 1 milionu zákaznických profilů do Braze může trvat až 40 minut.
- Počet zákaznických profilů, které můžete exportovat do Braze, závisí na vaší smlouvě s Braze a je jí omezen.

## <a name="set-up-connection-to-braze"></a>Nastavení připojení k Braze

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a volbou **Braze** začněte konfigurovat připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadáním [klíče rozhraní API pro Braze](https://www.braze.com/docs/api/basics/) pokračujte v přihlášení.

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Volbou **Připojit** inicializujete připojení k Braze.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **Připojení pro export** vyberte připojení v sekci Braze. Pokud tuto sekci nevidíte, nemáte k dispozici žádná připojení tohoto typu.  

1. Přidejte **zobrazované jméno** pro export.

1. Přidejte identifikátor API segmentu Braze, do kterého chcete exportovat, do pole **Identifikátor rozhraní API segmentu Braze**. Identifikátor najdete v detailu segmentu na platformě Braze.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. V poli **ID zákazníka** vyberte pole, které představuje ID Braze zákazníka. Segmenty je nutné exportovat do Braze. Volitelně můžete zvolit více polí.

1. Vyberte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte aplikaci Dynamics 365 Customer Insights přenos dat do služby Braze, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft taková data přenese na váš pokyn, ale vy jste odpovědní za zajištění toho, že Braze splňuje veškeré vaše případné povinnosti týkající se ochrany soukromí nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.
