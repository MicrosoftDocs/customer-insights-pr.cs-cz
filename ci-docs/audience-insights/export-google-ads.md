---
title: Export dat Customer Insights do služby Google Ads
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Google Ads.
ms.date: 09/27/2021
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28e2b35c5a47a025b8cdcccdb3f61c79878bf056
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227002"
---
# <a name="export-segments-to-google-ads-preview"></a>Export segmentů do Google Ads (náhled)

Exportujte segmenty sjednocených profilů zákazníků do seznamu cílové skupiny Google Ads a použijte je k inzerci v Google Search, Gmailu, YouTube a síti Google Display Network. 

> [!IMPORTANT]
> V současné době můžete vytvořit nové připojení a exportovat data do Google Ads, pouze pokud již máte schválený token vývojáře Google Ads. Kvůli změnám zásad brzy aktualizujeme export Google Ads a poskytneme možnost exportu, která nebude vyžadovat vývojářský token, aby byla zajištěna kontinuita vašeho prostředí a zjednodušen export do Google Ads. Doporučujeme nenastavovat více připojení ke službě Google Ads, aby se usnadnil přechod na novou možnost exportu.

## <a name="prerequisites-for-connection"></a>Předpoklady pro připojení

-   Máte [účet Google Ads](https://ads.google.com/) a odpovídající přihlašovací údaje správce.
-   Máte [schválený token vývojáře Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Splňujete požadavky [Zásad pro vlastní seznamy zákazníků](https://support.google.com/adspolicy/answer/6299717).
-   Splňujete požadavky [velikosti remarketingového seznamu](https://support.google.com/google-ads/answer/7558048).
-   Google Ads obsahuje cílové skupiny a odpovídající ID. Další informace viz [Cílové skupiny Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu, křestní jméno a příjmení.

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion zákaznických profilů na export do Google Ads.
- Export do služby Google Ads je omezen na segmenty.
- Export segmentů s celkem 1 milionem zákaznických profilů může kvůli omezením na straně poskytovatele trvat až 5 minut. 
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

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka.

1. Vyberte segmenty, které chcete exportovat. Do Google Ads můžete exportovat celkem až 1 milion zákaznických profilů.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). 

Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat do služby Google Ads, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Google Ads splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
