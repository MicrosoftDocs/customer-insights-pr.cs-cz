---
title: Export údajů ze služby Customer Insights do Klaviyo
description: Naučte se, jak nakonfigurovat propojení a exportovat ho do Klaviyo.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7c1297fd5381c00c07d6501186c51fe4798773d1
ms.sourcegitcommit: 205f931ec671a0ab1850f2c1c94df3307ffb62c9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/13/2021
ms.locfileid: "7385780"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Export seznamů segmentů do Klaviyo (Preview)

Exportujte segmenty sjednocených profilů zákazníků do Klaviyo a použijte je pro marketingové aktivity.

## <a name="prerequisites"></a>Požadavky

-   Máte [účet Klaviyo](https://www.klaviyo.com/) a odpovídající pověření správce.
-   V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Na export do Klaviyo můžete exportovat až 100 000 profilů.
- Export do Klaviyo je omezen na segmenty.
- Export až 1 milion profilů do služby Klaviyo může trvat až 20 minut. 
- Počet profilů, které můžete exportovat do Klaviyo, závisí na vaší smlouvě se společností Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Nastavení připojení ke Klaviyo

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Klaviyo** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Poskytněte svůj [klíč API rozhraní Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) a pokračujte k přihlášení. 

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Vyberte **Připojit** k inicializaci připojení ke Klaviyo.

1. Vyberte **Ověřit pomocí Klaviyo** a zadejte své přihlašovací údaje správce pro Klaviyo.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **Připojení pro export** zvolte připojení z části Klaviyo. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zadejte [**ID seznamu Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. Je potřeba pro export segmentů do Klaviyo.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenášet data do Klaviyo, povolíte tím přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese takové údaje podle vašeho pokynu, ale vy jste zodpovědní za zajištění, že Klaviyo bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.