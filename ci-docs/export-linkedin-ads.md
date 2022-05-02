---
title: Export údajů ze služby Customer Insights do služby LinkedIn Ads
description: Naučte se konfigurovat připojení a export do služby LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bf1d12ffbd7a4cfd7d268fea8a1f90cc37589e00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646448"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Export segmentů do LinkedIn Ads (preview)

Exportujte segmenty sjednocených profilů zákazníků do reklam LinkedIn Ads a vytvořte spárované cílové skupiny. Spárované cílové skupiny použijte k cílení na společnosti a kontakty.

## <a name="prerequisites"></a>Požadavky

-   Máte [účet LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) a odpovídající přihlašovací údaje správce.
-   [Nakonfigurovali jste segmenty](segments.md) v Customer Insights.
-   Profily zákazníků v exportovaných segmentech obsahují pole s e-mailovou adresou.

## <a name="known-limitations"></a>Známá omezení

- Váš segment v Customer Insights musí obsahovat alespoň 300 jedinečných profilů. 
- Do LinkedIn Ads můžete najednou exportovat až 100 000 zákaznických profilů.
- Export do LinkedIn Ads je omezen na segmenty.
- Export až 100 000 zákaznických profilů do LinkedIn Ads může trvat až 10 minut. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Nastavení připojení k LinkedIn Ads

1. Přejděte na **Správce** > **Propojení**.

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

1. V části **Shoda dat** pro cílení kontaktů vyberte alespoň jedno pole, které představuje e -mailovou adresu zákazníka, Apple Ad ID, Google Ad ID, Google User ID nebo jméno a příjmení. Pokud zvolíte cílení na společnost, vyberte alespoň jedno pole, které představuje název společnosti, e -mailovou doménu, adresu URL stránky LinkedIn, symbol akcií nebo web. Pro další definování exportu lze vybrat další pole. 

1. Vyberte segmenty, které chcete exportovat. Spárované cílové skupiny v LinkedIn Campaign Manager se vytvoří automaticky s názvem segmentů, které jste vybrali k exportu. Výsledkem každého segmentu bude samostatná spárovaná cílová skupina. 

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když aplikaci Dynamics 365 Customer Insights povolíte přenos dat do LinkedIn Ads, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že LinkedIn Ads bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.
