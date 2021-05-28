---
title: Export údajů ze služby Customer Insights do služby RollWorks
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do služby RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760498"
---
# <a name="export-segment-lists-to-rollworks-preview"></a>Export seznamů segmentů do služby RollWorks (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby RollWorks a použijte je pro reklamu. 

## <a name="prerequisites-for-a-connection"></a>Předpoklady pro připojení

-   Máte [účet RollWorks](https://www.rollworks.com/) a odpovídající přihlašovací údaje správce.
-   V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Můžete exportovat až 250 000 profilů na export do RollWorks.
- Do RollWorks nelze exportovat segmenty s méně než 100 profily. 
- Export do RollWorks je omezen na segmenty.
- Export až 250 000 profilů do RollWorks může trvat až 10 minut. 
- Počet profilů, které můžete exportovat do RollWorks, závisí na vaší smlouvě s RollWorks a je podle ní omezen.

## <a name="set-up-connection-to-rollworks"></a>Nastavení propojení s aplikací RollWorks

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **RollWorks** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. K inicializaci propojení se službou RollWorks vyberte **Připojit**.

1. Vyberte **Ověření pomocí RollWorks** a poskytněte své přihlašovací údaje pro RollWorks.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **propojení pro export** vyberte propojení v části RollWorks. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zadejte **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. Je nutné exportovat segmenty do RollWorks.

1. Vyberte segmenty, které chcete exportovat. Vyberte segment s nejméně 100 členy. Menší segmenty nelze exportovat. Maximální velikost segmentu k exportu je navíc 250 000 členů na export. 

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights k přenosu dat do RollWorks, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že RollWorks bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.