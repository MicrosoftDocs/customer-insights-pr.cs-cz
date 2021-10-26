---
title: Export dat Customer Insights do služby SendGrid
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: da3da5ea68d178deab3b9ab31dd810dee610f607
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617823"
---
# <a name="export-segments-to-sendgrid-preview"></a>Export segmentů do SendGrid (náhled)

Exportujte segmenty sjednocených profilů zákazníků do seznamů kontaktů SendGrid a použijte je pro kampaně a e-mailový marketing ve službě SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Předpoklady pro připojení

-   Máte [účet SendGrid](https://sendgrid.com/) a odpovídající přihlašovací údaje správce.
-   Služba SendGrid obsahuje seznamy kontaktů a odpovídající ID. Další informace viz [SendGrid – Správa kontaktů](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Celkem až 100 000 zákaznických profilů do SendGrid.
- Export do služby SendGrid je omezen na segmenty.
- Export až 100 000 zákaznických profilů do SendGrid může trvat pár hodin. 
- Počet zákaznických profilů, které můžete exportovat do SendGrid, závisí na vaší smlouvě se SendGrid a je jí omezen.

## <a name="set-up-connection-to-sendgrid"></a>Nastavení propojení se SendGrid

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **SendGrid** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **klíč rozhraní API SendGrid** [Klíč rozhraní API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Volbou **Připojit** inicializujte připojení ke službě SendGrid.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **Propojení pro export** vyberte propojení v části SendGrid. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zadejte své **[ID seznamu SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. Stejné kroky opakujte pro další volitelná pole, například **Křestní jméno**, **Příjmení**, **Země/oblast**, **Stát**, **Město** a **PSČ**.

1. Vyberte segmenty, které chcete exportovat. Velice **doporučujeme neexportovat více než 100 000 profilů zákazníků** do služby SendGrid. 

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat do služby SendGrid, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost SendGrid splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
