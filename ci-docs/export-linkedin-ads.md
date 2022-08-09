---
title: Export segmentů do LinkedIn Ads (preview)
description: Naučte se konfigurovat připojení a export do služby LinkedIn Ads.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d1a9ae985043398f4bc38163be26ecf0c3c8e2ba
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196800"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Export segmentů do LinkedIn Ads (preview)

Exportujte segmenty sjednocených profilů zákazníků do reklam LinkedIn Ads a vytvořte spárované cílové skupiny. Spárované cílové skupiny použijte k cílení na společnosti a kontakty.

## <a name="prerequisites"></a>Předpoklady

- [Účet LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) a odpovídající přihlašovací údaje správce.
- [ID obchodního vztahu LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 100 000 zákaznických profilů na export do LinkedIn Ads, což může trvat až 10 minut.
- Pouze segmenty. Segment musí obsahovat alespoň 300 jedinečných profilů.

## <a name="set-up-connection-to-linkedin-ads"></a>Nastavení připojení k LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **LinkedIn Ads**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte své ID účtu LinkedIn Campaign Manager.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Ověření pomocí LinkedIn** a zadejte své přihlašovací údaje do aplikace LinkedIn Campaign Manager.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Připojení pro export** vyberte připojení v části LinkedIn Ads. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Vyberte, zda chcete v LinkedIn exportovat data do [cílení kontaktů](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) nebo [cílení na společnost](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting).

1. V části **Shoda dat** pro cílení kontaktů vyberte alespoň jedno pole, které představuje e -mailovou adresu zákazníka, Apple Ad ID, Google Ad ID, Google User ID nebo jméno a příjmení. Pokud zvolíte cílení na společnost, vyberte alespoň jedno pole, které představuje název společnosti, e -mailovou doménu, adresu URL stránky LinkedIn, symbol akcií nebo web.

1. Volitelně přidejte pole, kterými dále definujete svůj export. Volbou **Přidat atribut** namapujte tato pole.

1. Vyberte segmenty, které chcete exportovat. Spárované cílové skupiny v LinkedIn Campaign Manager se vytvoří automaticky s názvem segmentů, které jste vybrali k exportu. Výsledkem každého segmentu bude samostatná spárovaná cílová skupina.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
