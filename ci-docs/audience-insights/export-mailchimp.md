---
title: Export dat Customer Insights do služby Mailchimp
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Mailchimp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f7a33f2eddb6b625ddb8663b97103de75beab44c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226838"
---
# <a name="export-segments-to-mailchimp-preview"></a>Export segmentů do služby Mailchimp (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby Mailchimp a vytvářejte bulletiny a e-mailové kampaně.

## <a name="prerequisites-for-connection"></a>Předpoklady pro připojení

-   Máte [účet Mailchimp](https://mailchimp.com/) a odpovídající přihlašovací údaje správce.
-   Služba Mailchimp obsahuje cílové skupiny a odpovídající ID. Další informace viz [Cílové skupiny Mailchimp](https://mailchimp.com/help/create-audience/).
-   Máte [konfigurované segmenty](segments.md)
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion zákaznických profilů na export do Mailchimp.
- Export do služby Mailchimp je omezen na segmenty.
- Export segmentů s celkem 1 miliony zákaznických profilů může trvat až tři hodiny. 
- Počet zákaznických profilů, které můžete exportovat do Mailchimp, závisí na vaší smlouvě s Mailchimp a je jí omezen.

## <a name="set-up-connection-to-mailchimp"></a>Nastavení propojení s aplikací Mailchimp

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Mailchimp** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. K inicializaci propojení se službou Mailchimp vyberte **Připojit**.

1. Vyberte **Ověření pomocí Mailchimp** a zadejte své přihlašovací údaje ke službě Mailchimp.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**. 

## <a name="configure-the-connector"></a>Konfigurace konektoru

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data**> **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **propojení pro export** vyberte propojení v části Mailchimp. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zadejte **[ID cílové skupiny Mailchimp](https://mailchimp.com/help/find-audience-id/)**

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. 

1. Volitelně můžete exportovat **křestní jméno** a **příjmení** pro vytvoření více přizpůsobených e-mailů. Volbou **Přidat atribut** namapujte tato pole.

1. Vyberte segmenty, které chcete exportovat. Do služby Mailchimp můžete exportovat celkem až 1 milion zákaznických profilů.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat do služby Mailchimp, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Mailchimp splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
