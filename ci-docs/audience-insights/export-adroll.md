---
title: Export dat Customer Insights do AdRoll
description: Naučte se, jak nakonfigurovat připojení k AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697066"
---
# <a name="connector-for-adroll-preview"></a>Konektor pro AdRoll (Preview)

Exportujte segmenty sjednocených profilů zákazníků do služby AdRoll a použijte je pro reklamu. 

## <a name="prerequisites"></a>Požadavky

-   Máte [účet AdRoll](https://www.adroll.com/) a odpovídající přihlašovací údaje správce.
-   V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="connect-to-adroll"></a>Připojit k AdRoll

1. Přejděte na **Správce** > **Cíle exportu**.

1. Pod **AdRoll** vyberte **Nastavení**.

1. Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfigurační podokno pro připojení služby AdRoll.":::

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Volbou **Připojit** inicializujte připojení ke službě AdRoll.

1. Vyberte **Ověření pomocí AdRoll** a zadejte své přihlašovací údaje správce k AdRoll. 

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Vložte svoje **ID inzerenta AdRoll** [Inzerovatelný AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Vyberte **Další** pro konfiguraci exportu.

## <a name="configure-the-connector"></a>Konfigurace konektoru

1. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. Je nutné exportovat segmenty do služby AdRoll.

1. Vyberte segmenty, které chcete exportovat. Vyberte segment s nejméně 100 členy. Menší segmenty nelze exportovat. Maximální velikost segmentu k exportu je navíc 250 000 členů na export. 

1. Zvolte **Uložit**.

## <a name="export-the-data"></a>Export dat

Můžete [exportovat data na vyžádání](export-destinations.md). Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).

## <a name="known-limitations"></a>Známá omezení

- Do služby AdRoll můžete exportovat maximálně 250 000 profilů na jeden export.
- Do AdRoll nelze exportovat segmenty s méně než 100 profily. 
- Export do služby Marketo je omezen na segmenty.
- Export až 250 000 profilů do služby AdRoll může trvat až 10 minut. 
- Počet profilů, které můžete exportovat do služby AdRoll, závisí a je omezen na vaší smlouvě se službou AdRoll.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenést data do služby AdRoll, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba AdRoll splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.
