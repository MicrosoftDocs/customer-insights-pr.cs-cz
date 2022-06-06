---
title: Export dat Customer Insights do Criteo
description: Zjistěte, jak nakonfigurovat připojení a export do Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 854f5f0c53f053fc5d742d69a045db1926fec00c
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808762"
---
# <a name="export-segments-to-criteo-preview"></a>Export segmentů do Criteo (Preview)

Exportujte segmenty jednotných zákaznických profilů pro generování kampaní, e-mailový marketing a využívání specifických skupin zákazníků pomocí služby Criteo.

## <a name="prerequisites-for-connection"></a>Předpoklady pro připojení

-   Máte [účet Criteo Dynamics Retargeting](https://www.criteo.com/login/) a odpovídající přihlašovací údaje správce.
-   Máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion zákaznických profilů na export do Criteo.
- Export do Criteo je omezen na segmenty.
- Export segmentů s celkem 1 miliony zákaznických profilů může trvat až 30 minut. 
- Počet zákaznických profilů, které můžete exportovat do Criteo, závisí na vaší smlouvě s Criteo a je jí omezen.

## <a name="set-up-connection-to-criteo"></a>Nastavení připojení ke Criteo

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a volbou **Criteo** začněte konfigurovat připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte **Souhlasím** pro potvrzení části **Ochrana osobních údajů a dodržování předpisů** a vyberte **Připojit** pro inicializaci připojení ke Criteo.

1. Vyberte **Ověřit pomocí Criteo** a zadejte své uživatelské jméno správce a přihlašovací údaje pro Criteo. 

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **Připojení pro export** vyberte připojení v sekci Criteo. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu. 

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. 

1. Volitelně můžete exportovat **ID inzerenta** a **Název**

1. Vyberte segmenty, které chcete exportovat. 

1. Vyberte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte aplikaci Dynamics 365 Customer Insights přenos dat do služby Criteo, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft taková data přenese na váš pokyn, ale vy jste odpovědní za zajištění toho, že Criteo splňuje veškeré vaše případné povinnosti týkající se ochrany soukromí nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](includes/footer-banner.md)]
