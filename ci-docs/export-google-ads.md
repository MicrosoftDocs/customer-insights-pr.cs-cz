---
title: Export segmentů do Google Ads (náhled)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196570"
---
# <a name="export-segments-to-google-ads-preview"></a>Export segmentů do Google Ads (náhled)

Exportujte segmenty sjednocených profilů zákazníků do seznamu cílové skupiny Google Ads a použijte je k inzerci v Google Search, Gmailu, YouTube a síti Google Display Network.

## <a name="prerequisites"></a>Předpoklady

- [Účet Google Ads](https://ads.google.com/) a odpovídající přihlašovací údaje správce.
- [ID zákazníka Google Ads](https://support.google.com/google-ads/answer/1704344).
- Jsou splněny požadavky [zásad řešení Customer Match](https://support.google.com/adspolicy/answer/6299717).
- Jsou splněny požadavky [velikosti remarketingového seznamu](https://support.google.com/google-ads/answer/7558048).
- [Konfigurované segmenty](segments.md).
- Profily Unified customer profile v exportovaných segmentech obsahují pole představující e-mailovou adresu, telefon, ID mobilního inzerenta, ID uživatele třetí strany nebo adresu.

## <a name="known-limitations"></a>Známá omezení

- Export až 1 milionu zákaznických profilů na jeden export do Google Ads, což může kvůli omezením na straně poskytovatele trvat až 30 minut.
- Pouze segmenty.
- Párování v Google Ads může trvat až 48 hodin.

## <a name="set-up-connection-to-google-ads"></a>Nastavení propojení ke Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Google Ads**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte své ID zákazníka Google Ads.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Vyberte **Ověření pomocí Google Ads** a zadejte své přihlašovací údaje k Google Ads.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části Google Ads. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Zvolte, zda použít existující cílovou skupinu, nebo vytvořit novou:
   - Chcete-li aktualizovat stávající cílovou skupinu Google Ads, zadejte své [ID cílové skupiny Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Chcete-li vytvořit novou cílovou skupinu, ponechte prázdné pole ID cílové skupiny Google. Customer Insights automaticky vytvoří ve vašem účtu Google Ads novou cílovou skupinu a použije název exportovaného segmentu.

1. V sekci **Párování dat** vyberte jedno nebo více datových polí k exportu a vyberte pole, které představuje odpovídající datová pole v Customer Insights.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
