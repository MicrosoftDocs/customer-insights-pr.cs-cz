---
title: Export dat Customer Insights do služby Google Ads
description: Naučte se, jak nakonfigurovat připojení ke službě Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568418"
---
# <a name="connector-for-google-ads-preview"></a>Konektor pro Google Ads (Preview)

Exportujte segmenty sjednocených profilů zákazníků do seznamu cílových skupin Google Ads a použijte je k inzerci ve službách Google Search, Gmail, YouTube a Google Display Network. 

## <a name="prerequisites"></a>Požadavky

-   Máte [účet Google Ads](https://ads.google.com/) a odpovídající přihlašovací údaje správce.
-   Google Ads obsahuje cílové skupiny a odpovídající ID. Další informace viz [Cílové skupiny Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Máte [konfigurované segmenty](segments.md)
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu, křestní jméno a příjmení

## <a name="connect-to-google-ads"></a>Připojit ke Google Ads

1. Přejděte na **Správce** > **Cíle exportu**.

1. Pod **Google Ads** vyberte **Nastavení**.

1. Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.

1. Zadejte své **[ID zákazníka Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Zadete svůj **[token vývojáře schválený službou Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Zadejte své **[ID cílové skupiny Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** a volbou **Připojit** inicializujte připojení k Google Ads.

1. Vyberte **Ověření pomocí Google Ads** a zadejte své přihlašovací údaje k Google Ads.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Screenshot exportu pro připojení Google Ads":::

1. Vyberte **Další** pro konfiguraci exportu.

## <a name="configure-the-connector"></a>Konfigurace konektoru

1. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. Stejné kroky opakujte pro pole **Křestní jméno** a **Příjmení**.

1. Vyberte segmenty, které chcete exportovat. Do Google Ads můžete exportovat celkem až 1 milion zákaznických profilů.

1. Zvolte **Uložit**.

## <a name="export-the-data"></a>Export dat

Můžete [exportovat data na vyžádání](export-destinations.md). Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab). V Google Ads nyní najdete své segmenty v části [Cílové skupiny Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion profilů na jeden export do služby Google Ads.
- Export do služby Google Ads je omezen na segmenty.
- Export segmentů s celkem 1 milionem profilů může z důvodu omezení na straně poskytovatele trvat až 5 minut. 
- Spárování v Google Ads může trvat až 48 hodin.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat do služby Google Ads, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Google Ads splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.
