---
title: Export dat Customer Insights do služby DotDigital
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f09be0dfa599c1ef7cf0055b7ce1df8784cf447ada64b56bc7543c214f9a5b99
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034628"
---
# <a name="export-segments-to-dotdigital-preview"></a>Export segmentů do služby DotDigital (preview)

Exportujte segmenty sjednocených profilů zákazníků do adresářů DotDigital a použijte je pro kampaně, e-mailový marketing a vytváření segmentů zákazníků s pomocí služby DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Předpoklady pro připojení

-   Máte [účet DotDigital](https://dotdigital.com/) a odpovídající přihlašovací údaje správce.
-   Služba DotDigital obsahuje adresáře a odpovídající ID. ID najdete v adrese URL, když vyberete a otevřete adresář. Další informace viz [Adresáře DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion profilů na jeden export do služby DotDigital.
- Export do služby DotDigital je omezen na segmenty.
- Export segmentů s celkem 1 milionem profilů může z důvodu omezení na straně poskytovatele trvat až 3 hodiny. 
- Počet profilů, které můžete exportovat do služby DotDigital, závisí a je omezen na vaší smlouvě se společností DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Nastavení propojení s aplikací DotDigital

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **DotDigital** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte své **uživatelské jméno a heslo pro DotDigital**.

1. Zadejte svoje **[ID adresáře DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Volbou **Připojit** inicializujte připojení ke službě DotDigital.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**. 

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **propojení pro export** vyberte propojení v části DotDigital. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.


1. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. Stejné kroky opakujte pro další volitelná pole, například **Křestní jméno**, **Příjmení**, **Celé jméno**, **Pohlaví** a **PSČ**.

1. Vyberte segmenty, které chcete exportovat. Do služby DotDigital můžete exportovat celkem až 1 milion zákaznických profilů.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 
 
Ve službě DotDigital nyní můžete najít své segmenty v [adresářích DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když pro Dynamics 365 Customer Insights povolíte přenos dat do služby DotDigital, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost DotDigital splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
