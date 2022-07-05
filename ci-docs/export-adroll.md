---
title: Export segmentů do služby AdRoll (preview)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 13c7dd3b8556ad807fba6c537525b463480e860b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080931"
---
# <a name="export-segments-to-adroll-preview"></a>Export segmentů do služby AdRoll (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby AdRoll a použijte je pro reklamu. 

## <a name="prerequisites-for-a-connection"></a>Předpoklady pro připojení

- Máte [účet AdRoll](https://www.adroll.com/) a odpovídající přihlašovací údaje správce.
- [Nakonfigurovali jste segmenty](segments.md) v Customer Insights.
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Do AdRoll můžete exportovat až 250 000 zákaznických profilů najednou.
- Do AdRoll nemůžete exportovat segmenty s méně než 100 zákaznickými profily. 
- Export do služby Marketo je omezen na segmenty.
- Export až 250 000 zákaznických profilů do AdRoll může trvat až 10 minut. 
- Počet zákaznických profilů, které můžete exportovat do AdRoll, závisí na vaší smlouvě s AdRoll a je jí omezen.

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

1. Vložte své **ID inzerenta AdRoll**. Další informace viz [Profily inzerentů AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. Je nutné exportovat segmenty do služby AdRoll.

1. Vyberte segmenty, které chcete exportovat. Vyberte segment s nejméně 100 členy. Menší segmenty nelze exportovat. Maximální velikost segmentu k exportu je navíc 250 000 členů na export. 

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). 

Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenést data do služby AdRoll, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba AdRoll splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.
