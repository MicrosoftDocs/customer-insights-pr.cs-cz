---
title: Export údajů ze služby Customer Insights do ActiveCampaign
description: Naučte se, jak nakonfigurovat propojení a exportovat ho do ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 14d420205a5c60d471ef21a04ab6d02295a65ca8fd5205ba782a300703b06102
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032201"
---
# <a name="export-segments-to-activecampaign-preview"></a>Export segmentů do ActiveCampaign (náhled)

Exportujte segmenty sjednocených profilů zákazníků do ActiveCampaign a použijte je pro marketingové aktivity.

## <a name="prerequisites"></a>Požadavky

-   Máte [účet ActiveCampaign](https://www.activecampaign.com/) a odpovídající pověření správce.
-   V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole s e-mailovou adresou.

## <a name="known-limitations"></a>Známá omezení

- Do aplikace ActiveCampaign můžete exportovat až 1 milion profilů na jeden export a dokončení může trvat až 90 minut.
- Export do ActiveCampaign je omezen na segmenty.
- Počet profilů, které můžete exportovat do služby ActiveCampaign, závisí na vaší smlouvě se společností ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Můžete nastavit propojení řešení s ActiveCampaign.

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **ActiveCampaign** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte [Klíč API ActiveCampaign a název hostitele koncového bodu REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Koncový bod názvu hostitele REST je pouze název hostitele, bez https://. 

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Vyberte **Připojit** k inicializaci připojení k ActiveCampaign.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Export můžete konfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **Připojení pro export** zvolte připojení z části ActiveCampaign. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zadejte [**ID seznamu ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

3. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. Je potřeba pro export segmentů do ActiveCampaign. Volitelně můžete exportovat křestní jméno, příjmení, a telefon a vytvářet více přizpůsobené e-maily. Volbou Přidat atribut namapujte tato pole.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenášet data do ActiveCampaign, povolíte tím přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese takové údaje podle vašeho pokynu, ale vy jste zodpovědní za zajištění, že ActiveCampaign bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.
