---
title: Export dat Customer Insights do služby Google Ads
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7a85237f7aff564d6b540b2c11553a52f875fac4
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523786"
---
# <a name="export-segments-to-google-ads-preview"></a>Export segmentů do Google Ads (náhled)

Exportujte segmenty sjednocených profilů zákazníků do seznamu cílové skupiny Google Ads a použijte je k inzerci v Google Search, Gmailu, YouTube a síti Google Display Network. 


## <a name="prerequisites-for-connection"></a>Předpoklady pro připojení

-   Máte [účet Google Ads](https://ads.google.com/) a odpovídající přihlašovací údaje správce.
-   Splňujete požadavky [Zásad pro vlastní seznamy zákazníků](https://support.google.com/adspolicy/answer/6299717).
-   Splňujete požadavky [velikosti remarketingového seznamu](https://support.google.com/google-ads/answer/7558048).
-   Máte [konfigurované segmenty](segments.md).
-   Profily Unified customer profile v exportovaných segmentech obsahují pole představující e-mailovou adresu, telefon, ID mobilního inzerenta, ID uživatele třetí strany nebo adresu.

## <a name="known-limitations"></a>Známá omezení

- Export do služby Google Ads je omezen na segmenty.
- Export segmentů s celkem 1 milionem zákaznických profilů může kvůli omezením na straně poskytovatele trvat až 30 minut. 
- Spárování v Google Ads může trvat až 48 hodin.

## <a name="set-up-connection-to-google-ads"></a>Nastavení propojení ke Google Ads

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Google Ads** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte své **[ID zákazníka Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Vyberte **Ověření pomocí Google Ads** a zadejte své přihlašovací údaje k Google Ads.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**. 

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **propojení pro export** vyberte propojení v části Google Ads. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Pokud chcete vytvořit novou cílovou skupinu, ponechte prázdné pole ID cílové skupiny Google. Ve vašem účtu Google Ads automaticky vytvoříme novou cílovou skupinu a použijeme název exportovaného segmentu. Pokud chcete aktualizovat stávající cílovou skupinu Google Ads, zadejte své [ID cílové skupiny Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. V sekci **Párování dat** vyberte jedno nebo více datových polí k exportu a vyberte pole, které představuje odpovídající datová pole v Customer Insights.

1. Vyberte segmenty, které chcete exportovat. 

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). 

Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat do služby Google Ads, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Google Ads splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
