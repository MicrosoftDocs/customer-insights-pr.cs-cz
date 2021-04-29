---
title: Export dat Customer Insights do služby Google Ads
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759685"
---
# <a name="export-segments-to-google-ads-preview"></a>Export segmentů do Google Ads (náhled)

Exportujte segmenty sjednocených profilů zákazníků do seznamu cílových skupin Google Ads a použijte je k inzerci ve službách Google Search, Gmail, YouTube a Google Display Network. 

## <a name="prerequisites-for-connection"></a>Předpoklady pro připojení

-   Máte [účet Google Ads](https://ads.google.com/) a odpovídající přihlašovací údaje správce.
-   Máte [schválený token vývojáře Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token) 
-   Splňujete požadavky [Zásad pro vlastní seznamy zákazníků](https://support.google.com/adspolicy/answer/6299717)
-   Splňujete požadavky [velikosti remarketingového seznamu](https://support.google.com/google-ads/answer/7558048) 

-   Google Ads obsahuje cílové skupiny a odpovídající ID. Další informace viz [Cílové skupiny Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Máte [konfigurované segmenty](segments.md)
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu, křestní jméno a příjmení

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion profilů na jeden export do služby Google Ads.
- Export do služby Google Ads je omezen na segmenty.
- Export segmentů s celkem 1 milionem profilů může z důvodu omezení na straně poskytovatele trvat až 5 minut. 
- Spárování v Google Ads může trvat až 48 hodin.

## <a name="set-up-connection-to-google-ads"></a>Nastavení propojení ke Google Ads

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Google Ads** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte své **[ID zákazníka Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Zadete svůj **[token vývojáře schválený službou Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Vyberte **Ověření pomocí Google Ads** a zadejte své přihlašovací údaje k Google Ads.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**. 

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **propojení pro export** vyberte propojení v části Google Ads. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zadejte své **[ID cílové skupiny Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** a volbou **Připojit** inicializujte připojení k Google Ads.

1. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. Stejné kroky opakujte pro pole **Křestní jméno** a **Příjmení**.

1. Vyberte segmenty, které chcete exportovat. Do Google Ads můžete exportovat celkem až 1 milion zákaznických profilů.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat do služby Google Ads, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Google Ads splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
