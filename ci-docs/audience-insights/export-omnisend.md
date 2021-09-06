---
title: Export údajů ze služby Customer Insights do služby Omnisend
description: Naučte se konfigurovat připojení a export do služby Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58b54dc24f4656f9dd376415a701539c8796e83e6d4e3c6754f5627ce77c5685
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031758"
---
# <a name="export-segments-to-omnisend-preview"></a>Export segmentů do Omnisend (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby Omnisend a použijte je pro marketingové aktivity.

## <a name="prerequisites"></a>Požadavky

-   Máte [účet Omnisend](https://www.omnisend.com/) a odpovídající přihlašovací údaje správce.
-   V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Do Omnisend můžete exportovat až 1 milion profilů na export a jeho dokončení může trvat až 4 hodiny.
- Export do Omnisend je omezen na segmenty.
- Počet profilů, které můžete exportovat do Omnisend, závisí na vaší smlouvě se společností Omnisend.

## <a name="set-up-connection-to-omnisend"></a>Nastavení připojení ke službě Omnisend

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Omnisend** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte svůj [klíč rozhraní API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. K inicializaci připojení ke službě Omnisend vyberte **Připojit**.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **Připojení pro export** vyberte připojení v části Omnisend. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. Je nutné exportovat segmenty do služby Omnisend. Volitelně můžete exportovat křestní jméno, příjmení, adresu, zemi/region, stát, město a PSČ, abyste vytvořili více přizpůsobené e-maily. Volbou **Přidat atribut** namapujte tato pole.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když aplikaci Dynamics 365 Customer Insights povolíte přenos dat do Omnisend, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data podle vašeho pokynu, ale vy jste zodpovědní za to, že Omnisend bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Váš správce Dynamics 365 Customer Insights může tento cíl exportu kdykoli odebrat a ukončit tak používání této funkce.
