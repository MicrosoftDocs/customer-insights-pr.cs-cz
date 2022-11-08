---
title: Export segmentů do Klaviyo (Preview)
description: Naučte se, jak nakonfigurovat propojení a exportovat ho do Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 075e6758f2c6992a1185756f9beecf852fdd0a96
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724573"
---
# <a name="export-segments-to-klaviyo-preview"></a>Export segmentů do Klaviyo (Preview)

Exportujte segmenty sjednocených profilů zákazníků do Klaviyo a použijte je pro marketingové aktivity.

## <a name="prerequisites"></a>Předpoklady

- [Účet Klaviyo](https://www.klaviyo.com/) a odpovídající pověření správce.
- [Klíč rozhraní API služby Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- [ID seznamu Klaviyo](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Privátní propojení v kombinaci s použitím vlastního úložiště (BYOS) není podporováno.
- Až 1 milion zákaznických profilů na export do služby Klaviyo, což může trvat až 20 minut. Počet zákaznických profilů, které můžete exportovat do služby Klaviyo, závisí na vaší smlouvě s Klaviyo.
- Pouze segmenty.

## <a name="set-up-connection-to-klaviyo"></a>Nastavení připojení ke Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Klaviyo**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Poskytněte svůj klíč API rozhraní Klaviyo a pokračujte k přihlášení.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Ověřit pomocí Klaviyo** a zadejte své přihlašovací údaje správce pro Klaviyo.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Připojení pro export** zvolte připojení z části Klaviyo. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Zadejte **ID seznamu Klaviyo**.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
