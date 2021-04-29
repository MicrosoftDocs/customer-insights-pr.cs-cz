---
title: Export dat Customer Insights do AdRoll
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895951"
---
# <a name="export-segment-lists-to-adroll-preview"></a>Export seznamů segmentů do služby AdRoll (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby AdRoll a použijte je pro reklamu. 

## <a name="prerequisites-for-a-connection"></a>Předpoklady pro připojení

-   Máte [účet AdRoll](https://www.adroll.com/) a odpovídající přihlašovací údaje správce.
-   V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Do služby AdRoll můžete exportovat maximálně 250 000 profilů na jeden export.
- Do AdRoll nelze exportovat segmenty s méně než 100 profily. 
- Export do služby Marketo je omezen na segmenty.
- Export až 250 000 profilů do služby AdRoll může trvat až 10 minut. 
- Počet profilů, které můžete exportovat do služby AdRoll, závisí a je omezen na vaší smlouvě se službou AdRoll.

## <a name="set-up-connection-to-adroll"></a>Nastavení propojení s AdRoll

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **AdRoll** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Volbou **Připojit** inicializujte připojení ke službě AdRoll.

1. Vyberte **Ověření pomocí AdRoll** a zadejte své přihlašovací údaje správce k AdRoll. 

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **propojení pro export** vyberte propojení v části AdRoll. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Vložte své **ID inzerenta AdRoll** Další informace viz [Profily inzerenta AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. Je nutné exportovat segmenty do služby AdRoll.

1. Vyberte segmenty, které chcete exportovat. Vyberte segment s nejméně 100 členy. Menší segmenty nelze exportovat. Maximální velikost segmentu k exportu je navíc 250 000 členů na export. 

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenést data do služby AdRoll, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba AdRoll splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.
