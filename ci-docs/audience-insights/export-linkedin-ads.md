---
title: Export údajů ze služby Customer Insights do služby LinkedIn Ads
description: Naučte se konfigurovat připojení a export do služby LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2cfaa37fd0ac697f29665792bab27a925d8ea1eede0519d424524a7e5accbfeb
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034215"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Export segmentů do LinkedIn Ads (preview)

Exportujte segmenty sjednocených profilů zákazníků do reklam LinkedIn Ads a vytvořte spárované cílové skupiny. Spárované cílové skupiny použijte k cílení na společnosti a kontakty.

## <a name="prerequisites"></a>Požadavky

-   Máte [účet LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) a odpovídající přihlašovací údaje správce.
-   V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).
-   Profily zákazníků v exportovaných segmentech obsahují pole s e-mailovou adresou.

## <a name="known-limitations"></a>Známá omezení

- Do LinkedIn Ads můžete exportovat až 100 000 profilů na export.
- Export do LinkedIn Ads je omezen na segmenty.
- Export až 100 tisíc profilů do LinkedIn Ads může trvat až 10 minut. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Nastavení připojení k LinkedIn Ads

1. Ve statistikách cílové skupiny přejděte na **Správce** > **Připojení**.

1. Vyberte **Přidat připojení** a zvolte **LinkedIn Ads** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí budou administrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte své [ID účtu LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. K inicializaci propojení se službou Campaign Monitor vyberte **Propojit**.

1. Vyberte **Ověření pomocí LinkedIn** a zadejte své přihlašovací údaje do aplikace LinkedIn Campaign Manager.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Export můžete konfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **Připojení pro export** vyberte připojení v části LinkedIn Ads. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Vyberte, zda chcete v LinkedIn exportovat data do [cílení kontaktů](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) nebo [cílení na společnost](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

1. V oddíle **Párování dat** vyberte pole sjednoceného profilu zákazníka, které představuje e-mailovou adresu zákazníka. Je nutné exportovat segmenty do LinkedIn Ads.

1. Vyberte segmenty, které chcete exportovat. Spárované cílové skupiny v LinkedIn Campaign Manager se vytvoří automaticky s názvem segmentů, které jste vybrali k exportu. Výsledkem každého segmentu bude samostatná spárovaná cílová skupina. 

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když aplikaci Dynamics 365 Customer Insights povolíte přenos dat do LinkedIn Ads, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že LinkedIn Ads bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.
