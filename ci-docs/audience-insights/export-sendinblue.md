---
title: Export údajů ze služby Customer Insights do Sendinblue
description: Naučte se, jak nakonfigurovat propojení a exportovat ho do Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: be52554763b57e1c1ef2f960d52bbae79ac9827913c97ac73b429f66bbf4db37
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036047"
---
# <a name="export-segments-to-sendinblue-preview"></a>Export segmentů do Sendinblue (náhled)

Segmenty sjednocených profilů zákazníků exportujte pro účely generování kampaní, poskytování e-mailového marketingu a využívání konkrétních skupin zákazníků se Sendinblue.

## <a name="prerequisites-for-connection"></a>Předpoklady pro připojení

-   Máte [účet Sendinblue](https://www.sendinblue.com/) a odpovídající pověření správce.
-   V Sendinblue existují seznamy a odpovídající ID.
-   Máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion profilů na export do Sendinblue.
- Export do Sendinblue je omezen na segmenty.
- Export segmentů s celkem 1 milionem profilů může trvat až 90 minut. 
- Počet profilů, které můžete exportovat do Sendinblue, závisí na vaší smlouvě se společností Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Nastavení připojení se Sendinblue

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Sendinblue** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **[klíč API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů** a vyberte **Připojit** pro inicializaci připojení k Sendinblue.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **Připojení pro export** zvolte připojení z části Sendinblue. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zadejte **ID seznamu Sendinblue** 

1. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. 

1. Volitelně můžete exportovat **křestní jméno**, **příjmení**, a **telefon** k vytvoření přizpůsobených e-mailů. Volbou **Přidat atribut** namapujte tato pole.

1. Vyberte segmenty, které chcete exportovat. 

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenášet data do Sendinblue, povolíte tím přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese takové údaje podle vašeho pokynu, ale vy jste zodpovědní za zajištění, že Sendinblue bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
