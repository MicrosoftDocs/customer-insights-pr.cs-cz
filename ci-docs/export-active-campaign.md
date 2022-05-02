---
title: Export údajů ze služby Customer Insights do ActiveCampaign
description: Naučte se, jak nakonfigurovat propojení a exportovat ho do ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d15b9bf7383d06070ac92d7a729fc6e6e00c9d7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645817"
---
# <a name="export-segments-to-activecampaign-preview"></a>Export segmentů do ActiveCampaign (náhled)

Exportujte segmenty sjednocených profilů zákazníků do ActiveCampaign a použijte je pro marketingové aktivity.

## <a name="prerequisites"></a>Požadavky

-   Máte [účet ActiveCampaign](https://www.activecampaign.com/) a odpovídající pověření správce.
-   [Nakonfigurovali jste segmenty](segments.md) v Customer Insights.
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole s e-mailovou adresou.

## <a name="known-limitations"></a>Známá omezení

- Na jeden export do ActiveCampaign můžete exportovat až 1 milion zákaznických profilů a jeho dokončení může trvat až 90 minut.
- Export do ActiveCampaign je omezen na segmenty.
- Počet zákaznických profilů, které můžete exportovat do ActiveCampaign, závisí na vaší smlouvě s ActiveCampaign.

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

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. Je potřeba pro export segmentů do ActiveCampaign. Volitelně můžete exportovat křestní jméno, příjmení, a telefon a vytvářet více přizpůsobené e-maily. Volbou Přidat atribut namapujte tato pole.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenášet data do ActiveCampaign, povolíte tím přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese takové údaje podle vašeho pokynu, ale vy jste zodpovědní za zajištění, že ActiveCampaign bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.
