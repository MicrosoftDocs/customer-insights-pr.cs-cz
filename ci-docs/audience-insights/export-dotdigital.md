---
title: Export dat Customer Insights do služby DotDigital
description: Naučte se, jak nakonfigurovat připojení ke službě DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644440"
---
# <a name="connector-for-dotdigital-preview"></a>Konektor pro DotDigital (Preview)

Exportujte segmenty sjednocených profilů zákazníků do adresářů DotDigital a použijte je pro kampaně, e-mailový marketing a vytváření segmentů zákazníků s pomocí služby DotDigital. 

## <a name="prerequisites"></a>Požadavky

-   Máte [účet DotDigital](https://dotdigital.com/) a odpovídající přihlašovací údaje správce.
-   Služba DotDigital obsahuje adresáře a odpovídající ID. ID najdete v adrese URL, když vyberete a otevřete adresář. Další informace viz [Adresáře DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="connect-to-dotdigital"></a>Připojení ke službě DotDigital

1. Přejděte na **Správce** > **Cíle exportu**.

1. Pod **DotDigital** vyberte **Nastavení**.

1. Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Podokno konfigurace pro export do služby DotDigital.":::

1. Zadejte své **uživatelské jméno a heslo pro DotDigital**.

1. Zadejte svoje **[ID adresáře DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Volbou **Připojit** inicializujte připojení ke službě DotDigital.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Vyberte **Další** pro konfiguraci exportu.

## <a name="configure-the-connector"></a>Konfigurace konektoru

1. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. Stejné kroky opakujte pro další volitelná pole, například **Křestní jméno**, **Příjmení**, **Celé jméno**, **Pohlaví** a **PSČ**.

1. Vyberte segmenty, které chcete exportovat. Do služby DotDigital můžete exportovat celkem až 1 milion zákaznických profilů.

1. Zvolte **Uložit**.

## <a name="export-the-data"></a>Export dat

Můžete [exportovat data na vyžádání](export-destinations.md). Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab). Ve službě DotDigital nyní můžete najít své segmenty v [adresářích DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion profilů na jeden export do služby DotDigital.
- Export do služby DotDigital je omezen na segmenty.
- Export segmentů s celkem 1 milionem profilů může z důvodu omezení na straně poskytovatele trvat až 3 hodiny. 
- Počet profilů, které můžete exportovat do služby DotDigital, závisí a je omezen na vaší smlouvě se společností DotDigital.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když pro Dynamics 365 Customer Insights povolíte přenos dat do služby DotDigital, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost DotDigital splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.
