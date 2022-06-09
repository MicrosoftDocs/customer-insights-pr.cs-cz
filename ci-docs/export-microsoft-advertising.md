---
title: Export dat Customer Insights do služby Microsoft Advertising
description: Naučte se konfigurovat připojení a export do služby Microsoft Advertising.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 14479e915dd6ae76e018b59bee5980a600bb222d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646447"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Export segmentů do služby Microsoft Advertising (preview)

Exportujte segmenty Customer Insights do služby Microsoft Advertising a vytvořte cílové skupiny shody zákazníků. Tyto cílové skupiny používejte pro své reklamní kampaně.

## <a name="prerequisites"></a>Požadavky

-   Máte [účet Microsoft Advertising](https://ads.microsoft.com/) a odpovídající přihlašovací údaje správce.
-   Přijali jste podmínky použití shod zákazníků. 
-   [Nakonfigurované segmenty](segments.md) v Customer Insights.
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole s e-mailovou adresou.

## <a name="known-limitations"></a>Známá omezení

- Do Microsoft Advertising můžete najednou exportovat až 500 000 zákaznických profilů.
- Export do Microsoft Advertising je omezen na segmenty.
- Export až 500 000 zákaznických profilů do Microsoft Advertising může trvat až 10 minut. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Nastavení propojení se službou Microsoft Advertising

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Microsoft Advertising** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Výchozí jsou správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. K inicializaci propojení se službou Microsoft Advertising vyberte příkaz **Připojit**.

1. Vyberte **Ověření pomocí Microsoft Advertising** a zadejte své přihlašovací údaje pro Microsoft Advertising.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **Připojení pro export** vyberte připojení v části Microsoft Advertising. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Vyberte segmenty, které chcete exportovat. Cílové skupiny shody zákazníků ve službě Microsoft Advertising se automaticky vytvářejí s názvem segmentů vybraných pro export. Výsledkem každého segmentu bude samostatná cílová skupina shody zákazníků. 

1. Vložte své **ID zákazníka a ID účtu Microsoft Advertising**. ID zákazníka (`cid`) a ID účtu (`aid`) najdete v parametrech adresy URL, když jste přihlášeni do služby Microsoft Advertising.

1. V části **Párování dat** v poli **E-mail** vyberte pole s e-mailovou adresou zákazníka. Je nutné exportovat segmenty do Microsoft Advertising.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když aplikaci Dynamics 365 Customer Insights povolíte přenos dat do Microsoft Advertising, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že Microsoft Advertising bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.