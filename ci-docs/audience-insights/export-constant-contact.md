---
title: Export údajů ze služby Customer Insights do služby Constant
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Constant Contact.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8841945814397ffa70c56638a8bed25499c1a06f
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226395"
---
# <a name="export-segments-to-constant-contact-preview"></a>Export segmentů do služby Constant Contact (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby Constant Contact a použijte je pro marketingové aktivity. 

## <a name="prerequisites-for-a-connection"></a>Předpoklady pro připojení

-   Máte [účet Constant Contact](https://www.constantcontact.com/account-home) a odpovídající přihlašovací údaje správce.
-   V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Do Constant Contact můžete exportovat až 1 milion zákaznických profilů na export.
- Export do Constant Contact je omezen na segmenty.
- Export až 1 milionu zákaznických profilů do Constant Contact může trvat až 1 hodinu. 
- Počet zákaznických profilů, které můžete exportovat do Constant Contact, závisí na vaší smlouvě se Constant Contact a je jí omezen.

## <a name="set-up-connection-to-constant-contact"></a>Nastavení propojení s Constant Contact

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Constant Contact** pro konfiguraci propojení .

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. K inicializaci propojení se službou Constant Contact vyberte **Propojit**.

1. Vyberte **Ověřit pomocí konstantního kontaktu** a zadejte své přihlašovací údaje správce pro konstantní kontakt. 

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **Připojení pro export** vyberte připojení v části Constant Contact. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zadejte [**ID seznamu Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Otevřete seznam v Constant Contact a vyhledejte ID seznamu v adrese URL.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. Je nutné exportovat segmenty do Constant Contact.

1. Volitelně můžete exportovat Křestní jméno a Příjmení jako další pole k vytvoření lépe přizpůsobených e-mailů. Volbou **Přidat atribut** namapujte tato pole.

1. Vyberte segmenty, které chcete exportovat.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights k přenosu dat do Constant Contact, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že Constant Contact bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.
